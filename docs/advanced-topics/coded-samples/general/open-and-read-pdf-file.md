---
title: Validate a Locally Stored PDF File
page_title: Validate a Locally Stored PDF File
description: "Open a PDF file in Test Studio test and read its content. During the test run there is a PDF file created and stored locally on the hard disc. I would like to open that one and read its content."
position: 1
publish: false
---
# Validate a Locally Stored PDF File

*During the test run there is a PDF file created and stored locally on the hard disc. I would like to open that one and read its content.*

**Solution**

Test Studio cannot interact with PDF files opened in a browser - these do not contain DOM (Document Object Model) or HTML, so the Test Studio recorder cannot parse that content. However, a PDF file can be read in a coded step using an external dll to handle the PDF content. There are few steps to go through in order to prepare the coded step to open and read the PDF file.

1.&nbsp; The third party dll, which you can use for that is called *iTextSharp.dll* and can be downloaded <a href="https://sourceforge.net/projects/itextsharp/" target="_blank">here</a>.

2.&nbsp; Copy the unzipped dll into the project root folder and <a href="/features/coded-steps/add-assembly-reference" target="_blank">reference this in the Test Studio project</a> from that location.

3.&nbsp; Create a coded step in your test and add the following *usings*, or *Imports* for VB.Net, on top:

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

4.&nbsp; Below is listed sample code snippet to open a PDF file, which is stored locally on the disc, then read and output its content to the test execution log file. To store the text from the PDF is also used the <a href="https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder?view=netframework-4.8" target="_blank">C# StringBuidler Class</a>

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
