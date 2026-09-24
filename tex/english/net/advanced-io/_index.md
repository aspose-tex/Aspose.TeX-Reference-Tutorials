---
date: 2026-09-24
description: Learn how to configure TeX input directory, streams, images, and terminal
  input using Aspose.TeX for .NET in C#.
images:
- /net/advanced-io/og-image.png
keywords:
- configure tex input directory
- add image stream tex
- add images from stream
lastmod: 2026-09-24
linktitle: Advanced Aspose.TeX Input and Output
og_description: Configure TeX input directory, add image streams, and handle terminal
  input with Aspose.TeX for .NET in C#. Learn step‑by‑step.
og_image_alt: Guide showing how to configure TeX input directory and streams in Aspose.TeX
  for .NET
og_title: Configure TeX input directory – Advanced Aspose.TeX guide
schemas:
- author: Aspose
  dateModified: '2026-09-24'
  description: Learn how to configure TeX input directory, streams, images, and terminal
    input using Aspose.TeX for .NET in C#.
  headline: Configure TeX input directory – Advanced Aspose.TeX Input and Output
  type: TechArticle
- description: Learn how to configure TeX input directory, streams, images, and terminal
    input using Aspose.TeX for .NET in C#.
  name: Configure TeX input directory – Advanced Aspose.TeX Input and Output
  steps:
  - name: instantiate TeXInputOptions
    text: Assign the base folder that holds the primary TeX source.
  - name: add extra search paths
    text: If your project stores figures in a separate folder (e.g., *Images*), call
      `AddSearchPath` to include it.
  - name: hand the options to the processor
    text: Create a `TeXProcessor`, provide the configured options, and invoke `Process`
      or `Render`.
  type: HowTo
- questions:
  - answer: Yes—you can create a new `TeXInputOptions` instance with a different `BaseFolder`
      and pass it to a fresh `TeXProcessor` whenever you need to reconfigure.
    question: Can I change the input directory at runtime?
  - answer: Retrieve the image as a `byte[]`, wrap it in a `MemoryStream`, and call
      `TeXInputOptions.AddImage("image.png", stream)`. The name must match the reference
      in your `.tex` file.
    question: How do I add images that are stored in a database?
  - answer: Absolutely. Convert the incoming string to a `MemoryStream`, set it as
      the source for `TeXProcessor`, and render directly to your desired output format.
    question: Is it possible to process LaTeX code received from a web API without
      saving a file?
  - answer: Dispose of any streams you create, and for large workloads invoke `TeXProcessor.Cleanup()`
      to free native resources.
    question: Do I need to call any cleanup methods after processing?
  - answer: The two tutorial links above contain full code samples that demonstrate
      each scenario in detail, including error handling and performance tips.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.TeX .NET API
tags:
- Aspose.TeX
- input directory
- C# document processing
title: Configure TeX input directory – Advanced Aspose.TeX Input and Output
url: /net/advanced-io/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configure TeX input directory in Aspose.TeX for .NET

Aspose.TeX for .NET lets you embed full‑featured TeX processing directly into your C# applications. In this tutorial you’ll learn how to **configure TeX input directory**, feed LaTeX content from streams, and add images without touching the file system. If you need precise control over where the engine looks for `.tex` files and resources, you’re in the right place.

## Quick answers
- **What does “configure tex input directory” mean?**  
  It tells Aspose.TeX where to find the main `.tex` file, auxiliary files, and graphics.
- **Which class defines the input paths?**  
  `TeXInputOptions` stores the base folder and any additional search locations.
- **Can I load an image from a memory stream?**  
  Yes—use `TeXInputOptions.AddImage` with a `Stream` instance.
- **Is it possible to compile LaTeX code supplied at runtime?**  
  Absolutely—pass a `MemoryStream` containing the source text to the processor.
- **Do I need a license for production use?**  
  A valid Aspose.TeX license is required for non‑evaluation deployments.

## What is TeXInputOptions?
`TeXInputOptions` is the configuration object that defines the base folder and extra search paths for TeX resources. Setting it up correctly eliminates “file not found” errors and lets you keep assets organized.

## How to configure tex input directory?
`TeXInputOptions` is a configuration object that specifies the base folder and additional search paths for TeX resources. Load your main document and tell the processor where to look for everything in just a few lines. This direct answer explains the essential steps before any additional detail.

Create a `TeXInputOptions` instance, set `BaseFolder` to the folder that contains your primary `.tex` file, add any sub‑folders that hold images or auxiliary files, and pass the options to `TeXProcessor`. The engine will then resolve all relative references automatically.

### Step 1: instantiate TeXInputOptions
Assign the base folder that holds the primary TeX source.

