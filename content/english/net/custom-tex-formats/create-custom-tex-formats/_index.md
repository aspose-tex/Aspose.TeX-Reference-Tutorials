---
title: Creating Custom TeX Formats in .NET
linktitle: Creating Custom TeX Formats in .NET
second_title: Aspose.TeX .NET API
description: 
type: docs
weight: 10
url: /net/custom-tex-formats/create-custom-tex-formats/
---

## Complete Source Code
```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using Aspose.TeX.ResourceProviders;
using System.IO;
using System.Text;

namespace Aspose.TeX.Examples.CSharp.TeXTypesetting
{
    /// <summary>
    /// Typesetting a TeX file using a custom TeX format.
    /// </summary>
    class TypesetWithCustomTeXFormat
    {
        public static void Run()
        {
            // ExStart:TypesetWithCustomTeXFormat
            // Create the format provider using the file system input working directory.
            // We use the project output directory as our custom format file is supposed to be located there.
            using (FormatProvider formatProvider =
                new FormatProvider(new InputFileSystemDirectory("Your Output Directory"), "customtex"))
            {
                // Create conversion options for a custom format upon ObjectTeX engine extension.
                TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX(formatProvider));
                options.JobName = "typeset-with-custom-format";
                // Specify the input working directory. This is not required here as we are providing the main input as a stream.
                // But it is required when the main input has dependencies (e.g. images).
                options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
                // Specify a file system working directory for the output.
                options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");

                // Run the job.
                new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
                        "Congratulations! You have successfully typeset this text with your own TeX format!\\end")),
                        new XpsDevice(), options).Run();

                // For further output to look fine.
                options.TerminalOut.Writer.WriteLine();
            }
            // ExEnd:TypesetWithCustomTeXFormat
        }
    }
}
```