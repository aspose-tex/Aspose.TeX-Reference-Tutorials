---
title: ジョブ名をオーバーライドしてターミナル出力を Zip に書き込む (C#)
linktitle: ジョブ名をオーバーライドしてターミナル出力を Zip に書き込む (C#)
second_title: Aspose.TeX .NET API
description: Aspose.TeX for .NET を使用してジョブ名をオーバーライドし、ターミナル出力を ZIP ファイルに書き込む方法を学びます。 C# の例を含むステップバイステップのガイド。
weight: 11
url: /ja/net/job-output/override-job-name-zip-output-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ジョブ名をオーバーライドしてターミナル出力を Zip に書き込む (C#)

## 導入

このチュートリアルでは、Aspose.TeX for .NET を使用してジョブ名をオーバーライドし、ターミナル出力を ZIP ファイルに書き込む方法を検討します。 Aspose.TeX は、開発者が .NET アプリケーションで TeX ドキュメントを操作できるようにする強力なライブラリです。この特定の例では、ジョブ名をオーバーライドする機能を備えたターミナル出力を ZIP ファイルに書き込むという一般的なタスクに焦点を当てます。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

- C# の実用的な知識
- Aspose.TeX for .NET がインストールされている
- 作業ディレクトリの ZIP アーカイブを入力します
- ターミナル出力用の ZIP アーカイブを出力する

## 名前空間のインポート

コードに入る前に、必要な名前空間が C# プロジェクトに含まれていることを確認してください。

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Pdf;
using System.IO;
```

ここで、プロセスをガイドするために例を複数のステップに分けてみましょう。

## ステップ 1: 入力および出力 ZIP ストリームを開く

```csharp
using (Stream inZipStream = File.Open(Path.Combine("Your Input Directory", "zip-in.zip"), FileMode.Open))
using (Stream outZipStream = File.Open(Path.Combine("Your Output Directory", "terminal-out-to-zip.zip"), FileMode.Create))
{
    //ステップ 1 のコードはここにあります
}
```

## ステップ 2: 変換オプションを設定する

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
options.JobName = "terminal-output-to-zip";
options.InputWorkingDirectory = new InputZipDirectory(inZipStream, "in");
options.OutputWorkingDirectory = new OutputZipDirectory(outZipStream);
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## ステップ 3: 保存オプションを定義する

```csharp
options.SaveOptions = new PdfSaveOptions();
```

## ステップ 4: TeX ジョブを実行する

```csharp
new TeXJob("hello-world", new PdfDevice(), options).Run();
```

## ステップ 5: 出力 ZIP アーカイブを完成させる

```csharp
((OutputZipDirectory)options.OutputWorkingDirectory).Finish();
```

## 結論

おめでとう！ Aspose.TeX for .NET を使用してジョブ名をオーバーライドし、ターミナル出力を ZIP ファイルに書き込む方法を学習しました。このテクニックは、C# アプリケーションで TeX ドキュメントを扱うときに非常に役立ちます。

## よくある質問

### Q1: Aspose.TeX for .NET を VB.NET などの他の .NET 言語で使用できますか?

A1: はい、Aspose.TeX for .NET はすべての .NET 言語と互換性があります。

### Q2: Aspose.TeX for .NET のドキュメントはどこで入手できますか?

 A2: にアクセスしてください。[ドキュメンテーション](https://reference.aspose.com/tex/net/)詳細については。

### Q3: Aspose.TeX の一時ライセンスを取得するにはどうすればよいですか?

 A3: を入手してください。[仮免許](https://purchase.aspose.com/temporary-license/)テスト目的のため。

### Q4: Aspose.TeX サポートのためのコミュニティ フォーラムはありますか?

 A4: はい、参加してください。[Aspose.TeX フォーラム](https://forum.aspose.com/c/tex/47)コミュニティサポートのために。

### Q5: Aspose.TeX for .NET はどこで購入できますか?

 A5: Aspose.TeX を購入できます。[ここ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
