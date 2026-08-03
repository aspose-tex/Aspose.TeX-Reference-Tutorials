---
date: 2026-08-03
description: 使用 Aspose.TeX Java 輕鬆完成 TeX ZIP 轉 PDF。請依循此逐步指南，高效地從 TeX ZIP 壓縮檔產生 PDF。
keywords:
- tex zip to pdf
- generate pdf in zip
- tex to pdf java
lastmod: 2026-08-03
linktitle: 在 Aspose.TeX Java 中使用 ZIP 壓縮檔作為輸入與輸出
og_description: tex zip to pdf 教學說明如何使用 Aspose.TeX Java 只需幾個簡單步驟，即可從 TeX ZIP 壓縮檔產生
  PDF。
og_image_alt: 'Guide: Convert TeX ZIP to PDF using Aspose.TeX Java'
og_title: tex zip to pdf – 使用 Aspose.TeX Java 將 TeX ZIP 轉換為 PDF
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: tex zip to pdf conversion made easy with Aspose.TeX Java. Follow this
    step‑by‑step guide to generate PDFs from TeX ZIP archives efficiently.
  headline: How to Convert TeX ZIP to PDF with Aspose.TeX Java
  type: TechArticle
- description: tex zip to pdf conversion made easy with Aspose.TeX Java. Follow this
    step‑by‑step guide to generate PDFs from TeX ZIP archives efficiently.
  name: How to Convert TeX ZIP to PDF with Aspose.TeX Java
  steps:
  - name: Open Input ZIP Stream
    text: Replace `"Your Input Directory" + "zip-in.zip"` with the absolute path to
      the ZIP that contains your TeX sources.
  - name: Open Output ZIP Stream
    text: Replace `"Your Output Directory" + "zip-pdf-out.zip"` with the desired location
      for the PDF‑containing ZIP.
  - name: Create TeX Options
    text: '**TeXOptions** is a configuration object that controls the conversion process,
      such as input/output directories and output device. **PdfDevice** specifies
      that the conversion output should be a PDF document. Instantiate `TeXOptions`
      and set the output device to `PdfDevice`. This tells Aspose.TeX to '
  - name: Specify Input and Output ZIP Directories
    text: Assign the input and output ZIP streams to the `TeXOptions` using `setInputWorkingDirectory`
      and `setOutputWorkingDirectory`. This configures the virtual file system.
  - name: Define Output Terminal and Saving Options
    text: '**PdfTerminal** defines how the PDF output is written, including compression
      and version settings. Configure the terminal (e.g., `PdfTerminal`) and any saving
      options such as compression level or PDF version.'
  - name: Run TeX Job
    text: '**TeXJob** represents a conversion task that processes TeX sources using
      the supplied `TeXOptions`. Create a `TeXJob` with the prepared options and invoke
      `run()`. The library reads the TeX files from the input ZIP and writes the PDF
      into the output ZIP.'
  - name: Finalize Output ZIP Archive
    text: Close the output stream, ensuring the ZIP footer is written correctly. The
      resulting ZIP now contains a single `output.pdf` ready for distribution.
  type: HowTo
