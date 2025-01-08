---
title: Firefox Dialogs
page_title: Firefox Dialogs
description: "Test Studio Testing Framework FF dialogs - obsolete"
position: 1
published: false
published: false
---
# How to Handle Firefox Dialogs
# How to Handle Firefox Dialogs

Firefox dialogs require special attention because some of them are not standard Win32 dialogs, for example Firefox's download manager dialog. As a result the usual method for handing dialogs does not work with Firefox dialogs. Here is what the download manager dialog looks like:

<table id="no-table" style="border:none;">
	<tr style="text-align: center; background-color: transparent; border:none;">
		<td>
        
![Firefox download manager dialog window][1] <br><br>**Firefox download manager dialog window**</td>
<td>
        
![Firefox download manager dialog window after download completes][2] <br><br>**Firefox download manager dialog window after download completes**</td>
</tr>
</table>

Using Microsoft's Spy++ tool the first thing we discover about this dialog is that the class name is **MozillaUIWindowClass** instead of the standard dialog class name of #**32770**. As a result this dialog will not be included in the WindowCollection list that is passed in to the IsDialogActive function. This is because DialogMonitor filters the desktop windows on the class name #**32770**. This fact alone necessitates rolling our own custom dialog handler using the IDialog interface to overcome this problem.
 
The other thing we discover about this dialog is that the Clear List button and the links are not Win32 accessible. We'll have to come up with different methods of accessing them if needed. Fortunately in this case all we want to do is close the dialog when the download is finished.
 
Let's start implementing our dialog handler. First we'll need some local class variables and property accessors:

````C#
using System;
using System.Threading;
 
using ArtOfTest.WebAii.Win32;
using ArtOfTest.WebAii.Win32.Dialogs;
 
namespace WebTesting
{
     public class FFDownloadsDialog : IDialog
     {
        #region Members
        /// <summary>
        /// Private storage for the number of times this dialog has been successfully handled.
        /// </summary>
        private int _handleCount;
        /// <summary>
        /// The number of times in a row the dialog has been found. This overcomes the problem
        /// where the dialog is first put up and momentarily displays "Downloads" and is
        /// quickly changed to "16% complete 1 file � Downloads".
        /// </summary>
        private int _foundCount = 0;
        /// <summary>
        /// The download window found.
        /// </summary>
        private Window _window;
        /// <summary>
        /// Stores the custom handler delegate, if set by the test code.
        /// </summary>
        private DialogHandlerDelegate _handlerDelegate;
        /// <summary>
        /// Stores the current handled state.
        /// </summary>
        private DialogCurrentState _currentState = DialogCurrentState.NotActive;
        /// <summary>
        /// Semaphore used by the WaitUntilHandled function.
        /// </summary>
        private AutoResetEvent _autoEvent = new AutoResetEvent(false);
        #endregion
 
        #region Private Constants
        /// <summary>
        /// The title of the dialog we want handled.
        /// </summary>
        private const string DIALOG_TITLE = "Downloads";
        #endregion
 
        #region Properties
        /// <summary>
        /// Gets the Window object of the dialog being handled.
        /// </summary>
        public Window Window
        {
            get {return this._window; }
        }
 
        /// <summary>
        /// Gets/Sets the number of times the dialog has been successfully handled.
        /// </summary>
        public int HandleCount
        {
            get {return this._handleCount; }
            set {this._handleCount = value; }
        }
 
        /// <summary>
        /// Gets/Sets the dialog custom handler.
        /// </summary>
        public DialogHandlerDelegate HandlerDelegate
        {
            get {return this._handlerDelegate; }
            set {this._handlerDelegate = value; }
        }
 
        /// <summary>
        /// Gets/Sets the current handled state. Will be set automatically by
        /// the DialogMonitor object so we don't need to worry about it in our
        /// code.
        /// </summary>
        public DialogCurrentState CurrentState
        {
            get {return this._currentState; }
            set {this._currentState = value; }
        }
        #endregion
````
````VB
Public Class FFDownloadsDialog
    Implements ArtOfTest.WebAii.Win32.Dialogs.IDialog
 
