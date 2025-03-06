---
title: Master Streams, Images, & Terminal Input in Aspose.TeX for C#
linktitle: Master Streams, Images, & Terminal Input in Aspose.TeX for C#
second_title: Aspose.TeX .NET API
description: Explore the power of Aspose.TeX for C# master streams, images, and terminal input effortlessly. Download now for seamless document processing.
weight: 11
url: /net/advanced-io/stream-input-image-output-terminal-input-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Master Streams, Images, & Terminal Input in Aspose.TeX for C#

## Introduction

Welcome to this comprehensive tutorial on mastering streams, images, and terminal input in Aspose.TeX for C#. Aspose.TeX is a powerful library that allows developers to work with TeX files, providing a wide range of features for document manipulation and conversion. In this guide, we will delve into handling streams, managing images, and capturing terminal input using Aspose.TeX for C#. By the end of this tutorial, you'll be equipped with the knowledge to efficiently work with these essential aspects of document processing.

## Prerequisites

Before we dive into the examples, ensure you have the following prerequisites:

- Basic knowledge of C# programming language.
- Aspose.TeX for .NET library installed. You can download it [here](https://releases.aspose.com/tex/net/).
- A development environment set up for C#.

## Import Namespaces

In your C# project, make sure to include the necessary namespaces to access Aspose.TeX functionalities. Add the following lines at the beginning of your code:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Image;
using System.IO;
using System.Text;
```

## Step 1: Set Up Conversion Options

```csharp
// ExStart:TakeMainInputFromStream-AuxFromFileSystem-TakeTerminalInputFromConsole-AlternativeImagesStorage
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
options.JobName = "stream-in-image-out";
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
options.TerminalIn = new InputConsoleTerminal();
options.TerminalOut = new OutputConsoleTerminal();
options.SaveOptions = new PngSaveOptions() { Resolution = 300 };
```

## Step 2: Create Image Device and Run the Job

```csharp
ImageDevice device = new ImageDevice();
TeXJob job = new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
    "\\hrule height 10pt width 95pt\\vskip10pt\\hrule height 5pt")),
    device, options);
job.Run();
```

## Step 3: Provide Input in the Console

When prompted in the console, type "ABC," press Enter, then type "\end," and press Enter again.

## Step 4: Fine-Tune Output

```csharp
options.TerminalOut.Writer.WriteLine();
byte[][] result = device.Result;
// ExEnd:TakeMainInputFromStream-AuxFromFileSystem-TakeTerminalInputFromConsole-AlternativeImagesStorage
```

Congratulations! You've successfully processed TeX input from streams, managed images, and captured terminal input using Aspose.TeX for C#. These skills are invaluable for various document processing scenarios.

## Conclusion

In this tutorial, we covered essential aspects of working with streams, images, and terminal input in Aspose.TeX for C#. You learned how to set up conversion options, create image devices, run jobs, and fine-tune output. With this knowledge, you're well-equipped to handle diverse document processing tasks efficiently.

## FAQ's

### Q1: Can I use Aspose.TeX for .NET in a non-console application?

A1: Absolutely! Aspose.TeX can be seamlessly integrated into various types of applications, including desktop and web applications.

### Q2: How can I customize the output image resolution?

A2: In the provided example, the resolution is set in the `PngSaveOptions` object. You can adjust the `Resolution` property based on your requirements.

### Q3: Is there a trial version available?

A3: Yes, you can explore Aspose.TeX with a free trial available [here](https://releases.aspose.com/).

### Q4: Where can I find additional support and assistance?

A4: Visit the Aspose.TeX forum [here](https://forum.aspose.com/c/tex/47) for community support and discussions.

### Q5: How can I obtain a temporary license for Aspose.TeX?

A5: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
