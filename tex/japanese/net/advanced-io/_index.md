---
date: 2026-09-24
description: C# で Aspose.TeX for .NET を使用して、TeX 入力ディレクトリ、ストリーム、画像、端末入力の設定方法を学びます。
keywords:
- configure tex input directory
- add image stream tex
- add images from stream
lastmod: 2026-09-24
linktitle: 高度な Aspose.TeX 入力と出力
og_description: C# で Aspose.TeX for .NET を使用して、TeX 入力ディレクトリの設定、画像ストリームの追加、端末入力の処理方法をステップバイステップで学びます。
og_image_alt: Guide showing how to configure TeX input directory and streams in Aspose.TeX
  for .NET
og_title: TeX 入力ディレクトリの設定 – 高度な Aspose.TeX ガイド
schemas:
- author: Aspose
  dateModified: '2026-09-24'
  description: Learn how to configure TeX input directory, streams, images, and terminal
    input using Aspose.TeX for .NET in C#.
  headline: Configure TeX input directory – Advanced Aspose.TeX Input and Output
  type: TechArticle
- description: Learn how to configure TeX input directory, streams, images, and terminal
    input using Aspose.TeX for .NET in C#.
  name: Configure TeX input directory – Advanced Aspose.TeX Input and Output
  steps:
  - name: instantiate TeXInputOptions
    text: Assign the base folder that holds the primary TeX source.
  - name: add extra search paths
    text: If your project stores figures in a separate folder (e.g., *Images*), call
      `AddSearchPath` to include it.
  - name: hand the options to the processor
    text: Create a `TeXProcessor`, provide the configured options, and invoke `Process`
      or `Render`.
  type: HowTo
- questions:
  - answer: Yes—you can create a new `TeXInputOptions` instance with a different `BaseFolder`
      and pass it to a fresh `TeXProcessor` whenever you need to reconfigure.
    question: Can I change the input directory at runtime?
  - answer: Retrieve the image as a `byte[]`, wrap it in a `MemoryStream`, and call
      `TeXInputOptions.AddImage("image.png", stream)`. The name must match the reference
      in your `.tex` file.
    question: How do I add images that are stored in a database?
  - answer: Absolutely. Convert the incoming string to a `MemoryStream`, set it as
      the source for `TeXProcessor`, and render directly to your desired output format.
    question: Is it possible to process LaTeX code received from a web API without
      saving a file?
  - answer: Dispose of any streams you create, and for large workloads invoke `TeXProcessor.Cleanup()`
      to free native resources.
    question: Do I need to call any cleanup methods after processing?
  - answer: The two tutorial links above contain full code samples that demonstrate
      each scenario in detail, including error handling and performance tips.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.TeX .NET API
tags:
- Aspose.TeX
- input directory
- C# document processing
title: TeX 入力ディレクトリの設定 – 高度な Aspose.TeX 入力と出力
url: /ja/net/advanced-io/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.TeX for .NET で TeX 入力ディレクトリを構成する

Aspose.TeX for .NET を使用すると、C# アプリケーションにフル機能の TeX 処理を直接組み込むことができます。このチュートリアルでは、**TeX 入力ディレクトリを構成**する方法、ストリームから LaTeX コンテンツを供給する方法、ファイルシステムに触れずに画像を追加する方法を学びます。エンジンが `.tex` ファイルやリソースを検索する場所を正確に制御したい場合は、ここが適切な場所です。

## クイック回答
- **“configure tex input directory” とは何ですか？**  
  Aspose.TeX にメインの `.tex` ファイル、補助ファイル、グラフィックの場所を知らせます。
- **どのクラスが入力パスを定義しますか？**  
  `TeXInputOptions` はベースフォルダーと追加の検索場所を保持します。
- **メモリストリームから画像をロードできますか？**  
  はい — `TeXInputOptions.AddImage` を `Stream` インスタンスと共に使用します。
- **実行時に提供された LaTeX コードをコンパイルできますか？**  
  もちろんです — ソーステキストを含む `MemoryStream` をプロセッサに渡します。
- **本番環境で使用するにはライセンスが必要ですか？**  
  評価版以外のデプロイには有効な Aspose.TeX ライセンスが必要です。

## TeXInputOptions とは何ですか？
`TeXInputOptions` は TeX リソースのベースフォルダーと追加検索パスを定義する構成オブジェクトです。正しく設定すれば “file not found” エラーを防ぎ、アセットを整理された状態に保てます。

## TeX 入力ディレクトリを構成する方法
`TeXInputOptions` は TeX リソースのベースフォルダーと追加検索パスを指定する構成オブジェクトです。メインドキュメントをロードし、数行でプロセッサにすべての検索場所を指示できます。この直接的な回答は、追加の詳細に入る前に必要な手順を説明します。

`TeXInputOptions` のインスタンスを作成し、`BaseFolder` にプライマリ `.tex` ファイルがあるフォルダーを設定し、画像や補助ファイルを格納するサブフォルダーを追加し、オプションを `TeXProcessor` に渡します。エンジンは自動的にすべての相対参照を解決します。

### 手順 1: TeXInputOptions のインスタンス化
プライマリ TeX ソースが格納されているベースフォルダーを割り当てます。

### 手順 2: 追加検索パスを追加
プロジェクトが図を別のフォルダー（例: *Images*）に保存している場合は、`AddSearchPath` を呼び出してそれを含めます。

### 手順 3: オプションをプロセッサに渡す
`TeXProcessor` を作成し、設定したオプションを提供し、`Process` または `Render` を呼び出します。

