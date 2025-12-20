---
date: 2025-12-20
description: Aspose.TeX for C# を使用して TeX を PNG に変換する方法を学びましょう。このガイドでは、TeX から画像を生成し、ストリームを処理し、端末入力を取得する方法を示します。
linktitle: Convert TeX to PNG – Master Streams, Images, & Terminal Input in Aspose.TeX
  for C#
second_title: Aspose.TeX .NET API
title: TeX を PNG に変換 – Aspose.TeX for C# でストリーム、画像、端末入力をマスター
url: /ja/net/advanced-io/stream-input-image-output-terminal-input-csharp/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# TeX を PNG に変換 – Aspose.TeX for C# におけるストリーム、画像、端末入力のマスター

## Introduction

この包括的なチュートリアルでは、Aspose.TeX for C# を使用して **TeX を PNG に変換する方法** を学びます。レポート、Web プレビュー、または自動化されたドキュメント パイプライン向けに **TeX から画像を生成** したい場合でも、本ガイドはストリームの取り扱い、画像の管理、端末入力の取得を、シングルで分かりやすいサンプルを通じて解説します。

## Quick Answers
- **Aspose.TeX の役割は？** TeX ソースを解析し、PNG などのさまざまな形式にレンダリングします。  
- **ファイルをディスクに書き込まずに TeX を PNG に変換できますか？** はい – `MemoryStream` に TeX を渡し、PNG バイト列を直接取得できます。  
- **対応している .NET バージョンは？** 最新の .NET バージョンすべて (Framework 4.6+、.NET Core 3.1+、.NET 5/6)。  
- **本番環境で使用するにはライセンスが必要ですか？** 本番利用には商用ライセンスが必要です。無料トライアルも利用可能です。  
- **画像解像度は設定できますか？** `PngSaveOptions.Resolution` プロパティで DPI を指定できます（例: 300 dpi）。

## What is “convert tex to png”?

TeX を PNG に変換するとは、TeX マークアップ文字列（科学文書で使用される言語）をラスタ画像としてレンダリングすることを指します。数式や TeX 全体のページを Web ページ、モバイルアプリ、または TeX をネイティブにレンダリングできない環境に埋め込む際に便利です。

## Why generate image from TeX with Aspose.TeX?

- **外部依存が不要** – Aspose.TeX は純粋な .NET ライブラリなので、サーバーに TeX ディストリビューションをインストールする必要がありません。  
- **ストリーム対応 API** – `MemoryStream` と直接連携でき、クラウドサービスやマイクロサービスに最適です。  
- **細かな制御が可能** – 画像解像度、出力ディレクトリ、さらにはインタラクティブな端末入力の取得まで設定できます。  

## Prerequisites

コードに入る前に、以下を用意してください。

- 基本的な C# の知識。  
- Aspose.TeX for .NET がインストール済み – **[こちら](https://releases.aspose.com/tex/net/)** からダウンロードできます。  
- C# 開発環境 (Visual Studio、VS Code、Rider など)。  

## Import Namespaces

C# ファイルの先頭に必要な `using` 文を追加して、Aspose.TeX のクラスにアクセスできるようにします。

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Image;
using System.IO;
using System.Text;
```

## Step 1: Set Up Conversion Options

変換パイプラインを構成します。ここではアプリケーションをコンソール アプリとして扱い、入力/出力フォルダーを指定し、端末 I/O をルーティングし、300 dpi の PNG 出力を要求します。

```csharp
// ExStart:TakeMainInputFromStream-AuxFromFileSystem-TakeTerminalInputFromConsole-AlternativeImagesStorage
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
options.JobName = "stream-in-image-out";
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
options.TerminalIn = new InputConsoleTerminal();
options.TerminalOut = new OutputConsoleTerminal();
options.SaveOptions = new PngSaveOptions() { Resolution = 300 };
```

## Step 2: Create Image Device and Run the Job

`ImageDevice` がレンダリングされた PNG データを取得します。`MemoryStream` 経由で簡単な TeX スニペットを渡し、ジョブを実行して Aspose.TeX に処理させます。

```csharp
ImageDevice device = new ImageDevice();
TeXJob job = new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
    "\\hrule height 10pt width 95pt\\vskip10pt\\hrule height 5pt")),
    device, options);
job.Run();
```

## Step 3: Provide Input in the Console

コンソールのプロンプトが表示されたら **ABC** と入力し **Enter**、続いて **\end** と入力して再度 **Enter** を押します。これにより、TeX エンジン実行中に端末入力が取得できることを示します。

## Step 4: Fine‑Tune Output

ジョブが完了したらコンソールに改行を書き込み、デバイスから生の PNG バイト列を取得します。`result` 配列にはページごとに 1 つの PNG 画像が格納されています。

```csharp
options.TerminalOut.Writer.WriteLine();
byte[][] result = device.Result;
// ExEnd:TakeMainInputFromStream-AuxFromFileSystem-TakeTerminalInputFromConsole-AlternativeImagesStorage
```

これで `result[0]` をファイルに保存したり、ネットワーク経由で送信したり、UI コンポーネントに直接埋め込んだりできます。

## Common Issues and Solutions

| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **No PNG output** | `SaveOptions` が設定されていない、または解像度が 0 になっている。 | `options.SaveOptions = new PngSaveOptions() { Resolution = 300 };` を確実に設定してください。 |
| **Console hangs** | TeX 入力が `\end` で終了していない。 | 必ず TeX ストリームを `\end`（または `\stop`）で終端してください。 |
| **Incorrect image size** | デフォルト DPI が 96 になっている。 | `PngSaveOptions` の `Resolution` を上げてください。 |
| **File‑system paths not found** | 作業ディレクトリ文字列が誤っている。 | 絶対パスを使用するか、実行前にディレクトリが存在することを確認してください。 |

## Frequently Asked Questions

### Q1: Can I use Aspose.TeX for .NET in a non‑console application?

A1: Absolutely! Aspose.TeX works in desktop, web, and service‑oriented apps. You just replace the console terminals with custom streams or UI controls.

### Q2: How can I customize the output image resolution?

A2: In the example, the resolution is set via `PngSaveOptions.Resolution`. Change the integer value (e.g., `Resolution = 600`) to get higher‑quality PNGs.

### Q3: Is there a trial version available?

A3: Yes, you can explore Aspose.TeX with a free trial available **[here](https://releases.aspose.com/)**.

### Q4: Where can I find additional support and assistance?

A4: Visit the Aspose.TeX forum **[here](https://forum.aspose.com/c/tex/47)** for community support and discussions.

### Q5: How can I obtain a temporary license for Aspose.TeX?

A5: You can acquire a temporary license **[here](https://purchase.aspose.com/temporary-license/)**.

## Conclusion

You’ve now seen how to **convert TeX to PNG** using Aspose.TeX for C#. By configuring streams, setting up an `ImageDevice`, and handling terminal input, you can generate high‑resolution images from any TeX source—perfect for reports, web previews, or automated pipelines. Explore further by experimenting with different TeX snippets, adjusting DPI, or integrating the byte array into your own UI.

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.TeX 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}