---
title: 使用外部串流在 Java 中將 TeX 排版為 XPS
linktitle: 使用外部串流在 Java 中將 TeX 排版為 XPS
second_title: Aspose.TeX Java API
description: 了解如何使用 Aspose.TeX 在 Java 中將 TeX 排版為 XPS。探索無縫文件處理的逐步指南。
weight: 10
url: /zh-hant/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用外部串流在 Java 中將 TeX 排版為 XPS

## 介紹

在 Java 開發領域，Aspose.TeX 作為將 TeX 文檔排版為各種格式（包括 XPS）的強大工具而脫穎而出。如果您希望增強 Java 應用程式的文件處理能力，本教學課程就是為您量身訂製的。在本逐步指南中，我們將引導您完成使用 Aspose.TeX for Java 和外部串流將 TeX 排版為 XPS 的過程。

## 先決條件

在深入學習本教程之前，請確保您具備以下先決條件：

-  Java 開發工具包 (JDK)：確保您的系統上安裝了 Java。您可以從以下位置下載：[這裡](https://www.oracle.com/java/technologies/javase-downloads.html).

-  Aspose.TeX for Java：下載並安裝 Aspose.TeX for Java。你可以找到下載鏈接[這裡](https://releases.aspose.com/tex/java/).

## 導入包

首先匯入必要的套件來開始您的 TeX 到 XPS 轉換之旅。在您的 Java 專案中包含以下程式碼片段：

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

## 第 1 步：配置轉換選項

首先使用以下程式碼為預設的 ObjectTeX 格式建立轉換選項：

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

這為排版過程奠定了基礎。

## 第 2 步：指定作業名稱和目錄

定義作業名稱並設定輸入和輸出工作目錄：

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

確保將“您的輸入目錄”等佔位符替換為實際的目錄路徑。

## 步驟 3：配置終端輸出

指定終端輸出應寫入輸出工作目錄中的檔案：

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

此步驟可確保捕獲詳細日誌以進行偵錯。

## 第 4 步：開啟輸出流

開啟一個流來寫入排版的 XPS 文件：

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

將“您的輸出目錄”替換為適當的路徑。

## 第 5 步：運行作業

執行 TeX 到 XPS 的轉換作業：

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

過程就完成了，您將在指定的輸出目錄中找到排版的 XPS 文件。

## 結論

恭喜！您已使用 Aspose.TeX 在 Java 中成功將 TeX 排版為 XPS。這為 Java 應用程式中的文件處理開闢了無限可能。嘗試不同的 TeX 檔案並探索 Aspose.TeX 提供的各種功能。

## 常見問題解答

### Q1：我可以將 Aspose.TeX for Java 與其他文件格式一起使用嗎？

A1：Aspose.TeX主要專注於TeX相關的文件處理。對於其他格式，請探索 Aspose 廣泛的產品系列。

### Q2：有試用版嗎？

 A2：是的，您可以透過下載免費試用版來體驗Aspose.TeX[這裡](https://releases.aspose.com/).

### Q3：在哪裡可以找到全面的文件？

 A3：參考文檔[這裡](https://reference.aspose.com/tex/java/)取得詳細資訊和範例。

### Q4：我如何獲得支持或尋求協助？

 A4：造訪 Aspose.TeX 論壇[這裡](https://forum.aspose.com/c/tex/47)以獲得社區支持和討論。

### Q5：我可以獲得臨時許可證用於測試目的嗎？

 A5：是的，您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
