---
date: 2026-02-12
description: 學習如何在 Java 中使用 Aspose.TeX 擷取控制台輸出、將終端機輸出寫入檔案，以及覆寫作業名稱。本一步一步指南亦涵蓋 Java
  的控制台輸出重定向。
linktitle: Write Terminal Output to File and Override Job Name in Java
second_title: Aspose.TeX Java API
title: 如何在 Java 中捕獲控制台輸出並覆寫作業名稱
url: /zh-hant/java/customizing-output/override-job-name-disk/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 將終端機輸出寫入檔案並在 Java 中覆寫工作名稱

## 簡介

在本教學中，您將會了解 **如何捕獲主控台輸出**，同時處理 Aspose.TeX for Java 的 TeX 檔案。我們將示範如何將終端機輸出寫入檔案、覆寫預設工作名稱，並在 Java 中重新導向主控台輸出，使日誌易於定位與分析。當您需要為批次轉換或自動化文件管線提供可靠的記錄時，這些技巧相當重要。

## 快速答案
- **我可以更改工作名稱嗎？** 可以，在執行工作之前使用 `options.setJobName(...)`。  
- **終端機輸出會保存在哪裡？** 它會以 `<job_name>.trm` 的檔名儲存在輸出工作目錄中。  
- **此功能需要授權嗎？** 此功能可在任何有效的 Aspose.TeX 授權下使用；亦提供免費試用版。  
- **輸出檔案的格式是什麼？** 純文字終端機日誌，與主控台輸出相同。  
- **這與其他輸出裝置相容嗎？** 絕對相容——寫入日誌後，您可以使用任何能讀取文字檔的工具來處理它。

## 在 Aspose.TeX 中，**如何捕獲主控台** 是什麼意思？

捕獲主控台輸出是指將原本會顯示在標準輸出串流（終端機）上的所有內容重新導向至磁碟上的檔案。使用 Aspose.TeX，只需設定 `OutputFileTerminal` 並將其指派給轉換選項，即可輕鬆完成此操作。

## 為什麼要覆寫工作名稱？

覆寫工作名稱可為每次轉換執行提供唯一的識別碼。這讓產生的日誌檔案（`*.trm`）與其他產物更易追蹤，尤其在平行執行多個工作或排程批次處理時。

## 先決條件

- 具備 Java 程式設計的基本功。  
- 已安裝 Aspose.TeX for Java（從官方 [Aspose.TeX Java 文件](https://reference.aspose.com/tex/java/) 下載）。  
- 具備可編譯並執行範例的 Java IDE 或建置工具（Maven/Gradle）。

## 匯入套件

要開始使用，請在您的 Java 專案中匯入必要的套件。在 Java 檔案中加入以下匯入語句：

```java
package com.aspose.tex.OverridenJobNameAndTerminalOutputWrittenToDisk;

import java.io.IOException;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

> **小技巧：** 僅在需要 Aspose 範例工具中的 `util.Utils` 輔助方法時才保留其匯入；否則可將其移除以保持程式碼整潔。

## 如何在 Java 中捕獲主控台輸出

以下是一個逐步指南，說明如何正確設定轉換選項、覆寫工作名稱，並將終端機輸出寫入磁碟檔案。

### 步驟 1：建立轉換選項

首先，建立一個使用預設 ObjectTeX 設定的 `TeXOptions` 實例。此物件將保存所有轉換過程的設定。

```java
// ExStart:OverrideJobName-WriteTerminalOutputToFileSystem
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
// ExEnd:OverrideJobName-WriteTerminalOutputToFileSystem
```

### 步驟 2：指定工作名稱與工作目錄

接著，設定自訂的工作名稱，並定義輸入與輸出檔案所在的位置。如果未設定工作名稱，`TeXJob` 建構式的第一個參數會自動成為工作名稱。

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

> **為什麼要覆寫工作名稱？**  
> 覆寫工作名稱可讓日誌檔案與產生的產物更易辨識，特別是在平行執行多個工作或自動化批次處理時。

### 步驟 3：將終端機輸出寫入檔案系統

告訴 Aspose.TeX 捕獲原本會顯示在主控台的所有內容，並寫入檔案。該檔案將以 `<job_name>.trm` 命名，並放置於上述定義的輸出工作目錄中。

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### 步驟 4：執行工作

最後，使用欲處理的輸入檔案（此處以簡單的「hello‑world」範例為例）與 XPS 呈現裝置建立 `TeXJob`。然後呼叫 `run()` 以執行轉換。

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
```

工作完成後，您會在 **您的輸出目錄** 中找到名為 `overridden-job-name.trm` 的檔案，內含完整的終端機日誌。

## 常見問題與除錯

| 問題 | 原因 | 解決方式 |
|-------|-------|-----|
| **未產生 `.trm` 檔案** | `setTerminalOut` 未被呼叫或輸出目錄不存在 | 確認輸出目錄已存在，且在 `job.run()` 之前已執行 `options.setTerminalOut(...)`。 |
| **檔案名稱不是覆寫後的名稱** | 工作名稱未正確設定 | 確保在建立 `TeXJob` 之前呼叫 `options.setJobName("your‑desired‑name")` **before** 建立 `TeXJob`。 |
| **日誌檔案為空** | 在開始記錄前拋出例外 | 將 `job.run()` 包在 try‑catch 區塊中，並檢查例外堆疊追蹤，以找出缺少字型或錯誤的 TeX 原始碼。 |

## 常見問與答

**Q: 我可以將 Aspose.TeX for Java 與其他 Java 函式庫一起使用嗎？**  
A: 可以，Aspose.TeX 設計為能與其他 Java 函式庫無縫整合，讓您在同一工作流程中結合 PDF、影像或資料庫工具。

**Q: 我可以在哪裡取得 Aspose.TeX for Java 的支援？**  
A: 前往 [Aspose.TeX 論壇](https://forum.aspose.com/c/tex/47) 取得社群協助，或透過 Aspose 支援入口開立支援票證。

**Q: Aspose.TeX for Java 有提供免費試用嗎？**  
A: 當然。您可從 [Aspose.TeX 免費試用頁面](https://releases.aspose.com/) 下載功能完整的試用版。

**Q: 我該如何取得測試用的臨時授權？**  
A: 前往 [Aspose 臨時授權](https://purchase.aspose.com/temporary-license/) 填寫臨時授權申請表，即可取得 30 天的評估授權。

**Q: 我可以在哪裡購買永久授權？**  
A: 直接前往 [Aspose.TeX 購買頁面](https://purchase.aspose.com/buy) 進行購買。

**最後更新：** 2026-02-12  
**測試環境：** Aspose.TeX 24.11 for Java  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}