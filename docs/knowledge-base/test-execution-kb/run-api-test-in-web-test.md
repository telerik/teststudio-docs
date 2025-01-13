---
title: Run an API Test within a Web Test
page_title: Run an API Test within a Web Test
description:  Run an API Test within a Web Test with Test Studio. Execute API test as step in a web test in Test Studio. Run API tests as part of a Test Studio web project. Integrate API testing with Test Studio web tests. 
position: 1
---
# How to Run an API Test within a Web Test

In some cases you may need to combine a Test Studio web test with an API test. For example, if your application under test interacts with a service (e.g. creates a user in a web interface that gets stored in a database) and you want to verify directly against that interface that your new user is correctly created.

> __Tip__
><br>
><br>
> Test Studio gives the option for <a href="/features/execute-apitest/add-api-test-as-step" target="_blank">running API tests as steps</a> from a web test out-of-the-box.

To achieve that with Test Studio you will need to create a Test Studio for APIs project and create a test that performs the necessary requests and verifications.

The next step is to create a coded step in the web test that will start a system process. The following code will run the Telerik.ApiTesting.Runner.exe with the `test` command and the following arguments:

- the path to the API test project (`-p C:\ApiTests\DemoTests`)
- the test inside this project that needs to be executed  (`-t "".\Get User Id By Its Username""`)

