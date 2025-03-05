---
title: Typeset TeX to XPS in Java with External Stream
linktitle: Typeset TeX to XPS in Java with External Stream
second_title: Aspose.TeX Java API
description: Learn how to typeset TeX to XPS in Java using Aspose.TeX. Explore step-by-step guidance for seamless document processing.
type: docs
weight: 10
url: /java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
---
## Introduction

In the world of Java development, Aspose.TeX stands out as a powerful tool for typesetting TeX documents into various formats, including XPS. If you're looking to enhance your Java application's document processing capabilities, this tutorial is tailored for you. In this step-by-step guide, we'll walk you through the process of typesetting TeX to XPS using Aspose.TeX for Java with an external stream.

## Prerequisites

Before diving into the tutorial, make sure you have the following prerequisites in place:

- Java Development Kit (JDK): Ensure that you have Java installed on your system. You can download it from [here](https://www.oracle.com/java/technologies/javase-downloads.html).

- Aspose.TeX for Java: Download and install Aspose.TeX for Java. You can find the download link [here](https://releases.aspose.com/tex/java/).

## Import Packages

Start by importing the necessary packages to kick off your TeX to XPS conversion journey. Include the following code snippet in your Java project:

```java
package com.aspose.tex.TypesetXpsWrittenToExternalStream;

import java.io.FileOutputStream;
import java.io.IOException;
import java.io.OutputStream;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

## Step 1: Configure Conversion Options

Begin by creating conversion options for the default ObjectTeX format using the following code:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

This sets up the foundation for the typesetting process.

## Step 2: Specify Job Name and Directories

Define a job name and set the input and output working directories:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Ensure you replace placeholders like "Your Input Directory" with your actual directory paths.

## Step 3: Configure Terminal Output

Specify that the terminal output should be written to a file in the output working directory:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

This step ensures detailed logs are captured for debugging.

## Step 4: Open Output Stream

Open a stream to write the typeset XPS document:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

Replace "Your Output Directory" with the appropriate path.

## Step 5: Run the Job

Execute the TeX to XPS conversion job:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

This completes the process, and you'll find your typeset XPS document in the specified output directory.

## Conclusion

Congratulations! You've successfully typeset TeX to XPS in Java using Aspose.TeX. This opens up a world of possibilities for document processing in your Java applications. Experiment with different TeX files and explore the diverse features offered by Aspose.TeX.

## FAQ's

### Q1: Can I use Aspose.TeX for Java with other document formats?

A1: Aspose.TeX primarily focuses on TeX-related document processing. For other formats, explore Aspose's extensive product range.

### Q2: Is there a trial version available?

A2: Yes, you can experience Aspose.TeX by downloading the free trial [here](https://releases.aspose.com/).

### Q3: Where can I find comprehensive documentation?

A3: Refer to the documentation [here](https://reference.aspose.com/tex/java/) for detailed information and examples.

### Q4: How do I get support or seek assistance?

A4: Visit the Aspose.TeX forum [here](https://forum.aspose.com/c/tex/47) for community support and discussions.

### Q5: Can I obtain a temporary license for testing purposes?

A5: Yes, you can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
