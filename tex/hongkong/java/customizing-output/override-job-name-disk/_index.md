---
date: 2026-08-18
description: 了解如何使用 Aspose.TeX 在 Java 中重新導向主控台輸出、將終端輸出寫入檔案，以及覆寫工作名稱以提升日誌記錄效果。
keywords:
- redirect console output java
- Aspose.TeX Java
- Java logging
- override job name
lastmod: 2026-08-18
linktitle: 在 Java 中將終端輸出寫入檔案並覆寫工作名稱
og_description: 使用 Aspose.TeX 在 Java 中重新導向主控台輸出，並覆寫工作名稱以產生不同的日誌檔案。請依照本步驟教學，以確保可靠的日誌記錄。
og_image_alt: Screenshot of Java console output redirection using Aspose.TeX
og_title: 在 Java 中重新導向主控台輸出並覆寫工作名稱 – Aspose.TeX 指南
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Learn how to redirect console output in Java using Aspose.TeX, write
    terminal output to a file, and override the job name for better logging.
  headline: How to redirect console output in Java and override job name
  type: TechArticle
- description: Learn how to redirect console output in Java using Aspose.TeX, write
    terminal output to a file, and override the job name for better logging.
  name: How to redirect console output in Java and override job name
  steps:
  - name: create conversion options
    text: '`TeXOptions` is the configuration object that controls how Aspose.TeX processes
      a TeX job. It holds settings such as output format, font handling, and terminal
      redirection.'
  - name: specify job name and working directories
    text: '`TeXJob` represents a single conversion task, linking input, output, and
      options together. Setting a custom job name ensures the generated log file is
      uniquely named. > **Why override the job name?** > Overriding the job name makes
      log files and generated artifacts easier to identify, especially whe'
  - name: write terminal output to file system
    text: '`setTerminalOut` tells Aspose.TeX where to write the console log file.
      The file will be named `<job_name>.trm` and placed in the output working directory
      you defined above. Configure the terminal output redirection:'
  - name: run the job
    text: '`run()` executes the conversion based on the supplied options and writes
      output files (including the `.trm` log) to the designated folder. Create a `TeXJob`
      with the desired input file (here we use a simple “hello‑world” example) and
      the XPS rendering device, then call `run()`: When the job finishes'
  type: HowTo
