---
title: LaTeX to PDF in .NET - 2 Easy Methods with Aspose.TeX
linktitle: LaTeX to PDF in .NET - 2 Easy Methods with Aspose.TeX
second_title: Aspose.TeX .NET API
description: 
type: docs
weight: 10
url: /net/latex-conversion/to-pdf/
---

## Complete Source Code
```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Pdf;
using System.IO;

namespace Aspose.TeX.Examples.CSharp.TeXTypesetting
{
    class LaTeXPdfConversionSimplest
    {
        public static void Run()
        {
            // ExStart:Conversion-LaTeXToPdf-Simplest
            // Create conversion options for Object LaTeX format upon Object TeX engine extension.
            TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectLaTeX);
            // Specify a file system working directory for the output.
            options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
            // Initialize the options for saving in PDF format.
            options.SaveOptions = new PdfSaveOptions();
            // Run LaTeX to PDF conversion.
            new TeXJob(Path.Combine("Your Input Directory", "hello-world.ltx"), new PdfDevice(), options).Run();
            // ExEnd:Conversion-LaTeXToPdf-Simplest
        }
    }
}

```
