---
date: 2026-10-19
description: Learn how to perform tex document generation, create custom tex format
  and set tex input directory using Aspose.TeX for .NET. Step‑by‑step guide with code
  snippets and troubleshooting tips.
images:
- /net/custom-tex-formats/create-custom-tex-formats/og-image.png
keywords:
- tex document generation
- create custom tex format
- set tex input directory
- custom tex macros
lastmod: 2026-10-19
linktitle: Creating Custom TeX Formats in .NET
og_description: tex document generation with Aspose.TeX lets you create custom tex
  format and set tex input directory in .NET. Follow this guide for XPS, PDF or PNG
  output.
og_image_alt: Developer guide showing tex document generation using Aspose.TeX in
  .NET
og_title: How to do tex document generation with format in .NET
schemas:
- author: Aspose
  dateModified: '2026-10-19'
  description: Learn how to perform tex document generation, create custom tex format
    and set tex input directory using Aspose.TeX for .NET. Step‑by‑step guide with
    code snippets and troubleshooting tips.
  headline: How to do tex document generation with format in .NET
  type: TechArticle
- description: Learn how to perform tex document generation, create custom tex format
    and set tex input directory using Aspose.TeX for .NET. Step‑by‑step guide with
    code snippets and troubleshooting tips.
  name: How to do tex document generation with format in .NET
  steps:
  - name: '**Aspose.TeX for .NET** – download it from the [Aspose.TeX website](https://releases.aspose.com/tex/net/).'
    text: '**Aspose.TeX for .NET** – download it from the [Aspose.TeX website](https://releases.aspose.com/tex/net/).'
  - name: A **.NET development environment** (Visual Studio, VS Code, or the .NET
      CLI).
    text: A **.NET development environment** (Visual Studio, VS Code, or the .NET
      CLI).
  - name: (Optional) A valid **Aspose.TeX license** for production use.
    text: (Optional) A valid **Aspose.TeX license** for production use.
  type: HowTo
- questions:
  - answer: Absolutely. Replace `new XpsDevice()` with `new PdfDevice()` and adjust
      the output path accordingly.
    question: Can I output PDF instead of XPS?
  - answer: Yes. Any modification to macros or engine settings requires re‑running
      `tex -ini` to generate a fresh `.fmt` file.
    question: Do I need to re‑compile the format file after every change?
  type: FAQPage
second_title: Aspose.TeX .NET API
tags:
- tex document generation
- Aspose.TeX
- .NET document processing
- custom tex format
title: How to do tex document generation with format in .NET
url: /net/custom-tex-formats/create-custom-tex-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to do tex document generation with format in .NET

In modern .NET development, **tex document generation** is a powerful way to produce high‑quality typeset output without relying on external LaTeX installations. Aspose.TeX for .NET gives you full control: you can **create custom tex format**, point the engine at a dedicated input folder, and export to XPS, PDF, PNG, or other devices—all from straightforward C# code.

## Quick answers
- **What does “create custom tex format” mean?** It means defining your own TeX engine configuration and compiled format file so the processor follows your macros and settings.  
- **Which library do I need?** Aspose.TeX for .NET, which supports 30+ input and output formats.  
- **Do I have to set a tex input directory?** Yes – use `InputWorkingDirectory` to tell the engine where auxiliary files live.  
- **What output can I generate?** XPS, PDF, PNG, TIFF, and many more device formats.  
- **Is a license required for production?** A valid Aspose.TeX license is mandatory for commercial deployments.

## What is a custom tex format?
A custom tex format is a pre‑compiled collection of macros and engine settings that the TeX processor loads at start‑up. By creating one, you can embed corporate branding, enforce layout standards, and reduce compilation time for repetitive documents. It enables consistent styling across all generated documents and simplifies maintenance of complex typesetting workflows.

## Why set a tex input directory?
Setting the **tex input directory** tells the engine where to locate auxiliary files such as style files, custom fonts, or additional macro packages. This eliminates “file not found” errors and keeps your project folder tidy. It also improves build reproducibility by ensuring all resources are resolved from a known location.

## Prerequisites

Before you start, ensure you have:

