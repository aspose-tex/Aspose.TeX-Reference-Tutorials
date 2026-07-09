---
title: How to create custom tex format in .NET using Aspose.TeX
linktitle: Creating Custom TeX Formats in .NET
second_title: Aspose.TeX .NET API
description: Learn how to create custom tex format in .NET with Aspose.TeX and set tex input directory for flexible document generation. This step‑by‑step guide shows you how to configure the format provider, set tex input directory, and generate XPS output.
weight: 10
url: /net/custom-tex-formats/create-custom-tex-formats/
date: 2026-03-26
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create custom tex format in .NET using Aspose.TeX

In the dynamic world of .NET development, **creating custom tex format** files gives you fine‑grained control over how documents are typeset. With Aspose.TeX for .NET you can tailor the TeX engine, point it at a specific input folder, and produce professional‑looking XPS output—all from a few lines of C# code.

## Quick Answers
- **What does “create custom tex format” mean?** It means defining your own TeX engine configuration and format files to control the typesetting process.  
- **Which library do I need?** Aspose.TeX for .NET.  
- **Do I have to set a tex input directory?** Yes – you specify it with `InputFileSystemDirectory`.  
- **What output can I generate?** Any device supported by Aspose.TeX, e.g., XPS, PDF, or PNG.  
- **Is a license required for production?** A valid Aspose.TeX license is required for commercial use.

## What is a custom TeX format?
A custom TeX format is a pre‑compiled set of macros and engine settings that the TeX processor uses to interpret your source files. By creating one, you can embed company branding, enforce document standards, or speed up compilation for repetitive tasks.

## Why set a tex input directory?
Setting the **tex input directory** tells the engine where to look for auxiliary files, custom fonts, or additional style files. This keeps your project organized and prevents “file not found” errors during compilation.

## Prerequisites

Before diving into the customization journey, make sure you have:

1. **Aspose.TeX for .NET** – download it from the [Aspose.TeX website](https://releases.aspose.com/tex/net/).  
2. A **.NET development environment** (Visual Studio, VS Code, or the .NET CLI).  
3. (Optional) A valid **Aspose.TeX license** if you plan to run the code in production.

## Import Namespaces

First, import the namespaces that give you access to the Aspose.TeX API. This step ensures that the classes we’ll use are recognized by the compiler.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using Aspose.TeX.ResourceProviders;
using System.IO;
using System.Text;
```

## Step 1: Create the Format Provider

The `FormatProvider` points the engine to the folder that contains your custom format file (`customtex.fmt`). Replace `"Your Output Directory"` with the path where you stored the compiled format.

```csharp
using (FormatProvider formatProvider =
    new FormatProvider(new InputFileSystemDirectory("Your Output Directory"), "customtex"))
{
```

## Step 2: Configure Conversion Options (and set tex input directory)

Here we build the `TeXOptions` object. Notice the `InputWorkingDirectory` – this is where we **set tex input directory** so the engine can locate any supporting files.

```csharp
    TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX(formatProvider));
    options.JobName = "typeset-with-custom-format";
    options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
    options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

## Step 3: Run the Job

Now we feed a simple TeX string to the engine, choose an output device (XPS in this example), and execute the job.

```csharp
    new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
        "Congratulations! You have successfully typeset this text with your own TeX format!\\end")),
        new XpsDevice(), options).Run();
```

## Step 4: Polish the Terminal Output

Adding a blank line makes the console output easier to read, especially when you run multiple jobs in a batch.

```csharp
    options.TerminalOut.Writer.WriteLine();
}
// ExEnd:TypesetWithCustomTeXFormat
```

Congratulations! You've now **created a custom tex format** and successfully used it to typeset a document in .NET.

## Common Issues and Solutions

| Issue | Reason | Fix |
|-------|--------|-----|
| *“Format file not found”* | Wrong path in `FormatProvider` | Verify that `"Your Output Directory"` contains `customtex.fmt` and that the path is absolute or correctly relative to the executable. |
| *“Cannot find input file”* | `InputWorkingDirectory` points to the wrong folder | Ensure `"Your Input Directory"` contains the TeX source file or that you are passing the source as a stream (as in the example). |
| *Terminal output garbled* | Encoding mismatch | Use `Encoding.UTF8` if your TeX source contains non‑ASCII characters. |
| *XPS file is empty* | Job did not run due to earlier exception | Check the console for error messages; they often indicate missing packages or syntax errors in the TeX string. |

## Frequently Asked Questions

### Q1: Can I use Aspose.TeX for .NET with other document processing libraries?
A1: Yes, Aspose.TeX is designed to integrate seamlessly with other Aspose document processing libraries for comprehensive document handling.

### Q2: Is there a free trial available for Aspose.TeX for .NET?
A2: Yes, you can access the free trial [here](https://releases.aspose.com/).

### Q3: How can I get support for Aspose.TeX for .NET?
A3: Visit the [Aspose.TeX forum](https://forum.aspose.com/c/tex/47) for community support or explore premium support options [here](https://purchase.aspose.com/buy).

### Q4: Are temporary licenses available for Aspose.TeX for .NET?
A4: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).

### Q5: Where can I find the documentation for Aspose.TeX for .NET?
A5: Refer to the comprehensive documentation [here](https://reference.aspose.com/tex/net/).

**Additional Q&A**

**Q: Can I output PDF instead of XPS?**  
A: Absolutely. Replace `new XpsDevice()` with `new PdfDevice()` and adjust the output directory accordingly.

**Q: Do I need to re‑compile the format file after every change?**  
A: Yes. Any change to macros or engine settings requires re‑running `tex -ini` to generate a new `.fmt` file.

## Conclusion

In conclusion, Aspose.TeX for .NET provides a robust solution for **create custom tex format** scenarios, giving developers unprecedented control over document typesetting. Experiment with different configurations, set the appropriate tex input directory, and integrate the workflow into your larger .NET applications for automated, high‑quality document generation.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-26  
**Tested With:** Aspose.TeX 24.11 for .NET  
**Author:** Aspose