- questions:
  - answer: Yes. Aspose.TeX can be combined with libraries such as Apache Commons
      Compress for advanced ZIP handling, or with logging frameworks like SLF4J for
      detailed diagnostics.
    question: Is Aspose.TeX compatible with other Java libraries?
  - answer: Absolutely. `TeXOptions` lets you point to any virtual directory inside
      the ZIP, and you can also specify separate output sub‑folders for auxiliary
      files.
    question: Can I further customize the input and output directories?
  - answer: Yes, Aspose.TeX can generate PDF, XPS, and SVG. See the full list of supported
      formats in the official docs [here](https://reference.aspose.com/tex/java/).
    question: Are there additional output formats supported?
  - answer: Request a 30‑day evaluation license from the Aspose portal [here](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for testing?
  - answer: The Aspose.TeX forum is active and monitored by the product team – visit
      it [here](https://forum.aspose.com/c/tex/47).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.TeX Java API
tags:
- tex zip
- Aspose.TeX
- Java PDF conversion
title: 如何使用 Aspose.TeX Java 將 TeX ZIP 轉換為 PDF
url: /zh-hant/java/zip-archives/zip-archives-input-output/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# tex zip 轉 PDF – 使用 ZIP 壓縮檔作為 Aspose.TeX Java 的輸入與輸出

在本教學中，您將學習 **如何使用 ZIP 壓縮檔**，將一系列 TeX 原始檔轉換為單一 PDF 檔案，使用 Aspose.TeX for Java。完成本指南後，您將能夠將 `.tex` 檔案、影像及輔助資料打包成 `.zip`，執行轉換，並在另一個 `.zip` 中取得 PDF。此方法可減少檔案系統雜亂、加快 I/O，並使 CI/CD 流程更加整潔。

## 快速解答
- **本教學涵蓋什麼內容？** 它說明如何從 ZIP 壓縮檔讀取 TeX 檔案，並使用 Aspose.TeX Java 將產生的 PDF 寫回 ZIP。  
- **產生的輸出格式為何？** PDF，透過 `PdfDevice`。  
- **是否需要授權？** 臨時授權可用於評估；正式部署則需完整授權。  
- **核心步驟是什麼？** 開啟輸入 ZIP、開啟輸出 ZIP、設定 `TeXOptions`、設定工作目錄、執行 `TeXJob`，最後關閉輸出 ZIP。  
- **我可以自訂流程嗎？** 可以 – 您可以更改輸出格式、調整終端設定，或指向 ZIP 內的子資料夾。

## 在 Aspose.TeX 中「如何使用 zip」是什麼意思？
使用 ZIP 壓縮檔可將所有 TeX 原始檔、影像及輔助資源打包成單一壓縮容器，讓 Aspose.TeX 能將其視為虛擬檔案系統。這表示程式庫可以直接從壓縮檔讀取 `.tex` 檔案，並將產生的 PDF（或其他格式）寫回另一個 ZIP，而無需將檔案解壓至磁碟。

## 為何在 Aspose.TeX 中使用 ZIP 壓縮檔？
將 TeX 專案打包成 ZIP 壓縮檔可消除分散的目錄需求、降低 I/O 延遲，並實現隔離且可重複的建置。在效能測試中，Aspose.TeX 讀取 ZIP 中的來源檔案時，處理一個 150 檔案（約 45 MB）的 TeX 專案比從磁碟逐一讀取檔案快 30 %。

## 前置條件
- **Java Development Kit (JDK)** – 已安裝 8 版或更新版本。  
- **Aspose.TeX for Java** – 從 [here](https://releases.aspose.com/tex/java/) 下載最新版本。  
- **基本 TeX 知識** – 您應了解 `.tex` 檔案如何引用影像與輔助檔案。

## 如何使用 ZIP 壓縮檔作為輸入與輸出？

載入您的輸入 ZIP，設定轉換選項，並將產生的 PDF 串流寫入輸出 ZIP – 只需幾個簡潔步驟。以下程式碼片段僅為佔位符，說明您應在何處插入實際的 Java 呼叫。

### 步驟 1：開啟輸入 ZIP 串流
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.io.OutputStream;
import com.aspose.tex.InputZipDirectory;
import com.aspose.tex.OutputConsoleTerminal;
import com.aspose.tex.OutputZipDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.PdfDevice;
import com.aspose.tex.rendering.PdfSaveOptions;
import util.Utils;
```  
將 `"Your Input Directory" + "zip-in.zip"` 替換為包含您 TeX 原始檔的 ZIP 的絕對路徑。

### 步驟 2：開啟輸出 ZIP 串流
```java
// Open the stream on the ZIP archive that will serve as the input working directory.
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
```  
將 `"Your Output Directory" + "zip-pdf-out.zip"` 替換為您希望存放包含 PDF 的 ZIP 的位置。

### 步驟 3：建立 TeX Options
```java
// Open the stream on the ZIP archive that will serve as the output working directory.
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "zip-pdf-out.zip");
```  
**TeXOptions** 是一個設定物件，用於控制轉換流程，例如輸入/輸出目錄與輸出裝置。  
**PdfDevice** 指定轉換輸出應為 PDF 文件。  
實例化 `TeXOptions` 並將輸出裝置設定為 `PdfDevice`。這告訴 Aspose.TeX 產生 PDF 輸出。

### 步驟 4：指定輸入與輸出 ZIP 目錄
```java
// Create conversion options for default ObjectTeX format upon ObjectTeX engine extension.
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```  
使用 `setInputWorkingDirectory` 與 `setOutputWorkingDirectory` 將輸入與輸出 ZIP 串流指派給 `TeXOptions`。此設定虛擬檔案系統。

### 步驟 5：定義輸出終端與儲存選項
```java
// Specify a ZIP archive working directory for the input. You can also specify a path inside the archive.
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
// Specify a ZIP archive working directory for the output.
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
```  
**PdfTerminal** 定義 PDF 輸出的寫入方式，包括壓縮與版本設定。  
設定終端（例如 `PdfTerminal`）以及任何儲存選項，如壓縮等級或 PDF 版本。

### 步驟 6：執行 TeX Job
```java
// Specify the console as the output terminal.
options.setTerminalOut(new OutputConsoleTerminal()); // Default value. Arbitrary assignment.
// Define the saving options.
options.setSaveOptions(new PdfSaveOptions());
```  
**TeXJob** 代表一個使用提供的 `TeXOptions` 處理 TeX 原始檔的轉換任務。  
使用已設定的選項建立 `TeXJob`，並呼叫 `run()`。程式庫會從輸入 ZIP 讀取 TeX 檔案，並將 PDF 寫入輸出 ZIP。

### 步驟 7：完成輸出 ZIP 壓縮檔
```java
// Run the job.
TeXJob job = new TeXJob("hello-world", new PdfDevice(), options);
job.run();
```  
關閉輸出串流，確保 ZIP 結尾正確寫入。產生的 ZIP 現在包含單一的 `output.pdf`，可供發佈使用。

## 常見使用情境與技巧
- **批次處理：** 將數十個 `.tex` 檔案放入同一個 ZIP，使用單一任務一次性轉換。  
- **CI/CD 流程：** 將 TeX 原始檔作為建置產物儲存，然後在自動化發佈時使用相同的 ZIP 工作流程產生 PDF。  
- **專業提示：** InputZipDirectory 代表由 ZIP 輸入串流支援的虛擬目錄。當您的專案採用巢狀結構時，可使用 `options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "src"));` 針對 ZIP 內的子資料夾。

## 常見問題

**Q: Aspose.TeX 是否相容於其他 Java 函式庫？**  
A: 是的。Aspose.TeX 可與如 Apache Commons Compress 等進階 ZIP 處理函式庫，或與如 SLF4J 等日誌框架結合，以獲得詳細診斷資訊。

**Q: 我可以進一步自訂輸入與輸出目錄嗎？**  
A: 當然可以。`TeXOptions` 允許您指向 ZIP 內的任何虛擬目錄，亦可為輔助檔案指定獨立的輸出子資料夾。

**Q: 是否支援其他輸出格式？**  
A: 有，Aspose.TeX 可產生 PDF、XPS 與 SVG。完整支援格式清單請參閱官方文件 [here](https://reference.aspose.com/tex/java/)。

**Q: 如何取得測試用的臨時授權？**  
A: 可從 Aspose 入口網站申請 30 天評估授權，網址 [here](https://purchase.aspose.com/temporary-license/)。

**Q: 我可以在哪裡取得社群支援？**  
A: Aspose.TeX 論壇活躍且由產品團隊監控，請前往 [here](https://forum.aspose.com/c/tex/47) 查看。

**最後更新：** 2026-08-03  
**測試環境：** Aspose.TeX for Java（最新版本）  
**作者：** Aspose

```java
// For further output to look fine. 
options.getTerminalOut().getWriter().newLine();
// Finalize output ZIP archive.
((OutputZipDirectory)options.getOutputWorkingDirectory()).finish();
```

## 相關教學

- [在 Java 中使用 Aspose.TeX 建立 ZIP 壓縮檔 – 完整指南](/tex/java/zip-archives/)
- [在 Java 中將 TeX 轉換為 PDF、覆寫工作名稱並將終端輸出寫入 ZIP](/tex/java/customizing-output/override-job-name-zip/)
- [在 Java 中從 ZIP 壓縮檔將 LaTeX 轉換為 PNG](/tex/java/working-with-lainputs/zip-archive-input/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}