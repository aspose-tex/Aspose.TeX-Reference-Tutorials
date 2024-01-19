---
title: Work with Filesystem & ZIP Inputs in Aspose.TeX for .NET
linktitle: Work with Filesystem & ZIP Inputs in Aspose.TeX for .NET
second_title: Aspose.TeX .NET API
description: 
type: docs
weight: 11
url: /net/file-input-output/required-inputs-from-filesystem-and-zip/
---

## Complete Source Code
```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Image;
using System.IO;

namespace Aspose.TeX.Examples.CSharp.TeXTypesetting
{
    class LaTeXRequiredInputFs
    {
        public static void Run()
        {
            // ExStart:Conversion-RequiredInput-FileSystem
            // Create conversion options for Object LaTeX format upon Object TeX engine extension.
            TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectLaTeX);
            // Specify a file system working directory for the output.
            options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
            // Specify a file system working directory for the required input.
            // The directory containing packages may be located anywhere.
            options.RequiredInputDirectory = new InputFileSystemDirectory(Path.Combine("Your Input Directory", "packages"));
            // Initialize the options for saving in PNG format.
            options.SaveOptions = new PngSaveOptions();
            // Run LaTeX to PNG conversion.
            new TeXJob(Path.Combine("Your Input Directory", "required-input-fs.tex"), new ImageDevice(), options).Run();
            // ExEnd:Conversion-RequiredInput-FileSystem
        }
    }
}

```
