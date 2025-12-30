---
date: 2025-12-30
description: Aspose.TeX を使用して .NET で TeX を XPS に変換する方法を学びましょう。シームレスな統合と信頼できる出力のために、このステップバイステップガイドに従ってください。
linktitle: How to Convert TeX to XPS in .NET
second_title: Aspose.TeX .NET API
title: .NETでTeXをXPSに変換する方法
url: /ja/net/xps-output/typeset-tex-to-xps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NETでTeXをXPSに変換する方法

## TeXをXPSに変換する方法 – はじめに

Welcome to our comprehensive, step‑by‑step guide on **how to convert TeX** documents into XPS format within a .NET environment. Using the powerful Aspose.TeX library, you’ll be able to integrate TeX‑to‑XPS conversion into any .NET application—whether it’s a desktop tool, a web service, or an automated reporting pipeline. In the sections that follow we’ll walk through every required setting, show you the exact code you need, and explain why each piece matters, so you can implement the solution with confidence.

## クイック回答
- **このチュートリアルでカバーする内容は？** Aspose.TeX for .NET を使用した TeX ファイルの XPS への変換。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **ライセンスは必要ですか？** テストには無料トライアルで動作しますが、製品版には商用ライセンスが必要です。  
- **実装にどれくらい時間がかかりますか？** 基本的な変換で通常 15 分未満です。  
- **ライブラリはどこで入手できますか？** 公式 Aspose.TeX リリースページからダウンロードしてください。

## 前提条件

Before we dive into the tutorial, make sure you have the following prerequisites in place:

- Aspose.TeX for .NET: Aspose.TeX ライブラリがインストールされていることを確認してください。ダウンロードは[here](https://releases.aspose.com/tex/net/)から。  
- ドキュメント: ライブラリについては、ドキュメント[here](https://reference.aspose.com/tex/net/)を参照して理解してください。  
- 入出力ディレクトリ: サンプルコードで指定された入力ディレクトリと出力ディレクトリを設定してください。

Now that you have everything set up, let's proceed with the step‑by‑step guide.

## 名前空間のインポート

In your .NET application, begin by importing the necessary namespaces. This ensures that you have access to the Aspose.TeX functionalities required for typesetting TeX to XPS.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
```

## 手順 1: 変換オプションの設定

Define the conversion options, specifying the ObjectTeX format upon the ObjectTeX engine extension. Also, set the job name, input and output directories, and terminal output details.

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

## 手順 2: XPS ドキュメントストリームの作成

Open a stream to write the typeset XPS document. The file name is not necessarily the same as the job name.

```csharp
using (Stream stream = File.Open(Path.Combine("Your Output Directory", options.JobName + ".xps"), FileMode.Create))
```

## 手順 3: TeX ジョブの実行

Initiate and run the TeX job, specifying the document name, XpsDevice, and conversion options.

```csharp
new TeXJob("hello-world", new XpsDevice(stream), options).Run();
```

Congratulations! You've successfully typeset TeX to XPS in .NET using Aspose.TeX. Feel free to explore more features and options based on your specific requirements.

## 結論

In this tutorial, we covered the essential steps to seamlessly convert TeX documents to XPS format in .NET using Aspose.TeX. By following this guide, you've gained valuable insights into the library's capabilities and how to leverage them for your projects.

## FAQ

### Q1: Aspose.TeX は .NET Core と互換性がありますか？

A1: はい、Aspose.TeX は .NET Core と完全に互換性があります。

### Q2: Aspose.TeX を商用プロジェクトで使用できますか？

A2: もちろんです！Aspose.TeX は商用・個人利用の両方で利用可能です。

### Q3: 追加のサンプルやリソースはどこで見つけられますか？

A3: 詳細なサンプルやリソースは、Aspose.TeX ドキュメント[here](https://reference.aspose.com/tex/net/)をご覧ください。

### Q4: Aspose.TeX のサポートはどのように受けられますか？

A4: コミュニティからの支援は、Aspose.TeX サポートフォーラム[here](https://forum.aspose.com/c/tex/47)をご利用ください。

### Q5: 無料トライアルはありますか？

A5: はい、無料トライアルは[here](https://releases.aspose.com/)から利用できます。

## よくある質問

**Q: XPS 出力（例: ページサイズや余白）をカスタマイズできますか？**  
A: はい。変換前に XpsDevice の設定を調整するか、TeX ソースを変更してページレイアウトを制御できます。

**Q: 入力 TeX ファイルにエラーが含まれている場合はどうなりますか？**  
A: 変換プロセスはエラー詳細を端末出力ファイル（`*.trm`）に書き込みます。このファイルを確認して問題を診断・修正してください。

**Q: 1 回の実行で複数の TeX ファイルを変換できますか？**  
A: TeX ソースファイルのコレクションをループし、各ファイルごとに別々の TeXJob を作成しながら、同じ `TeXOptions` インスタンスを再利用できます。

**Q: Aspose.TeX は `amsmath` や `graphicx` などの LaTeX パッケージをサポートしていますか？**  
A: ほとんどの標準 LaTeX パッケージがサポートされています。互換性のあるパッケージの完全なリストは公式ドキュメントをご確認ください。

**Q: 生成された XPS ファイルにフォントを埋め込むにはどうすればよいですか？**  
A: Aspose.TeX は TeX エンジンが使用するフォントを自動的に埋め込みます。変換を実行するマシンに必要なフォントがインストールされていることを確認してください。

---

**最終更新日:** 2025-12-30  
**テスト環境:** Aspose.TeX for .NET 24.11  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}