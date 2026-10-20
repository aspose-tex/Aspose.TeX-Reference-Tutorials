---
date: 2026-10-19
description: 了解如何使用 Aspose.TeX for .NET 执行 tex 文档生成、创建自定义 tex 格式并设置 tex 输入目录。提供代码片段和故障排除技巧的分步指南。
keywords:
- tex document generation
- create custom tex format
- set tex input directory
- custom tex macros
lastmod: 2026-10-19
linktitle: .NET 中创建自定义 TeX 格式
og_description: 使用 Aspose.TeX 进行 tex 文档生成，可在 .NET 中创建自定义 tex 格式并设置 tex 输入目录。请遵循本指南以获取
  XPS、PDF 或 PNG 输出。
og_image_alt: Developer guide showing tex document generation using Aspose.TeX in
  .NET
og_title: 如何在 .NET 中使用格式进行 tex 文档生成
schemas:
- author: Aspose
  dateModified: '2026-10-19'
  description: Learn how to perform tex document generation, create custom tex format
    and set tex input directory using Aspose.TeX for .NET. Step‑by‑step guide with
    code snippets and troubleshooting tips.
  headline: How to do tex document generation with format in .NET
  type: TechArticle
- description: Learn how to perform tex document generation, create custom tex format
    and set tex input directory using Aspose.TeX for .NET. Step‑by‑step guide with
    code snippets and troubleshooting tips.
  name: How to do tex document generation with format in .NET
  steps:
  - name: '**Aspose.TeX for .NET** – download it from the [Aspose.TeX website](https://releases.aspose.com/tex/net/).'
    text: '**Aspose.TeX for .NET** – download it from the [Aspose.TeX website](https://releases.aspose.com/tex/net/).'
  - name: A **.NET development environment** (Visual Studio, VS Code, or the .NET
      CLI).
    text: A **.NET development environment** (Visual Studio, VS Code, or the .NET
      CLI).
  - name: (Optional) A valid **Aspose.TeX license** for production use.
    text: (Optional) A valid **Aspose.TeX license** for production use.
  type: HowTo
- questions:
  - answer: Absolutely. Replace `new XpsDevice()` with `new PdfDevice()` and adjust
      the output path accordingly.
    question: Can I output PDF instead of XPS?
  - answer: Yes. Any modification to macros or engine settings requires re‑running
      `tex -ini` to generate a fresh `.fmt` file.
    question: Do I need to re‑compile the format file after every change?
  type: FAQPage
second_title: Aspose.TeX .NET API
tags:
- tex document generation
- Aspose.TeX
- .NET document processing
- custom tex format
title: 如何在 .NET 中使用格式进行 tex 文档生成
url: /zh/net/custom-tex-formats/create-custom-tex-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 .NET 中进行 tex 文档生成并使用格式

## 快速答案
- **“create custom tex format” 是什么意思？** 它指的是定义您自己的 TeX 引擎配置和已编译的格式文件，以便处理器遵循您的宏和设置。  
- **我需要哪个库？** Aspose.TeX for .NET，支持 30 多种输入和输出格式。  
- **我必须设置 tex 输入目录吗？** 是的 – 使用 `InputWorkingDirectory` 来告诉引擎辅助文件所在的位置。  
- **我可以生成哪些输出？** XPS、PDF、PNG、TIFF 以及更多设备格式。  
- **生产环境是否需要许可证？** 商业部署必须拥有有效的 Aspose.TeX 许可证。

## 什么是自定义 tex 格式？
自定义 tex 格式是一组预编译的宏和引擎设置，TeX 处理器在启动时加载。创建它后，您可以嵌入企业品牌、强制执行布局标准，并减少重复文档的编译时间。它实现了所有生成文档的一致样式，并简化了复杂排版工作流的维护。

## 为什么要设置 tex 输入目录？
设置 **tex 输入目录** 可告知引擎在何处查找辅助文件，如样式文件、自定义字体或额外的宏包。这可消除 “文件未找到” 错误并保持项目文件夹整洁。它还通过确保所有资源均从已知位置解析，提高了构建的可重复性。

## 前置条件

在开始之前，请确保您拥有：