   #Region "Members"
    ' <summary>
    ' Private storage for the number of times this dialog has been successfully handled.
    ' </summary>
    Private _handleCount As Integer
    ' <summary>
    ' The number of times in a row the dialog has been found. This overcomes the problem
    ' where the dialog is first put up and momentarily displays "Downloads" and is
    ' quickly changed to "16% complete 1 file – Downloads".
    ' </summary>
    Private _foundCount As Integer = 0
    ' <summary>
    ' The download window found.
    ' </summary>
    Private _window As Window
    ' <summary>
    ' Stores the custom handler delegate, if set by the test code.
    ' </summary>
    Private _handlerDelegate As DialogHandlerDelegate
    ' <summary>
    ' Stores the current handled state.
    ' </summary>
    Private _currentState As DialogCurrentState = DialogCurrentState.NotActive
    ' <summary>
    ' Semaphore used by the WaitUntilHandled function.
    ' </summary>
    Private _autoEvent As AutoResetEvent = New AutoResetEvent(False)
#End Region
 
#Region "Private Constants"
    ' <summary>
    ' The title of the dialog we want handled.
    ' </summary>
    Private Const DIALOG_TITLE As String = "Downloads"
#End Region
 
#Region "Properties"
    ' <summary>
    ' Gets the Window object of the dialog being handled.
    ' </summary>
    ReadOnly Property Window() As Window _
    Implements ArtOfTest.WebAii.Win32.Dialogs.IDialog.Window
        Get
            Return Me._window
        End Get
    End Property
 
    ' <summary>
    ' Gets/Sets the number of times the dialog has been successfully handled.
    ' </summary>
    Property HandleCount() As Integer _
    Implements ArtOfTest.WebAii.Win32.Dialogs.IDialog.HandleCount
        Get
            Return Me._handleCount
        End Get
        Set(ByVal value As Integer)
            Me._handleCount = value
        End Set
    End Property
 
    ' <summary>
    ' Gets/Sets the dialog custom handler.
    ' </summary>
    Property HandlerDelegate() As DialogHandlerDelegate _
    Implements ArtOfTest.WebAii.Win32.Dialogs.IDialog.HandlerDelegate
        Get
            Return Me._handlerDelegate
        End Get
        Set(ByVal value As DialogHandlerDelegate)
            Me._handlerDelegate = value
        End Set
    End Property
 
