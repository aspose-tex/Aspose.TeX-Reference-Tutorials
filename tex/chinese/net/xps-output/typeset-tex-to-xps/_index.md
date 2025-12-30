---
date: 2025-12-30
description: 了解如何在 .NET 中使用 Aspose.TeX 将 TeX 转换为 XPS。请遵循本分步指南，实现无缝集成和可靠输出。
linktitle: How to Convert TeX to XPS in .NET
second_title: Aspose.TeX .NET API
title: 如何在 .NET 中将 TeX 转换为 XPS
url: /zh/net/xps-output/typeset-tex-to-xps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 .NET 中将 TeX 转换为 XPS

## 如何在 .NET 中将 TeX 转换为 XPS – 介绍

欢迎阅读我们的完整分步指南，了解 **如何将 TeX** 文档转换为 XPS 格式并在 .NET 环境中使用。借助强大的 Aspose.TeX 库，您可以将 TeX 到 XPS 的转换集成到任何 .NET 应用程序——无论是桌面工具、Web 服务还是自动化报表流水线。接下来的章节将逐一演示所有必要的设置，提供完整代码示例，并解释每一步的意义，帮助您自信地实现该解决方案。

## 快速答案
- **本教程涵盖哪些内容？** 使用 Aspose.TeX for .NET 将 TeX 文件转换为 XPS。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **是否需要许可证？** 免费试用可用于测试；生产环境需购买商业许可证。  
- **实现大概需要多长时间？** 基本转换通常在 15 分钟以内完成。  
- **在哪里获取库？** 请从官方 Aspose.TeX 发布页面下载。

## 前置条件

在开始教程之前，请确保已满足以下前置条件：

- Aspose.TeX for .NET：确保已安装 Aspose.TeX 库。您可以在[此处](https://releases.aspose.com/tex/net/)下载。  
- 文档：通过阅读[此处](https://reference.aspose.com/tex/net/)的文档熟悉库的使用。  
- 输入和输出目录：按照示例代码的说明创建输入、输出目录。

准备工作完成后，接下来进入分步指南。

## 导入命名空间

在 .NET 应用程序中，首先导入所需的命名空间，以便使用 Aspose.TeX 提供的排版功能。

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
```

## 步骤 1：设置转换选项

定义转换选项，指定 ObjectTeX 引擎的扩展格式。同时设置作业名称、输入输出目录以及终端输出细节。

```csharp
// Create conversion options for default ObjectTeX format upon ObjectTeX engine extension.
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
// Specify a job name.
options.JobName = "external-file-stream";
// Specify a file system working directory for input.
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
// Specify a file system working directory for output.
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
// Specify that the terminal output must be written to a file in the output working directory.
// The file name is <job_name>.trm.
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## 步骤 2：创建 XPS 文档流

打开流以写入排版后的 XPS 文档。文件名不一定与作业名称相同。

```csharp
using (Stream stream = File.Open(Path.Combine("Your Output Directory", options.JobName + ".xps"), FileMode.Create))
```

## 步骤 3：运行 TeX 作业

初始化并运行 TeX 作业，指定文档名称、XpsDevice 和转换选项。

```csharp
new TeXJob("hello-world", new XpsDevice(stream), options).Run();
```

恭喜！您已成功使用 Aspose.TeX 在 .NET 中将 TeX 排版为 XPS。欢迎根据具体需求进一步探索更多功能和选项。

## 结论

本教程介绍了在 .NET 环境下使用 Aspose.TeX 将 TeX 文档无缝转换为 XPS 格式的关键步骤。通过本指南，您已掌握该库的核心能力，并能够在项目中灵活运用。

## 常见问题

### Q1: Aspose.TeX 是否兼容 .NET Core？

A1: 是的，Aspose.TeX 完全兼容 .NET Core。

### Q2: 我可以在商业项目中使用 Aspose.TeX 吗？

A2: 当然！Aspose.TeX 可用于商业和个人用途。

### Q3: 哪里可以找到更多示例和资源？

A3: 请在 Aspose.TeX 文档的[此处](https://reference.aspose.com/tex/net/)查阅更多示例和详细资源。

### Q4: 如何获取 Aspose.TeX 的技术支持？

A4: 访问 Aspose.TeX 支持论坛[此处](https://forum.aspose.com/c/tex/47)获取社区帮助。

### Q5: 是否提供免费试用？

A5: 是的，您可以在[此处](https://releases.aspose.com/)获取免费试用。

## Frequently Asked Questions

**Q: 我可以自定义 XPS 输出（例如页面尺寸或边距）吗？**  
A: 可以。您可以调整 XpsDevice 设置或在转换前修改 TeX 源文件以控制页面布局。

**Q: 如果输入的 TeX 文件包含错误会怎样？**  
A: 转换过程会将错误详情写入终端输出文件（`*.trm`），您可以查看该文件以诊断并修复问题。

**Q: 能否在一次运行中转换多个 TeX 文件？**  
A: 可以。遍历 TeX 源文件集合，为每个文件创建单独的 TeXJob，同时复用同一个 `TeXOptions` 实例。

**Q: Aspose.TeX 是否支持 LaTeX 包如 `amsmath` 或 `graphicx`？**  
A: 大多数标准 LaTeX 包均受支持。请查阅官方文档获取完整兼容包列表。

**Q: 如何在生成的 XPS 文件中嵌入字体？**  
A: Aspose.TeX 会自动嵌入 TeX 引擎使用的字体。请确保运行转换的机器已安装所需字体。

---

**最后更新：** 2025-12-30  
**测试环境：** Aspose.TeX for .NET 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}