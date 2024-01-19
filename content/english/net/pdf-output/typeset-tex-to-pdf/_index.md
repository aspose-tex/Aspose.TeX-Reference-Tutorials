---
title: How to Typeset TeX to PDF in .NET
linktitle: How to Typeset TeX to PDF in .NET
second_title: Aspose.TeX .NET API
description: 
type: docs
weight: 10
url: /net/pdf-output/typeset-tex-to-pdf/
---

## Complete Source Code
```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Pdf;
using System.IO;

namespace Aspose.TeX.Examples.CSharp.TeXTypesetting
{
    /// <summary>
    /// Alternative way to obtain typeset document from PDF device.
    /// </summary>
    class TypesetPdfWrittenToExternalStream
    {
        public static void Run()
        {
            // ExStart:WriteOutputPdfToExternalStream
            // Open a stream on a ZIP archive that will serve as the input working directory.
            using (Stream inZipStream = File.Open(Path.Combine("Your Input Directory", "zip-in.zip"), FileMode.Open))
            // Open a stream on a ZIP archive that will serve as the output working directory.
            using (Stream outZipStream = File.Open(Path.Combine("Your Output Directory", "typeset-pdf-to-external-stream.zip"), FileMode.Create))
            {
                // Create conversion options for default ObjectTeX format upon ObjectTeX engine extension.
                TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
                // Specify a job name.
                options.JobName = "typeset-pdf-to-external-stream"; // does NOT define the name of the output PDF.
                // Specify a ZIP archive working directory for the input. You can also specify a path inside the archive.
                options.InputWorkingDirectory = new InputZipDirectory(inZipStream, "in");
                // Specify a ZIP archive working directory for the output.
                options.OutputWorkingDirectory = new OutputZipDirectory(outZipStream);
                // Specify that the terminal output must be written to a file in the output working directory.
                // The file name is <job_name>.trm.
                options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);

                // Define the saving options.
                options.SaveOptions = new PdfSaveOptions();
                // Open a stream to write the output PDF to.
                // 1) A file somewhere on a local file system.
                using (Stream stream = File.Open(Path.Combine("Your Output Directory", "file-name.pdf"), FileMode.Create)) // writing PDF somewhere else
                // 2) A file in the output ZIP. A weird feature that extends flexibilty :)
                //using (Stream stream = options.OutputWorkingDirectory.GetFile("file-name.pdf", out string fullName)) // writing PDF to the same ZIP
                    new TeXJob("hello-world", new PdfDevice(stream), options).Run();

                // Finalize output ZIP archive.
                ((OutputZipDirectory)options.OutputWorkingDirectory).Finish();
            }
            // ExEnd:WriteOutputPdfToExternalStream
        }
    }
}
```