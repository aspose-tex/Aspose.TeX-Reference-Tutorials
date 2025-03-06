---
title: Aspose.TeX を使用して LaTeX 図を SVG にレンダリングする (C#)
linktitle: Aspose.TeX を使用して LaTeX 図を SVG にレンダリングする (C#)
second_title: Aspose.TeX .NET API
description: Aspose.TeX を使用して .NET でのドキュメント レンダリングを強化します。数式をシームレスに統合するために、LaTeX 図を C# で SVG にレンダリングする方法を学びます。
weight: 11
url: /ja/net/render-latex-figures/svg-latex-figure-renderer-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.TeX を使用して LaTeX 図を SVG にレンダリングする (C#)

## 導入

LaTeX Figure を使用して .NET でのドキュメント レンダリング機能を強化したい場合は、Aspose.TeX が最適なソリューションです。このステップバイステップ ガイドでは、C# で Aspose.TeX を使用して LaTeX Figure を SVG にレンダリングする手順を説明します。このチュートリアルを終えると、プロセスを明確に理解し、高品質な数式や図をドキュメントにシームレスに組み込むことができるようになります。

## 前提条件

チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。

- C# プログラミング言語の基本的な知識。
-  Aspose.TeX for .NET ライブラリがインストールされています。ダウンロードできます[ここ](https://releases.aspose.com/tex/net/).

## 名前空間のインポート

C# コードで、必要な名前空間を必ずインポートしてください。

```csharp
using Aspose.TeX.Features;
```

ここで、チュートリアルを複数のステップに分けてみましょう。

## ステップ 1: レンダリング オプションを作成する

```csharp
FigureRendererOptions options = new SvgFigureRendererOptions();
options.Preamble = "\\usepackage{pict2e}";
options.Scale = 3000;
options.BackgroundColor = Color.White;
options.LogStream = new System.IO.MemoryStream();
options.ShowTerminal = true;
```

ここでは、プリアンブル、スケール係数、背景色、ログ ストリーム、および端末出力を表示するかどうかを指定して、レンダリング オプションを設定します。

## ステップ 2: ディメンションと出力ストリームを定義する

```csharp
SizeF size = new SizeF();
using (Stream stream = File.Open(Path.Combine("Your Output Directory", "text-and-formula.svg"), FileMode.Create))
{
    //レンダリングを実行します。
    new SvgFigureRenderer().Render("Your LaTeX Code", stream, options, out size);
}
```

「出力ディレクトリ」を目的のディレクトリに置き換え、LaTeX コードを文字列として指定します。

## ステップ 3: 結果の表示

```csharp
Console.Out.WriteLine(options.ErrorReport);
Console.Out.WriteLine();
Console.Out.WriteLine("Size: " + size);
```

このステップでは、エラー レポートと結果の画像のサイズが表示されます。

## 結論

おめでとう！ C# で Aspose.TeX を使用して LaTeX Figure を SVG にレンダリングする方法を学習しました。数式や数値を .NET アプリケーションにシームレスに統合できるようになりました。

## よくある質問

### Q1: Aspose.TeX は無料で使用できますか?

 A1: Aspose.TeX は無料トライアルを提供しています。アクセスできます[ここ](https://releases.aspose.com/).

### Q2: Aspose.TeX ドキュメントはどこで見つけられますか?

 A2: ドキュメントを参照してください。[ここ](https://reference.aspose.com/tex/net/).

### Q3: Aspose.TeX のサポートを受けるにはどうすればよいですか?

 A3: サポート フォーラムにアクセスしてください[ここ](https://forum.aspose.com/c/tex/47).

### Q4: Aspose.TeX を購入できますか?

 A4: はい、Aspose.TeX を購入できます。[ここ](https://purchase.aspose.com/buy).

### Q5: 仮免許は必要ですか?

 A5: 必要に応じて、一時ライセンスを取得できます。[ここ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
