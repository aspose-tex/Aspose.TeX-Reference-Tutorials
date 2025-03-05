---
title: 使用外部串流在 Java 中將 TeX 排版為 PDF
linktitle: 使用外部串流在 Java 中將 TeX 排版為 PDF
second_title: Aspose.TeX Java API
description: 了解如何使用 Aspose.TeX 的外部串流在 Java 中將 TeX 排版為 PDF。請按照我們的逐步指南進行無縫整合。
type: docs
weight: 10
url: /zh-hant/java/typesetting-tex-to-pdf/typeset-tex-to-pdf-external-stream/
---
## 介紹

在 Java 開發領域，從 TeX 檔案建立 PDF 是一種常見的需求。 Aspose.TeX for Java 簡化了這個過程，為將 TeX 排版為 PDF 提供了有效的解決方案。在本教學中，我們將引導您完成使用外部串流將 TeX 排版為 PDF 的步驟。最後，您將清楚地了解如何在 Java 應用程式中無縫地實現此過程。

## 先決條件

在深入學習本教程之前，請確保您具備以下先決條件：

- Aspose.TeX for Java：確保您已安裝 Aspose.TeX for Java 函式庫。您可以從[Aspose.TeX for Java 文檔](https://reference.aspose.com/tex/java/).

- 輸入和輸出目錄：準備輸入和輸出目錄。您可以使用提供的下載連結來獲取必要的文件。

## 導入包

首先將所需的套件匯入到您的 Java 專案中：

```java
package com.aspose.tex.TypesetPdfWrittenToExternalStream;

import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.io.OutputStream;

import com.aspose.tex.InputZipDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.OutputZipDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.PdfDevice;
import com.aspose.tex.rendering.PdfSaveOptions;

import util.Utils;
```

## 第 1 步：開啟輸入和輸出流

首先開啟輸入 ZIP 檔案（充當輸入工作目錄）和輸出 ZIP 檔案（充當輸出工作目錄）的流程。確保將“您的輸入目錄”和“您的輸出目錄”替換為您的實際目錄路徑。

```java
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "typeset-pdf-to-external-stream.zip");
```

## 第 2 步：配置 TeXOptions

建立 TeXOptions 物件並根據您的要求進行配置。設定作業名稱、輸入工作目錄、輸出工作目錄和其他選項。

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("typeset-pdf-to-external-stream");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
options.setSaveOptions(new PdfSaveOptions());
```

## 步驟 3：將 TeX 排版為 PDF

現在，打開一個流以將輸出 PDF 寫入所需位置。您可以選擇將其寫入本機檔案或直接寫入輸出 ZIP 檔案。

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + "file-name.pdf");
try {
    new TeXJob("hello-world", new PdfDevice(stream), options).run();
} finally {
    stream.close();
}
```

## 第 4 步：最終確定輸出 ZIP 存檔

完成輸出ZIP存檔即可完成排版流程。

```java
((OutputZipDirectory)options.getOutputWorkingDirectory()).finish();
```

## 結論

恭喜！您已成功使用 Aspose.TeX 的外部串流在 Java 中將 TeX 排版為 PDF。本教學為將 TeX 到 PDF 轉換無縫整合到 Java 應用程式中提供了堅實的基礎。

## 常見問題解答

### Q1: 我可以自訂輸出PDF的檔名嗎？

 A1：是的，您可以修改`options.setJobName("typeset-pdf-to-external-stream")`設定您想要的作業名稱。

### Q2：排版過程中常見問題如何檢查？

 A2：訪問[Aspose.TeX 論壇](https://forum.aspose.com/c/tex/47)以獲得社區的支持和幫助。

### Q3：Aspose.TeX for Java 有免費試用版嗎？

 A3：是的，您可以免費試用[這裡](https://releases.aspose.com/).

### Q4：在哪裡可以找到其他文件和範例？

 A4：探索綜合[Aspose.TeX 文檔](https://reference.aspose.com/tex/java/)獲取詳細資訊。

### Q5：我可以取得 Aspose.TeX 的臨時授權嗎？

 A5：是的，您可以申請臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).