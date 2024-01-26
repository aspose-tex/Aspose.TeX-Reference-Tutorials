---
title: 使用外部流在 Java 中将 TeX 排版为 XPS
linktitle: 使用外部流在 Java 中将 TeX 排版为 XPS
second_title: Aspose.TeX Java API
description: 了解如何使用 Aspose.TeX 在 Java 中将 TeX 排版为 XPS。探索无缝文档处理的分步指南。
type: docs
weight: 10
url: /zh/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
---
## 介绍

在 Java 开发领域，Aspose.TeX 作为将 TeX 文档排版为各种格式（包括 XPS）的强大工具而脱颖而出。如果您希望增强 Java 应用程序的文档处理能力，本教程就是为您量身定制的。在本分步指南中，我们将引导您完成使用 Aspose.TeX for Java 和外部流将 TeX 排版为 XPS 的过程。

## 先决条件

在深入学习本教程之前，请确保您具备以下先决条件：

-  Java 开发工具包 (JDK)：确保您的系统上安装了 Java。您可以从以下位置下载：[这里](https://www.oracle.com/java/technologies/javase-downloads.html).

-  Aspose.TeX for Java：下载并安装 Aspose.TeX for Java。你可以找到下载链接[这里](https://releases.aspose.com/tex/java/).

## 导入包

首先导入必要的包来开始您的 TeX 到 XPS 转换之旅。在您的 Java 项目中包含以下代码片段：

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

## 第 1 步：配置转换选项

首先使用以下代码为默认的 ObjectTeX 格式创建转换选项：

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

这为排版过程奠定了基础。

## 第 2 步：指定作业名称和目录

定义作业名称并设置输入和输出工作目录：

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

确保将“您的输入目录”等占位符替换为实际的目录路径。

## 步骤 3：配置终端输出

指定终端输出应写入输出工作目录中的文件：

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

此步骤可确保捕获详细日志以进行调试。

## 第 4 步：打开输出流

打开一个流来写入排版的 XPS 文档：

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

将“您的输出目录”替换为适当的路径。

## 第 5 步：运行作业

执行 TeX 到 XPS 的转换作业：

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

该过程就完成了，您将在指定的输出目录中找到排版的 XPS 文档。

## 结论

恭喜！您已使用 Aspose.TeX 在 Java 中成功将 TeX 排版为 XPS。这为 Java 应用程序中的文档处理开辟了无限可能。尝试不同的 TeX 文件并探索 Aspose.TeX 提供的各种功能。

## 常见问题解答

### Q1：我可以将 Aspose.TeX for Java 与其他文档格式一起使用吗？

A1：Aspose.TeX主要专注于TeX相关的文档处理。对于其他格式，请探索 Aspose 广泛的产品系列。

### Q2：有试用版吗？

 A2：是的，您可以通过下载免费试用版来体验Aspose.TeX[这里](https://releases.aspose.com/).

### Q3：在哪里可以找到全面的文档？

 A3：参考文档[这里](https://reference.aspose.com/tex/java/)获取详细信息和示例。

### Q4：我如何获得支持或寻求帮助？

 A4：访问 Aspose.TeX 论坛[这里](https://forum.aspose.com/c/tex/47)以获得社区支持和讨论。

### Q5：我可以获得临时许可证用于测试目的吗？

 A5：是的，您可以获得临时许可证[这里](https://purchase.aspose.com/temporary-license/).