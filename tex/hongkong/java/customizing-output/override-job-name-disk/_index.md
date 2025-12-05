---
date: 2025-12-05
description: 學習如何使用 Aspose.TeX for Java 將終端機輸出寫入檔案並覆寫作業名稱。請跟隨本逐步指南，內含完整程式碼範例。
language: zh-hant
linktitle: Write Terminal Output to File and Override Job Name in Java
second_title: Aspose.TeX Java API
title: 將終端機輸出寫入檔案並覆寫 Java 中的作業名稱
url: /java/customizing-output/override-job-name-disk/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 中將終端輸出寫入檔案並覆寫作業名稱

## 簡介

Aspose.TeX for Java 提供強大的功能來處理 TeX 檔案，讓開發人員能夠操作與自訂 TeX 文件的處理流程。在本教學中，您將學習 **如何將終端輸出寫入檔案**，同時覆寫預設的作業名稱——這兩項功能讓您對批次處理與記錄擁有精細的控制。

## 快速解答
- **我可以變更作業名稱嗎？** 是的，在執行作業前使用 `options.setJobName(...)`。  
- **終端輸出會儲存到哪裡？** 它會以 `<job_name>.trm` 的檔名儲存在輸出工作目錄中。  
- **此功能需要授權嗎？** 只要擁有有效的 Aspose.TeX 授權即可使用；亦提供免費試用版。  
- **輸出檔案的格式是什麼？** 純文字的終端日誌，與主控台輸出相同。  
- **這與其他輸出裝置相容嗎？** 完全相容——寫入日誌後，您可以使用任何能讀取文字檔的工具進行處理。

## 前置條件

在深入程式碼之前，請確保您具備以下條件：

- 扎實的 Java 程式設計基礎。  
- 已安裝 Aspose.TeX for Java（從官方 [Aspose.TeX Java 文件](https://reference.aspose.com/tex/java/) 下載）。  
- 具備可編譯與執行範例的 Java IDE 或建置工具（Maven/Gradle）。

## 匯入套件

首先，將必要的套件匯入您的 Java 專案。在 Java 檔案中加入以下匯入語句：

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

> **專業提示：** 只在需要 Aspose 範例工具的 `util.Utils` 輔助方法時才保留其匯入；若不需要，可將其移除以保持程式碼簡潔。

## 如何在 Java 中將終端輸出寫入檔案

以下是逐步說明，展示如何設定轉換選項、覆寫作業名稱，並將終端輸出導向磁碟上的檔案。

### 步驟 1：建立轉換選項

首先，建立使用預設 ObjectTeX 設定的 `TeXOptions` 實例。此物件將保存轉換過程的所有設定。

```java
// ExStart:OverrideJobName-WriteTerminalOutputToFileSystem
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
// ExEnd:OverrideJobName-WriteTerminalOutputToFileSystem
```

### 步驟 2：指定作業名稱與工作目錄

接著，設定自訂的作業名稱，並定義輸入與輸出檔案所在的位置。若未設定作業名稱，`TeXJob` 建構式的第一個參數會自動成為作業名稱。

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

> **為什麼要覆寫作業名稱？**  
> 覆寫作業名稱可讓日誌檔案與產生的產物更易辨識，尤其在同時執行多個作業或自動化批次處理時。

### 步驟 3：將終端輸出寫入檔案系統

指示 Aspose.TeX 捕獲原本會顯示在主控台的所有內容，並寫入檔案。該檔案名稱為 `<job_name>.trm`，並放置於上述定義的輸出工作目錄中。

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### 步驟 4：執行作業

最後，使用目標輸入檔案（此處使用簡單的 “hello‑world” 範例）與 XPS 呈現裝置建立 `TeXJob`。接著呼叫 `run()` 以執行轉換。

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
```

作業完成後，您會在 **您的輸出目錄** 中找到名為 `overridden-job-name.trm` 的檔案，內含完整的終端日誌。

## 常見問題與除錯

| 問題 | 原因 | 解決方法 |
|------|------|----------|
| **未產生 `.trm` 檔案** | `setTerminalOut` 未呼叫或輸出目錄不存在 | 確認輸出目錄已存在，且在 `job.run()` 之前已執行 `options.setTerminalOut(...)`。 |
| **檔案名稱未使用覆寫的名稱** | 作業名稱設定不正確 | 確保在建立 `TeXJob` 之前已呼叫 `options.setJobName("your‑desired‑name")`。 |
| **日誌檔案為空** | 在開始記錄前拋出例外 | 將 `job.run()` 包在 try‑catch 區塊，並檢查例外堆疊追蹤，以找出缺少字型或錯誤的 TeX 原始碼等問題。 |

## 常見問答

**Q: 我可以將 Aspose.TeX for Java 與其他 Java 函式庫一起使用嗎？**  
A: 可以，Aspose.TeX 設計為能與其他 Java 函式庫無縫整合，讓您在同一工作流程中結合 PDF、影像或資料庫工具。

**Q: 我可以在哪裡取得 Aspose.TeX for Java 的支援？**  
A: 前往 [Aspose.TeX 論壇](https://forum.aspose.com/c/tex/47) 尋求社群協助，或透過 Aspose 支援入口開立支援票證。

**Q: 是否提供 Aspose.TeX for Java 的免費試用？**  
A: 當然可以。您可從 [Aspose.TeX 免費試用頁面](https://releases.aspose.com/) 下載完整功能的試用版。

**Q: 我要如何取得測試用的臨時授權？**  
A: 透過 [Aspose 臨時授權](https://purchase.aspose.com/temporary-license/) 申請表取得 30 天的評估授權。

**Q: 我該從哪裡購買永久授權？**  
A: 可直接在 [Aspose.TeX 購買頁面](https://purchase.aspose.com/buy) 購買授權。

## 結論

本指南示範了如何使用 Aspose.TeX for Java **將終端輸出寫入檔案** 並覆寫預設的作業名稱。這些功能讓您能保留詳細的除錯日誌、自動化批次處理，並維持整潔有序的輸出結構——對於生產等級的文件轉換流程而言至關重要。

---

**最後更新：** 2025-12-05  
**測試環境：** Aspose.TeX 24.11 for Java  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}