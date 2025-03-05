---
title: .NET での TeX から XPS への植字
linktitle: .NET での TeX から XPS への植字
second_title: Aspose.TeX .NET API
description: Aspose.TeX を使用すると、.NET で TeX ドキュメントを XPS に簡単に変換できます。シームレスな統合エクスペリエンスについては、ステップバイステップのガイドを参照してください。
type: docs
weight: 10
url: /ja/net/xps-output/typeset-tex-to-xps/
---
## 導入

強力な Aspose.TeX ライブラリを使用して、.NET で TeX を XPS にタイプセットするためのステップバイステップ ガイドへようこそ。 .NET アプリケーションで TeX ドキュメントを XPS 形式にシームレスに変換したい場合は、ここが適切な場所です。このチュートリアルでは、スムーズな実装を保証するために各ステップに分けてプロセス全体を説明します。

## 前提条件

チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。

-  Aspose.TeX for .NET: Aspose.TeX ライブラリがインストールされていることを確認してください。ダウンロードできます[ここ](https://releases.aspose.com/tex/net/).

- ドキュメント: ドキュメントを参照してライブラリについてよく理解してください。[ここ](https://reference.aspose.com/tex/net/).

- 入力ディレクトリと出力ディレクトリ: コード例で指定されているように、入力ディレクトリと出力ディレクトリを設定します。

すべての設定が完了したので、ステップバイステップのガイドに進みましょう。

## 名前空間のインポート

.NET アプリケーションで、必要な名前空間をインポートすることから始めます。これにより、TeX を XPS に植字するために必要な Aspose.TeX 機能に確実にアクセスできるようになります。

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
```

## ステップ 1: 変換オプションを設定する

変換オプションを定義し、ObjectTeX エンジン拡張で ObjectTeX 形式を指定します。また、ジョブ名、入出力ディレクトリ、ターミナル出力の詳細を設定します。

```csharp
//ObjectTeX エンジン拡張時にデフォルトの ObjectTeX 形式の変換オプションを作成します。
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
//ジョブ名を指定します。
options.JobName = "external-file-stream";
//入力用のファイル システムの作業ディレクトリを指定します。
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
//出力用のファイル システムの作業ディレクトリを指定します。
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
//端末出力を出力作業ディレクトリ内のファイルに書き込む必要があることを指定します。
//ファイル名は<ジョブ名>.trmです。
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## ステップ 2: XPS ドキュメント ストリームを作成する

ストリームを開いてタイプセット XPS ドキュメントを書き込みます。ファイル名はジョブ名と同じである必要はありません。

```csharp
using (Stream stream = File.Open(Path.Combine("Your Output Directory", options.JobName + ".xps"), FileMode.Create))
```

## ステップ 3: TeX ジョブを実行する

ドキュメント名、XpsDevice、および変換オプションを指定して、TeX ジョブを開始して実行します。

```csharp
new TeXJob("hello-world", new XpsDevice(stream), options).Run();
```

おめでとう！ Aspose.TeX を使用して .NET で TeX を XPS にタイプセットすることに成功しました。特定の要件に基づいて、さらに多くの機能やオプションを自由に探索してください。

## 結論

このチュートリアルでは、Aspose.TeX を使用して .NET で TeX ドキュメントを XPS 形式にシームレスに変換するための重要な手順について説明しました。このガイドに従うことで、ライブラリの機能とそれをプロジェクトに活用する方法についての貴重な洞察が得られます。

## よくある質問

### Q1: Aspose.TeX は .NET Core と互換性がありますか?

A1: はい、Aspose.TeX は .NET Core と完全な互換性があります。

### Q2: Aspose.TeX を商用プロジェクトに使用できますか?

A2：もちろんです！ Aspose.TeX は商用利用と個人利用の両方で利用できます。

### Q3: 追加の例やリソースはどこで入手できますか?

 A3: Aspose.TeX ドキュメントを参照してください。[ここ](https://reference.aspose.com/tex/net/)より多くの例と詳細なリソースについては、こちらをご覧ください。

### Q4: Aspose.TeX のサポートを受けるにはどうすればよいですか?

 A4: Aspose.TeX サポート フォーラムにアクセスしてください。[ここ](https://forum.aspose.com/c/tex/47)コミュニティから支援を得るため。

### Q5: 無料トライアルはありますか?

 A5: はい、無料トライアルにアクセスできます。[ここ](https://releases.aspose.com/).