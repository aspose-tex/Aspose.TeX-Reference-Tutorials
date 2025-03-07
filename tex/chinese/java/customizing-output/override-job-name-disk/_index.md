---
title: 覆盖作业名称并用 Java 编写终端输出
linktitle: 覆盖作业名称并用 Java 编写终端输出
second_title: Aspose.TeX Java API
description: 探索有关使用 Aspose.TeX for Java 覆盖作业名称和编写终端输出的分步指南。通过强大的自定义选项增强您的文档处理。
weight: 10
url: /zh/java/customizing-output/override-job-name-disk/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 覆盖作业名称并用 Java 编写终端输出

## 介绍

Aspose.TeX for Java 提供了处理 TeX 文件的强大功能，允许开发人员操作和自定义 TeX 文档处理。在本教程中，我们将指导您完成使用 Java 中的 Aspose.TeX 覆盖作业名称并将终端输出写入文件系统的过程。

## 先决条件

在我们深入学习本教程之前，请确保您具备以下先决条件：

- Java 编程的实用知识。
-  Aspose.TeX for Java 已安装。您可以从[Aspose.TeX Java 文档](https://reference.aspose.com/tex/java/).

## 导入包

首先，将必要的包导入到您的 Java 项目中。在您的 Java 文件中，包含以下导入：

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

## 覆盖作业名称并写入终端输出

### 第 1 步：创建转换选项

首先为 ObjectTeX 引擎扩展上的默认 ObjectTeX 格式创建转换选项。使用以下代码片段：

```java
//ExStart：OverrideJobName-WriteTerminalOutputToFileSystem
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

### 第 2 步：指定作业名称和工作目录

指定作业名称、输入工作目录和输出工作目录。如果未指定作业名称，TeXJob 构造函数的第一个参数将被视为作业名称。使用以下代码片段：

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### 步骤 3：将终端输出写入文件系统

指定终端输出必须写入输出工作目录中的文件。文件名将是`<job_name>.trm`。添加以下代码：

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### 第 4 步：运行作业

使用指定的选项和作业名称运行 TeX 作业。您可以这样做：

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
// ExEnd：OverrideJobName-WriteTerminalOutputToFileSystem
```

恭喜！您已使用 Java 中的 Aspose.TeX 成功覆盖作业名称并将终端输出写入文件系统。

## 结论

在本教程中，我们探讨了如何利用 Aspose.TeX for Java 覆盖作业名称并捕获终端输出。这些功能使开发人员能够对 TeX 文档处理进行细粒度控制，从而增强定制性和灵活性。

## 常见问题解答

### Q1：我可以将 Aspose.TeX for Java 与其他 Java 库一起使用吗？

A1：是的，Aspose.TeX for Java 旨在与其他 Java 库无缝集成，以增强您的文档处理能力。

### Q2：哪里可以找到 Aspose.TeX for Java 的支持？

 A2：访问[Aspose.TeX 论坛](https://forum.aspose.com/c/tex/47)对于您可能遇到的任何问题，寻求社区支持和帮助。

### Q3：Aspose.TeX for Java 有免费试用版吗？

 A3：是的，您可以访问 Aspose.TeX for Java 的免费试用版[这里](https://releases.aspose.com/).

### Q4：如何获得 Aspose.TeX for Java 的临时许可证？

 A4：按照这个[关联](https://purchase.aspose.com/temporary-license/)获得用于测试和评估目的的临时许可证。

### Q5: 在哪里可以购买 Aspose.TeX for Java？

 A5：访问[购买页面](https://purchase.aspose.com/buy)获取 Aspose.TeX for Java 的许可证。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
