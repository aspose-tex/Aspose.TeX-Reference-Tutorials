---
title: Java で LaTeX を XPS 形式に簡単に変換
linktitle: Java で LaTeX を XPS 形式に簡単に変換
second_title: Aspose.TeX Java API
description: Aspose.TeX を使用して Java で LaTeX を XPS に簡単に変換します。シームレスな統合については、ステップバイステップのガイドに従ってください。
weight: 10
url: /ja/java/converting-lato-xps/simple-xps-conversion/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java で LaTeX を XPS 形式に簡単に変換

## 導入

Java アプリケーションで LaTeX ドキュメントを XPS 形式にシームレスに変換したいと考えていますか? Aspose.TeX for Java は、これを簡単に実現できる強力なソリューションを提供します。このステップバイステップのガイドでは、Aspose.TeX を使用して LaTeX を XPS に変換するプロセスを説明します。

## 前提条件

変換プロセスに入る前に、次の前提条件が満たされていることを確認してください。

- Java Development Kit (JDK) がシステムにインストールされています。
-  Java ライブラリ用の Aspose.TeX がダウンロードされました。ダウンロードリンクが見つかります[ここ](https://releases.aspose.com/tex/java/).

## パッケージのインポート

まず、Java プロジェクトに必要なパッケージをインポートします。プロジェクトの依存関係に Aspose.TeX ライブラリを必ず含めてください。

```java
package com.aspose.tex.LaTeXXpsConversionSimplest;

import java.io.ByteArrayInputStream;
import java.io.IOException;
import java.util.Calendar;
import java.util.GregorianCalendar;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.Interaction;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;
import com.aspose.tex.rendering.XpsSaveOptions;

import util.Utils;
```

ここで、提供されたコード例を使用して、変換プロセスを複数のステップに分割してみましょう。

## ステップ 1: 入力ディレクトリと出力ディレクトリを設定する

```java
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

LaTeX 入力ファイルが存在するディレクトリと、変換された XPS ファイルを保存する場所を指定します。

## ステップ 2: TeX オプションを構成する

さまざまなオプションを設定して、ニーズに応じて変換プロセスをカスタマイズします。

```java
options.setInteraction(Interaction.NonstopMode);
options.setDateTime(new GregorianCalendar(2022, Calendar.DECEMBER, 18).getTime());
options.ignoreMissingPackages(true);
options.noLigatures(true);
options.repeat(true);
```

必要に応じて、インタラクション モード、タイトルの日付、不足しているパッケージの処理、合字、繰り返しを調整します。

## ステップ 3: XPS 保存オプションを初期化する

```java
options.setSaveOptions(new XpsSaveOptions());
```

XPS 形式で保存するためのオプションを初期化します。

## ステップ 4: XPS 保存オプションをカスタマイズする

```java
options.getSaveOptions().rasterizeFormulas(true);
options.getSaveOptions().rasterizeIncludedGraphics(true);
options.getSaveOptions().subsetFonts(true);
```

XPS 保存オプションをカスタマイズして、数式、含まれるグラフィックス、およびフォントのサブセットの変換を制御します。

## ステップ 5: LaTeX から XPS への変換を実行する

```java
new TeXJob("Your Input Directory" + "sample.ltx", new XpsDevice(), options).run();
```

指定された入力ファイル、出力デバイス (XpsDevice)、およびオプションを使用して TeX ジョブを実行することにより、変換プロセスを開始します。

## 追加の例

さまざまな入力ソースを使用して追加の変換方法を検討します。

### 入力ストリームを使用する

```java
new TeXJob(new ByteArrayInputStream(
    "\\documentclass{article} \\begin{document} Hello, World! \\end{document}".getBytes("ASCII")),
    new XpsDevice(), options).run();
```

### メイン入力端子を使用する

```java
new TeXJob(new XpsDevice(), options).run();
```

## 結論

Aspose.TeX for Java を使用すると、LaTeX から XPS への変換が簡単になります。次の手順に従ってオプションをカスタマイズし、この機能を Java アプリケーションにシームレスに統合します。

## よくある質問

### Q1: Aspose.TeX を使用して、複雑な数式を含む LaTeX 文書を変換できますか?

A1: もちろんです！ Aspose.TeX は、変換プロセス中に複雑な数式をシームレスに処理します。

### Q2: Aspose.TeX for Java の試用版はありますか?

 A2: はい、無料試用版があります。[ここ](https://releases.aspose.com/).

### Q3: Aspose.TeX のサポートを受けるにはどうすればよいですか?

 A3: にアクセスしてください。[Aspose.TeX フォーラム](https://forum.aspose.com/c/tex/47)援助とコミュニティサポートのために。

### Q4: Aspose.TeX の一時ライセンスは利用できますか?

 A4: はい、一時ライセンスを取得できます。[ここ](https://purchase.aspose.com/temporary-license/).

### Q5: Aspose.TeX のドキュメントはどこで見つけられますか?

 A5: を参照してください。[ドキュメンテーション](https://reference.aspose.com/tex/java/)総合的な指導を行います。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
