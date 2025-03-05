---
title: Override Job Name and Write Terminal Output to Disk (C#)
linktitle: Override Job Name and Write Terminal Output to Disk (C#)
second_title: Aspose.TeX .NET API
description: Explore how to use Aspose.TeX for .NET to override job names and capture terminal output. Follow our comprehensive guide for seamless TeX file management.
type: docs
weight: 10
url: /content/net/job-output/override-job-name-disk-output-csharp/
---
## Introduction

Welcome to this step-by-step guide on using Aspose.TeX for .NET to override job names and write terminal output to disk in the C# programming language. Aspose.TeX for .NET is a powerful library that allows you to seamlessly work with TeX files, and in this tutorial, we will focus on a specific task: overriding job names and capturing terminal output.

## Prerequisites

Before we dive into the tutorial, make sure you have the following prerequisites in place:

- Aspose.TeX for .NET Library: Ensure that you have the Aspose.TeX for .NET library installed. You can download it from the [Aspose.TeX website](https://releases.aspose.com/tex/net/).

- .NET Development Environment: Have a working .NET development environment, including an integrated development environment (IDE) such as Visual Studio.

- Basic C# Knowledge: Familiarize yourself with the basics of the C# programming language.

- Input and Output Directories: Prepare the input and output directories for your TeX files.

## Import Namespaces

In your C# code, make sure to include the necessary namespaces to access the Aspose.TeX functionalities:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

## Step 1: Create Conversion Options

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

Create TeXOptions with ConsoleAppOptions, specifying ObjectTeX as the TeXConfig.

## Step 2: Specify Job Name

```csharp
options.JobName = "overridden-job-name";
```

Specify the job name to override the default name.

## Step 3: Specify Input Working Directory

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

Set the input working directory for your TeX files.

## Step 4: Specify Output Working Directory

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Define the output working directory to save the processed TeX files.

## Step 5: Write Terminal Output to Disk

```csharp
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

Configure the terminal output to be written to a file in the output directory.

## Step 6: Run the Job

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

Create a TeXJob, specifying a job name, output device (XpsDevice), and options. Finally, run the job.

## Conclusion

Congratulations! You've successfully learned how to override job names and write terminal output to disk using Aspose.TeX for .NET in C#. This capability is valuable for managing your TeX processing tasks efficiently.

## FAQ's

### Q1: Can I use Aspose.TeX for .NET with other .NET libraries?

A1: Yes, Aspose.TeX for .NET can be integrated with other .NET libraries seamlessly.

### Q2: Is there a free trial available for Aspose.TeX for .NET?

A2: Yes, you can download a free trial version [here](https://releases.aspose.com/).

### Q3: How can I get support for Aspose.TeX for .NET?

A3: Visit the [Aspose.TeX forum](https://forum.aspose.com/c/tex/47) to get community and support.

### Q4: Are temporary licenses available for Aspose.TeX for .NET?

A4: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).

### Q5: Where can I find the documentation for Aspose.TeX for .NET?

A5: The documentation is available [here](https://reference.aspose.com/tex/net/).