    ' <summary>
    ' Gets/Sets the current handled state. Will be set automatically by
    ' the DialogMonitor object so we don't need to worry about it in our
    ' code.
    ' </summary>
    Property CurrentState() As DialogCurrentState _
    Implements ArtOfTest.WebAii.Win32.Dialogs.IDialog.CurrentState
        Get
            Return Me._currentState
        End Get
        Set(ByVal value As DialogCurrentState)
            Me._currentState = value
        End Set
    End Property
#End Region
```


So far everything is very simple and straightforward. Now that the local variables and properties are complete, it's time to implement the constructor. Since all we're going to do to handle the dialog is close it, we don't require the Desktop or DialogButton parameter that standard Win32 dialog handlers require:

```C#
#region Constructor
/// <summary>
/// Create the dialog.
/// </summary>
public FFDownloadsDialog()
{
}
#endregion
```
```VB
#Region "Constructor"
    ' <summary>
    ' Create the dialog handler instance.
    ' </summary>
    Public Sub New()
        MyBase.New()
    End Sub
#End Region
```

Since there's nothing to the constructor, we could optionally leave it out and let the default constructor take over. So let's start implementing the IDialog methods starting with IsDialogActive.

```C#
#region IDialog Members
/// <summary>
/// Check whether the dialog is present or not. This function is
/// called by the DialogMonitor object.
/// </summary>
/// <param name="dialogs">This is a list of dialogs passed in
/// by the DialogMonitor object. Because the window we need is
/// of the "MozillaUIWindowClass" class instead of the "#32770"
/// dialog class, it's never included in the dialogs list.
/// Thus we deliberately ignore this input parameter</param>
/// <returns>True/False whether this dialog is present.</returns>
public bool IsDialogActive(ArtOfTest.WebAii.Win32.WindowCollection dialogs)
{
    // Ignore dialogs parameter. It only contains windows of the 'Dialog' class.
    // The FireFox Downloads dialog is of the 'MozillaUIWindowClass' class
    this._window = WindowManager.FindWindowRecursively((IntPtr)0, "Downloads", false, 0);
    if (null == this._window ||
        !this._window.Caption.Equals("Downloads") ||
        !this._window.ClassName.Equals("MozillaUIWindowClass"))
    {
        this._foundCount = 0;
        return false;
    }
    this._foundCount++;
    if (this._foundCount < 4)
    {
        // Must find the dialog four times in a row to be considered real
        // instead of transient. When the dialog is first displayed it
        // reads "Downloads" but is quickly changed after initial display.
        return false;
    }
    return true;
}
````
````VB
' <summary>
' Check whether the dialog is present or not. This function is
' called by the DialogMonitor object.
' </summary>
' <param name="dialogs">This is a list of dialogs passed in
' by the DialogMonitor object. Because the window we need is
' of the "MozillaUIWindowClass" class instead of the "#32770"
' dialog class, it's never included in the dialogs list.
' Thus we deliberately ignore this input parameter</param>
' <returns>True/False whether this dialog is present.</returns>
Public Function IsDialogActive(ByVal dialogs As ArtOfTest.WebAii.Win32.WindowCollection) As Boolean _
    Implements ArtOfTest.WebAii.Win32.Dialogs.IDialog.IsDialogActive
    ' Ignore dialogs parameter. It only contains windows of the 'Dialog' class.
    ' The FireFox Downloads dialog is of the 'MozillaUIWindowClass' class
    Me._window = WindowManager.FindWindowRecursively(CType(0, System.IntPtr), "Downloads", False, 0)
    If IsNothing(Me._window) Or _
          Not Me._window.Caption.Equals("Downloads") Or _
          Not Me._window.ClassName.Equals("MozillaUIWindowClass") Then
            Me._foundCount = 0
            Return False
        End If
        Me._foundCount += 1
        If (Me._foundCount < 4) Then
            ' Must find the dialog four times in a row to be considered real
            ' instead of transient. When the dialog is first displayed it
            ' reads "Downloads" but is quickly changed after initial display.
            Return False
        End If
    Return True
End Function
````

Because the DialogMonitor object passes in a **WindowCollection** of windows that have a class name of "#**32770**" and the FireFox dialog has the class name "**MozillaUIWindowClass**" we have to ignore the passed in WindowCollection and perform our own FindWindowRecursively. Once a window with the right caption is found we still need to verify it has the right class name.
 
Detecting when the download manager has finished downloading files is a little bit tricky (and the only way to know this is through experience). When the dialog is first displayed the caption initially reads "Downloads" which is exactly the same thing it displays when all the downloads are complete. When it actually begins downloading a file, the dialog caption is changed to something like "11% of 1 file - Downloads". This change usually happens very quickly (in less than a second). But since it isn't instantaneous we need to monitor the caption for a short period of time to make sure it is quiescent before accepting that Firefox has finished all the downloads. This is accomplished in the code by verifying that the caption reads "Downloads" in 4 consecutive calls to IsDialogActive.
 
Now we need to implement the Handle function:

````C#
/// <summary>
/// This is called by the DialogMonitor whenever IsDialogActive returns true.
/// </summary>
public void Handle()
{
    // If you are sharing this implementation with other
    // developers, this allows them to override this method
    // by setting the handler delegate. So if the
    // delegate is not null, perform the built in handling logic
    // otherwise call the custom handling logic.
    if (this.HandlerDelegate != null)
    {
        this.HandlerDelegate(this);
    }
    else
    {
        try
        {
                   this.Window.Close();
                   this.Window.WaitForVisibility(false, 500);
                   this._autoEvent.Set();    // trigger the semaphore used by WaitUntilHandled
        }
        catch
        {
                   // Do any custom handling and return error.
        }
    }
}
````
````VB
' <summary>
' This is called by the DialogMonitor whenever IsDialogActive returns true.
' </summary>
' <returns>True/False whether the dialog was handled.</returns>
Public Sub Handle() _
Implements ArtOfTest.WebAii.Win32.Dialogs.IDialog.Handle
    ' If you are sharing this implementation with other
    ' developers, this allows them to override this method
    ' by setting the handler delegate. So if the
    ' delegate is not null, perform the built in handling logic
    ' otherwise call the custom handling logic.
    If (Not IsNothing(Me.HandlerDelegate)) Then
    Me.HandlerDelegate.Invoke(Me)
    Else
        Try
             Me.Window.Close()
             Me.Window.WaitForVisibility(False, 500)
            Me._autoEvent.Set()        ' trigger the semaphore used by WaitUntilHandled
         Catch
             ' Do any custom handling and return error.
         End Try
     End If
End Sub
````

The normal action we want our custom dialog handler to perform is to simply close the window. This is easily accomplished with this.Window.Close. Once the handler sends to the window the close command we wait up to 500 milliseconds for it to actually go away. We also trigger a semaphore so that the main test thread can be notified that the dialog has been handled.
 
Optionally our handler code will call a custom handler function if the delegate has been set by the calling program.
 
Lastly we need to implement the WaitUntilHandled function:

````C#
        /// <summary>
///
        /// May be called by test code. Waits up to the specific time out
        /// period for the dialog to be handled. Optionally clears the
        /// HandleCount property.
        /// </summary>
        /// <param name="timeout">The maximum number of milliseconds to
        /// wait for the dialog to be handled. If the timeout expires
        /// before the dialog is handled a timeout exception is thrown.</param>
        /// <param name="resetCount">Set to true to reset the
        /// HandleCount property to zero just prior to waiting.</param>
        public void WaitUntilHandled(int timeout, bool resetCount)
         {
             if (resetCount)
             {
                this.HandleCount = 0;
             }
             if (false == this._autoEvent.WaitOne(timeout, false))
             {
                throw new System.TimeoutException("FFDownloadsDialog.WaitUntilHandled timed out.");
            }
         }
     }
}
````
````VB
    ' <summary>
