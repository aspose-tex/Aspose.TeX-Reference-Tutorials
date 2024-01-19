---
title: Effortlessly Convert LaTeX to SVG in .NET with Aspose.TeX
linktitle: Effortlessly Convert LaTeX to SVG in .NET with Aspose.TeX
second_title: Aspose.TeX .NET API
description: 
type: docs
weight: 12
url: /net/latex-conversion/to-svg/
---

## Complete Source Code
```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Svg;
using System.IO;

namespace Aspose.TeX.Examples.CSharp.TeXTypesetting
{
    class LaTeXSvgConversionSimplest
    {
        public static void Run()
        {
            // ExStart:Conversion-LaTeXToSvg-Simplest
            // Create conversion options for Object LaTeX format upon Object TeX engine extension.
            TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectLaTeX);
            // Specify a file system working directory for the output.
            options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
            // Initialize the options for saving in SVG format.
            options.SaveOptions = new SvgSaveOptions();
            // Run LaTeX to SVG conversion.
            new TeXJob(Path.Combine("Your Input Directory", "hello-world.ltx"), new SvgDevice(), options).Run();
            // ExEnd:Conversion-LaTeXToSvg-Simplest
        }
    }
}

```
