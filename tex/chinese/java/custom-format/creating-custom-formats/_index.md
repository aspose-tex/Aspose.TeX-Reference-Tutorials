---
date: 2026-09-04
description: 了解如何在 Java 中使用 Aspose.TeX 从 TeX 生成 PDF，设置工作目录，并创建自定义 TeX 格式文件以实现一致的排版。
keywords:
- generate pdf from tex
- set working directories
- create custom tex format
- set tex input directory
- set tex output directory
lastmod: 2026-09-04
linktitle: 在 Java 中创建自定义 TeX 格式，实现一致的排版
og_description: 使用 Aspose.TeX 在 Java 中从 TeX 生成 PDF。了解如何设置工作目录、创建自定义 TeX 格式，并确保排版一致。
og_image_alt: Screenshot of Java code generating PDF from TeX using Aspose.TeX
og_title: 在 Java 中从 TeX 生成 PDF 并创建自定义格式
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to generate PDF from TeX in Java using Aspose.TeX, set working
    directories, and create custom TeX format files for consistent typesetting.
  headline: How to generate PDF from TeX and create formats in Java
  type: TechArticle
- description: Learn how to generate PDF from TeX in Java using Aspose.TeX, set working
    directories, and create custom TeX format files for consistent typesetting.
  name: How to generate PDF from TeX and create formats in Java
  steps:
  - name: Initialize TeX options (create a “no‑format” engine)
    text: The `TeXOptions` class lets you configure the TeX engine before any format
      is loaded.
  - name: Set the TeX input directory
    text: '`setInputWorkingDirectory` points the engine at the folder that contains
      your source `.tex` files, style packages, and any custom fonts. Using an absolute
      path during development avoids confusion with the IDE’s default working directory.
      > **Pro tip:** Keep your input folder read‑only in production '
  - name: Set the TeX output directory
    text: '`setOutputWorkingDirectory` defines where the engine writes compiled PDFs,
      log files, and auxiliary data. Separating output from source makes cleanup easier
      and enables you to archive results automatically.'
  - name: Run the format creation command
    text: Calling `createFormat("customtex", options)` tells Aspose.TeX to compile
      all packages referenced in the input directory into a binary format file named
      `customtex.fmt`. This step typically finishes within seconds, even for large
      collections of packages, because the engine only parses each macro once
  - name: Clean up the terminal output (optional)
    text: A simple `System.out.println()` adds a newline after the process finishes,
      keeping the console output tidy when you chain multiple conversions in a batch
      job.
  type: HowTo
