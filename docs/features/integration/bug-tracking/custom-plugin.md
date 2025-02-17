---
title: Custom Plugin
page_title: Create a Custom Bug Tracking Plugin
description: "Create a Custom Bug Tracking Plugin in Test Studio. Interface Test Studio with your custom Bug Tracking application. Sample code to build custom bug tracking plugin in Test Studio."
previous_url: /user-guide/extensions/bug-tracking/custom-plugin.aspx, /user-guide/extensions/bug-tracking/custom-plugin
position: 1
---
# Create a Custom Bug Tracking Plugin

This document shows you how to build a plugin to interface Test Studio with your custom Bug Tracking application, such as JIRA's bug tracking system. For a complete working example, including source code, go to the <a href="https://github.com/TestStudio/JiraPlugin" target="_blank">JIRA bug tracking repository on GitHub</a>.

> As of Test Studio release 2014 R2 (v.2014.2.618) Test Studio has integration with <a href="/features/integration/bug-tracking/Configuration#jira" target="_blank">Jira bug tracker</a>.

Test Studio uses its plugins model to run the Bug Trackers. The type of Bug Tracking tool isn't important – it's all about the actual implementation of the Bug Tracker (IBugTracker interface). The absolute minimum is to just implement the IBugTracker interface to display the app in the **Manage Bug Tracking** dialog. Find a sample class below.

1.&nbsp; Create a Class Library project in Visual Studio. This example uses C#.

2.&nbsp; Reference the following DLLs in **C:\Program Files (x86)\Progress\Test Studio\Bin\**: 

- **ArtOfTest.WebAii.dll**
- **ArtOfTest.WebAii.Design.dll**
- **Telerik.TestingFramework.Json.dll**

> Ensure the Specific Version property for these references is set to False. See [here](/troubleshooting-guide/visual-studio-tg/missing-assembly-references) for more information.

3.&nbsp; Add the following using statement to the class file:

```C#
using ArtOfTest.WebAii.Design.Extensibility.BugTracking;
```

4.&nbsp; The *ArtOfTest.WebAii.Design.Extensibility.BugTracking* namespace contains **IBugTracker** that the class needs 	to implement:

```C#
namespace ClassLibrary1
{
    public class Class2 : IBugTracker
    {
    }
}
```

5.&nbsp; Right click on IBugTracker and select Implement Interface > Implement Interface. This displays all the methods   	and notifications exposed by Test Studio. Here are definitions for each IBugTracker member:

```C#
	namespace ClassLibrary1
	{
		public class Class2 : IBugTracker
		{
        #region IBugTracker Members
 
        // Applies the persistable settings upon loading the user settings from the XML file where persisted.
        // The settings are persisted so that the user can get the configured bug tracker on the next project load.
        // <returns>Returns 'true' if the settings are valid and the operation is successful.</returns>
        public bool ApplyPersistableSettings(BugTrackerPersistableSettings settings)
        {
            // Your implementation goes here
        }
 
        // Get the connection settings UI.
        // Each provider exposes its own specific settings UI and handles connections internally.
        public IBugTrackerConnectionUI ConnectionUI
        {
            // Your implementation goes here
        }
 
        // Gets the current error message, if any, for display by Test Studio.
        public string ErrorMessage
        {
            // Your implementation goes here
        }
 
        // Retrieves the persistable settings specific to the bug tracking tool provider.
        // The settings are persisted so that the user can get the configured bug tracker on the next project load.
        // <returns>The persistable settings.</returns>
        public BugTrackerPersistableSettings GetPersistableSettings()
        {
            // Your implementation goes here
        }
 
        // Gets whether the provider is configured so that the user can submit bugs to the bug tracking tool.
        public bool IsConfigured
        {
            // Your implementation goes here
        }
 
        // Get the system name of your bug tracker plugin.
        // THis name will be displayed in Test Studio's list of available bug trackers.
        public string Name
        {
            // Your implementation goes here
        }
 
        // Reset all bug tracker connection settings.
        // Called when opening or closing a project.
        // Useful method to clean up the bug tracker data internally.
        public void ResetSettings()
        {
            // Your implementation goes here
        }
 
	#if Use2014_1_421
        // Submits a bug to the bug tracking tool.
        // Return the bug number created in your bug tracking tool.
        public int SubmitBug(IBug bug)
        {
            // Your implementation goes here
        }
	#else
        // As of build 2014.1.428 this function must return a string
        // Submits a bug to the bug tracking tool.
        // Return the bug ID created in your bug tracking tool.
        public string SubmitBug(IBug bug)
        {
            // Your implementation goes here
        }
	#endif
 
        #endregion
    }
    }
```

