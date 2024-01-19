---
title: Using Zip Files with Aspose.TeX for .NET
linktitle: Using Zip Files with Aspose.TeX for .NET
second_title: Aspose.TeX .NET API
description: 
type: docs
weight: 10
url: /net/zip-file-io/zip-files-aspose-tex/
---

## Complete Source Code
```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Pdf;
using System.IO;

namespace Aspose.TeX.Examples.CSharp.TeXTypesetting
{
    /// <summary>
    /// Using ZIP directories for input and output, outputting to PDF device, writing terminal output to console.
    /// </summary>
    class ZipFileInputOuputAndPdfOutput
    {
        public static void Run()
        {
            // ExStart:TakeInputFromZip-WriteOutputToZip
            // Open the stream on the ZIP archive that will serve as the input working directory.
            using (Stream inZipStream = File.Open(Path.Combine("Your Input Directory", "zip-in.zip"), FileMode.Open))
            // Open the stream on the ZIP archive that will serve as the output working directory.
            using (Stream outZipStream = File.Open(Path.Combine("Your Output Directory", "zip-pdf-out.zip"), FileMode.Create))
            {
                // Create conversion options for default ObjectTeX format upon ObjectTeX engine extension.
                TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
                // Specify a ZIP archive working directory for the input. You can also specify a path inside the archive.
                options.InputWorkingDirectory = new InputZipDirectory(inZipStream, "in");
                // Specify a ZIP archive working directory for the output.
                options.OutputWorkingDirectory = new OutputZipDirectory(outZipStream);
                // Specify the console as the output terminal.
                options.TerminalOut = new OutputConsoleTerminal(); // Default value. Arbitrary assignment.

                // Define the saving options.
                options.SaveOptions = new PdfSaveOptions();
                // Run the job.
                TeXJob job = new TeXJob("hello-world", new PdfDevice(), options);
                job.Run();

                // For further output to look fine. 
                options.TerminalOut.Writer.WriteLine();

                // Finalize output ZIP archive.
                ((OutputZipDirectory)options.OutputWorkingDirectory).Finish();
            }
            // ExEnd:TakeInputFromZip-WriteOutputToZip
        }
    }
}
```