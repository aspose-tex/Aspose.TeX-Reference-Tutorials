---
date: 2025-12-21
description: Aspose.TeX を使用して C# でコンソール出力を取得する方法、ジョブ名を上書きする方法、TeX 入力ディレクトリを設定する方法、そしてターミナル出力をファイルに書き込む方法を学びましょう。
linktitle: Capture Console Output C# – Override Job Name & Write Output to Disk
second_title: Aspose.TeX .NET API
title: C#でコンソール出力を取得 – ジョブ名を上書きし、出力をディスクに書き込む
url: /ja/net/job-output/override-job-name-disk-output-csharp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# コンソール出力の取得 C# – ジョブ名を上書きし、ターミナル出力をディスクに書き込む (C#)

## Introduction

このステップバイステップ ガイドでは、Aspose.TeX for .NET を使用する際の **コンソール出力の取得 C#** の方法を学びます。ジョブ名を上書きし、ターミナル出力をファイルにリダイレクトすることで、TeX 処理パイプラインを完全に制御できます。自動ビルドや CI/CD シナリオ、あるいは後で分析するためにコンソール ストリームを記録する必要があるあらゆる状況に最適です。

## Quick Answers
- **“capture console output C#” とは何ですか？** Aspose.TeX が生成する標準ターミナル ストリームを、指定したファイルへリダイレクトします。  
- **ジョブ名を上書きする理由は？** 上書きすることで、予測可能なファイル名が確保でき、複数ジョブを同時に実行した際の衝突を防げます。  
- **出力を書き込む Aspose.TeX クラスはどれですか？** `OutputFileTerminal`（`options.TerminalOut` で使用）。  
- **カスタムの TeX 入力フォルダーを設定できますか？** はい、`options.InputWorkingDirectory` を使用して **TeX 入力ディレクトリを設定** できます。  
- **この方法は .NET Core と互換性がありますか？** 完全に対応しています。同じ API が .NET Framework と .NET Core の両方で動作します。

## What is “capture console output C#” in the context of Aspose.TeX?
コンソール出力の取得とは、通常ターミナル ウィンドウに表示されるすべての情報（ログ メッセージ、警告、コンパイルの詳細など）を永続的なファイルに書き込むことです。大規模な TeX プロジェクトのデバッグや、TeX 処理を自動化ワークフローに組み込む際に特に有用です。

## Why override the job name and write terminal output to a file?
- **予測可能なファイル名:** ジョブ名を上書きすることで、生成されるファイルのベース名を自分で決められ、後続のスクリプト作成が容易になります。  
- **監査可能性:** ターミナル ログを保存することで、TeX コンパイルプロセス全体の完全な監査トレイルが得られます。  
- **並列実行:** 複数ジョブを同時に走らせる際、ユニークなジョブ名がファイル衝突を防止します。  

## Prerequisites

Before we dive in, ensure you have the following:

- Aspose.TeX for .NET Library: Ensure that you have the Aspose.TeX for .NET library installed. You can download it from the [Aspose.TeX website](https://releases.aspose.com/tex/net/).
- .NET Development Environment: Have a working .NET development environment, including an integrated development environment (IDE) such as Visual Studio.
- Basic C# Knowledge: Familiarity with the basics of the C# programming language.
- Input and Output Directories: Prepare the input and output directories for your TeX files.

## Import Namespaces

In your C# code, make sure to include the necessary namespaces to access the Aspose.TeX functionalities:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

## Step 1: Create Conversion Options

First, we create a `TeXOptions` instance that tells Aspose.TeX we are running in a console‑application scenario.

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

Create `TeXOptions` with `ConsoleAppOptions`, specifying `ObjectTeX` as the `TeXConfig`.

## Step 2: Specify Job Name (Override Default)

Overriding the job name gives us control over the base name of all generated artifacts.

```csharp
options.JobName = "overridden-job-name";
```

Specify the job name to override the default name.

## Step 3: Set TeX Input Directory

Tell Aspose.TeX where to find your source `.tex` files. This is the **set tex input directory** step.

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

Set the input working directory for your TeX files.

## Step 4: Specify Output Working Directory

Define where the processed files and the captured console log will be saved.

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Define the output working directory to save the processed TeX files.

## Step 5: Write Terminal Output to File

Now we direct the console stream to a physical file in the output directory. This implements the **write terminal output to file** requirement.

```csharp
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

Configure the terminal output to be written to a file in the output directory.

## Step 6: Run the Job

Finally, we create a `TeXJob` with the overridden job name, the XPS output device, and the options we configured. Running the job will generate the XPS file and capture the console log.

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

Create a `TeXJob`, specifying a job name, output device (`XpsDevice`), and options. Finally, run the job.

## Common Issues & Troubleshooting

| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| No output file created | Output directory path is incorrect or missing write permissions | Verify `options.OutputWorkingDirectory` points to a valid folder and the process has write access. |
| Terminal log is empty | `TerminalOut` not set or overwritten later | Ensure `options.TerminalOut = new OutputFileTerminal(...);` is executed before `job.Run();`. |
| Job fails with “file not found” | Input directory not set correctly | Double‑check the path passed to `InputFileSystemDirectory` and that the `.tex` files exist there. |

## Frequently Asked Questions

### Q1: Can I use Aspose.TeX for .NET with other .NET libraries?

A1: Yes, Aspose.TeX for .NET can be integrated with other .NET libraries seamlessly.

### Q2: Is there a free trial available for Aspose.TeX for .NET?

A2: Yes, you can download a free trial version [here](https://releases.aspose.com/).

### Q3: How can I get support for Aspose.TeX for .NET?

A3: Visit the [Aspose.TeX forum](https://forum.aspose.com/c/tex/47) to get community and support.

### Q4: Are temporary licenses available for Aspose.TeX for .NET?

A4: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).

### Q5: Where can I find the documentation for Aspose.TeX for .NET?

A5: The documentation is available [here](https://reference.aspose.com/tex/net/).

## Conclusion

Congratulations! You've successfully learned how to **capture console output C#** by overriding the job name, setting the TeX input directory, and writing the terminal output to a file using Aspose.TeX for .NET. This technique streamlines logging, improves traceability, and makes automated TeX processing pipelines more robust.

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.TeX 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}