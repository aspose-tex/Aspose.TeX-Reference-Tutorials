---
date: 2026-10-19
description: Aspose.TeX for .NET を使用して tex ドキュメントの生成、カスタム tex フォーマットの作成、tex 入力ディレクトリの設定方法を学びます。コードスニペットとトラブルシューティングのヒントを含むステップバイステップガイドです。
keywords:
- tex document generation
- create custom tex format
- set tex input directory
- custom tex macros
lastmod: 2026-10-19
linktitle: .NET でカスタム TeX フォーマットを作成する
og_description: Aspose.TeX を使用した tex ドキュメント生成により、.NET でカスタム tex フォーマットを作成し、tex 入力ディレクトリを設定できます。XPS、PDF、または
  PNG 出力のためのガイドに従ってください。
og_image_alt: Developer guide showing tex document generation using Aspose.TeX in
  .NET
og_title: .NET で tex ドキュメント生成とフォーマットの方法
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
title: .NET で tex ドキュメント生成とフォーマットの方法
url: /ja/net/custom-tex-formats/create-custom-tex-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET でフォーマット付き tex ドキュメント生成を行う方法

## クイック回答
- **“create custom tex format” とは何ですか？** 独自の TeX エンジン構成とコンパイル済みフォーマットファイルを定義し、プロセッサがマクロや設定に従うようにすることです。  
- **どのライブラリが必要ですか？** Aspose.TeX for .NET、30 以上の入力および出力フォーマットをサポートします。  
- **tex 入力ディレクトリを設定する必要がありますか？** はい – `InputWorkingDirectory` を使用してエンジンに補助ファイルの場所を指示します。  
- **どのような出力が生成できますか？** XPS、PDF、PNG、TIFF など多数のデバイス形式。  
- **本番環境でライセンスは必要ですか？** 商用デプロイには有効な Aspose.TeX ライセンスが必須です。

## カスタム tex フォーマットとは？
カスタム tex フォーマットは、TeX プロセッサが起動時に読み込む、マクロとエンジン設定を事前にコンパイルしたコレクションです。これを作成すると、企業のブランディングを埋め込んだり、レイアウト基準を強制したり、繰り返し使用するドキュメントのコンパイル時間を短縮したりできます。生成されるすべてのドキュメントで一貫したスタイルを実現し、複雑な組版ワークフローの保守性を向上させます。

## tex 入力ディレクトリを設定する理由
**tex 入力ディレクトリ** を設定すると、スタイルファイル、カスタムフォント、追加マクロパッケージなどの補助ファイルの所在をエンジンに知らせることができます。これにより「ファイルが見つかりません」エラーが回避され、プロジェクトフォルダーが整理されます。また、すべてのリソースが既知の場所から解決されるため、ビルドの再現性も向上します。

## 前提条件

開始する前に以下を確認してください。

