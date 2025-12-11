---
date: 2025-12-05
description: 學習如何使用 Aspose.TeX for Java 進行 TeX 排版，內容包括自訂格式的步驟以及如何取得臨時授權 (aspose)。
linktitle: How to Typeset TeX with Custom Formats in Java
second_title: Aspose.TeX Java API
title: 如何在 Java 中使用自訂格式排版 TeX
url: /zh-hant/java/custom-tex-formats/typesetting-custom-tex-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中使用自訂格式排版 TeX

## 介紹

如果您需要在 Java 應用程式中 **how to typeset tex**，Aspose.TeX 提供一個乾淨且高效能的方式來使用自訂 TeX 格式檔案。在本教學中，我們將逐步說明您所需的一切——從環境設定到執行使用您自訂格式的 TeX 工作。無論您是要打造科學出版工具或是自訂報告產生器，以下步驟都能讓您快速上手。

## 快速解答
- **需要哪個函式庫？** Aspose.TeX for Java  
- **可以使用自訂 TeX 格式嗎？** 可以，只要將 `FormatProvider` 指向您的檔案即可。  
- **開發時需要授權嗎？** 臨時授權 aspose 可用於測試；正式環境需購買完整授權。  
- **支援哪個 Java 版本？** JDK 8 或更高。  
- **範例產生的輸出格式為何？** XPS（您也可以切換為 PDF、PNG 等）。

## 什麼是自訂 TeX 格式？

自訂 TeX 格式是一組預先編譯好的巨集與原始指令，讓 TeX 引擎依照您的文件樣式進行調整。只要提供您自己的 `.fmt` 檔案，即可在不每次修改原始 TeX 的情況下，控制字型、版面規則與指令定義。

## 為什麼要使用 Aspose.TeX for Java？

- **純 Java** – 無原生二進位檔，易於嵌入任何基於 JVM 的專案。  
- **高保真度** – 產生的輸出與 LaTeX 風格的渲染相符。  
- **可擴充** – 支援自訂格式、多種輸出裝置與批次處理。  
- **授權彈性** – 可先使用臨時授權 aspose，正式上線時再升級。

## 前置條件

開始之前，請確保您已具備以下項目：

1. **Java Development Kit (JDK)** – 已安裝 JDK 8 或更新版本。若尚未安裝，請從官方 [Java website](https://www.oracle.com/java/technologies/javase-downloads.html) 下載。  
2. **Aspose.TeX library for Java** – 從 [Aspose.TeX for Java download page](https://releases.aspose.com/tex/java/) 取得最新 JAR。  
3. **您的自訂 TeX 格式檔案** – 將編譯好的 `.fmt`（例如 `customtex.fmt`）放置於作為輸出目錄的資料夾中。  

> **專業提示：** 若您在評估本產品，請向 Aspose 入口網站申請 *temporary license aspose*；此授權可在有限期間內移除評估浮水印。

## 匯入套件

首先，將必要的匯入加入您的 Java 專案。這些類別可讓您存取格式提供者、工作設定與渲染裝置。

```java
package com.aspose.tex.TypesetWithCustomTeXFormat;

import java.io.ByteArrayInputStream;
import java.io.IOException;

import com.aspose.tex.FormatProvider;
import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

## 步驟說明

### 步驟 1：建立 Format Provider

`FormatProvider` 指向包含自訂 TeX 格式檔案的目錄。將 `"Your Output Directory"` 替換為 `customtex.fmt` 所在的實際路徑。

```java
final FormatProvider formatProvider = new FormatProvider(
        new InputFileSystemDirectory("Your Output Directory"), "customtex");
```

### 步驟 2：設定轉換選項

設定工作使用 ObjectTeX 引擎（能理解自訂格式的引擎）。同時設定工作名稱並指定輸入/輸出工作目錄。

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX(formatProvider));
options.setJobName("typeset-with-custom-format");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### 步驟 3：執行 TeX 工作

建立 `TeXJob` 實例，提供一段簡單的 TeX 片段，並指示使用 `XpsDevice` 進行渲染。片段以 `\end` 結尾以關閉文件。

```java
new TeXJob(new ByteArrayInputStream(
        "Congratulations! You have successfully typeset this text with your own TeX format!\\end".getBytes("ASCII")),
        new XpsDevice(), options).run();
```

### 步驟 4：完成輸出

工作完成後，於終端機輸出加入換行，以保持主控台整潔。

```java
options.getTerminalOut().getWriter().newLine();
```

### 步驟 5：關閉 Format Provider

完成後，關閉提供者以釋放檔案句柄並釋放資源。

```java
formatProvider.close();
```

## 常見問題與解決方案

| 問題 | 原因 | 解決方式 |
|------|------|----------|
| **“Format file not found”** | `FormatProvider` 中的路徑錯誤 | 確認目錄與檔名（`customtex.fmt`）正確且可存取。 |
| **編碼錯誤** | TeX 字串中含有非 ASCII 字元 | 使用 UTF‑8 編碼（`"UTF-8"` 而非 `"ASCII"`）。 |
| **未產生輸出** | 輸出目錄缺乏寫入權限 | 確保 Java 程序對 `"Your Output Directory"` 具有寫入權限。 |
| **授權浮水印** | 僅使用評估授權 | 在測試時套用 *temporary license aspose*，或於正式環境購買完整授權。 |

**相關資源：** [Aspose.TeX API Reference](https://docs.aspose.com/tex/java/) | [Download Free Trial](https://releases.aspose.com/tex/java/)

## 常見問答

**Q: 我可以將 Aspose.TeX 與其他 Java 函式庫一起使用嗎？**  
A: 當然可以。此 API 為純 Java，可與 Apache PDFBox、iText 或 Spring Boot 等函式庫共存。

**Q: 我可以從哪裡取得評估用的 temporary license aspose？**  
A: 可於 [Aspose temporary license page](https://purchase.aspose.com/temporary-license/) 申請；此授權可在最多 30 天內移除評估浮水印。

**Q: Aspose.TeX 是否支援除 XPS 之外的輸出格式？**  
A: 支援。您可以將 `new XpsDevice()` 替換為 `new PdfDevice()`、`new PngDevice()` 等，視需求而定。

**Q: 如何偵錯失敗的 TeX 工作？**  
A: 透過呼叫 `options.setLogLevel(LogLevel.DEBUG);` 開啟詳細日誌，並檢查主控台輸出以取得錯誤資訊。

**Q: 是否提供免費試用？**  
A: 有 – 可從 [Aspose.TeX download page](https://releases.aspose.com/tex/java/) 下載試用二進位檔。

## 結論

您現在已了解如何在 Java 應用程式中使用 Aspose.TeX 及自訂 TeX 格式 **how to typeset tex**。依循上述步驟，即可將高品質排版整合至任何基於 Java 的工作流程，試驗自己的格式檔，並在取得正式授權後，從原型階段順利進入生產環境。

---

**Last Updated:** 2025-12-05  
**Tested With:** Aspose.TeX for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}