---
title: Rendering LaTeX Math as SVG in .NET
linktitle: Rendering LaTeX Math as SVG in .NET
second_title: Aspose.TeX .NET API
description: 
type: docs
weight: 10
url: /net/svg-math-rendering/render-latex-math-svg/
---

## Complete Source Code
```csharp
using Aspose.TeX.Features;

namespace Aspose.TeX.Examples.CSharp.LaTeXMathRendering
{
    class SvgLaTeXMathRenderer
    {
        public static void Run()
        {
            // ExStart:SvgLaTeXMathRendering
            // Create rendering options.
            MathRendererOptions options = new SvgMathRendererOptions();
            // Specify the preamble.
            options.Preamble = @"\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
\usepackage{color}";
            // Specify the scaling factor 300%.
            options.Scale = 3000;
            // Specify the foreground color.
            options.TextColor = System.Drawing.Color.Black;
            // Specify the background color.
            options.BackgroundColor = System.Drawing.Color.White;
            // Specify the output stream for the log file.
            options.LogStream = new System.IO.MemoryStream();
            // Specify whether to show the terminal output on the console or not.
            options.ShowTerminal = true;

            // The variable in which the dimensions of the resulting image will be written.
            System.Drawing.SizeF size = new System.Drawing.SizeF();
            // Create the output stream for the formula image.
            using (System.IO.Stream stream = System.IO.File.Open(
                System.IO.Path.Combine("Your Output Directory", "math-formula.svg"), System.IO.FileMode.Create))
            {
                // Run rendering.
                new SvgMathRenderer().Render(@"\begin{equation*}
e^x = x^{\color{red}0} + x^{\color{red}1} + \frac{x^{\color{red}2}}{2} + \frac{x^{\color{red}3}}{6} + \cdots = \sum_{n\geq 0} \frac{x^{\color{red}n}}{n!}
\end{equation*}", stream, options, out size);
            }

            // Show other results.
            System.Console.Out.WriteLine(options.ErrorReport);
            System.Console.Out.WriteLine();
            System.Console.Out.WriteLine("Size: " + size);
            // ExEnd:SvgLaTeXMathRenderering
        }
    }
}

```