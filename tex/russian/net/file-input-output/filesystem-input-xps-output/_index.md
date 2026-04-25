---
date: 2026-03-26
description: Узнайте, как создавать XPS из TeX с помощью Aspose.TeX для .NET, управлять
  вводом/выводом файловой системы и генерировать высококачественные XPS‑документы.
linktitle: Create XPS from TeX with Filesystems – Aspose.TeX for .NET
second_title: Aspose.TeX .NET API
title: Создание XPS из TeX с файловыми системами – Aspose.TeX для .NET
url: /ru/net/file-input-output/filesystem-input-xps-output/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание XPS из TeX с файловой системой – Aspose.TeX для .NET

## Introduction

Welcome! In this tutorial you’ll learn **how to create XPS from TeX** while working with filesystem input and output using Aspose.TeX for .NET. Whether you’re building a batch processor, a web service, or a desktop utility, the steps below will guide you through configuring the engine, pointing it at your files, and producing XPS documents that look exactly like the original LaTeX source.

We’ll break the process into clear, numbered steps, explain the “why” behind each line of code, and give you practical tips you can apply right away.

## Quick Answers
- **What does “create XPS from TeX” mean?** It refers to configuring an Aspose.TeX job that reads TeX files and writes the result as an XPS document.  
- **Do I need a license?** A temporary license is available for testing; a full license is required for production.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Can I change the output format?** Yes – replace `XpsDevice` with another device (PDF, PNG, etc.).  
- **Is console output required?** No – you can use a memory terminal for silent execution.

## How to create XPS from TeX using Aspose.TeX

Creating a TeX job that outputs XPS means initializing the Aspose.TeX engine, telling it where to read source files, and directing the rendered pages into an XPS package. XPS (XML Paper Specification) is a fixed‑layout format that preserves typography and vector graphics, making it ideal for printing or further conversion.

## What is “create tex job xps”?

Creating a TeX job that outputs XPS means initializing the Aspose.TeX engine, telling it where to read source files, and directing the rendered pages into an XPS package. XPS (XML Paper Specification) is a fixed‑layout format that preserves typography and vector graphics, making it ideal for printing or further conversion.

## Why use Aspose.TeX for XPS output?

- **High fidelity:** The engine reproduces LaTeX layout accurately in XPS.  
- **No external dependencies:** Pure .NET library, no need for native LaTeX installations.  
- **Flexible I/O:** Works with filesystem directories, memory streams, or custom providers.  
- **Scalable:** Suitable for single‑file conversions or bulk processing pipelines.

## Prerequisites

Before we dive in, ensure you have the following:

- **Aspose.TeX for .NET** – download the latest version from the [Aspose website](https://releases.aspose.com/tex/net/).  
- **.NET development environment** – Visual Studio, Rider, or VS Code with the .NET SDK.  
- **Input & output folders** – create two directories on your machine (e.g., `C:\TeX\Input` and `C:\TeX\Output`).  
- **License (optional for testing)** – you can obtain a temporary license from the Aspose portal.

## Import Namespaces

First, bring the required namespaces into scope so you can access filesystem helpers and the XPS device.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

These namespaces expose `InputFileSystemDirectory`, `OutputFileSystemDirectory`, and `XpsDevice`, which are essential for the **create XPS from TeX** workflow.

## Step 1: Create Conversion Options

We start by building a `TeXOptions` object that tells the engine to use the ObjectTeX configuration (the default for most LaTeX sources).

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

> **Pro tip:** `ConsoleAppOptions` sets sensible defaults for console‑style applications, but you can customize the options later if needed.

## Step 2: Specify Input and Output Directories

Point the engine at the folders you prepared earlier. Replace the placeholder strings with the actual paths on your machine.

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Now the TeX job knows where to find `.tex` files and where to drop the generated XPS files.

## Step 3: Choose an Output Terminal

The terminal controls where status messages are written. For quick debugging we’ll stick with the console, but you can switch to a memory terminal for silent runs.

```csharp
options.TerminalOut = new OutputConsoleTerminal(); // Default value. Arbitrary assignment.
```

> **Why this matters:** Using a console terminal gives you immediate feedback about compilation warnings or errors, which speeds up troubleshooting.

## Step 4: Run the TeX Job

Create a `TeXJob` instance, give it a friendly name, attach the `XpsDevice`, and execute it.

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

When `Run()` completes, you’ll find an `hello-world.xps` file in the output directory.

## Step 5: Fine‑Tune the Console Output

Adding a blank line after the job finishes makes the console log easier to read, especially when you run multiple jobs in a batch.

```csharp
options.TerminalOut.Writer.WriteLine();
```

## Common Use Cases

| Scenario | Why XPS? | How the snippet helps |
|----------|----------|-----------------------|
| **Batch conversion of academic papers** | Preserve exact layout for archival printing. | The filesystem‑based approach lets you point at a folder of `.tex` files and output a matching set of XPS files. |
| **Web service that renders LaTeX on‑the‑fly** | XPS can be streamed directly to browsers that support it. | By swapping `XpsDevice` with a memory stream you can return the document without touching the disk. |
| **Desktop publishing tool** | Need a fixed‑layout preview before PDF conversion. | The same job can be chained to a PDF device later for final distribution. |

## Common Issues and Solutions

| Issue | Cause | Fix |
|-------|-------|-----|
| **XPS file is empty** | Output directory path is incorrect or not writable. | Verify the path passed to `OutputFileSystemDirectory` and ensure the process has write permissions. |
| **Compilation errors** | LaTeX source uses packages not bundled with ObjectTeX. | Switch to a full TeX engine configuration (`TeXConfig.FullTeX()`) or add missing package files to the input directory. |
| **Console hangs** | Terminal waiting for input due to interactive prompts. | Use `OutputMemoryTerminal` to suppress interactive prompts in automated scripts. |

## Frequently Asked Questions

**Q1: Can I use a different output format instead of XPS?**  
A1: Yes, Aspose.TeX supports PDF, PNG, SVG, and other formats. Replace `new XpsDevice()` with the appropriate device class (e.g., `new PdfDevice()`).

**Q2: Is a temporary license available for testing purposes?**  
A2: Yes, you can obtain a temporary license for testing from [this link](https://purchase.aspose.com/temporary-license/).

**Q3: Where can I find additional documentation?**  
A3: Refer to the [Aspose.TeX for .NET documentation](https://reference.aspose.com/tex/net/) for detailed information.

**Q4: How can I get community support or ask questions?**  
A4: Visit the [Aspose.TeX forum](https://forum.aspose.com/c/tex/47) for community support and discussions.

**Q5: Are there any sample projects available?**  
A5: Explore the Aspose.TeX GitHub repository for sample projects and code snippets.

## Conclusion

By following the steps above, you now know how to **create XPS from TeX** using Aspose.TeX for .NET, manage your input and output folders, and fine‑tune the process for both development and production scenarios. Feel free to experiment with other output devices, integrate this logic into larger workflows, or automate batch conversions.

---

**Last Updated:** 2026-03-26  
**Tested With:** Aspose.TeX 24.11 for .NET (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}