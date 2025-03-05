---
title: Stream Input, Image Output, and Terminal Input in Java
linktitle: Stream Input, Image Output, and Terminal Input in Java
second_title: Aspose.TeX Java API
description: Learn stream input, image output, and terminal input in Java using Aspose.TeX. A comprehensive tutorial for seamless integration.
type: docs
weight: 11
url: /content/java/advanced-io/stream-input-image-output/
---
## Introduction

Aspose.TeX for Java is a powerful library that allows developers to work with TeX files, facilitating the creation and manipulation of high-quality documents. In this tutorial, we'll explore the process of taking stream input, generating image output, and handling terminal input in Java using Aspose.TeX.

## Prerequisites

Before diving into the tutorial, make sure you have the following prerequisites:

- Basic understanding of Java programming.
- Java Development Kit (JDK) installed on your machine.
- Familiarity with Aspose.TeX library.
- Aspose.TeX for Java installed. You can download it [here](https://releases.aspose.com/tex/java/).

## Import Packages

Ensure that you have the required packages imported for this tutorial. The following code snippet demonstrates the necessary imports:

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

## Step 1: Set Up Conversion Options

Create TeX conversion options with the default ObjectTeX format upon ObjectTeX engine extension. Specify a job name, input working directory, and output working directory.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("stream-in-image-out");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

## Step 2: Specify Input and Output Terminals

Specify the console as both the input and output terminals.

```java
options.setTerminalIn(new InputConsoleTerminal());
options.setTerminalOut(new OutputConsoleTerminal());
```

## Step 3: Define Saving Options

Define saving options for the output image. In this example, we use PNG format with a resolution of 300 DPI.

```java
PngSaveOptions pngOptions = new PngSaveOptions();
pngOptions.setResolution(300);
options.setSaveOptions(pngOptions);
```

## Step 4: Create Image Device

Create an image device to generate the output image.

```java
ImageDevice device = new ImageDevice();
```

## Step 5: Run the Job

Run the TeX job with the specified input, device, and options.

```java
TeXJob job = new TeXJob(new ByteArrayInputStream(
        "\\hrule height 10pt width 95pt\\vskip10pt\\hrule height 5pt".getBytes("ASCII")),
        device, options);
job.run();
```

## Step 6: Handle Terminal Input

When the console prompts for input, type "ABC," press Enter, then type "\end" and press Enter again.

```java
// For further output to look fine.
options.getTerminalOut().getWriter().newLine();
```

## Step 7: Retrieve Image Output

You can obtain images in the form of an array of byte arrays.

```java
byte[][] result = device.getResult();
```

This completes the step-by-step guide for stream input, image output, and terminal input in Java using Aspose.TeX.

## Conclusion

Aspose.TeX for Java simplifies the process of handling TeX documents, offering robust features for stream input, image output, and terminal interaction. By following this tutorial, you've learned how to seamlessly integrate these functionalities into your Java applications.

## FAQ's

### Q1: Is Aspose.TeX compatible with other Java libraries?

A1: Yes, Aspose.TeX can be seamlessly integrated with other Java libraries to enhance functionality.

### Q2: Can I customize the output image format?

A2: Absolutely! Aspose.TeX provides various options for saving output images, allowing customization based on your preferences.

### Q3: Is there a community forum for Aspose.TeX support?

A3: Yes, you can find support and interact with the community on the [Aspose.TeX forum](https://forum.aspose.com/c/tex/47).

### Q4: How can I obtain a temporary license for Aspose.TeX?

A4: You can get a temporary license from [here](https://purchase.aspose.com/temporary-license/).

### Q5: Are there any additional resources for Aspose.TeX documentation?

A5: Explore the comprehensive [documentation](https://reference.aspose.com/tex/java/) for detailed insights and examples.