## Aspose.TeX で画像を追加する方法
TeX ファイルで参照される画像は、フォルダー経由またはストリーム直接で提供できます。ストリームで供給することは、画像がデータベースに保存されている場合や動的に生成される場合に便利です。`AddImage(string name, Stream data)` は、指定されたファイル名で画像ストリームを TeX ドキュメントで使用できるように登録します。このメソッドにより、一時ファイルを回避し、処理速度が向上します。

## Aspose.TeX でストリームを処理する方法
LaTeX ソースが動的に生成される場合（ユーザー入力や Web サービスからの場合など）、ファイルに書き込まずに直接プロセッサに供給できます。`TeXProcessor` は TeX コンテンツを処理し、ソース LaTeX コードを含む `MemoryStream` を受け取れます。LaTeX 文字列を `MemoryStream` にラップし、`TeXProcessor` のソースストリームとして設定し、変換を実行します。この手法は、ディスク I/O が高コストなクラウドネイティブサービスでも同様に有効です。

## 高度な I/O に Aspose.TeX を使用する理由
Aspose.TeX は **30 以上の入力および出力フォーマット**（PDF、PNG、SVG など）をサポートし、ファイル全体をメモリにロードせずに数百ページにわたるドキュメントをレンダリングできます。ストリーム優先の設計により、ファイルベースのワークフローと比較して I/O オーバーヘッドを最大 40 % 削減し、高スループットのサーバーアプリケーションに最適です。

## 前提条件
- .NET 6.0 以降（ライブラリは .NET Core 3.1+ および .NET Framework 4.6.1+ でも動作します）
- Aspose.TeX for .NET NuGet パッケージ（バージョン 24.11 以上）
- 本番環境で使用するための有効な Aspose.TeX ライセンス

## Aspose.TeX を探求する：高度なドキュメント処理へのゲートウェイ
実際の設定を確認するには、ステップバイステップガイド **[Aspose.TeX の必須入力ディレクトリを指定する (C#)](./required-input-directory-csharp/)** に従ってください。そのチュートリアルでは `TeXInputOptions` オブジェクトの作成と PDF 出力のレンダリングを案内します。  
**[Aspose.TeX の必須入力ディレクトリを指定する (C#)](./required-input-directory-csharp/)**

## Aspose.TeX for C# におけるストリーム、画像、ターミナル入力のマスター
メモリから LaTeX を供給し、ストリームで画像を追加し、ターミナルスタイルの入力を使用する方法をさらに深く学ぶには、**[Aspose.TeX for C# におけるストリーム、画像、ターミナル入力のマスター](./stream-input-image-output-terminal-input-csharp/)** をご覧ください。このチュートリアルは、Aspose.TeX を Web API、バックグラウンドサービス、コンソールツールに統合する方法を示します。  
**[Aspose.TeX for C# におけるストリーム、画像、ターミナル入力のマスター](./stream-input-image-output-terminal-input-csharp/)**

## よくある問題と解決策
- **“File not found” エラー** – `BaseFolder` が正しいディレクトリを指していること、追加の検索パスがレンダリング前に追加されていることを確認してください。
- **画像が読み込めない** – `AddImage` の画像名が TeX ソースで使用されている名前（拡張子含む）と完全に一致していることを確認してください。
- **メモリ使用量の急増** – 非常に大きなドキュメントを処理する場合、レンダリング後に `TeXProcessor.Cleanup()` を呼び出してアンマネージドリソースを解放してください。

## よくある質問

**Q: 実行時に入力ディレクトリを変更できますか？**  
A: はい — 必要に応じて異なる `BaseFolder` を持つ新しい `TeXInputOptions` インスタンスを作成し、再構成が必要なときに新しい `TeXProcessor` に渡すことができます。

**Q: データベースに保存されている画像を追加するにはどうすればよいですか？**  
A: 画像を `byte[]` として取得し、`MemoryStream` でラップして `TeXInputOptions.AddImage("image.png", stream)` を呼び出します。名前は `.tex` ファイルで参照されているものと一致している必要があります。

**Q: Web API から受け取った LaTeX コードをファイルに保存せずに処理できますか？**  
A: もちろんです。受信した文字列を `MemoryStream` に変換し、`TeXProcessor` のソースとして設定し、希望の出力フォーマットに直接レンダリングします。

**Q: 処理後にクリーンアップメソッドを呼び出す必要がありますか？**  
A: 作成したストリームはすべて破棄し、大規模なワークロードの場合は `TeXProcessor.Cleanup()` を呼び出してネイティブリソースを解放してください。

**Q: もっと高度な例はどこで見つけられますか？**  
A: 上記の 2 つのチュートリアルリンクには、エラーハンドリングやパフォーマンスのヒントを含む各シナリオを詳細に示す完全なコードサンプルが含まれています。

---

**最終更新日:** 2026-09-24  
**テスト環境:** Aspose.TeX 24.11 for .NET  
**作者:** Aspose

## 関連チュートリアル

- [Aspose.TeX API を使用して TeX ファイルストリームを取得する (C#) 必要な入力ディレクトリ](/tex/net/advanced-io/required-input-directory-csharp/)
- [ファイルシステムで TeX から XPS を作成 – Aspose.TeX for .NET](/tex/net/file-input-output/filesystem-input-xps-output/)
- [Aspose.TeX for .NET を使用して LaTeX を PNG に変換 – ファイルシステムと ZIP 入力を処理](/tex/net/file-input-output/required-inputs-from-filesystem-and-zip/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}