---
date: 2026-03-26
description: Aspose.TeX for .NET を使用して TeX から XPS を作成し、ファイルシステムの入出力を管理し、高品質な XPS ドキュメントを生成する方法を学びましょう。
linktitle: Create XPS from TeX with Filesystems – Aspose.TeX for .NET
second_title: Aspose.TeX .NET API
title: ファイルシステムで TeX から XPS を作成 – Aspose.TeX for .NET
url: /ja/net/file-input-output/filesystem-input-xps-output/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ファイルシステムを使用して TeX から XPS を作成 – Aspose.TeX for .NET

## Introduction

ようこそ！このチュートリアルでは、Aspose.TeX for .NET を使用してファイルシステムの入出力と連携しながら **TeX から XPS を作成する方法** を学びます。バッチプロセッサ、Web サービス、デスクトップユーティリティのいずれを構築する場合でも、以下の手順に従ってエンジンの設定、ファイルへのパス指定、そして元の LaTeX ソースとまったく同じレイアウトの XPS ドキュメントの生成が行えます。

プロセスは分かりやすい番号付きステップに分割し、各コード行の「なぜ」を解説し、すぐに活用できる実践的なヒントを提供します。

## Quick Answers
- **“create XPS from TeX” とは何ですか？** Aspose.TeX ジョブを構成し、TeX ファイルを読み取って結果を XPS ドキュメントとして書き出すことを指します。  
- **ライセンスは必要ですか？** テスト用の一時ライセンスは利用可能です。製品環境ではフルライセンスが必要です。  
- **対応している .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。  
- **出力形式を変更できますか？** はい – `XpsDevice` を別のデバイス（PDF、PNG など）に置き換えるだけです。  
- **コンソール出力は必須ですか？** いいえ – メモリターミナルを使用すればサイレント実行が可能です。

## How to create XPS from TeX using Aspose.TeX

TeX ジョブで XPS を出力するには、Aspose.TeX エンジンを初期化し、ソースファイルの読み取り先を指定し、レンダリングされたページを XPS パッケージに書き込むよう指示します。XPS（XML Paper Specification）は固定レイアウト形式で、タイポグラフィとベクターグラフィックを正確に保持するため、印刷やさらに別の形式への変換に最適です。

## What is “create tex job xps”?

TeX ジョブで XPS を出力するには、Aspose.TeX エンジンを初期化し、ソースファイルの読み取り先を指定し、レンダリングされたページを XPS パッケージに書き込むよう指示します。XPS（XML Paper Specification）は固定レイアウト形式で、タイポグラフィとベクターグラフィックを正確に保持するため、印刷やさらに別の形式への変換に最適です。

## Why use Aspose.TeX for XPS output?

- **高忠実度:** エンジンは LaTeX のレイアウトを XPS に正確に再現します。  
- **外部依存なし:** 純粋な .NET ライブラリで、ネイティブ LaTeX のインストールは不要です。  
- **柔軟な I/O:** ファイルシステムディレクトリ、メモリストリーム、またはカスタムプロバイダーと連携できます。  
- **スケーラビリティ:** 単一ファイル変換から大量バッチ処理パイプラインまで対応可能です。

## Prerequisites

以下を事前に用意してください。

