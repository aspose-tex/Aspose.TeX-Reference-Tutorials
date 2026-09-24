---
date: 2026-09-24
description: 了解如何使用 Aspose.TeX for .NET 於 C# 中設定 TeX 輸入目錄、資料流、影像以及終端機輸入。
keywords:
- configure tex input directory
- add image stream tex
- add images from stream
lastmod: 2026-09-24
linktitle: 進階 Aspose.TeX 輸入與輸出
og_description: 設定 TeX 輸入目錄、加入影像資料流，並使用 Aspose.TeX for .NET 於 C# 處理終端機輸入。一步一步學習。
og_image_alt: Guide showing how to configure TeX input directory and streams in Aspose.TeX
  for .NET
og_title: 設定 TeX 輸入目錄 – 進階 Aspose.TeX 指南
schemas:
- author: Aspose
  dateModified: '2026-09-24'
  description: Learn how to configure TeX input directory, streams, images, and terminal
    input using Aspose.TeX for .NET in C#.
  headline: Configure TeX input directory – Advanced Aspose.TeX Input and Output
  type: TechArticle
- description: Learn how to configure TeX input directory, streams, images, and terminal
    input using Aspose.TeX for .NET in C#.
  name: Configure TeX input directory – Advanced Aspose.TeX Input and Output
  steps:
  - name: instantiate TeXInputOptions
    text: Assign the base folder that holds the primary TeX source.
  - name: add extra search paths
    text: If your project stores figures in a separate folder (e.g., *Images*), call
      `AddSearchPath` to include it.
  - name: hand the options to the processor
    text: Create a `TeXProcessor`, provide the configured options, and invoke `Process`
      or `Render`.
  type: HowTo
- questions:
  - answer: Yes—you can create a new `TeXInputOptions` instance with a different `BaseFolder`
      and pass it to a fresh `TeXProcessor` whenever you need to reconfigure.
    question: Can I change the input directory at runtime?
  - answer: Retrieve the image as a `byte[]`, wrap it in a `MemoryStream`, and call
      `TeXInputOptions.AddImage("image.png", stream)`. The name must match the reference
      in your `.tex` file.
    question: How do I add images that are stored in a database?
  - answer: Absolutely. Convert the incoming string to a `MemoryStream`, set it as
      the source for `TeXProcessor`, and render directly to your desired output format.
    question: Is it possible to process LaTeX code received from a web API without
      saving a file?
  - answer: Dispose of any streams you create, and for large workloads invoke `TeXProcessor.Cleanup()`
      to free native resources.
    question: Do I need to call any cleanup methods after processing?
  - answer: The two tutorial links above contain full code samples that demonstrate
      each scenario in detail, including error handling and performance tips.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.TeX .NET API
tags:
- Aspose.TeX
- input directory
- C# document processing
title: 設定 TeX 輸入目錄 – 進階 Aspose.TeX 輸入與輸出
url: /zh-hant/net/advanced-io/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.TeX for .NET 中設定 TeX 輸入目錄

Aspose.TeX for .NET 讓您能將完整功能的 TeX 處理直接嵌入 C# 應用程式中。在本教學中，您將學習如何**設定 TeX 輸入目錄**、從串流提供 LaTeX 內容，以及在不觸及檔案系統的情況下加入圖片。如果您需要精確控制引擎搜尋 `.tex` 檔案和資源的位置，這裡正是您需要的地方。

## 快速解答
- **什麼是「configure tex input directory」的含義？**  
  它告訴 Aspose.TeX 在哪裡尋找主要的 `.tex` 檔案、輔助檔案以及圖形。
- **哪個類別定義了輸入路徑？**  
  `TeXInputOptions` 儲存基礎資料夾以及任何額外的搜尋位置。
- **我可以從記憶體串流載入圖片嗎？**  
  可以——使用 `TeXInputOptions.AddImage` 搭配 `Stream` 實例。
- **是否能編譯在執行時提供的 LaTeX 程式碼？**  
  當然可以——將包含來源文字的 `MemoryStream` 傳遞給處理器。
- **生產環境使用是否需要授權？**  
  在非評估部署中，需要有效的 Aspose.TeX 授權。

## TeXInputOptions 是什麼？

`TeXInputOptions` 是用來定義 TeX 資源的基礎資料夾與額外搜尋路徑的設定物件。正確設定可消除「找不到檔案」錯誤，並讓您保持資產有條理。

## 如何設定 tex 輸入目錄？

`TeXInputOptions` 是一個設定物件，用於指定 TeX 資源的基礎資料夾與額外搜尋路徑。只需幾行程式碼即可載入主要文件並告訴處理器搜尋所有內容的位置。此直接答案說明了在任何額外細節之前的必要步驟。

建立 `TeXInputOptions` 實例，將 `BaseFolder` 設為包含主要 `.tex` 檔案的資料夾，加入任何存放圖片或輔助檔案的子資料夾，然後將此選項傳遞給 `TeXProcessor`。引擎將自動解析所有相對參照。

### 步驟 1：實例化 TeXInputOptions
指定保存主要 TeX 原始檔的基礎資料夾。

### 步驟 2：加入額外搜尋路徑
如果您的專案將圖形存放在獨立的資料夾（例如 *Images*），請呼叫 `AddSearchPath` 將其加入。

