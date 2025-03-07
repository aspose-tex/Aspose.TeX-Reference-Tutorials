---
title: 在 .NET 中将 TeX 排版为 XPS
linktitle: 在 .NET 中将 TeX 排版为 XPS
second_title: Aspose.TeX .NET API
description: 使用 Aspose.TeX 轻松将 TeX 文档转换为 .NET 中的 XPS。探索我们的分步指南，以获得无缝集成体验。
weight: 10
url: /zh/net/xps-output/typeset-tex-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 .NET 中将 TeX 排版为 XPS

## 介绍

欢迎阅读我们关于使用强大的 Aspose.TeX 库在 .NET 中将 TeX 排版为 XPS 的分步指南。如果您希望在 .NET 应用程序中将 TeX 文档无缝转换为 XPS 格式，那么您来对地方了。在本教程中，我们将引导您完成整个过程，分解每个步骤以确保顺利实施。

## 先决条件

在我们深入学习本教程之前，请确保您具备以下先决条件：

-  Aspose.TeX for .NET：确保您已安装 Aspose.TeX 库。你可以下载它[这里](https://releases.aspose.com/tex/net/).

- 文档：通过参考文档来熟悉该库[这里](https://reference.aspose.com/tex/net/).

- 输入和输出目录：按照示例代码中的指定设置输入和输出目录。

现在您已完成所有设置，让我们继续执行分步指南。

## 导入命名空间

在您的 .NET 应用程序中，首先导入必要的命名空间。这确保您可以访问将 TeX 排版为 XPS 所需的 Aspose.TeX 功能。

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
```

## 第 1 步：设置转换选项

定义转换选项，在 ObjectTeX 引擎扩展上指定 ObjectTeX 格式。此外，还可以设置作业名称、输入和输出目录以及终端输出详细信息。

```csharp
//根据 ObjectTeX 引擎扩展创建默认 ObjectTeX 格式的转换选项。
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
//指定作业名称。
options.JobName = "external-file-stream";
//指定用于输入的文件系统工作目录。
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
//指定输出的文件系统工作目录。
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
//指定终端输出必须写入输出工作目录中的文件。
//文件名为 <作业名称>.trm。
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## 步骤 2：创建 XPS 文档流

打开一个流来写入排版的 XPS 文档。文件名不一定与作业名称相同。

```csharp
using (Stream stream = File.Open(Path.Combine("Your Output Directory", options.JobName + ".xps"), FileMode.Create))
```

## 第 3 步：运行 TeX 作业

启动并运行 TeX 作业，指定文档名称、XpsDevice 和转换选项。

```csharp
new TeXJob("hello-world", new XpsDevice(stream), options).Run();
```

恭喜！您已使用 Aspose.TeX 在 .NET 中成功将 TeX 排版为 XPS。请根据您的具体要求随意探索更多功能和选项。

## 结论

在本教程中，我们介绍了使用 Aspose.TeX 将 TeX 文档无缝转换为 .NET 中的 XPS 格式的基本步骤。通过遵循本指南，您可以深入了解该库的功能以及如何将它们用于您的项目。

## 常见问题解答

### Q1：Aspose.TeX 与.NET Core 兼容吗？

A1：是的，Aspose.TeX 与 .NET Core 完全兼容。

### Q2：我可以将Aspose.TeX用于商业项目吗？

A2：当然！ Aspose.TeX 可用于商业和个人用途。

### Q3：在哪里可以找到更多示例和资源？

 A3：探索 Aspose.TeX 文档[这里](https://reference.aspose.com/tex/net/)了解更多示例和详细资源。

### Q4：如何获得 Aspose.TeX 的支持？

 A4：访问 Aspose.TeX 支持论坛[这里](https://forum.aspose.com/c/tex/47)获得社区的帮助。

### Q5: 有免费试用吗？

 A5：是的，您可以免费试用[这里](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
