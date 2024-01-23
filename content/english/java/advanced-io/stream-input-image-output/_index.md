---
title: Stream Input, Image Output, and Terminal Input in Java
linktitle: Stream Input, Image Output, and Terminal Input in Java
second_title: Aspose.TeX Java API
description: Explore Aspose.TeX for Java a versatile tool for streamlining TeX file processing with ease. Enhance your Java projects effortlessly.
type: docs
weight: 11
url: /java/advanced-io/stream-input-image-output/
---
## Introduction

In the realm of Java development, Aspose.TeX stands out as a powerful tool for processing and converting TeX files. Whether you're dealing with stream inputs, generating images, or taking terminal inputs, Aspose.TeX for Java provides a versatile solution. In this tutorial, we will delve into the intricacies of stream input, image output, and terminal input using Aspose.TeX.

## Prerequisites

Before diving into the tutorial, make sure you have the following prerequisites in place:

- Java Development Kit (JDK) installed on your machine.
- Aspose.TeX for Java library downloaded and set up.
  - [Download Aspose.TeX for Java](https://releases.aspose.com/tex/java/)
- Basic understanding of TeX and Java programming.

## Import Packages

In your Java project, import the necessary Aspose.TeX packages:

```java
package com.aspose.tex.StreamInputImageOutputAndTerminalInput;

import java.io.ByteArrayInputStream;
import java.io.IOException;

import com.aspose.tex.InputConsoleTerminal;
import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputConsoleTerminal;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.ImageDevice;
import com.aspose.tex.rendering.PngSaveOptions;
```

## Step 1: Set Up License and Options

```java
public static void main(String[] args) throws IOException {
    Utils.setLicense();

    TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
    options.setJobName("stream-in-image-out");
    options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
    options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
    options.setTerminalIn(new InputConsoleTerminal());
    options.setTerminalOut(new OutputConsoleTerminal());

    PngSaveOptions pngOptions = new PngSaveOptions();
    pngOptions.setResolution(300);
    options.setSaveOptions(pngOptions);
    ImageDevice device = new ImageDevice();
```

## Step 2: Create TeXJob and Run

```java
    TeXJob job = new TeXJob(new ByteArrayInputStream(
            "\\hrule height 10pt width 95pt\\vskip10pt\\hrule height 5pt".getBytes("ASCII")),
            device, options);
    job.run();
```

## Step 3: Input from Console

```java
    // When the console prompts the input, type "ABC", press Enter, then type "\end" and press Enter again.
    options.getTerminalOut().getWriter().newLine();
```

## Step 4: Obtain Image Result

```java
    byte[][] result = device.getResult();
}
```

## Conclusion

Aspose.TeX for Java streamlines TeX file processing, providing an efficient solution for stream input, image output, and terminal input. By following the steps outlined in this tutorial, you can harness the full potential of Aspose.TeX in your Java projects.

## FAQ's

### Q1: Can I use Aspose.TeX for Java with other Java libraries?

A1: Yes, Aspose.TeX seamlessly integrates with other Java libraries to enhance functionality.

### Q2: Is there a trial version available?

A2: Yes, you can explore Aspose.TeX for Java by obtaining a [free trial](https://releases.aspose.com/).

### Q3: How can I get support for Aspose.TeX?

A3: Visit the [Aspose.TeX forum](https://forum.aspose.com/c/tex/47) for community support and assistance.

### Q4: Where can I find detailed documentation?

A4: Refer to the [documentation](https://reference.aspose.com/tex/java/) for comprehensive guidance.

### Q5: How do I purchase a license for Aspose.TeX for Java?

A5: You can acquire a license from the [purchase page](https://purchase.aspose.com/buy).