1. **Aspose.TeX for .NET** – [Aspose.TeX のウェブサイト](https://releases.aspose.com/tex/net/) からダウンロード。  
2. **.NET 開発環境**（Visual Studio、VS Code、または .NET CLI）。  
3. （オプション）本番利用向けの有効な **Aspose.TeX ライセンス**。

## 名前空間のインポート

以下の名前空間で Aspose.TeX のコア クラスにアクセスできます。  
`Document` 系クラスは `Aspose.TeX` に、オプションやデバイスは `Aspose.TeX.Rendering` にあります。

`Document` クラスは、メモリ内の単一 TeX ドキュメントを表すトップレベル オブジェクトです。

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using Aspose.TeX.ResourceProviders;
using System.IO;
using System.Text;
```

## 手順 1: フォーマットプロバイダーの作成

`FormatProvider` は、コンパイル済みフォーマット ファイル（`customtex.fmt`）の所在をエンジンに伝えます。`"Your Output Directory"` をカスタムフォーマットを含む絶対パスに置き換えてください。

`FormatProvider` は `.fmt` ファイルを一度だけ読み込み、すべての変換で再利用する軽量ラッパーであり、バッチ ジョブのパフォーマンスを大幅に向上させます。

```csharp
using (FormatProvider formatProvider =
    new FormatProvider(new InputFileSystemDirectory("Your Output Directory"), "customtex"))
{
```

## 手順 2: 変換オプションの設定（tex 入力ディレクトリも設定）

ここでは `TeXOptions` インスタンスを構築します。`InputWorkingDirectory` プロパティは **tex 入力ディレクトリ** を設定し、エンジンがカスタム パッケージやフォントなどの補助ファイルを見つけられるようにします。

`TeXOptions` では出力デバイス、ページサイズ、レンダリング品質も指定できます。大規模生成の場合は `EnableParallelProcessing` を有効にしてマルチコア サーバーでのレンダリングを高速化できます。

```csharp
    TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX(formatProvider));
    options.JobName = "typeset-with-custom-format";
    options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
    options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

## 手順 3: ジョブの実行

簡単な TeX 文字列をエンジンに渡し、出力デバイス（この例では XPS）を選択してジョブを実行します。`TeXEngine` はカスタムフォーマットを読み込み、ソースを処理し、選択したデバイスに結果を書き込みます。

`TeXEngine` は Aspose.TeX のコア プロセッサで、TeX ソースを解析し、カスタムフォーマットを適用し、指定されたデバイスへレンダリングされたページをストリームします。

```csharp
    new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
        "Congratulations! You have successfully typeset this text with your own TeX format!\\end")),
        new XpsDevice(), options).Run();
```

## 手順 4: ターミナル出力の整形

ジョブ完了後に空行を追加すると、コンソール ログが見やすくなり、スクリプトで複数の変換を連結したときに便利です。

`Console.WriteLine()` は標準出力ストリームにテキスト行を書き込みます。これは視覚的な区切りのためだけに使用され、生成されたドキュメントには影響しません。

```csharp
    options.TerminalOut.Writer.WriteLine();
}
// ExEnd:TypesetWithCustomTeXFormat
```

おめでとうございます！これで **カスタム tex フォーマット** を作成し、.NET で **tex ドキュメント生成** に使用できました。`XpsDevice` を `PdfDevice`、`PngDevice`、または他のサポートデバイスに置き換えて、配信ニーズに合わせて出力形式を変更できます。

## よくある問題と解決策

| 問題 | 原因 | 対策 |
|-------|--------|-----|
| *“Format file not found”* | `FormatProvider` のパスが間違っている | `"Your Output Directory"` に `customtex.fmt` が存在し、パスが絶対パスまたは実行ファイルからの相対パスであることを確認してください。 |
| *“Cannot find input file”* | `InputWorkingDirectory` が誤ったフォルダーを指している | `"Your Input Directory"` に TeX ソース ファイルがあるか、例のようにストリームでソースを渡していることを確認してください。 |
| *Terminal output garbled* | エンコーディングの不一致 | TeX ソースに非 ASCII 文字が含まれる場合は `Encoding.UTF8` を使用してください。 |
| *XPS file is empty* | 前段の例外によりジョブが実行されていない | コンソールのエラーメッセージを確認してください。多くの場合、パッケージの欠如や TeX 文字列の構文エラーが原因です。 |

## FAQ

**Q1: Aspose.TeX for .NET を他の Aspose ライブラリと併用できますか？**  
A: はい、Aspose.TeX は Aspose.PDF、Aspose.Words、その他の Aspose 製品とシームレスに統合でき、エンドツーエンドのドキュメント パイプラインを構築できます。

**Q2: Aspose.TeX for .NET の無料トライアルはありますか？**  
A: はい、**Aspose.TeX 無料トライアル ダウンロードページ** からダウンロードできます (https://releases.aspose.com/tex/net/)。

**Q3: Aspose.TeX for .NET のサポートはどこで受けられますか？**  
A: コミュニティ支援は [Aspose.TeX フォーラム](https://forum.aspose.com/c/tex/47) で、プレミアムオプションは **プレミアムサポート購入ページ** (https://purchase.aspose.com/buy) をご覧ください。

**Q4: Aspose.TeX for .NET の一時ライセンスは利用できますか？**  
A: はい、**一時ライセンス申請ページ** (https://purchase.aspose.com/temporary-license/) からリクエストできます。

**Q5: 公式 API リファレンスはどこにありますか？**  
A: 詳細なドキュメントは **API リファレンス ドキュメント** (https://reference.aspose.com/tex/net/) に掲載されています。

### 追加 Q&A

**Q: XPS ではなく PDF を出力できますか？**  
A: もちろんです。`new XpsDevice()` を `new PdfDevice()` に置き換え、出力パスを適切に変更してください。

**Q: フォーマット ファイルを変更したら毎回再コンパイルが必要ですか？**  
A: はい。マクロやエンジン設定を変更した場合は、`tex -ini` を再実行して新しい `.fmt` ファイルを生成する必要があります。

## 結論

Aspose.TeX for .NET は **tex ドキュメント生成のための堅牢で高性能なソリューション** を提供し、**カスタム tex フォーマットの作成**、**tex 入力ディレクトリの設定**、任意のサポートデバイスへの出力を可能にします。上記手順を CI/CD パイプラインに組み込めば、大規模レポートの自動生成や、組織のブランディング基準を満たすカスタム出版エンジンの構築が実現できます。

---

**最終更新日:** 2026-10-19  
**テスト環境:** Aspose.TeX 24.11 for .NET  
**作者:** Aspose

## 関連チュートリアル

- [Get TeX File Stream (C#) Using Aspose.TeX API Required Input Directory](/tex/net/advanced-io/required-input-directory-csharp/)
- [How to Create PDF with Aspose.TeX for .NET – Step by Step](/tex/net/pdf-output/)
- [How to create XPS document .NET – Convert TeX to XPS Output with Aspose.TeX for .NET](/tex/net/xps-output/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}