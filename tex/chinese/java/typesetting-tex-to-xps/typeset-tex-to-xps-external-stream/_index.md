---
date: 2025-12-11
description: 学习如何在 Java 中使用 Aspose.TeX 将 TeX 转换为 XPS。本分步指南向您展示如何高效生成 XPS 文档流。
linktitle: How to Convert TeX to XPS in Java with External Stream
second_title: Aspose.TeX Java API
title: 如何在 Java 中使用外部流将 TeX 转换为 XPS
url: /zh/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中使用外部流将 TeX 转换为 XPS

## 介绍

如果您需要 **将 TeX** 文件从 Java 应用程序转换为高质量的 XPS 输出，Aspose.TeX for Java 能让此工作变得轻而易举。在本教程中，您将看到 **如何使用外部输出流将 TeX** 转换为 XPS 文档，这在您希望将结果直接写入响应、云存储服务或任何自定义目标时非常理想。让我们从环境搭建到最终写入 XPS 文件，完整演示整个过程。

## 快速回答
- **本教程覆盖了哪些内容？** 使用 Aspose.TeX 通过外部流将 TeX 转换为 XPS。  
- **需要的主要库是什么？** Aspose.TeX for Java。  
- **是否需要许可证？** 生产环境需要临时或正式许可证。  
- **可以生成 XPS 文档流吗？** 可以——示例直接将 XPS 写入 `OutputStream`。  
- **支持的 Java 版本？** 任意 JDK 8 以上（本教程以 JDK 11 为参考）。

## 先决条件

在编写代码之前，请确保您具备以下条件：

- Java Development Kit (JDK)：确保系统已安装 Java。您可以从 [here](https://www.oracle.com/java/technologies/javase-downloads.html) 下载。
- Aspose.TeX for Java：下载并安装 Aspose.TeX for Java。下载链接请参见 [here](https://releases.aspose.com/tex/java/)。

## 导入包

首先导入必要的包，以开启您的 TeX‑to‑XPS 转换之旅。在 Java 项目中加入以下代码片段：

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

## 步骤 1：配置转换选项

使用以下代码创建默认 ObjectTeX 格式的转换选项：

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

这为排版过程奠定了基础。

## 步骤 2：指定作业名称和目录

定义作业名称并设置输入、输出工作目录：

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

请将 “Your Input Directory” 等占位符替换为实际的目录路径。

## 步骤 3：配置终端输出

指定将终端输出写入输出工作目录中的文件：

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

此步骤可捕获详细日志，便于调试。

## 步骤 4：打开输出流

打开流以写入排版后的 XPS 文档：

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

将 “Your Output Directory” 替换为相应的路径。

## 步骤 5：运行作业

执行 TeX 到 XPS 的转换作业：

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

完成后，您将在指定的输出目录中找到生成的 XPS 文档。

## 常见问题及解决方案

| 问题 | 出现原因 | 解决方法 |
|------|----------|----------|
| **FileNotFoundException** 在打开流时 | 输出目录路径不正确或不存在。 | 核实路径，提前创建目录，或使用 `Files.createDirectories`。 |
| **NullPointerException** 在 `options.getOutputWorkingDirectory()` 上 | 未调用 `setOutputWorkingDirectory` 或返回 `null`。 | 确保在使用前调用 `options.setOutputWorkingDirectory`。 |
| **LicenseException** 运行时 | 未使用有效的 Aspose.TeX 许可证。 | 使用 `License license = new License(); license.setLicense("Aspose.TeX.lic");` 应用临时或永久许可证。 |

## 常见问题

**Q: 可以将 Aspose.TeX for Java 与其他文档格式一起使用吗？**  
A: Aspose.TeX 主要专注于 TeX 相关文档处理。其他格式请参考 Aspose 丰富的产品线。

**Q: 是否提供试用版？**  
A: 是的，您可以通过下载免费试用版 [here](https://releases.aspose.com/) 进行体验。

**Q: 哪里可以找到完整的文档？**  
A: 请访问文档页面 [here](https://reference.aspose.com/tex/java/) 获取详细信息和示例。

**Q: 如何获取支持或寻求帮助？**  
A: 前往 Aspose.TeX 论坛 [here](https://forum.aspose.com/c/tex/47) 与社区交流。

**Q: 能否获取用于测试的临时许可证？**  
A: 可以，临时许可证可在此处获取 [here](https://purchase.aspose.com/temporary-license/)。

## 结论

恭喜！您已经学习了 **如何在 Java 中使用 Aspose.TeX 和外部流将 TeX 转换为 XPS 文档**。此技术让您完全掌控 XPS 输出的去向——无论是文件系统、Web 响应还是云存储桶。欢迎尝试不同的 TeX 源、调整 `TeXOptions` 以使用自定义字体，或将流集成到更大的文档生成管道中。

---

**Last Updated:** 2025-12-11  
**Tested With:** Aspose.TeX for Java 24.11（撰写时的最新版本）  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}