' <summary>
    ' May be called by test code. Waits up to the specific time out
    ' period for the dialog to be handled. Optionally clears the
    ' HandleCount property.
    ' </summary>
    ' <param name="timeout">The maximum number of milliseconds to
    ' wait for the dialog to be handled. If the timeout expires
    ' before the dialog is handled a timeout exception is thrown.</param>
    ' <param name="resetCount">Set to true to reset the
    ' HandleCount property to zero just prior to waiting.</param>
    Public Sub WaitUntilHandled(ByVal timeout As Integer, ByVal resetCount As Boolean)
         If (resetCount) Then
             Me.HandleCount = 0
         End If
             If (False = Me._autoEvent.WaitOne(timeout, False)) Then
             Throw New System.TimeoutException("FFDownloadsDialog.WaitUntilHandled timed out.")
    End If
End Sub
 
End Class
````

The only thing really happening in this code is to wait on the semaphore to be set. If the semaphore is not set within the timeout period it throws a System.TimeoutException exception. Optionally it will also reset the HandleCount property prior to waiting for the semaphore.

[1]: /img/testing-framework/write-tests-in-code/advanced-topics-wtc/html-popups-and-dialogs-wtc/firefox-dialogs/fig1.png
[2]: /img/testing-framework/write-tests-in-code/advanced-topics-wtc/html-popups-and-dialogs-wtc/firefox-dialogs/fig2.png