- **Aspose.TeX for .NET** – 最新バージョンは [Aspose website](https://releases.aspose.com/tex/net/) からダウンロードしてください。  
- **.NET 開発環境** – Visual Studio、Rider、または .NET SDK がインストールされた VS Code。  
- **入力・出力フォルダー** – マシン上に 2 つのディレクトリを作成します（例: `C:\TeX\Input` と `C:\TeX\Output`）。  
- **ライセンス（テスト用は任意）** – Aspose ポータルから一時ライセンスを取得できます。

## Import Namespaces

まず、ファイルシステムヘルパーと XPS デバイスにアクセスできるよう、必要な名前空間をインポートします。

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

これらの名前空間は `InputFileSystemDirectory`、`OutputFileSystemDirectory`、`XpsDevice` を公開し、**create XPS from TeX** ワークフローに必須です。

## Step 1: Create Conversion Options

エンジンに ObjectTeX 設定（ほとんどの LaTeX ソースのデフォルト）を使用させるため、`TeXOptions` オブジェクトを構築します。

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

> **Pro tip:** `ConsoleAppOptions` はコンソール向けアプリケーションの妥当なデフォルトを設定しますが、必要に応じて後からオプションをカスタマイズできます。

## Step 2: Specify Input and Output Directories

先ほど作成したフォルダーをエンジンに指示します。プレースホルダー文字列は実際のパスに置き換えてください。

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

これで TeX ジョブは `.tex` ファイルの所在と生成された XPS ファイルの出力先を認識します。

## Step 3: Choose an Output Terminal

ターミナルはステータスメッセージの出力先を制御します。デバッグのためにコンソールを使用しますが、サイレント実行したい場合はメモリターミナルに切り替えられます。

```csharp
options.TerminalOut = new OutputConsoleTerminal(); // Default value. Arbitrary assignment.
```

> **Why this matters:** コンソールターミナルを使用すると、コンパイル時の警告やエラーが即座に確認でき、トラブルシューティングが迅速になります。

## Step 4: Run the TeX Job

`TeXJob` インスタンスを作成し、わかりやすい名前を付け、`XpsDevice` を添付して実行します。

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

`Run()` が完了すると、出力ディレクトリに `hello-world.xps` ファイルが生成されます。

## Step 5: Fine‑Tune the Console Output

ジョブ完了後に空行を追加すると、特にバッチで複数ジョブを実行する際にコンソールログが見やすくなります。

```csharp
options.TerminalOut.Writer.WriteLine();
```

## Common Use Cases

| Scenario | Why XPS? | How the snippet helps |
|----------|----------|-----------------------|
| **学術論文のバッチ変換** | アーカイブ印刷のために正確なレイアウトを保持したい。 | ファイルシステムベースのアプローチにより、フォルダー内の `.tex` ファイル群を対象に同名の XPS ファイルを一括生成できます。 |
| **オンデマンドで LaTeX をレンダリングする Web サービス** | XPS は対応ブラウザーへ直接ストリーム配信可能。 | `XpsDevice` をメモリストリームに置き換えるだけで、ディスクに書き込まずにドキュメントを返せます。 |
| **デスクトップ出版ツール** | PDF 変換前に固定レイアウトのプレビューが必要。 | 同じジョブを後続で PDF デバイスにチェーンすれば、最終配布用の PDF を生成できます。 |

## Common Issues and Solutions

| Issue | Cause | Fix |
|-------|-------|-----|
| **XPS ファイルが空** | 出力ディレクトリのパスが間違っている、または書き込み権限がない。 | `OutputFileSystemDirectory` に渡すパスを確認し、プロセスに書き込み権限があることを確認してください。 |
| **コンパイルエラー** | LaTeX ソースが ObjectTeX に含まれないパッケージを使用している。 | `TeXConfig.FullTeX()` などフル TeX エンジン構成に切り替えるか、必要なパッケージファイルを入力ディレクトリに追加してください。 |
| **コンソールがハングする** | 対話プロンプト待ちのターミナルが原因。 | `OutputMemoryTerminal` を使用して対話プロンプトを抑制し、スクリプトの自動実行を可能にします。 |

## Frequently Asked Questions

**Q1: XPS 以外の出力形式に変更できますか？**  
A1: はい、Aspose.TeX は PDF、PNG、SVG など多数の形式をサポートしています。`new XpsDevice()` を目的のデバイスクラス（例: `new PdfDevice()`）に置き換えるだけです。

**Q2: テスト用の一時ライセンスは入手できますか？**  
A2: はい、[このリンク](https://purchase.aspose.com/temporary-license/) からテスト用の一時ライセンスを取得できます。

**Q3: 追加のドキュメントはどこで確認できますか？**  
A3: 詳細は [Aspose.TeX for .NET documentation](https://reference.aspose.com/tex/net/) を参照してください。

**Q4: コミュニティサポートや質問はどこで受けられますか？**  
A4: [Aspose.TeX forum](https://forum.aspose.com/c/tex/47) でコミュニティサポートやディスカッションが行われています。

**Q5: サンプルプロジェクトはありますか？**  
A5: Aspose.TeX の GitHub リポジトリでサンプルプロジェクトやコードスニペットを確認できます。

## Conclusion

上記の手順に従うことで、Aspose.TeX for .NET を使用して **TeX から XPS を作成** し、入力・出力フォルダーを管理し、開発・本番シナリオの両方に合わせてプロセスを微調整できるようになりました。ぜひ他の出力デバイスでも試したり、より大規模なワークフローに組み込んだり、バッチ変換を自動化してみてください。

---

**Last Updated:** 2026-03-26  
**Tested With:** Aspose.TeX 24.11 for .NET (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}