---
title: Custom Handlers
page_title: Custom Handlers
description: "Test Studio Testing Framework Custom Dialog handling. Handle a custom dialog in a coded step in Test Studio. Coded test to handle custom (non-common) dialogs in Test Studio."
position: 11
---
#Creating Custom Dialog Handlers

So far we've addressed the common dialogs that browsers popup and how the built-in support can be used to handle them. So what do we do if we have a different dialog that we need to handle? Telerik Testing Framework provides a **GenericDialog class** (which does all the work for you of implementing a custom dialog handler), a **BaseDialog class** (which does most of the work of implementing a custom dialog handler), and the IDialog interface for when you need to roll your own custom dialog handler from scratch. Once implemented you can add your custom dialog handler to the **DialogMonitor** and have all your other dialogs handled just like the rest of the built-in dialogs.

##Using the GenericDialog Class

Using the GenericDialog class you can create your own custom dialog handler that can handle most any simple standard Win32 dialog. Here's an example of how to implement a handler for Internet Explorers Security Warning dialog:

```C#
GenericDialog SecurityWarningDialog = new GenericDialog(ActiveBrowser, "Security Warning", false, 1);  // Click on the Yes button
Manager.DialogMonitor.AddDialog(SecurityWarningDialog);
```
```VB
Dim SecurityWarningDialog As GenericDialog = New GenericDialog(Me.ActiveBrowser, "Security Warning", False, 1)  ' Click on the Yes button
SecurityWarningDialog GenericDialog = GenericDialog(.ActiveBrowser, , , 1) 
Manager.DialogMonitor.AddDialog(SecurityWarningDialog)
```

##Using the BaseDialog Class

By using the BaseDialog class as your base class to derive your custom dialog handler you only need to override the IsDialogActive() and Handle() functions. You may also provide your own constructor to validate the button type that will dismiss the dialog and/or accept a Desktop object (which you will need if you need to call Mouse.Click or Keyboard.SendString). Reference to System.Drawing.dll have to be added to the project as well.

The below example is a complete custom dialog handler that handles the "Security Alert" dialog displayed by Internet Explorer:

```C#
using System;
using ArtOfTest.WebAii.Core;
using ArtOfTest.Common.Win32;
using ArtOfTest.WebAii.Win32.Dialogs;
 
namespace WebTesting
{
    public class SecurityAlertDialog : BaseDialog
    {
        #region Members
        /// <summary>
        /// The desktop object used to click dialog buttons.
        /// </summary>
        private Desktop _desktopObject;
        #endregion
 
        #region Private Constants
        /// <summary>
        /// The title (caption) of the dialog we want handled.
        /// </summary>
        private const string DIALOG_TITLE = "Security Alert";
        #endregion
 
        #region Constructor
        /// <summary>
        /// Create the dialog handler instance by passing it the parent browser and the
        /// button to click on to dismiss the dialog.
        /// </summary>
        /// <param name="parentBrowser">The parent browser.</param>
        /// <param name="dismissButton">The button to click to dismiss the dialog.</param>
        /// <param name="desktop">The desktop object to use for Mouse.Click calls.</param>
        public SecurityAlertDialog(Browser parentBrowser,
            DialogButton dismissButton, Desktop desktop)
            : base(parentBrowser, dismissButton)
        {
            if (dismissButton != DialogButton.YES && dismissButton != DialogButton.NO
                && dismissButton != DialogButton.CLOSE)
            {
                throw new
                    ArgumentException("Security dialog can only have dismiss button of types : YES, NO or CLOSE.");
            }
            _desktopObject = desktop;
        }
        #endregion
 
        #region Base Dialog Implementation
        /// <summary>
        /// Check whether the dialog is present or not. This function is
        /// called by the dialogmonitor object
        /// </summary>
        /// <param name="dialogs">This is a list of dialogs passed in
        /// by the DialogMonitor.</param>
        /// <returns>True/False whether this dialog is present.</returns>
        public override bool IsDialogActive(ArtOfTest.WebAii.Win32.WindowCollection dialogs)
        {
            return this.IsDialogActiveByTitle(dialogs, DIALOG_TITLE);
        }
 
        /// <summary>
        /// This is called by the DialogMonitor whenever IsDialogActive returns true.
        /// </summary>
        /// <returns>True/False whether the dialog was successfully handled.</returns>
        public override void Handle()
        {
            // If you are sharing this implementation with other
            // developers, this allows them to override this method
            // by setting the handler delegate. So if the
            // delegate is null, perform the built in handling logic
            // otherwise call the custom handling logic.
            if (this.HandlerDelegate != null)
            {
                this.HandlerDelegate(this);
            }
            else
            {
                try
                {
                    Window yesButton = WindowManager.FindWindowRecursively(this.Window.Handle, "Yes", false, 0);
                    Window noButton = WindowManager.FindWindowRecursively(this.Window.Handle, "No", false, 0);
                    Window okButton = WindowManager.FindWindowRecursively(this.Window.Handle, "OK", false, 0);
 
                    switch (this.DismissButton)
                    {
                        case DialogButton.CLOSE:
                            this.Window.Close();
                            break;
 
                        case DialogButton.OK:
                            _desktopObject.Mouse.Click(MouseClickType.LeftClick, okButton.Rectangle);
                            break;
 
                        case DialogButton.YES:
                            _desktopObject.Mouse.Click(MouseClickType.LeftClick, yesButton.Rectangle);
                            break;
 
                        case DialogButton.NO:
                            _desktopObject.Mouse.Click(MouseClickType.LeftClick, noButton.Rectangle);
                            break;
                    }
 
                    // Make sure the dialog is knocked down.
                    this.Window.WaitForVisibility(false, 500);
                }
                catch
                {
                    // Do any custom handling and return error.
                }
            }
        }
        #endregion
    }
}
```
```VB
Imports ArtOfTest.WebAii.Core
Imports ArtOfTest.Common.Win32
Imports ArtOfTest.WebAii.Win32.Dialogs

Namespace WebTesting
	Public Class SecurityAlertDialog
		Inherits BaseDialog
		#Region "Members"
		''' <summary>
		''' The desktop object used to click dialog buttons.
		''' </summary>
		Private _desktopObject As Desktop
		#End Region

		#Region "Private Constants"
		''' <summary>
		''' The title (caption) of the dialog we want handled.
		''' </summary>
		Private Const DIALOG_TITLE As String = "Security Alert"
		#End Region

		#Region "Constructor"
		''' <summary>
		''' Create the dialog handler instance by passing it the parent browser and the
		''' button to click on to dismiss the dialog.
		''' </summary>
		''' <param name="parentBrowser">The parent browser.</param>
		''' <param name="dismissButton">The button to click to dismiss the dialog.</param>
		''' <param name="desktop">The desktop object to use for Mouse.Click calls.</param>
		Public Sub New(parentBrowser As Browser, dismissButton As DialogButton, desktop As Desktop)
			MyBase.New(parentBrowser, dismissButton)
			If dismissButton <> DialogButton.YES AndAlso dismissButton <> DialogButton.NO AndAlso dismissButton <> DialogButton.CLOSE Then
				Throw New ArgumentException("Security dialog can only have dismiss button of types : YES, NO or CLOSE.")
			End If
			_desktopObject = desktop
		End Sub
		#End Region

		#Region "Base Dialog Implementation"
		''' <summary>
		''' Check whether the dialog is present or not. This function is
		''' called by the dialogmonitor object
		''' </summary>
		''' <param name="dialogs">This is a list of dialogs passed in
		''' by the DialogMonitor.</param>
		''' <returns>True/False whether this dialog is present.</returns>
		Public Overrides Function IsDialogActive(dialogs As ArtOfTest.WebAii.Win32.WindowCollection) As Boolean
			Return Me.IsDialogActiveByTitle(dialogs, DIALOG_TITLE)
		End Function

		''' <summary>
		''' This is called by the DialogMonitor whenever IsDialogActive returns true.
		''' </summary>
		''' <returns>True/False whether the dialog was successfully handled.</returns>
		Public Overrides Sub Handle()
			' If you are sharing this implementation with other
			' developers, this allows them to override this method
			' by setting the handler delegate. So if the
			' delegate is null, perform the built in handling logic
			' otherwise call the custom handling logic.
			If Me.HandlerDelegate IsNot Nothing Then
				Me.HandlerDelegate(Me)
			Else
				Try
					Dim yesButton As Window = WindowManager.FindWindowRecursively(Me.Window.Handle, "Yes", False, 0)
					Dim noButton As Window = WindowManager.FindWindowRecursively(Me.Window.Handle, "No", False, 0)
					Dim okButton As Window = WindowManager.FindWindowRecursively(Me.Window.Handle, "OK", False, 0)

					Select Case Me.DismissButton
						Case DialogButton.CLOSE
							Me.Window.Close()
							Exit Select

						Case DialogButton.OK
							_desktopObject.Mouse.Click(MouseClickType.LeftClick, okButton.Rectangle)
							Exit Select

						Case DialogButton.YES
							_desktopObject.Mouse.Click(MouseClickType.LeftClick, yesButton.Rectangle)
							Exit Select

						Case DialogButton.NO
							_desktopObject.Mouse.Click(MouseClickType.LeftClick, noButton.Rectangle)
							Exit Select
					End Select

					' Make sure the dialog is knocked down.
					Me.Window.WaitForVisibility(False, 500)
						' Do any custom handling and return error.
				Catch
				End Try
			End If
		End Sub
		#End Region
	End Class
End Namespace
```