6.&nbsp; Any implementation beyond this is specific to the actual Bug Tracking application you're using.

- **ConnectionUI** is a WPF control Test Studio loads when you choose to configure the selected bug tracker.
- The bug tracker implementation is supposed to work with the ConnectionUI inputs, hence it depends on the needs of the specific bug tracker.
- For example, if the bug tracker requires a Server URL field, you can add that input here.

7.&nbsp; You can also persist the configured bug tracker settings so that you don't have to reconfigure the bug tracker 	each time you load the project. The process is straight-forward – just implement the Save/Load methods in 	regards to the fields specific to the bug tracker to which you're connecting.

- To provide that ability, **Get/ApplyPersistableSettings** are exposed to work with **BugTrackerPersistableSettings**. 
- Implement that class and use it for the **IBugTracker** related methods. 
- **Get/Apply** is called by Test Studio to save the settings in the Settings.aiis file, as well as load them and configure the bug tracker on project load. 

8.&nbsp; Compile the class library.

9.&nbsp; Deploy the plugin by copying the DLL from the **%Project Folder%\ClassLibrary1\ClassLibrary1\bin\Debug** to one of the following directories:

- For Test Studio versions 2012.2.920 and later:  **C:\Program Files (x86)\Progress\Test Studio\Bin\Plugins\**
- For Test Studio versions before 2012.2.920: **C:\Program Files (x86)\Progress\Test Studio\Bin\Plugins\BugTrackers\**

> To implement the auto-submit option (specifically for Visual Studio execution), the signed assembly must be installed into the GAC.
</br>
</br>
</br>
> __Note!__ As of Test Studio version **2017 R3 2017.3.1010** the default installation path for new installation is **C:\Program Files (x86)\Progress\Test Studio**.

The **IBugTrackerConnectionUI** interface exposes additional methods to further customize the connection dialog behavior. For example, use it if you'd like to restrict submitting the data depending on what's entered.


Create another class and implement the **IBugTrackerConnectionUI** interface. Here are the definitions for each **IBugTrackerConnectionUI** member:

```C#
        public class Class3 : IBugTrackerConnectionUI
                {
    	#region IBugTrackerConnectionUI Members
 
    	/// <summary>
	    /// The WPF UserControl to present to the users so that they can fill in the necessary configuration data.
	    /// This control will be placed inside a Grid that has a fixed size of 390w x 382h.
	    /// </summary>
	    public System.Windows.Controls.Control SettingsControl
	    {
	        // Your implementation goes here
	    }
	 
	    /// <summary>
	    /// Whether to let the user close the UI. Optional, return 'true' so that the user can click
	    /// the 'Cancel' button i.e. to enable it.
	    /// </summary>
	    public bool CanClose
	    {
	        // Your implementation goes here
	    }
	 
	    /// <summary>
	    /// Whether to allow the user to save the state (makes sense in addition to OnSave implementation).
	    /// Return 'true' so that the user can click the 'Done' button i.e. to enable it.
	    /// </summary>
	    public bool CanSave
	    {
	        // Your implementation goes here
	    }
	 
	    /// <summary>
	    /// Optional. Called whenever the bug tracker UI is closed for any reason.
	    /// Clear the view for the next project to be loaded, which may not have Jira settings.
	    /// </summary>
	    public void OnClose()
	    {
	        // Your implementation goes here
	    }
	 
	    /// <summary>
	    /// Optional. Called whenever user clicks Save in the UI to save the settings.
	    /// Enables customizing the save click handling.
	    /// We'll make the settings in the ViewModel the active settings for submitting bugs.
	    /// </summary>
	    public void OnSave()
	    {
	        // Your implementation goes here
	    }
	 
	    #endregion
	 
	    #region INotifyPropertyChanged Members
	 
	    public event System.ComponentModel.PropertyChangedEventHandler PropertyChanged;
	 
	    private void OnPropertyChanged(string propertyName)
	    {
	        PropertyChangedEventHandler handler = PropertyChanged;
	 
	        if (handler != null)
	            handler(this, new PropertyChangedEventArgs(propertyName));
	    }
	 
	    #endregion
		}
```