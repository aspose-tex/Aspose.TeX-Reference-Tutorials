---
title: 在 Java 中轻松将 LaTeX 转换为 XPS 格式
linktitle: 在 Java 中轻松将 LaTeX 转换为 XPS 格式
second_title: Aspose.TeX Java API
description: 使用 Aspose.TeX 在 Java 中轻松将 LaTeX 转换为 XPS。请按照我们的分步指南进行无缝集成。
weight: 10
url: /zh/java/converting-lato-xps/simple-xps-conversion/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 中轻松将 LaTeX 转换为 XPS 格式

## 介绍

您是否希望在 Java 应用程序中将 LaTeX 文档无缝转换为 XPS 格式？ Aspose.TeX for Java 提供了强大的解决方案，让您轻松实现这一目标。在本分步指南中，我们将引导您完成使用 Aspose.TeX 将 LaTeX 转换为 XPS 的过程。

## 先决条件

在深入转换过程之前，请确保满足以下先决条件：

- 您的系统上安装了 Java 开发工具包 (JDK)。
- 下载 Aspose.TeX for Java 库。你可以找到下载链接[这里](https://releases.aspose.com/tex/java/).

## 导入包

首先，导入 Java 项目所需的包。确保您的项目依赖项中包含 Aspose.TeX 库。

```java
package com.aspose.tex.LaTeXXpsConversionSimplest;

import java.io.ByteArrayInputStream;
import java.io.IOException;
import java.util.Calendar;
import java.util.GregorianCalendar;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.Interaction;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;
import com.aspose.tex.rendering.XpsSaveOptions;

import util.Utils;
```

现在，让我们使用提供的代码示例将转换过程分解为多个步骤。

## 第1步：设置输入和输出目录

```java
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

指定 LaTeX 输入文件所在的目录以及要保存转换后的 XPS 文件的目录。

## 第 2 步：配置 TeX 选项

配置各种选项以根据您的需要自定义转换过程。

```java
options.setInteraction(Interaction.NonstopMode);
options.setDateTime(new GregorianCalendar(2022, Calendar.DECEMBER, 18).getTime());
options.ignoreMissingPackages(true);
options.noLigatures(true);
options.repeat(true);
```

根据需要调整交互模式、标题中的日期、丢失包的处理、连字和重复。

## 步骤 3：初始化 XPS 保存选项

```java
options.setSaveOptions(new XpsSaveOptions());
```

初始化以 XPS 格式保存的选项。

## 第 4 步：自定义 XPS 保存选项

```java
options.getSaveOptions().rasterizeFormulas(true);
options.getSaveOptions().rasterizeIncludedGraphics(true);
options.getSaveOptions().subsetFonts(true);
```

自定义 XPS 保存选项以控制公式、包含的图形和字体子集的转换。

## 第 5 步：运行 LaTeX 到 XPS 的转换

```java
new TeXJob("Your Input Directory" + "sample.ltx", new XpsDevice(), options).run();
```

通过使用指定的输入文件、输出设备 (XpsDevice) 和选项运行 TeX 作业来启动转换过程。

## 其他示例

使用不同的输入源探索其他转换方法：

### 使用输入流

```java
new TeXJob(new ByteArrayInputStream(
    "\\documentclass{article} \\begin{document} Hello, World! \\end{document}".getBytes("ASCII")),
    new XpsDevice(), options).run();
```

### 使用主输入端子

```java
new TeXJob(new XpsDevice(), options).run();
```

## 结论

借助 Aspose.TeX for Java，将 LaTeX 转换为 XPS 变得轻而易举。按照以下步骤操作，自定义选项，并将此功能无缝集成到您的 Java 应用程序中。

## 常见问题解答

### Q1：我可以使用Aspose.TeX转换具有复杂公式的LaTeX文档吗？

A1：当然！ Aspose.TeX 在转换过程中无缝处理复杂的公式。

### Q2：Aspose.TeX for Java 有试用版吗？

 A2：是的，您可以找到免费试用版[这里](https://releases.aspose.com/).

### Q3：如何获得 Aspose.TeX 的支持？

A3：访问[Aspose.TeX 论坛](https://forum.aspose.com/c/tex/47)寻求帮助和社区支持。

### Q4：Aspose.TeX 是否有临时许可证？

 A4：是的，您可以获得临时许可证[这里](https://purchase.aspose.com/temporary-license/).

### Q5：哪里可以找到Aspose.TeX的文档？

 A5：请参阅[文档](https://reference.aspose.com/tex/java/)进行全面指导。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