### 步驟 3：將選項交給處理器
建立 `TeXProcessor`，提供已設定的選項，然後呼叫 `Process` 或 `Render`。

## 如何使用 Aspose.TeX 加入圖片
在 TeX 檔案中引用的圖片可以透過資料夾或直接從串流提供。當圖片儲存在資料庫或即時產生時，使用串流特別有用。`AddImage(string name, Stream data)` 會以給定的檔名註冊圖片串流，以供 TeX 文件使用。此方法可避免暫存檔，並加快處理速度。

## 如何在 Aspose.TeX 中處理串流
當您的 LaTeX 原始碼是動態產生的——可能來自使用者輸入或 Web 服務時，您可以直接將其餵入處理器而不必寫入檔案。`TeXProcessor` 會處理 TeX 內容，並可接受包含來源 LaTeX 程式碼的 `MemoryStream`。將 LaTeX 字串包裝成 `MemoryStream`，在 `TeXProcessor` 中設為來源串流，然後執行轉換。此技巧同樣適用於磁碟 I/O 成本高的雲端原生服務。

## 為何使用 Aspose.TeX 進行進階 I/O？
Aspose.TeX 支援 **30 多種輸入與輸出格式**（包括 PDF、PNG、SVG），且能在不將整個檔案載入記憶體的情況下渲染數百頁的文件。其以串流為先的設計相較於基於檔案的工作流程，可減少高達 40 % 的 I/O 開銷，十分適合高吞吐量的伺服器應用程式。

## 前置條件
- .NET 6.0 或更新版本（此函式庫亦支援 .NET Core 3.1+ 與 .NET Framework 4.6.1+）
- Aspose.TeX for .NET NuGet 套件（版本 24.11 或更新）
- 生產環境使用的有效 Aspose.TeX 授權

## 探索 Aspose.TeX：進階文件處理的入口
要看到設定實際運作的樣子，請依照我們的步驟指南 **[指定 Aspose.TeX 所需的輸入目錄 (C#)](./required-input-directory-csharp/)**。該教學會帶您建立 `TeXInputOptions` 物件並產生 PDF 輸出。  
**[指定 Aspose.TeX 所需的輸入目錄 (C#)](./required-input-directory-csharp/)**

## 精通 Aspose.TeX for C# 中的串流、圖片與終端輸入
若想更深入了解從記憶體餵入 LaTeX、透過串流加入圖片，以及使用終端式輸入，請參考 **[精通 Aspose.TeX for C# 中的串流、圖片與終端輸入](./stream-input-image-output-terminal-input-csharp/)**。它示範了如何將 Aspose.TeX 整合到 Web API、背景服務與主控台工具中。  
**[精通 Aspose.TeX for C# 中的串流、圖片與終端輸入](./stream-input-image-output-terminal-input-csharp/)**

## 常見問題與解決方案
- **「File not found」錯誤** – 確認 `BaseFolder` 指向正確的目錄，且在渲染前已加入任何額外的搜尋路徑。
- **圖片未載入** – 確保 `AddImage` 中的圖片名稱與 TeX 原始碼中使用的名稱完全相同，包含檔案副檔名。
- **記憶體使用激增** – 處理非常大的文件時，渲染完成後呼叫 `TeXProcessor.Cleanup()` 以釋放非受控資源。

## 常見問與答

**Q: 我可以在執行時變更輸入目錄嗎？**  
A: 可以——您可以建立具有不同 `BaseFolder` 的新 `TeXInputOptions` 實例，並在需要重新設定時將其傳遞給新的 `TeXProcessor`。

**Q: 如何加入儲存在資料庫中的圖片？**  
A: 先將圖片以 `byte[]` 形式取回，包裝成 `MemoryStream`，然後呼叫 `TeXInputOptions.AddImage("image.png", stream)`。名稱必須與 `.tex` 檔案中的引用相符。

**Q: 是否能在不儲存檔案的情況下處理從 Web API 接收的 LaTeX 程式碼？**  
A: 當然可以。將收到的字串轉換為 `MemoryStream`，設為 `TeXProcessor` 的來源，然後直接渲染為您想要的輸出格式。

**Q: 處理完畢後需要呼叫任何清理方法嗎？**  
A: 請釋放您建立的任何串流，對於大量工作負載，請呼叫 `TeXProcessor.Cleanup()` 以釋放原生資源。

**Q: 我可以在哪裡找到更進階的範例？**  
A: 上述兩個教學連結提供完整的程式碼範例，詳細示範每個情境，包括錯誤處理與效能技巧。

---

**最後更新:** 2026-09-24  
**測試環境:** Aspose.TeX 24.11 for .NET  
**作者:** Aspose

## 相關教學

- [取得 TeX 檔案串流 (C#) 使用 Aspose.TeX API 所需的輸入目錄](/tex/net/advanced-io/required-input-directory-csharp/)
- [使用檔案系統從 TeX 建立 XPS – Aspose.TeX for .NET](/tex/net/file-input-output/filesystem-input-xps-output/)
- [使用 Aspose.TeX for .NET 將 LaTeX 轉換為 PNG – 處理檔案系統與 ZIP 輸入](/tex/net/file-input-output/required-inputs-from-filesystem-and-zip/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}