1. **Aspose.TeX for .NET** – download it from the [Aspose.TeX website](https://releases.aspose.com/tex/net/).  
2. A **.NET development environment** (Visual Studio, VS Code, or the .NET CLI).  
3. (Optional) A valid **Aspose.TeX license** for production use.

## Import namespaces

The following namespaces give you access to the core Aspose.TeX classes.  
`Document`‑related classes live under `Aspose.TeX`, while options and devices are in `Aspose.TeX.Rendering`.

The `Document` class is the top‑level object that represents a single TeX document in memory.  

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using Aspose.TeX.ResourceProviders;
using System.IO;
using System.Text;
```

## Step 1: create the format provider

The `FormatProvider` tells the engine where the compiled format file (`customtex.fmt`) resides. Replace `"Your Output Directory"` with the absolute path that contains your custom format.

`FormatProvider` is a lightweight wrapper that loads the `.fmt` file once and reuses it for every conversion, dramatically improving performance for batch jobs.

```csharp
using (FormatProvider formatProvider =
    new FormatProvider(new InputFileSystemDirectory("Your Output Directory"), "customtex"))
{
```

## Step 2: configure conversion options (and set tex input directory)

Here we build a `TeXOptions` instance. The `InputWorkingDirectory` property **sets the tex input directory** so the engine can locate any supporting files such as custom packages or fonts.

`TeXOptions` also lets you specify the output device, page size, and rendering quality. For large‑scale generation, you can enable `EnableParallelProcessing` to speed up rendering on multi‑core servers.

```csharp
    TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX(formatProvider));
    options.JobName = "typeset-with-custom-format";
    options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
    options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

## Step 3: run the job

Now feed a simple TeX string to the engine, choose an output device (XPS in this example), and execute the job. The `TeXEngine` reads the custom format, processes the source, and writes the result to the selected device.

`TeXEngine` is Aspose.TeX's core processor that parses the TeX source, applies the custom format, and streams the rendered pages to the device you specify.

```csharp
    new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
        "Congratulations! You have successfully typeset this text with your own TeX format!\\end")),
        new XpsDevice(), options).Run();
```

## Step 4: polish the terminal output

Adding a blank line after the job finishes makes console logs easier to read, especially when you chain multiple conversions in a script.

`Console.WriteLine()` writes a line of text to the standard output stream. It is used here purely for visual separation; it does not affect the generated document.

```csharp
    options.TerminalOut.Writer.WriteLine();
}
// ExEnd:TypesetWithCustomTeXFormat
```

Congratulations! You have now **created a custom tex format** and used it for **tex document generation** in .NET. You can swap the `XpsDevice` for `PdfDevice`, `PngDevice`, or any other supported device to suit your delivery needs.

## Common issues and solutions

| Issue | Reason | Fix |
|-------|--------|-----|
| *“Format file not found”* | Wrong path in `FormatProvider` | Verify that `"Your Output Directory"` contains `customtex.fmt` and that the path is absolute or correctly relative to the executable. |
| *“Cannot find input file”* | `InputWorkingDirectory` points to the wrong folder | Ensure `"Your Input Directory"` contains the TeX source file or that you are passing the source as a stream (as in the example). |
| *Terminal output garbled* | Encoding mismatch | Use `Encoding.UTF8` if your TeX source contains non‑ASCII characters. |
| *XPS file is empty* | Job did not run due to earlier exception | Check the console for error messages; they often indicate missing packages or syntax errors in the TeX string. |

## Frequently asked questions

**Q1: Can I use Aspose.TeX for .NET with other Aspose libraries?**  
A: Yes, Aspose.TeX integrates smoothly with Aspose.PDF, Aspose.Words, and other Aspose products for end‑to‑end document pipelines.

**Q2: Is there a free trial available for Aspose.TeX for .NET?**  
A: Yes, you can download a trial from the **Aspose.TeX free trial download page** (https://releases.aspose.com/tex/net/).

**Q3: How can I get support for Aspose.TeX for .NET?**  
A: Visit the [Aspose.TeX forum](https://forum.aspose.com/c/tex/47) for community help or explore premium options on the **premium support purchase page** (https://purchase.aspose.com/buy).

**Q4: Are temporary licenses available for Aspose.TeX for .NET?**  
A: Yes, request one on the **temporary license request page** (https://purchase.aspose.com/temporary-license/).

**Q5: Where can I find the official API reference?**  
A: The comprehensive documentation is hosted on the **API reference documentation** (https://reference.aspose.com/tex/net/).

### Additional Q&A

**Q: Can I output PDF instead of XPS?**  
A: Absolutely. Replace `new XpsDevice()` with `new PdfDevice()` and adjust the output path accordingly.

**Q: Do I need to re‑compile the format file after every change?**  
A: Yes. Any modification to macros or engine settings requires re‑running `tex -ini` to generate a fresh `.fmt` file.

## Conclusion

Aspose.TeX for .NET delivers a **robust, high‑performance solution for tex document generation**, letting you **create custom tex format**, set the **tex input directory**, and output to any supported device. Incorporate the steps above into your CI/CD pipeline, automate large‑scale report generation, or build a custom publishing engine that meets your organization’s branding standards.

---

**Last Updated:** 2026-10-19  
**Tested With:** Aspose.TeX 24.11 for .NET  
**Author:** Aspose

## Related Tutorials

- [Get TeX File Stream (C#) Using Aspose.TeX API Required Input Directory](/tex/net/advanced-io/required-input-directory-csharp/)
- [How to Create PDF with Aspose.TeX for .NET – Step by Step](/tex/net/pdf-output/)
- [How to create XPS document .NET – Convert TeX to XPS Output with Aspose.TeX for .NET](/tex/net/xps-output/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}