- questions:
  - answer: You can refer to the [Aspose.TeX for Java documentation](https://reference.aspose.com/tex/java/)
      for comprehensive API details and usage examples.
    question: Where can I find the documentation for Aspose.TeX for Java?
  - answer: You can download the library from the [Aspose.TeX download page](https://releases.aspose.com/tex/java/).
    question: How can I download Aspose.TeX for Java?
  - answer: You can buy Aspose.TeX for Java from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.TeX for Java?
  - answer: Yes, you can access the free trial version on the [Aspose.TeX free trial
      download page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.TeX for Java?
  - answer: You can seek support on the [Aspose.TeX forum](https://forum.aspose.com/c/tex/47).
    question: How can I get support for Aspose.TeX for Java?
  type: FAQPage
second_title: Aspose.TeX Java API
tags:
- generate pdf
- Aspose.TeX
- Java typesetting
- custom tex format
title: 如何在 Java 中使用 TeX 生成 PDF 并创建格式
url: /zh/java/custom-format/creating-custom-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Java 从 TeX 生成 PDF 并创建格式

Generating PDF from TeX is a common requirement when you need high‑quality scientific or mathematical documents in a Java‑based pipeline. In this tutorial you’ll discover how to **create a custom TeX format** with Aspose.TeX, **set TeX input and output directories**, and finally **generate PDF from TeX** in a repeatable, performant way. By the end you’ll have a reusable `.fmt` file that guarantees identical styling for every document you process.

## 快速答案
- **“create custom TeX format” 是什么意思？** 它将一组宏、字体和布局规则编译成二进制文件，供引擎即时加载。  
- **我需要许可证吗？** 免费试用版足以用于开发；生产部署需要商业许可证。  
- **需要哪个 JDK 版本？** Java 8 或更高（推荐使用 Java 17 LTS）。  
- **我可以在运行时更改输入文件夹吗？** 可以——在 options 对象上调用 `setInputWorkingDirectory`。  
- **输出文件夹可以配置吗？** 当然——使用 `setOutputWorkingDirectory` 来控制 PDF 和日志的写入位置。

## 如何在 Java 中创建 TeX 格式？

`TeXOptions` 是一个配置对象，用于控制 Aspose.TeX 引擎的设置。首先，实例化一个 `TeXOptions` 对象，指向您的源文件夹，指定结果写入位置，最后调用 `createFormat("customtex", options)`。`createFormat` 方法将源文件编译成可重复使用的 `.fmt` 二进制文件，您可以在后续的 PDF 生成中加载它。此方法可将编译时间降低最多 70 %，并保证所有文档的布局一致。

## 为什么要设置 TeX 输入和输出目录？

设置输入目录告诉引擎在哪里查找 `.tex` 源文件、字体文件和辅助包，而输出目录则定义编译后的 PDF、日志文件和临时产物的存放位置。正确的目录配置可消除“文件未找到”错误，保持项目结构整洁，并允许并行运行多个转换而不会产生冲突。

## 前提条件
Before we dive into the code, make sure you have:

- **Aspose.TeX for Java** – 从 [Aspose.TeX 下载页面](https://releases.aspose.com/tex/java/) 下载。  
- **工作目录** – 确定一个 *input* 文件夹（存放 `.tex` 文件）和一个 *output* 文件夹（保存生成的 PDF）。在代码片段中将 `"Your Input Directory"` 和 `"Your Output Directory"` 替换为实际路径。  
- **Java Development Kit (JDK)** – 已安装 8 版或更高版本，并在 IDE 或构建系统中配置。

## 导入包
The `TeXOptions` class configures the Aspose.TeX engine, and the utility `FileHelper` provides simple file‑system helpers used in the sample project.

```java
package com.aspose.tex.CustomTeXFormatFileCreation;

import java.io.IOException;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;

import util.Utils;
```

## 创建自定义 TeX 格式的分步指南

### 步骤 1：初始化 TeX 选项（创建 “no‑format” 引擎）

The `TeXOptions` class lets you configure the TeX engine before any format is loaded.

```java
// Create TeX engine options for no format upon ObjectTeX engine extension.
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectIniTeX());
```

### 步骤 2：设置 TeX 输入目录

`setInputWorkingDirectory` 将引擎指向包含源 `.tex` 文件、样式包和任何自定义字体的文件夹。在开发期间使用绝对路径可避免 IDE 默认工作目录的混淆。

```java
// Specify a file system working directory for the input.
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
```

> **专业提示：** 在生产环境中将输入文件夹设为只读，以防止意外修改源 TeX 文件。

### 步骤 3：设置 TeX 输出目录

`setOutputWorkingDirectory` 定义引擎写入编译后 PDF、日志文件和辅助数据的位置。将输出与源文件分离可简化清理，并实现结果的自动归档。

```java
// Specify a file system working directory for the output.
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### 步骤 4：运行格式创建命令

调用 `createFormat("customtex", options)` 告诉 Aspose.TeX 将输入目录中引用的所有包编译成名为 `customtex.fmt` 的二进制格式文件。即使是大型包集合，此步骤通常也在几秒内完成，因为引擎只会解析每个宏一次。

```java
// Run format creation.
TeXJob.createFormat("customtex", options);
```

调用完成后，您将在输出文件夹中找到 `customtex.fmt`。在后续运行中加载此文件可将每个文档的编译时间降低最多 **70 %**（依据 Aspose 基准测试）。

### 步骤 5：清理终端输出（可选）

简单的 `System.out.println()` 在进程结束后添加换行，使在批处理作业中串联多个转换时控制台输出保持整洁。

```java
// For further output to look fine.
options.getTerminalOut().getWriter().newLine();
// ExEnd:CreateCustomTeXFormatFile
```

## 常见问题与解决方案
| Issue | Cause | Fix |
|-------|-------|-----|
| **“.tex 源文件未找到”** | 输入目录路径不正确 | 确认传递给 `setInputWorkingDirectory` 的路径与包含 `.tex` 文件的文件夹相匹配。 |
| **输出文件夹权限被拒绝** | 缺少写入权限 | 确保 Java 进程对通过 `setOutputWorkingDirectory` 设置的目录拥有写入权限。 |
| **格式创建卡住** | 加载的包过多 | 仅预编译所需的包；Aspose.TeX 可在不加载完整 TeX 发行版的情况下处理 **60+** 输入格式。 |

## 常见问题

**Q: 在哪里可以找到 Aspose.TeX for Java 的文档？**  
A: 您可以参考 [Aspose.TeX for Java 文档](https://reference.aspose.com/tex/java/) 获取全面的 API 细节和使用示例。

**Q: 如何下载 Aspose.TeX for Java？**  
A: 您可以从 [Aspose.TeX 下载页面](https://releases.aspose.com/tex/java/) 下载该库。

**Q: 在哪里可以购买 Aspose.TeX for Java？**  
A: 您可以在 [购买页面](https://purchase.aspose.com/buy) 购买 Aspose.TeX for Java。

**Q: 是否提供 Aspose.TeX for Java 的免费试用？**  
A: 是的，您可以在 [Aspose.TeX 免费试用下载页面](https://releases.aspose.com/) 获取免费试用版。

**Q: 如何获取 Aspose.TeX for Java 的支持？**  
A: 您可以在 [Aspose.TeX 论坛](https://forum.aspose.com/c/tex/47) 寻求帮助。

## 结论
您现在拥有一套完整的、可用于生产的 **从 TeX 生成 PDF** 的方案，使用 Aspose.TeX for Java。通过 **设置 TeX 输入目录** 和 **设置 TeX 输出目录**，您可以完全控制源文件的读取位置和结果的写入位置，从而在所有 Java 项目中实现可靠、可重复的排版。 在后续运行中重复使用 `customtex.fmt` 文件，可获得更快的编译速度和一致的布局。

---

**最后更新：** 2026-09-04  
**测试环境：** Aspose.TeX for Java 24.11  
**作者：** Aspose

## 相关教程

- [排版自定义 Tex 格式](/tex/java/custom-tex-formats/typesetting-custom-tex-formats/)
- [如何读取 TeX – 使用 Aspose.TeX for Java 设置输入目录的 Java 指南](/tex/java/advanced-io/required-input-directory/)
- [如何在 Java 中将 TeX 转换为 XPS – 分步指南](/tex/java/typesetting-tex-to-xps/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}