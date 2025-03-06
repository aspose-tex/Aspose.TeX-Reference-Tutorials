---
title: Override Job Name and Write Terminal Output in Java
linktitle: Override Job Name and Write Terminal Output in Java
second_title: Aspose.TeX Java API
description: Explore the step-by-step guide on overriding job names and writing terminal output using Aspose.TeX for Java. Enhance your document processing with powerful customization options.
weight: 10
url: /java/customizing-output/override-job-name-disk/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Override Job Name and Write Terminal Output in Java

## Introduction

Aspose.TeX for Java provides powerful features for working with TeX files, allowing developers to manipulate and customize the TeX document processing. In this tutorial, we will guide you through the process of overriding the job name and writing terminal output to the file system using Aspose.TeX in Java.

## Prerequisites

Before we dive into the tutorial, make sure you have the following prerequisites in place:

- A working knowledge of Java programming.
- Aspose.TeX for Java installed. You can download it from the [Aspose.TeX Java documentation](https://reference.aspose.com/tex/java/).

## Import Packages

To get started, import the necessary packages into your Java project. In your Java file, include the following imports:

```java
package com.aspose.tex.OverridenJobNameAndTerminalOutputWrittenToDisk;

import java.io.IOException;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

## Override Job Name and Write Terminal Output

### Step 1: Create Conversion Options

Begin by creating conversion options for the default ObjectTeX format upon ObjectTeX engine extension. Use the following code snippet:

```java
// ExStart:OverrideJobName-WriteTerminalOutputToFileSystem
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

### Step 2: Specify Job Name and Working Directories

Specify a job name, input working directory, and output working directory. If the job name is not specified, the first argument of the TeXJob constructor will be taken as the job name. Use the following code snippet:

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### Step 3: Write Terminal Output to File System

Specify that the terminal output must be written to a file in the output working directory. The file name will be `<job_name>.trm`. Add the following code:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### Step 4: Run the Job

Run the TeX job using the specified options and job name. Here's how you can do it:

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
// ExEnd:OverrideJobName-WriteTerminalOutputToFileSystem
```

Congratulations! You have successfully overridden the job name and written terminal output to the file system using Aspose.TeX in Java.

## Conclusion

In this tutorial, we explored how to utilize Aspose.TeX for Java to override the job name and capture terminal output. These features empower developers to have fine-grained control over TeX document processing, enhancing customization and flexibility.

## FAQ's

### Q1: Can I use Aspose.TeX for Java with other Java libraries?

A1: Yes, Aspose.TeX for Java is designed to seamlessly integrate with other Java libraries to enhance your document processing capabilities.

### Q2: Where can I find support for Aspose.TeX for Java?

A2: Visit the [Aspose.TeX forum](https://forum.aspose.com/c/tex/47) for community support and assistance with any issues you may encounter.

### Q3: Is there a free trial available for Aspose.TeX for Java?

A3: Yes, you can access the free trial version of Aspose.TeX for Java [here](https://releases.aspose.com/).

### Q4: How can I obtain a temporary license for Aspose.TeX for Java?

A4: Follow this [link](https://purchase.aspose.com/temporary-license/) to obtain a temporary license for testing and evaluation purposes.

### Q5: Where can I purchase Aspose.TeX for Java?

A5: Visit the [purchase page](https://purchase.aspose.com/buy) to acquire a license for Aspose.TeX for Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