> You can read more about running API tests with Test Studio for APIs command line from [here](http://docs.telerik.com/teststudio-apis/features/command-line/command-line-parameters)

The code will wait for the end of the API test execution. After the process ends - the exit code is placed in assert statement to check if this step passed or failed depending on the API test status.

Hint: in a default installation, the path to the executable Telerik.ApiTesting.Runner.exe is: 
"C:\Program Files (x86)\Progress\Test Studio\Bin\ApiTesting\runnerconsole\Telerik.ApiTesting.Runner.exe"

````C#
	
	// Have to include the references:
	using System.Diagnostics;
	
	[CodedStep(@"Run Api Test")]
	public void Run_Api_Test_CodedStep()
	{
		// initialize new system process
		Process runApiTest = new Process();

		// define the process name to be started
		runApiTest.StartInfo.FileName = @"[PathToExecutable]\Telerik.ApiTesting.Runner.exe";

	    // set the arguments
		runApiTest.StartInfo.Arguments = @"test -p [PathToTheTestProject]\DemoTests -t "".\Get User Id By Its Username""";

	    // run the process
	    runApiTest.Start();

	    // wait until the test return an exit code
	    runApiTest.WaitForExit();

	    // get the exit code from the executed process 
	    int exitCode = runApiTest.ExitCode;

	    // check if this test step pass or fail. If return 0 - process complete normally, else - process fould.
	    Assert.AreEqual(exitCode, 0);
	}
	
````
````VB
	
	Imports System.Diagnostics
	
	<CodedStep("Run Api Test")> _
    Public Sub Run_Api_Test_CodedStep()

        Dim runApiTest As New Process()

		runApiTest.StartInfo.FileName = "[PathToExecutable]\Telerik.ApiTesting.Runner.exe"
		
        runApiTest.StartInfo.Arguments = "test -p [PathToTheTestProject]\DemoTests -t "".\Get User Id By Its Username"""
    	
		runApiTest.Start()
		
		runApiTest.WaitForExit()
		
		Dim exitCode As Integer = runApiTest.ExitCode			

		Assert.AreEqual(exitCode, 0)

	End Sub
	
````

## Advanced: Passing a Variable from an API Test to a Web Test

Sometimes you may need to get a variable that is acquired by your API test and use it into your web test. (For example if you want to create a user first via a REST service and than use his user ID to perform an action in your web test.)

> __Tip__
><br>
><br>
> Test Studio gives the option for <a href="/features/execute-apitest/passing-variables" target="_blank">passing variables from the web test to the embedded API test and vice versa</a> out-of-the-box.

Test Studio for APIs stores [runtime variables](http://docs.telerik.com/teststudio-apis/features/variables#Runtime-Variables) in a ".variables" directory inside the root of the test project being executed. The files in that folder are usually consumed only by the user interface of Test Studio for APIs. This is why by default, if you run your tests via command line, the ".variables" folder will not be generated. In order to generate it when running tests, you need to add an additional parameter to your execution command: `--save-contexts`. For example, to run a single test in a test project and generate .variables, you can use a command like:

`C:\>"C:\Program Files (x86)\Progress\Test Studio for APIs\Bin\ApiTesting\runnerconsole\Telerik.ApiTesting.Runner.exe" test -p "C:\ApiTests\DemoTests" -t ".\CRUD Tests\Get All Users" --save-contexts`

Inside the ".variables" folder, Test Studio for APIs generates a separate file for each executed test (with a file name like: `my-test-name.variables`) and an additional "root" file for project-level variables, called ".global.variables".

Every time you use a [Set Variable step](http://docs.telerik.com/teststudio-apis/features/steps/set-variable) in an API test, its value gets stored in the .variables file for the respective test. 

The easiest way to transfer any value from an API test to a web test is to store it with a Set Variable step in Test Studio for APIs and extract it from the .variables file later in a coded step in your web test.

To achieve that you can:
 - Create a web test in Test Studio. 
 - Use the coded step described above to run your API test, but add `--save-contexts` to your arguments - e.g.:

	`runApiTest.StartInfo.Arguments = "test -p [PathToTheTestProject]\DemoTests -t "".\Get User Id By Its Username""" --save-contexts`

 - Add another coded step after that, that will read the .variables file for your test and extract the desired variable:

````C#
		
		// Have to include the references:
		using System.IO;
		using Newtonsoft.Json.Linq;
		
		[CodedStep(@"Get Variable from Api Test")]
		public void Get_Variable_from_Api_Test_CodedStep()
		{
			string path = @"[PathToTheTestProject]\TestStudioTest\.variables\Test Case.variables";
	
	        string json = string.Empty;
	
	        using (StreamReader reader = new StreamReader(path))
	        {
	            json = reader.ReadToEnd();
	        }
	
	        var result = JToken.Parse(json);
	
			// Select the desired value from the json. 
			// In this example ".\\Test Case" is the path to the test case
			// and "user-email" is the name of the variable stored by the API test
	        string email = result["scopes"][".\\Test Case"]["variables"]["user-email"].ToString();
	        
			// Store the email to an extracted variable which can be used in a UI step or another coded step
	        SetExtractedValue("extractedEmail", email);
		}
		
````
````VB

		Imports System.IO
		Imports Newtonsoft.Json.Linq

        <CodedStep("Get Variable from Api Test")> _
        Public Sub Get_Variable_from_Api_Test_CodedStep()
            
            Dim path As String = "C:\tmp\TestStudioTest\.variables\Test Case.variables"
        	Dim json As String = String.Empty

        	Using reader As New StreamReader(path)
        		json = reader.ReadToEnd()
        	End Using

        	Dim result = JToken.Parse(json)

        	Dim email As String = result("scopes")(".\Test Case")("variables")("user-email").ToString()

        	SetExtractedValue("extractedEmail", email)
           
        End Sub

````

Note: .variables files contain text in json format. An easy way to extract a particular value from them is if you parse the file using [Json.NET](http://www.newtonsoft.com/json). Test Studio already uses Json.NET so its .dll file (Newtonsoft.Json.dll) is available in the Bin folder of the Test Studio installation folder. In order to add `using Newtonsoft.Json.Linq;` to your coded step, you need to add an assembly reference to Newtonsoft.Json.dll as described [here](http://docs.telerik.com/teststudio/features/coded-steps/add-assembly-reference)

The code snippet saves the extracted value to a variable in the web test. See [here](http://docs.telerik.com/teststudio/advanced-topics/coded-samples/general/extracted-variables-in-code) for more information. 

Once extracted, the variable can be used as described [here](http://docs.telerik.com/teststudio/knowledge-base/data-driven-testing-kb/pass-a-variable)