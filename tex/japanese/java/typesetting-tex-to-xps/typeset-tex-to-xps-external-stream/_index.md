---
title: 外部ストリームを使用して Java で TeX を XPS にタイプセットする
linktitle: 外部ストリームを使用して Java で TeX を XPS にタイプセットする
second_title: Aspose.TeX Java API
description: Aspose.TeX を使用して Java で TeX を XPS にタイプセットする方法を学びます。シームレスな文書処理のための段階的なガイダンスをご覧ください。
type: docs
weight: 10
url: /ja/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
---
## 導入

Java 開発の世界では、Aspose.TeX は、TeX ドキュメントを XPS などのさまざまな形式に植字するための強力なツールとして際立っています。 Java アプリケーションのドキュメント処理機能を強化したい場合は、このチュートリアルが最適です。このステップバイステップのガイドでは、Aspose.TeX for Java と外部ストリームを使用して TeX を XPS に植字するプロセスを説明します。

## 前提条件

チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。

-  Java Development Kit (JDK): システムに Java がインストールされていることを確認してください。からダウンロードできます[ここ](https://www.oracle.com/java/technologies/javase-downloads.html).

- Aspose.TeX for Java: Aspose.TeX for Java をダウンロードしてインストールします。ダウンロードリンクが見つかります[ここ](https://releases.aspose.com/tex/java/).

## パッケージのインポート

TeX から XPS への変換作業を開始するには、必要なパッケージをインポートすることから始めます。 Java プロジェクトに次のコード スニペットを含めます。

```java
package com.aspose.tex.TypesetXpsWrittenToExternalStream;

import java.io.FileOutputStream;
import java.io.IOException;
import java.io.OutputStream;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

## ステップ 1: 変換オプションを構成する

まず、次のコードを使用して、デフォルトの ObjectTeX 形式の変換オプションを作成します。

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

これにより、植字プロセスの基礎が確立されます。

## ステップ 2: ジョブ名とディレクトリを指定する

ジョブ名を定義し、入力および出力の作業ディレクトリを設定します。

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

「入力ディレクトリ」などのプレースホルダーを実際のディレクトリ パスに置き換えてください。

## ステップ 3: 端末出力を構成する

ターミナル出力を出力作業ディレクトリ内のファイルに書き込むように指定します。

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

この手順により、デバッグ用に詳細なログが確実に取得されます。

## ステップ 4: 出力ストリームを開く

ストリームを開いてタイプセット XPS ドキュメントを書き込みます。

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

「出力ディレクトリ」を適切なパスに置き換えます。

## ステップ 5: ジョブを実行する

TeX から XPS への変換ジョブを実行します。

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

これでプロセスは完了し、指定した出力ディレクトリにタイプセット XPS ドキュメントが表示されます。

## 結論

おめでとう！ Aspose.TeX を使用して Java で TeX を XPS にタイプセットすることに成功しました。これにより、Java アプリケーションでのドキュメント処理の可能性が広がります。さまざまな TeX ファイルを試して、Aspose.TeX が提供するさまざまな機能を調べてください。

## よくある質問

### Q1: Aspose.TeX for Java を他の文書形式で使用できますか?

A1: Aspose.TeX は主に TeX 関連の文書処理に焦点を当てています。他の形式については、Aspose の幅広い製品範囲をご覧ください。

### Q2: 体験版はありますか?

 A2: はい、無料トライアルをダウンロードすると、Aspose.TeX を体験できます。[ここ](https://releases.aspose.com/).

### Q3: 包括的なドキュメントはどこで入手できますか?

 A3: ドキュメントを参照してください。[ここ](https://reference.aspose.com/tex/java/)詳細な情報と例については、

### Q4: サポートを受ける、または支援を求めるにはどうすればよいですか?

 A4: Aspose.TeX フォーラムにアクセスしてください。[ここ](https://forum.aspose.com/c/tex/47)コミュニティのサポートとディスカッションのために。

### Q5: テスト目的で一時ライセンスを取得できますか?

 A5: はい、仮ライセンスを取得できます。[ここ](https://purchase.aspose.com/temporary-license/).