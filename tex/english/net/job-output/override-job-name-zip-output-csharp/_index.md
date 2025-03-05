---
title: Override Job Name and Write Terminal Output to Zip (C#)
linktitle: Override Job Name and Write Terminal Output to Zip (C#)
second_title: Aspose.TeX .NET API
description: Learn how to override job names and write terminal output to a ZIP file using Aspose.TeX for .NET. Step-by-step guide with C# examples.
type: docs
weight: 11
url: /net/job-output/override-job-name-zip-output-csharp/
---
## Introduction

In this tutorial, we will explore how to override the job name and write terminal output to a ZIP file using Aspose.TeX for .NET. Aspose.TeX is a powerful library that allows developers to work with TeX documents in their .NET applications. In this particular example, we will focus on a common task – writing terminal output to a ZIP file with the ability to override the job name.

## Prerequisites

Before we begin, ensure that you have the following prerequisites in place:

- A working knowledge of C#
- Aspose.TeX for .NET installed
- Input ZIP archive for the working directory
- Output ZIP archive for terminal output

## Import Namespaces

Before diving into the code, make sure to include the necessary namespaces in your C# project:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Pdf;
using System.IO;
```

Now, let's break down the example into multiple steps to guide you through the process.

## Step 1: Open Input and Output ZIP Streams

```csharp
using (Stream inZipStream = File.Open(Path.Combine("Your Input Directory", "zip-in.zip"), FileMode.Open))
using (Stream outZipStream = File.Open(Path.Combine("Your Output Directory", "terminal-out-to-zip.zip"), FileMode.Create))
{
    // Code for step 1 goes here
}
```

## Step 2: Set Conversion Options

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
options.JobName = "terminal-output-to-zip";
options.InputWorkingDirectory = new InputZipDirectory(inZipStream, "in");
options.OutputWorkingDirectory = new OutputZipDirectory(outZipStream);
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## Step 3: Define Saving Options

```csharp
options.SaveOptions = new PdfSaveOptions();
```

## Step 4: Run the TeX Job

```csharp
new TeXJob("hello-world", new PdfDevice(), options).Run();
```

## Step 5: Finalize Output ZIP Archive

```csharp
((OutputZipDirectory)options.OutputWorkingDirectory).Finish();
```

## Conclusion

Congratulations! You have successfully learned how to override the job name and write terminal output to a ZIP file using Aspose.TeX for .NET. This technique can be incredibly useful when dealing with TeX documents in your C# applications.

## FAQ's

### Q1: Can I use Aspose.TeX for .NET with other .NET languages like VB.NET?

A1: Yes, Aspose.TeX for .NET is compatible with all .NET languages.

### Q2: Where can I find more documentation for Aspose.TeX for .NET?

A2: Visit the [documentation](https://reference.aspose.com/tex/net/) for detailed information.

### Q3: How can I get a temporary license for Aspose.TeX?

A3: Obtain a [temporary license](https://purchase.aspose.com/temporary-license/) for testing purposes.

### Q4: Is there a community forum for Aspose.TeX support?

A4: Yes, join the [Aspose.TeX forum](https://forum.aspose.com/c/tex/47) for community support.

### Q5: Where can I purchase Aspose.TeX for .NET?

A5: You can buy Aspose.TeX [here](https://purchase.aspose.com/buy).
