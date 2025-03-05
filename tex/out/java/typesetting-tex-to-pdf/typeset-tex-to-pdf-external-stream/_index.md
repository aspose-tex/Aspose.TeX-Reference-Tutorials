---
title: Typeset TeX to PDF in Java with External Stream
linktitle: Typeset TeX to PDF in Java with External Stream
second_title: Aspose.TeX Java API
description: Learn how to typeset TeX to PDF in Java using external streams with Aspose.TeX. Follow our step-by-step guide for seamless integration.
type: docs
weight: 10
url: /content/java/typesetting-tex-to-pdf/typeset-tex-to-pdf-external-stream/
---
## Introduction

In the world of Java development, creating PDFs from TeX files is a common requirement. Aspose.TeX for Java simplifies this process, providing an efficient solution for typesetting TeX to PDF. In this tutorial, we will walk you through the steps of typesetting TeX to PDF using external streams. By the end, you'll have a clear understanding of how to implement this process seamlessly in your Java applications.

## Prerequisites

Before diving into the tutorial, make sure you have the following prerequisites in place:

- Aspose.TeX for Java: Ensure that you have the Aspose.TeX library for Java installed. You can download it from the [Aspose.TeX for Java documentation](https://reference.aspose.com/tex/java/).

- Input and Output Directories: Prepare the input and output directories. You can use the provided download link to get the necessary files.

## Import Packages

Start by importing the required packages into your Java project:

```java
package com.aspose.tex.TypesetPdfWrittenToExternalStream;

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

## Step 1: Open Input and Output Streams

Begin by opening streams for the input ZIP archive (acting as the input working directory) and the output ZIP archive (serving as the output working directory). Make sure to replace "Your Input Directory" and "Your Output Directory" with your actual directory paths.

```java
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "typeset-pdf-to-external-stream.zip");
```

## Step 2: Configure TeXOptions

Create the TeXOptions object and configure it according to your requirements. Set the job name, input working directory, output working directory, and other options.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("typeset-pdf-to-external-stream");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
options.setSaveOptions(new PdfSaveOptions());
```

## Step 3: Typeset TeX to PDF

Now, open a stream to write the output PDF to the desired location. You can choose to write it to a local file or directly to the output ZIP archive.

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + "file-name.pdf");
try {
    new TeXJob("hello-world", new PdfDevice(stream), options).run();
} finally {
    stream.close();
}
```

## Step 4: Finalize Output ZIP Archive

Finish the output ZIP archive to complete the typesetting process.

```java
((OutputZipDirectory)options.getOutputWorkingDirectory()).finish();
```

## Conclusion

Congratulations! You've successfully typeset TeX to PDF in Java using external streams with Aspose.TeX. This tutorial provides a robust foundation for incorporating TeX to PDF conversion into your Java applications seamlessly.

## FAQ's

### Q1: Can I customize the output PDF's file name?

A1: Yes, you can modify the `options.setJobName("typeset-pdf-to-external-stream")` to set your desired job name.

### Q2: How do I troubleshoot common issues during typesetting?

A2: Visit the [Aspose.TeX forum](https://forum.aspose.com/c/tex/47) for community support and assistance.

### Q3: Is there a free trial available for Aspose.TeX for Java?

A3: Yes, you can access the free trial [here](https://releases.aspose.com/).

### Q4: Where can I find additional documentation and examples?

A4: Explore the comprehensive [Aspose.TeX documentation](https://reference.aspose.com/tex/java/) for detailed information.

### Q5: Can I obtain a temporary license for Aspose.TeX?

A5: Yes, you can request a temporary license [here](https://purchase.aspose.com/temporary-license/).