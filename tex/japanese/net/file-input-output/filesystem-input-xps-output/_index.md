---
date: 2025-12-20
description: Aspose.TeX for .NET を使用して TeX ジョブの XPS 出力を作成し、ファイルシステムの入出力を管理し、高品質な XPS
  ドキュメントを生成する方法を学びましょう。
linktitle: Create TeX Job XPS Output with Filesystems – Aspose.TeX for .NET
second_title: Aspose.TeX .NET API
title: ファイルシステムで TeX ジョブの XPS 出力を作成 – Aspose.TeX for .NET
url: /ja/net/file-input-output/filesystem-input-xps-output/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create TeX Job XPS Output with Filesystems – Aspose.TeX for .NET

## Introduction

ようこそ！このチュートリアルでは、**TeX ジョブの XPS 出力を作成**し、ファイルシステムの入力と出力を使用して Aspose.TeX for .NET で処理する方法を学びます。バッチプロセッサ、Web サービス、デスクトップユーティリティのいずれを構築する場合でも、以下の手順に従ってエンジンの設定、ファイルの指定、元の LaTeX ソースと同一のレイアウトを持つ XPS ドキュメントの生成が行えます。

プロセスは明確な番号付きステップに分割し、各コード行の「なぜ」を解説し、すぐに活用できる実践的なヒントを提供します。

## Quick Answers
- **What does “create tex job xps” mean?** It refers to configuring an Aspose.TeX job that reads TeX files and writes the result as an XPS document.  
- **Do I need a license?** A temporary license is available for testing; a full license is required for production.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Can I change the output format?** Yes – replace `XpsDevice` with another device (PDF, PNG, etc.).  
- **Is console output required?** No – you can use a memory terminal for silent execution.

## What is “create tex job xps”?

TeX ジョブで XPS を出力するということは、Aspose.TeX エンジンを初期化し、ソースファイルの読み取り先を指定し、レンダリングされたページを XPS パッケージに書き込むことを意味します。XPS（XML Paper Specification）は、タイポグラフィとベクターグラフィックを保持する固定レイアウト形式で、印刷やさらに別の形式への変換に最適です。

## Why use Aspose.TeX for XPS output?

- **High fidelity:** The engine reproduces LaTeX layout accurately in XPS.  
- **No external dependencies:** Pure .NET library, no need for native LaTeX installations.  
- **Flexible I/O:** Works with filesystem directories, memory streams, or custom providers.  
- **Scalable:** Suitable for single‑file conversions or bulk processing pipelines.

## Prerequisites

作業を始める前に、以下を用意してください。

- **Aspose.TeX for .NET** – 最新バージョンは [Aspose website](https://releases.aspose.com/tex/net/) からダウンロードしてください。  
- **.NET development environment** – Visual Studio、Rider、または .NET SDK がインストールされた VS Code。  
- **Input & output folders** – マシン上に 2 つのディレクトリを作成します（例: `C:\TeX\Input` と `C:\TeX\Output`）。  
- **License (optional for testing)** – テスト用の一時ライセンスは Aspose ポータルから取得できます。

## Import Namespaces

まず、ファイルシステムヘルパーと XPS デバイスにアクセスできるよう、必要な名前空間をインポートします。

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

これらの名前空間は `InputFileSystemDirectory`、`OutputFileSystemDirectory`、`XpsDevice` を公開し、**create tex job xps** ワークフローに不可欠です。

## Step 1: Create Conversion Options

エンジンに ObjectTeX 設定（ほとんどの LaTeX ソースのデフォルト）を使用させるため、`TeXOptions` オブジェクトを作成します。

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

> **Pro tip:** `ConsoleAppOptions` はコンソール向けアプリケーションに適したデフォルトを設定しますが、必要に応じて後からオプションをカスタマイズできます。

## Step 2: Specify Input and Output Directories

先ほど作成したフォルダーをエンジンに指示します。プレースホルダー文字列は実際のパスに置き換えてください。

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

これで TeX ジョブは `.tex` ファイルの所在と生成された XPS ファイルの出力先を認識します。

## Step 3: Choose an Output Terminal

ターミナルはステータスメッセージの出力先を制御します。デバッグのためにコンソールを使用しますが、サイレント実行が必要な場合はメモリターミナルに切り替えられます。

```csharp
options.TerminalOut = new OutputConsoleTerminal(); // Default value. Arbitrary assignment.
```

> **Why this matters:** コンソールターミナルを使用すると、コンパイル時の警告やエラーが即座に確認でき、トラブルシューティングが迅速になります。

## Step 4: Run the TeX Job

`TeXJob` インスタンスを作成し、フレンドリーネームを付け、`XpsDevice` を添付して実行します。

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

`Run()` が完了すると、出力ディレクトリに `hello-world.xps` ファイルが生成されます。

## Step 5: Fine‑Tune the Console Output

ジョブ完了後に空行を追加すると、バッチで複数ジョブを実行した際にコンソールログが見やすくなります。

```csharp
options.TerminalOut.Writer.WriteLine();
```

## Common Issues and Solutions

| Issue | Cause | Fix |
|-------|-------|-----|
| **XPS file is empty** | Output directory path is incorrect or not writable. | Verify the path passed to `OutputFileSystemDirectory` and ensure the process has write permissions. |
| **Compilation errors** | LaTeX source uses packages not bundled with ObjectTeX. | Switch to a full TeX engine configuration (`TeXConfig.FullTeX()`) or add missing package files to the input directory. |
| **Console hangs** | Terminal waiting for input due to interactive prompts. | Use `OutputMemoryTerminal` to suppress interactive prompts in automated scripts. |

## Frequently Asked Questions

**Q1: Can I use a different output format instead of XPS?**  
A1: Yes, Aspose.TeX supports PDF, PNG, SVG, and other formats. Replace `new XpsDevice()` with the appropriate device class (e.g., `new PdfDevice()`).  

**Q2: Is a temporary license available for testing purposes?**  
A2: Yes, you can obtain a temporary license for testing from [this link](https://purchase.aspose.com/temporary-license/).  

**Q3: Where can I find additional documentation?**  
A3: Refer to the [Aspose.TeX for .NET documentation](https://reference.aspose.com/tex/net/) for detailed information.  

**Q4: How can I get community support or ask questions?**  
A4: Visit the [Aspose.TeX forum](https://forum.aspose.com/c/tex/47) for community support and discussions.  

**Q5: Are there any sample projects available?**  
A5: Explore the Aspose.TeX GitHub repository for sample projects and code snippets.

## Conclusion

上記の手順に従うことで、Aspose.TeX for .NET を使用して **create tex job xps** を実現し、入力・出力フォルダーを管理し、開発・本番シナリオの両方に適したプロセスを微調整できるようになりました。その他の出力デバイスを試したり、ロジックを大規模ワークフローに統合したり、バッチ変換を自動化したりしてみてください。

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.TeX 24.11 for .NET (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}