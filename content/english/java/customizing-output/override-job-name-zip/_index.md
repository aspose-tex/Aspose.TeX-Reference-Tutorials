---
title: Override Job Name and Write Terminal Output to Zip in Java
linktitle: Override Job Name and Write Terminal Output to Zip in Java
second_title: Aspose.TeX Java API
description: Learn how to override job names and write terminal output to ZIP in Java with Aspose.TeX. A comprehensive tutorial for Java developers.
type: docs
weight: 11
url: /java/customizing-output/override-job-name-zip/
---
## Introduction

In the world of Java development, Aspose.TeX stands out as a powerful tool for handling TeX file formats. In this tutorial, we'll delve into a specific scenario – overriding job names and writing terminal output to a zip file. This step-by-step guide will walk you through the process using Aspose.TeX for Java.

## Prerequisites

Before we embark on this tutorial, make sure you have the following prerequisites in place:
- Basic knowledge of Java programming.
- Installed Aspose.TeX for Java. If not, you can download it from the [Aspose website](https://releases.aspose.com/tex/java/).
- An understanding of how to set up a Java development environment.

## Import Packages

Begin by importing the necessary packages into your Java project. This ensures that you have access to the Aspose.TeX functionalities required for the task.

```java
package com.aspose.tex.OverridenJobNameAndTerminalOutputWrittenToZip;

import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.io.OutputStream;

import com.aspose.tex.InputZipDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.OutputZipDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.PdfDevice;
import com.aspose.tex.rendering.PdfSaveOptions;

import util.Utils;
```

## Step 1: Open ZIP Archives

Firstly, open a stream on the ZIP archive that will serve as the input working directory. This is the archive from which your data will be processed.

```java
// Open a stream on the input ZIP archive
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
```

## Step 2: Open Output ZIP Archive

Next, open a stream on a ZIP archive that will serve as the output working directory. This is where the terminal output will be written.

```java
// Open a stream on the output ZIP archive
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "terminal-out-to-zip.zip");
```

## Step 3: Set Conversion Options

Create conversion options for the default ObjectTeX format upon ObjectTeX engine extension. Specify a job name and ZIP archive working directories for both input and output.

```java
// Create TeX options for ObjectTeX format
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("terminal-output-to-zip");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
```

## Step 4: Specify Terminal Output

Specify that the terminal output must be written to a file in the output working directory. The file name will be `<job_name>.trm`.

```java
// Specify terminal output settings
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

## Step 5: Define Saving Options and Run the Job

Define saving options, such as PDF save options in this case. Run the TeX job to execute the conversion.

```java
// Define saving options and run the job
options.setSaveOptions(new PdfSaveOptions());
new TeXJob("hello-world", new PdfDevice(), options).run();
```

## Step 6: Finalize Output ZIP Archive

After the job is completed, finalize the output ZIP archive to ensure proper completion.

```java
// Finalize the output ZIP archive
((OutputZipDirectory) options.getOutputWorkingDirectory()).finish();
```

## Conclusion

Congratulations! You've successfully learned how to override job names and write terminal output to a ZIP file in Java using Aspose.TeX. This powerful functionality adds flexibility and efficiency to your Java development projects.

## FAQ's

### Q1: What is Aspose.TeX?

A1: Aspose.TeX is a Java library that allows developers to work with TeX file formats, providing advanced functionalities for document processing.

### Q2: How can I obtain a temporary license for Aspose.TeX?

A2: You can get a temporary license from [this link](https://purchase.aspose.com/temporary-license/).

### Q3: Where can I find Aspose.TeX documentation?

A3: The documentation is available [here](https://reference.aspose.com/tex/java/).

### Q4: Is there a free trial version of Aspose.TeX?

A4: Yes, you can find the free trial version [here](https://releases.aspose.com/).

### Q5: Where can I seek support or ask questions about Aspose.TeX?

A5: Visit the [Aspose.TeX forum](https://forum.aspose.com/c/tex/47) for support and discussions.

