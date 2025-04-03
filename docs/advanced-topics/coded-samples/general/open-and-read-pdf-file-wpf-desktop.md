---
title: Read Saved PDF File - WPF and Desktop Tests
page_title: Read Saved PDF File - WPF and Desktop Tests
description: "Open a saved locally PDF file in Test Studio WPF and Desktop Tests and read its content. The tested application creates a PDF file and let's you save it locally on the hard disc. How to open that PDF file and read its content from WPF or Desktop test?"
position: 1
published: true
---
# Read Saved PDF File 

The automation scenario requires a saved PDF file to be opened, then to read its content and to validate it. 

The described approach using a 3rd party and open source dll is applicable for WPF and Desktop tests. <a href="/automated-tests/recording/pdf-validation" target="_blank">Test Studio web tests let's you validate the PDF file in the browser out-of-the-box</a>. 

**Solution**

1. We prepared a sample using the third party dll **iTextSharp.dll**. It can be downloaded from its official page <a href="https://sourceforge.net/projects/itextsharp/" target="_blank">here</a>.

    > __Note__
    ><br>
    > You can choose any other external library with similar functionality and implement the proper code for the actions that suits your needs. 

2. Copy the unzipped dll into the project root folder and <a href="/features/coded-steps/add-assembly-reference" target="_blank">add reference to it in the Test Studio project</a> from that location.

3. <a href="/automated-tests/coded-tests/coded-step" target="_blank">Create a coded step in your test and add the following *usings*, or *Imports* for VB.Net, on top:

    ```C#
    using iTextSharp.text.pdf;
    using iTextSharp.text.pdf.parser;
    using System.IO;
    ```
    ```VB
    Imports iTextSharp.text.pdf
    Imports iTextSharp.text.pdf.parser
    Imports System.IO
    ```

4. The below snippet opens a PDF file, which is stored locally on the disc, then reads and outputs its content to the test execution log file. The sample uses <a href="https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder?view=netframework-4.8" target="_blank">C# StringBuidler Class</a> to append the text from the PDF file. 

    ```C#
    // Define the name of the file to open
    string fileName = "C:\\pathToYourPDF\\PDFName.pdf";

    // Define the file to store the read from PDF content
    StringBuilder text = new StringBuilder();

    // Verify if the PDF file exists and open it
    if (File.Exists(fileName))
        {
        // Initilize the pdfReader
        PdfReader pdfReader = new PdfReader(fileName);

        // Go through the pages of the PDF file, read its content and append it
        for (int page = 1; page <= pdfReader.NumberOfPages; page++)
            {
                ITextExtractionStrategy strategy = new SimpleTextExtractionStrategy();
                string currentText = PdfTextExtractor.GetTextFromPage(pdfReader, page, strategy);

                currentText = Encoding.UTF8.GetString(ASCIIEncoding.Convert(Encoding.Default, Encoding.UTF8, Encoding.Default.GetBytes(currentText)));
                text.Append(currentText);
            }

        // Output the collected text in the test execution log file
        Log.WriteLine(text.ToString());

        // Close the pdfReader
        pdfReader.Close();
        }
    ```
    ```VB
    ' Define the name of the file to open
    Dim fileName AsString = "folder\\pdfFileName.pdf"

    ' Define the file to store the read from PDF content
    Dim text AsNew StringBuilder()

    ' Verify if the PDF file exists and open it
    If File.Exists(fileName)
        Then
            ' Initilize the pdfReader
            Dim pdfReader AsNew PdfReader(fileName)

            ' Go through the pages of the PDF file, read its content and append it
            For page AsInteger = 1 To pdfReader.NumberOfPages

                Dim strategy As ITextExtractionStrategy = New SimpleTextExtractionStrategy()
                Dim currentText AsString = PdfTextExtractor.GetTextFromPage(pdfReader, page, strategy)

                currentText = Encoding.UTF8.GetString(ASCIIEncoding.Convert(Encoding.[Default], Encoding.UTF8, Encoding.[Default].GetBytes(currentText)))
                text.Append(currentText)
            Next
        ' Output the collected text in the test execution log file
        Log.WriteLine(text.ToString())

        ' Close the pdfReader
        pdfReader.Close()
    EndIf
    ```