Once you have implemented your new custom dialog handler it requires just one line of code to add it to the DialogMonitor:

```C#
Manager.DialogMonitor.AddDialog(new SecurityAlertDialog(ActiveBrowser, DialogButton.YES, Manager.Desktop));
```
```VB
Manager.DialogMonitor.AddDialog(New SecurityAlertDialog(Me.ActiveBrowser, DialogButton.YES, Me.Manager.Desktop))
```

##Implementing a Custom Dialog Handler with IDialog

When the GenericDialog and the BaseDialog classes don't provide the functionality you need, you can roll your own complete custom dialog handling by implementing the <a href="http://docs.telerik.com/teststudioapi/html/T_ArtOfTest_WebAii_Win32_Dialogs_IDialog.htm" target="_blank">IDialog</a> interface. An example of when this is necessary is when creating handlers for most FireFox dialogs. See How to handle FireFox dialogs for an example of a FireFox dialog handler implemented using the IDialog interface. A reference to UIAutomationClient.dll has to be added to the project and a using to System.Windows.Automation namespace would be required in the code. The IDialog interface has the following methods and properties that you must implement:

```C#
/// <summary>
/// Interface to implement for dialogs to be monitored and handled by the DialogMonitor object.
/// </summary>
public interface IDialog
{
     /// <summary>
     /// The dialogs current state. This property is Managed by the dialog
     /// monitor. Implementors should simply provide a private field to
     /// store this value for get/set operations.
     /// </summary>
     DialogCurrentState CurrentState { get; set; }

     /// <summary>
     /// This property is set when a dialog errors out and needs to abort.
     /// </summary>
     string ErrorText { get; set; }

     /// <summary>
     /// Gets/Sets the number of times this dialog has been handled.
     /// </summary>
     int HandleCount { get; set; }
 
     /// <summary>
     /// Gets/Sets a dialog handler delegate that will be used instead of
     /// the Handle() function.
     /// </summary>
     DialogHandlerDelegate HandlerDelegate { set; get;}

     /// <summary>
     /// Gets/Sets the time to before handling of the dialog starts.
     /// </summary>
     int InitializationTime { get; set; }

     /// <summary>
     /// Gets/Sets a dialog delegate that will be used if handling dialog will be skipped.
     /// </summary>
     Func<bool> SkipHandling { get; set; }

     /// <summary>
     /// The Window object that represents this dialog.
     /// IsDialogActive() should set this property if it is returning true.
     /// </summary>
     Window Window { get; }
 
     /// <summary>
     /// Whether the dialog is active or not.
     /// </summary>
     /// <param name="dialogs">The list of dialogs present on the desktop.</param>
     /// <returns>True/False whether the dialog is active/present.</returns>
     bool IsDialogActive(WindowCollection dialogs);
 
     /// <summary>
     /// If a HandlerDelegate is set, this function should call the delegate,
     /// otherwise handle the dialog itself.
     /// </summary>
     void Handle();

     /// <summary>
     /// Detect whether this UI element completes the awaited conditions.
     /// For situations where window handles do not or need not apply.
     /// </summary>
	 bool MatchesUIAutomationElement(AutomationElement element);
}
```
```VB
''' <summary>
''' The dialogs current state. This property is Managed by the dialog
''' monitor. Implementors should simply provide a private field to
''' store this value for get/set operations.
''' </summary>
Private Property CurrentState() As DialogCurrentState
	Get
		Return m_CurrentState
	End Get
	Set
		m_CurrentState = Value
	End Set
End Property
Private m_CurrentState As DialogCurrentState

''' <summary>
''' When a dialog encounters an error and needs to abort, this property is set.
''' </summary>
Private Property ErrorText() As String
	Get
		Return m_ErrorText
	End Get
	Set
		m_ErrorText = Value
	End Set
End Property
Private m_ErrorText As String

''' <summary>
''' Gets/Sets the number of times this dialog has been handled.
''' </summary>
Private Property HandleCount() As Integer
	Get
		Return m_HandleCount
	End Get
	Set
		m_HandleCount = Value
	End Set
End Property
Private m_HandleCount As Integer

''' <summary>
''' Gets/Sets a dialog handler delegate that will be used instead of
''' the Handle() function.
''' </summary>
Private Property HandlerDelegate() As DialogHandlerDelegate
	Get
		Return m_HandlerDelegate
	End Get
	Set
		m_HandlerDelegate = Value
	End Set
End Property
Private m_HandlerDelegate As DialogHandlerDelegate

''' <summary>
''' Gets/Sets the time to before handling of the dialog starts.
''' </summary>
Private Property InitializationTime() As Integer
	Get
		Return m_InitializationTime
	End Get
	Set
		m_InitializationTime = Value
	End Set
End Property
Private m_InitializationTime As Integer

''' <summary>
''' Gets/Sets a dialog delegate that will be used if handling dialog will be skipped.
''' </summary>
Private Property SkipHandling() As Func(Of Boolean)
	Get
		Return m_SkipHandling
	End Get
	Set
		m_SkipHandling = Value
	End Set
End Property
Private m_SkipHandling As Func(Of Boolean)

''' <summary>
''' The Window object that represents this dialog.
''' IsDialogActive() should set this property if it is returning true.
''' </summary>
Private ReadOnly Property Window() As Window

''' <summary>
''' Whether the dialog is active or not.
''' </summary>
''' <param name="dialogs">The list of dialogs present on the desktop.</param>
''' <returns>True/False whether the dialog is active/present.</returns>
Private Function IsDialogActive(dialogs As WindowCollection) As Boolean
End Function

''' <summary>
''' If a HandlerDelegate is set, this function should call the delegate,
''' otherwise handle the dialog itself.
''' </summary>
Private Sub Handle()
End Sub

''' <summary>
''' Detect whether this UI element completes the awaited conditions.
''' For situations where window handles do not or need not apply.
''' </summary>
Private Function MatchesUIAutomationElement(element As AutomationElement) As Boolean
End Function
```

After implementing this interface and creating an instance of your class in your test code, you can add the instance to the DialogMonitor to begin handling of your special dialog. See Handling FireFox dialogs for an example of implementing the IDialog interface. The interface is pretty straight forward but here is how the DialogMonitor uses it:

* Periodically (depending on the monitoring interval), the DialogMonitor will call the IsDialogActive() passing all active dialogs currently on the desktop. [Note: The DialogMonitor passes only the dialog windows, not all windows. Meaning windows with class name = #32770]

* The implementation of IsDialogActive then should determine if the dialog it was built to handle is active or not. If so, it should set an internal property to store that window and return true. The instance should be accessible using the Window property.

* If the DialogMonitor() detects true to any call to IsDialogActive(), it will automatically call the Handle() method.

* The Handle() method should then perform the custom handling for that dialog and knock it down. The method should return 'true' if it was successful in knocking down the dialog else 'false'.