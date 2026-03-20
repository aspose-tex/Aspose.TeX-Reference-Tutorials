---
date: 2025-12-20
description: 了解如何使用 Aspose.TeX for .NET 创建 TeX 作业的 XPS 输出，管理文件系统的输入/输出，并生成高质量的 XPS
  文档。
linktitle: Create TeX Job XPS Output with Filesystems – Aspose.TeX for .NET
second_title: Aspose.TeX .NET API
title: 使用文件系统创建 TeX 作业 XPS 输出 – Aspose.TeX for .NET
url: /zh/net/file-input-output/filesystem-input-xps-output/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建 TeX 作业 XPS 输出与文件系统 – Aspose.TeX for .NET

## 介绍

欢迎！在本教程中，您将学习 **如何创建 TeX 作业 XPS 输出**，并使用 Aspose.TeX for .NET 处理文件系统的输入和输出。无论您是在构建批处理器、Web 服务还是桌面实用工具，下面的步骤都将指导您配置引擎、指向文件并生成与原始 LaTeX 源完全相同的 XPS 文档。

我们将把过程拆分为清晰的编号步骤，解释每行代码背后的 “为什么”，并提供您可以立即应用的实用技巧。

## 快速答案
- **“create tex job xps” 是什么意思？** 它指的是配置一个 Aspose.TeX 作业，读取 TeX 文件并将结果写入 XPS 文档。  
- **我需要许可证吗？** 提供临时许可证用于测试；生产环境需要正式许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。  
- **可以更改输出格式吗？** 可以 —— 将 `XpsDevice` 替换为其他设备（PDF、PNG 等）。  
- **需要控制台输出吗？** 不需要 —— 您可以使用内存终端实现静默执行。

## 什么是 “create tex job xps”？

创建一个输出 XPS 的 TeX 作业意味着初始化 Aspose.TeX 引擎，指定读取源文件的位置，并将渲染的页面写入 XPS 包。XPS（XML Paper Specification）是一种固定布局格式，能够保留排版和矢量图形，非常适合打印或进一步转换。

## 为什么使用 Aspose.TeX 生成 XPS 输出？

- **高保真度：** 引擎能够在 XPS 中准确再现 LaTeX 布局。  
- **无外部依赖：** 纯 .NET 库，无需本地 LaTeX 安装。  
- **灵活的 I/O：** 支持文件系统目录、内存流或自定义提供程序。  
- **可扩展性：** 适用于单文件转换或批量处理流水线。

## 前置条件

在开始之前，请确保您具备以下条件：

- **Aspose.TeX for .NET** – 从 [Aspose 网站](https://releases.aspose.com/tex/net/) 下载最新版本。  
- **.NET 开发环境** – Visual Studio、Rider 或带有 .NET SDK 的 VS Code。  
- **输入 & 输出文件夹** – 在机器上创建两个目录（例如 `C:\TeX\Input` 和 `C:\TeX\Output`）。  
- **许可证（可选，用于测试）** – 您可以从 Aspose 门户获取临时许可证。

## 导入命名空间

首先，引入所需的命名空间，以便访问文件系统帮助类和 XPS 设备。

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

这些命名空间公开了 `InputFileSystemDirectory`、`OutputFileSystemDirectory` 和 `XpsDevice`，它们是 **create tex job xps** 工作流的关键。

## 步骤 1：创建转换选项

我们首先构建一个 `TeXOptions` 对象，告诉引擎使用 ObjectTeX 配置（大多数 LaTeX 源的默认设置）。

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

> **小贴士：** `ConsoleAppOptions` 为控制台式应用程序设置了合理的默认值，后续如果需要可以自行定制选项。

## 步骤 2：指定输入和输出目录

将引擎指向您之前准备好的文件夹。将占位符字符串替换为机器上的实际路径。

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

现在 TeX 作业知道在哪里寻找 `.tex` 文件以及将生成的 XPS 文件放置在哪里。

## 步骤 3：选择输出终端

终端决定状态信息写入的位置。为了快速调试，我们使用控制台终端，但也可以切换到内存终端实现静默运行。

```csharp
options.TerminalOut = new OutputConsoleTerminal(); // Default value. Arbitrary assignment.
```

> **为什么重要：** 使用控制台终端可以立即看到编译警告或错误，从而加快排查问题的速度。

## 步骤 4：运行 TeX 作业

创建 `TeXJob` 实例，给它一个友好的名称，附加 `XpsDevice`，然后执行。

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

当 `Run()` 完成后，您将在输出目录中看到 `hello-world.xps` 文件。

## 步骤 5：微调控制台输出

在作业完成后添加一个空行，可使控制台日志更易阅读，尤其是在批量运行多个作业时。

```csharp
options.TerminalOut.Writer.WriteLine();
```

## 常见问题及解决方案

| 问题 | 原因 | 解决方案 |
|------|------|----------|
| **XPS 文件为空** | 输出目录路径不正确或不可写。 | 验证传递给 `OutputFileSystemDirectory` 的路径，并确保进程拥有写入权限。 |
| **编译错误** | LaTeX 源使用了 ObjectTeX 未包含的宏包。 | 切换到完整 TeX 引擎配置 (`TeXConfig.FullTeX()`) 或将缺失的宏包文件添加到输入目录。 |
| **控制台卡住** | 终端因交互提示等待输入。 | 使用 `OutputMemoryTerminal` 抑制交互提示，以实现自动化脚本运行。 |

## 常见问答

**Q1：我可以使用除 XPS 之外的其他输出格式吗？**  
A1：可以，Aspose.TeX 支持 PDF、PNG、SVG 等格式。将 `new XpsDevice()` 替换为相应的设备类（例如 `new PdfDevice()`）。

**Q2：是否提供用于测试的临时许可证？**  
A2：是的，您可以从 [此链接](https://purchase.aspose.com/temporary-license/) 获取临时许可证用于测试。

**Q3：在哪里可以找到更多文档？**  
A3：请参考 [Aspose.TeX for .NET 文档](https://reference.aspose.com/tex/net/) 获取详细信息。

**Q4：如何获取社区支持或提问？**  
A4：访问 [Aspose.TeX 论坛](https://forum.aspose.com/c/tex/47) 与社区交流并获取帮助。

**Q5：是否有示例项目可供参考？**  
A5：可在 Aspose.TeX 的 GitHub 仓库中查找示例项目和代码片段。

## 结论

通过上述步骤，您已经掌握了使用 Aspose.TeX for .NET **创建 TeX 作业 XPS 输出** 的方法，能够管理输入输出文件夹，并针对开发和生产场景微调整个过程。欢迎尝试其他输出设备，将此逻辑集成到更大的工作流中，或实现批量自动转换。

---

**最后更新：** 2025-12-20  
**测试环境：** Aspose.TeX 24.11 for .NET（撰写时的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}