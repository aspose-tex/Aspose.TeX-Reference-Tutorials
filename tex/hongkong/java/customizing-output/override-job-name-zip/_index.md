---
date: 2025-12-07
description: 了解如何使用 Aspose.TeX for Java 將 TeX 轉換為 PDF、覆寫作業名稱並將終端輸出寫入 ZIP 檔案。針對 Java
  開發者的逐步指南。
language: zh-hant
linktitle: Convert TeX to PDF, Override Job Name and Write Terminal Output to ZIP
  in Java
second_title: Aspose.TeX Java API
title: 在 Java 中將 TeX 轉換為 PDF、覆寫作業名稱並將終端輸出寫入 ZIP
url: /java/customizing-output/override-job-name-zip/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 將 TeX 轉換為 PDF、覆寫作業名稱並將終端輸出寫入 ZIP（Java）

## 簡介

如果您需要 **將 TeX 轉換為 PDF**，同時完全掌控作業名稱與終端日誌，Aspose.TeX for Java 可讓此過程變得簡單。在本教學中，我們將示範一個實務情境：覆寫作業名稱、將終端輸出導入 ZIP 壓縮檔，最後產生 PDF 文件。完成後，您將擁有一段可直接放入任何 Java 專案的可重用程式碼片段。

## 快速解答
- **本教學的目的是什麼？** 它示範如何將 TeX 轉換為 PDF、設定自訂作業名稱，並將終端輸出捕獲至 ZIP 檔案。  
- **需要哪個函式庫？** Aspose.TeX for Java（最新版本）。  
- **是否需要授權？** 評估時可使用臨時授權；正式上線則需完整授權。  
- **會產生哪些輸出檔案？** PDF 文件以及位於輸出 ZIP 內的 `<job_name>.trm` 終端日誌。  
- **實作需要多久？** 大約 10‑15 分鐘即可複製程式碼並執行。

## 什麼是「將 TeX 轉換為 PDF」？

將 TeX 轉換為 PDF 意指將 TeX 原始檔（或多個 TeX 檔案）轉譯為 PDF 文件。Aspose.TeX 提供高效能引擎，完整處理 TeX 編譯流程，無需外部 LaTeX 發行版。

## 為何要覆寫作業名稱並將終端輸出寫入 ZIP？

- **清晰度：** 自訂作業名稱會出現在日誌檔案中，方便在自動化流水線中辨識執行。  
- **可移植性：** 將終端輸出 (`*.trm`) 存於 ZIP 中，可將所有產出集中管理，對 CI/CD 或雲端處理相當便利。  
- **除錯：** 終端日誌包含詳細的編譯訊息，協助您排除 TeX 錯誤。

## 先決條件

在開始之前，請確保您已具備：

- 可運作的 Java 開發環境（JDK 8 或以上）。  
- 從 [Aspose 官方網站](https://releases.aspose.com/tex/java/) 下載的 Aspose.TeX for Java。  
- 基本的 Java I/O 串流使用經驗。

## 匯入套件

首先匯入所需的類別，以取得 Aspose.TeX API 以及標準 Java I/O 工具。

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

## 步驟 1：開啟輸入 ZIP 壓縮檔

我們首先開啟指向包含 TeX 原始檔的 ZIP 檔案的串流。此壓縮檔充當 **轉換作業的輸入工作目錄**。

```java
// Open a stream on the input ZIP archive
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
```

## 步驟 2：開啟輸出 ZIP 壓縮檔

接著，為將接收產生的 PDF 與終端日誌的 ZIP 檔案建立串流。這即為 **輸出工作目錄**。

```java
// Open a stream on the output ZIP archive
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "terminal-out-to-zip.zip");
```

## 步驟 3：設定轉換選項（含作業名稱）

在此我們設定 ObjectTeX 格式的轉換選項、指定自訂作業名稱，並將輸入與輸出 ZIP 目錄綁定。

```java
// Create TeX options for ObjectTeX format
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("terminal-output-to-zip");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
```

## 步驟 4：將終端輸出寫入 ZIP 中的檔案

我們指示 Aspose.TeX 將編譯終端輸出寫入輸出 ZIP 內名為 `<job_name>.trm` 的檔案。

```java
// Specify terminal output settings
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

## 步驟 5：定義儲存選項並執行作業

設定欲使用的渲染裝置（PDF）並執行作業。此步驟 **將 TeX 轉換為 PDF**，並將結果儲存於輸出 ZIP 中。

```java
// Define saving options and run the job
options.setSaveOptions(new PdfSaveOptions());
new TeXJob("hello-world", new PdfDevice(), options).run();
```

## 步驟 6：完成輸出 ZIP 壓縮檔

作業完成後，我們必須正確關閉 ZIP 串流，以確保壓縮檔有效。

```java
// Finalize the output ZIP archive
((OutputZipDirectory) options.getOutputWorkingDirectory()).finish();
```

## 常見問題與解決方案

| Issue | Likely Cause | Fix |
|-------|--------------|-----|
| **PDF 為空** | 輸入 ZIP 未包含有效的 `*.tex` 檔案，或檔案未放置於 `in` 資料夾下。 | 確認 ZIP 結構（`in/yourfile.tex`）。 |
| **缺少 `.trm` 檔案** | `setTerminalOut` 未被呼叫，或輸出目錄不是 `OutputZipDirectory`。 | 確保在 `run()` 之前執行 `options.setTerminalOut(...)`。 |
| **完成時發生 `IOException`** | 輸出串流已在其他地方關閉。 | 僅在作業完成後呼叫一次 `finish()`。 |
| **轉換因 TeX 錯誤失敗** | TeX 原始碼包含語法錯誤。 | 開啟產生的 `<job_name>.trm` 日誌，以查看詳細錯誤訊息。 |

## 常見問答

**Q: 什麼是 Aspose.TeX？**  
A: Aspose.TeX 是一個 Java 函式庫，讓開發者能 **從 TeX 原始碼建立 PDF**、操作 TeX 文件，並在不需外部 LaTeX 安裝的情況下執行高階渲染。

**Q: 如何取得 Aspose.TeX 的臨時授權？**  
A: 您可從 [此連結](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

**Q: 在哪裡可以找到官方的 Aspose.TeX 文件？**  
A: 文件可於 [此處](https://reference.aspose.com/tex/java/) 取得。

**Q: 有免費試用版的 Aspose.TeX 嗎？**  
A: 有，您可從 [此處](https://releases.aspose.com/) 下載免費試用版。

**Q: 若遇到問題，該向哪裡尋求協助？**  
A: 請前往 [Aspose.TeX 論壇](https://forum.aspose.com/c/tex/47) 取得社群支援與官方協助。

## 結論

現在您已了解如何使用 Aspose.TeX for Java **將 TeX 轉換為 PDF**、覆寫作業名稱，並將終端輸出捕獲於 ZIP 壓縮檔中。此方法特別適用於自動化建置流水線，將日誌與產出檔案一起保存，可簡化除錯與稽核流程。歡迎將程式碼套用至您自己的專案結構，或擴充至 Aspose.TeX 支援的其他輸出格式。

---

**最後更新：** 2025-12-07  
**測試環境：** Aspose.TeX for Java 24.11（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}