1. **Aspose.TeX for .NET** – 从 [Aspose.TeX 网站](https://releases.aspose.com/tex/net/) 下载。  
2. **.NET 开发环境**（Visual Studio、VS Code 或 .NET CLI）。  
3. （可选）用于生产的有效 **Aspose.TeX 许可证**。

## 导入命名空间

以下命名空间提供对核心 Aspose.TeX 类的访问。  
与 `Document` 相关的类位于 `Aspose.TeX`，而选项和设备位于 `Aspose.TeX.Rendering`。

`Document` 类是表示内存中单个 TeX 文档的顶层对象。  

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using Aspose.TeX.ResourceProviders;
using System.IO;
using System.Text;
```

## 步骤 1：创建格式提供程序

`FormatProvider` 告诉引擎已编译的格式文件 (`customtex.fmt`) 所在位置。将 `"Your Output Directory"` 替换为包含自定义格式的绝对路径。

`FormatProvider` 是一个轻量级包装器，加载一次 `.fmt` 文件后在每次转换中复用，从而显著提升批处理作业的性能。

```csharp
using (FormatProvider formatProvider =
    new FormatProvider(new InputFileSystemDirectory("Your Output Directory"), "customtex"))
{
```

## 步骤 2：配置转换选项（并设置 tex 输入目录）

这里我们创建一个 `TeXOptions` 实例。`InputWorkingDirectory` 属性 **设置 tex 输入目录**，以便引擎能够定位自定义包或字体等支持文件。

`TeXOptions` 还允许您指定输出设备、页面尺寸和渲染质量。对于大规模生成，您可以启用 `EnableParallelProcessing` 以在多核服务器上加速渲染。

```csharp
    TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX(formatProvider));
    options.JobName = "typeset-with-custom-format";
    options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
    options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

## 步骤 3：运行任务

现在将一个简单的 TeX 字符串提供给引擎，选择输出设备（本例为 XPS），并执行任务。`TeXEngine` 读取自定义格式，处理源代码，并将结果写入所选设备。

`TeXEngine` 是 Aspose.TeX 的核心处理器，解析 TeX 源代码，应用自定义格式，并将渲染的页面流式传输到您指定的设备。

```csharp
    new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
        "Congratulations! You have successfully typeset this text with your own TeX format!\\end")),
        new XpsDevice(), options).Run();
```

## 步骤 4：美化终端输出

在任务完成后添加空行可使控制台日志更易阅读，尤其是在脚本中串联多个转换时。

`Console.WriteLine()` 向标准输出流写入一行文本。此处仅用于视觉分隔，对生成的文档没有影响。

```csharp
    options.TerminalOut.Writer.WriteLine();
}
// ExEnd:TypesetWithCustomTeXFormat
```

恭喜！您已经 **创建了自定义 tex 格式** 并在 .NET 中用于 **tex 文档生成**。您可以将 `XpsDevice` 替换为 `PdfDevice`、`PngDevice` 或其他任何受支持的设备，以满足您的交付需求。

## 常见问题及解决方案

| 问题 | 原因 | 解决方案 |
|-------|--------|-----|
| *“未找到格式文件”* | `FormatProvider` 中的路径错误 | 确认 `"Your Output Directory"` 包含 `customtex.fmt`，且路径为绝对路径或相对于可执行文件的正确相对路径。 |
| *“找不到输入文件”* | `InputWorkingDirectory` 指向了错误的文件夹 | 确保 `"Your Input Directory"` 包含 TeX 源文件，或像示例中那样将源作为流传递。 |
| *终端输出乱码* | 编码不匹配 | 如果 TeX 源包含非 ASCII 字符，请使用 `Encoding.UTF8`。 |
| *XPS 文件为空* | 任务因之前的异常未运行 | 检查控制台错误信息；通常会指示缺少的包或 TeX 字符串中的语法错误。 |

## 常见问答

**Q1: 我可以将 Aspose.TeX for .NET 与其他 Aspose 库一起使用吗？**  
A: 是的，Aspose.TeX 可与 Aspose.PDF、Aspose.Words 以及其他 Aspose 产品无缝集成，实现端到端的文档流水线。

**Q2: Aspose.TeX for .NET 有免费试用吗？**  
A: 有，您可以从 **Aspose.TeX 免费试用下载页面** (https://releases.aspose.com/tex/net/) 下载试用版。

**Q3: 我如何获得 Aspose.TeX for .NET 的支持？**  
A: 访问 [Aspose.TeX 论坛](https://forum.aspose.com/c/tex/47) 获取社区帮助，或在 **高级支持购买页面** (https://purchase.aspose.com/buy) 查看付费选项。

**Q4: Aspose.TeX for .NET 有临时许可证吗？**  
A: 有，请在 **临时许可证请求页面** (https://purchase.aspose.com/temporary-license/) 申请。

**Q5: 我在哪里可以找到官方 API 参考文档？**  
A: 完整文档托管在 **API 参考文档** (https://reference.aspose.com/tex/net/) 上。

### 其他问答

**Q: 我可以输出 PDF 而不是 XPS 吗？**  
A: 当然。将 `new XpsDevice()` 替换为 `new PdfDevice()` 并相应调整输出路径。

**Q: 每次更改后我需要重新编译格式文件吗？**  
A: 是的。对宏或引擎设置的任何修改都需要重新运行 `tex -ini` 以生成新的 `.fmt` 文件。

## 结论

Aspose.TeX for .NET 提供了 **强大且高性能的 tex 文档生成解决方案**，让您 **创建自定义 tex 格式**、设置 **tex 输入目录**，并输出到任何受支持的设备。将上述步骤整合到 CI/CD 流水线中，自动化大规模报告生成，或构建满足组织品牌标准的自定义发布引擎。

---

**最后更新：** 2026-10-19  
**测试环境：** Aspose.TeX 24.11 for .NET  
**作者：** Aspose

## 相关教程

- [获取 TeX 文件流（C#）使用 Aspose.TeX API 必需的输入目录](/tex/net/advanced-io/required-input-directory-csharp/)
- [如何使用 Aspose.TeX for .NET 创建 PDF – 步骤指南](/tex/net/pdf-output/)
- [如何在 .NET 中创建 XPS 文档 – 使用 Aspose.TeX for .NET 将 TeX 转换为 XPS 输出](/tex/net/xps-output/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}