- questions:
  - answer: Yes, Aspose.TeX integrates seamlessly with other Java libraries, allowing
      you to combine PDF, image, or database utilities in the same workflow.
    question: Can I use Aspose.TeX for Java with other Java libraries?
  - answer: Visit the [Aspose.TeX forum](https://forum.aspose.com/c/tex/47) for community
      help, or open a support ticket through the Aspose support portal.
    question: Where can I find support for Aspose.TeX for Java?
  - answer: Absolutely. You can download a fully functional trial from the [Aspose.TeX
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.TeX for Java?
  - answer: Use the temporary‑license request form at [Aspose temporary license](https://purchase.aspose.com/temporary-license/)
      to get a 30‑day evaluation license.
    question: How can I obtain a temporary license for testing?
  - answer: Purchase a license directly from the [Aspose.TeX buying page](https://purchase.aspose.com/buy).
    question: Where can I purchase a permanent license?
  type: FAQPage
second_title: Aspose.TeX Java API
tags:
- redirect console output
- Aspose.TeX
- Java console logging
- job name override
title: 如何在 Java 中重新導向主控台輸出並覆寫工作名稱
url: /zh-hant/java/customizing-output/override-job-name-disk/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 中將終端輸出寫入檔案並覆寫作業名稱

## 介紹

在本教學中，您將學習如何在使用 Aspose.TeX 處理 TeX 檔案時 **在 Java 中重新導向主控台輸出**。我們會示範如何將終端日誌寫入 `.trm` 檔案、覆寫預設作業名稱，並將日誌妥善組織，以便批次轉換或自動化流程使用。Aspose.TeX 支援 **30 多種輸入與輸出格式**，且能在不將整個檔案載入記憶體的情況下處理最多 **500 頁** 的文件，十分適合高容量情境。

## 快速解答

`options.setJobName(String name)` 設定自訂的作業識別碼，該識別碼將用於產生的日誌與輸出檔案。

- **我可以變更作業名稱嗎？** 可以 – 在建立 `TeXJob` 之前呼叫 `options.setJobName("my‑job")`。  
- **終端輸出會儲存到哪裡？** 會以 `<job_name>.trm` 的檔名儲存在您指定的輸出工作目錄中。  
- **此功能需要授權嗎？** 此功能可在任何有效的 Aspose.TeX 授權下使用；亦提供免費試用版。  
- **輸出檔案的格式是什麼？** 純文字終端日誌，會鏡像所有印在主控台的內容。  
- **這與其他輸出裝置相容嗎？** 完全相容 – 日誌寫入後，您可以將其提供給任何文字處理工具。

## 在 Aspose.TeX 的情境中，**如何擷取主控台** 是什麼？

擷取主控台輸出表示將原本會顯示在標準輸出串流（終端）上的所有內容重新導向至磁碟上的檔案。使用 Aspose.TeX，只需設定 `OutputFileTerminal` 並將其指派給轉換選項，即可輕鬆完成此操作。

## 為什麼要覆寫作業名稱？

覆寫作業名稱可為每次轉換執行提供唯一的識別碼。這使得產生的日誌檔案（`*.trm`）與其他產出更易於追蹤，特別是在平行執行多個作業或排程批次處理時。提供獨特的名稱亦可避免覆寫先前的日誌，並簡化依賴可預測檔名的後處理腳本。

## 前置條件

- 具備 Java 程式設計的基本熟練度。  
- 已安裝 Aspose.TeX for Java（可從官方的 [Aspose.TeX Java 文件](https://reference.aspose.com/tex/java/) 下載）。  
- 具備可編譯並執行範例的 Java IDE 或建置工具（Maven/Gradle）。

## 匯入套件

要開始使用，請在 Java 專案中匯入必要的套件。在您的 Java 檔案中，加入以下匯入語句：

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

> **專業提示：** 只在需要 Aspose 範例工具中的輔助方法時才保留 `util.Utils` 的匯入；否則可將其移除，以保持程式碼簡潔。

## 如何在 Java 中擷取主控台輸出

以下是一個逐步指南，說明如何設定轉換選項、覆寫作業名稱，並將終端輸出導向磁碟上的檔案。接下來的步驟展示所需的 API 呼叫，並示範如何設定環境，使所有主控台訊息皆被擷取，而無需修改 Aspose.TeX 的核心程式碼。

### 步驟 1：建立轉換選項

`TeXOptions` 是用來控制 Aspose.TeX 處理 TeX 作業方式的設定物件。它包含輸出格式、字型處理與終端重新導向等設定。

```java
// ExStart:OverrideJobName-WriteTerminalOutputToFileSystem
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
// ExEnd:OverrideJobName-WriteTerminalOutputToFileSystem
```

### 步驟 2：指定作業名稱與工作目錄

`TeXJob` 代表單一的轉換任務，將輸入、輸出與選項串聯起來。設定自訂的作業名稱可確保產生的日誌檔案具有唯一名稱。

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

> **為什麼要覆寫作業名稱？**  
> 覆寫作業名稱可讓日誌檔案與產生的產出更易於辨識，特別是在平行執行多個作業或自動化批次處理時。

### 步驟 3：將終端輸出寫入檔案系統

`setTerminalOut` 告訴 Aspose.TeX 將主控台日誌寫入何處。檔案會以 `<job_name>.trm` 命名，並放置於上述定義的輸出工作目錄中。

設定終端輸出重新導向：

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### 步驟 4：執行作業

`run()` 依據提供的選項執行轉換，並將輸出檔案（包括 `.trm` 日誌）寫入指定的資料夾。

建立一個使用目標輸入檔案的 `TeXJob`（此處使用簡單的「hello‑world」範例）與 XPS 呈現裝置，然後呼叫 `run()`：

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
```

作業完成後，您會在 **您的輸出目錄** 中找到名為 `overridden-job-name.trm` 的檔案，內含完整的終端日誌。

## 常見問題與故障排除

| 問題 | 原因 | 解決方法 |
|-------|-------|-----|
| **未產生 `.trm` 檔案** | `setTerminalOut` 未被呼叫或輸出目錄不存在 | 確認輸出目錄已存在，且在 `job.run()` 之前已執行 `options.setTerminalOut(...)`。 |
| **檔名未使用覆寫的名稱** | 作業名稱未正確設定 | 確保在建立 `TeXJob` **之前** 呼叫 `options.setJobName("your‑desired‑name")`。 |
| **日誌檔案為空** | 在日誌開始前拋出例外 | 將 `job.run()` 包裹於 try‑catch 區塊，並檢查例外堆疊追蹤，以找出缺少字型或格式錯誤的 TeX 原始碼。 |

## 常見問答

**Q: 我可以在 Java 中將 Aspose.TeX 與其他 Java 函式庫一起使用嗎？**  
A: 可以，Aspose.TeX 可無縫整合其他 Java 函式庫，讓您能在同一工作流程中結合 PDF、影像或資料庫工具。

**Q: 我可以在哪裡取得 Aspose.TeX for Java 的支援？**  
A: 請前往 [Aspose.TeX 論壇](https://forum.aspose.com/c/tex/47) 取得社群協助，或透過 Aspose 支援入口開立支援票證。

**Q: 是否提供 Aspose.TeX for Java 的免費試用？**  
A: 當然可以。您可從 [Aspose.TeX 免費試用頁面](https://releases.aspose.com/) 下載完整功能的試用版。

**Q: 我該如何取得測試用的臨時授權？**  
A: 請使用位於 [Aspose 臨時授權](https://purchase.aspose.com/temporary-license/) 的臨時授權申請表，以取得 30 天的評估授權。

**Q: 我可以從哪裡購買永久授權？**  
A: 可直接於 [Aspose.TeX 購買頁面](https://purchase.aspose.com/buy) 購買授權。

**最後更新：** 2026-08-18  
**測試環境：** Aspose.TeX 24.11 for Java  
**作者：** Aspose

## 相關教學

- [在 Java 中將 TeX 轉換為 PDF、覆寫作業名稱並將終端輸出寫入 ZIP](/tex/java/customizing-output/override-job-name-zip/)
- [在 Aspose.TeX Java 中如何使用 ZIP 壓縮檔作為輸入與輸出](/tex/java/zip-archives/zip-archives-input-output/)
- [在 Java 中使用串流輸入與終端處理將 TeX 轉換為 PNG](/tex/java/advanced-io/stream-input-image-output/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}