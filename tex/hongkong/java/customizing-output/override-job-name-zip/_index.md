---
title: 在 Java 中覆蓋作業名稱並將終端輸出寫入 Zip
linktitle: 在 Java 中覆蓋作業名稱並將終端輸出寫入 Zip
second_title: Aspose.TeX Java API
description: 了解如何使用 Aspose.TeX 覆寫作業名稱並將終端輸出寫入 Java 中的 ZIP。面向 Java 開發人員的綜合教程。
weight: 11
url: /zh-hant/java/customizing-output/override-job-name-zip/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 中覆蓋作業名稱並將終端輸出寫入 Zip

## 介紹

在 Java 開發領域，Aspose.TeX 作為處理 TeX 檔案格式的強大工具脫穎而出。在本教程中，我們將深入研究一個特定的場景 - 覆蓋作業名稱並將終端輸出寫入 zip 檔案。本逐步指南將引導您完成使用 Aspose.TeX for Java 的過程。

## 先決條件

在開始本教學之前，請確保您具備以下先決條件：
- Java 程式設計的基礎知識。
- 安裝了 Aspose.TeX for Java。如果沒有，您可以從以下位置下載[阿斯普斯網站](https://releases.aspose.com/tex/java/).
- 了解如何設定 Java 開發環境。

## 導入包

首先將必要的套件匯入到您的 Java 專案中。這可確保您可以存取任務所需的 Aspose.TeX 功能。

```java
package com.aspose.tex.OverridenJobNameAndTerminalOutputWrittenToZip;

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

## 第 1 步：開啟 ZIP 檔案

首先，在 ZIP 檔案上開啟一個串流，該串流將用作輸入工作目錄。這是將處理您的資料的存檔。

```java
//在輸入 ZIP 檔案上開啟串流
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
```

## 第 2 步：開啟輸出 ZIP 檔案

接下來，開啟 ZIP 檔案上的流，該流將用作輸出工作目錄。這是終端輸出將被寫入的地方。

```java
//在輸出 ZIP 檔案上開啟串流
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "terminal-out-to-zip.zip");
```

## 第 3 步：設定轉換選項

根據 ObjectTeX 引擎擴充功能建立預設 ObjectTeX 格式的轉換選項。指定輸入和輸出的作業名稱和 ZIP 存檔工作目錄。

```java
//為 ObjectTeX 格式建立 TeX 選項
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("terminal-output-to-zip");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
```

## 步驟 4：指定終端輸出

指定終端輸出必須寫入輸出工作目錄中的檔案。檔案名稱將是`<job_name>.trm`.

```java
//指定終端輸出設定
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

## 第 5 步：定義儲存選項並執行作業

定義儲存選項，例如本範例中的 PDF 儲存選項。執行 TeX 作業來執行轉換。

```java
//定義儲存選項並執行作業
options.setSaveOptions(new PdfSaveOptions());
new TeXJob("hello-world", new PdfDevice(), options).run();
```

## 第 6 步：最終確定輸出 ZIP 存檔

作業完成後，最終確定輸出 ZIP 檔案以確保正確完成。

```java
//最終確定輸出 ZIP 存檔
((OutputZipDirectory) options.getOutputWorkingDirectory()).finish();
```

## 結論

恭喜！您已經成功學習如何使用 Aspose.TeX 覆寫作業名稱並將終端輸出寫入 Java 中的 ZIP 檔案。這項強大的功能為您的 Java 開發專案增加了靈活性和效率。

## 常見問題解答

### Q1：什麼是Aspose.TeX？

A1：Aspose.TeX 是一個 Java 函式庫，允許開發人員使用 TeX 檔案格式，為文件處理提供進階功能。

### Q2：如何取得 Aspose.TeX 的臨時授權？

 A2：您可以從以下地點獲得臨時許可證：[這個連結](https://purchase.aspose.com/temporary-license/).

### Q3：哪裡可以找到Aspose.TeX文件？

 A3：文檔可用[這裡](https://reference.aspose.com/tex/java/).

### Q4：Aspose.TeX 有免費試用版嗎？

 A4：是的，您可以找到免費試用版[這裡](https://releases.aspose.com/).

### Q5：我可以在哪裡尋求有關 Aspose.TeX 的支援或提出問題？

 A5：訪問[Aspose.TeX 論壇](https://forum.aspose.com/c/tex/47)以尋求支持和討論。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