### Step 2: add extra search paths
If your project stores figures in a separate folder (e.g., *Images*), call `AddSearchPath` to include it.

### Step 3: hand the options to the processor
Create a `TeXProcessor`, provide the configured options, and invoke `Process` or `Render`.

## How to add images with Aspose.TeX
Images referenced in a TeX file can be supplied either through a folder or directly from a stream. Supplying a stream is useful when images are stored in a database or generated on the fly. `AddImage(string name, Stream data)` registers an image stream with the given filename for use in the TeX document. This method lets you avoid temporary files and speeds up processing.

## How to process streams in Aspose.TeX
When your LaTeX source is generated dynamically—perhaps from user input or a web service—you can feed it straight to the processor without writing a file. `TeXProcessor` processes TeX content and can accept a `MemoryStream` containing the source LaTeX code. Wrap the LaTeX string in a `MemoryStream`, set it as the source stream in `TeXProcessor`, and run the conversion. This technique works equally well for cloud‑native services where disk I/O is expensive.

## Why use Aspose.TeX for advanced I/O?
Aspose.TeX supports **30+ input and output formats** (including PDF, PNG, SVG) and can render multi‑hundred‑page documents without loading the entire file into memory. Its stream‑first design reduces I/O overhead by up to 40 % compared with file‑based workflows, making it ideal for high‑throughput server applications.

## Prerequisites
- .NET 6.0 or later (the library also works with .NET Core 3.1+ and .NET Framework 4.6.1+)
- Aspose.TeX for .NET NuGet package (version 24.11 or newer)
- A valid Aspose.TeX license for production use

## Explore Aspose.TeX: a gateway to advanced document processing
To see the configuration in action, follow our step‑by‑step guide **[Specify Required Input Directory for Aspose.TeX (C#)](./required-input-directory-csharp/)**. That tutorial walks you through creating the `TeXInputOptions` object and rendering a PDF output.  
**[Specify Required Input Directory for Aspose.TeX (C#)](./required-input-directory-csharp/)**

## Mastering streams, images, and terminal input in Aspose.TeX for C#
For a deeper dive into feeding LaTeX from memory, adding images via streams, and using terminal‑style input, check out **[Master Streams, Images, & Terminal Input in Aspose.TeX for C#](./stream-input-image-output-terminal-input-csharp/)**. It shows how to integrate Aspose.TeX into web APIs, background services, and console tools.  
**[Master Streams, Images, & Terminal Input in Aspose.TeX for C#](./stream-input-image-output-terminal-input-csharp/)**

## Common issues and solutions
- **“File not found” errors** – Verify that `BaseFolder` points to the correct directory and that any additional search paths are added before rendering.
- **Images not loading** – Ensure the image name in `AddImage` matches exactly the name used in the TeX source, including file extension.
- **Memory usage spikes** – When processing very large documents, call `TeXProcessor.Cleanup()` after rendering to release unmanaged resources.

## Frequently asked questions

**Q: Can I change the input directory at runtime?**  
A: Yes—you can create a new `TeXInputOptions` instance with a different `BaseFolder` and pass it to a fresh `TeXProcessor` whenever you need to reconfigure.

**Q: How do I add images that are stored in a database?**  
A: Retrieve the image as a `byte[]`, wrap it in a `MemoryStream`, and call `TeXInputOptions.AddImage("image.png", stream)`. The name must match the reference in your `.tex` file.

**Q: Is it possible to process LaTeX code received from a web API without saving a file?**  
A: Absolutely. Convert the incoming string to a `MemoryStream`, set it as the source for `TeXProcessor`, and render directly to your desired output format.

**Q: Do I need to call any cleanup methods after processing?**  
A: Dispose of any streams you create, and for large workloads invoke `TeXProcessor.Cleanup()` to free native resources.

**Q: Where can I find more advanced examples?**  
A: The two tutorial links above contain full code samples that demonstrate each scenario in detail, including error handling and performance tips.

---

**Last Updated:** 2026-09-24  
**Tested With:** Aspose.TeX 24.11 for .NET  
**Author:** Aspose

## Related Tutorials

- [Get TeX File Stream (C#) Using Aspose.TeX API Required Input Directory](/tex/net/advanced-io/required-input-directory-csharp/)
- [Create XPS from TeX with Filesystems – Aspose.TeX for .NET](/tex/net/file-input-output/filesystem-input-xps-output/)
- [Convert LaTeX to PNG Using Aspose.TeX for .NET – Process Filesystem & ZIP Inputs](/tex/net/file-input-output/required-inputs-from-filesystem-and-zip/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}