---
date: 2026-10-19
description: 了解如何使用 Aspose.TeX for C# 將 latex 渲染為圖像並從 TeX 產生 PNG。本指南將帶您完成串流式轉換、高解析度輸出以及終端輸入處理。
keywords:
- render latex to image
- generate png from tex
- convert latex to png
- stream tex to png
lastmod: 2026-10-19
linktitle: 如何將 latex 渲染為圖像 – 在 C# 中將 TeX 轉換為 PNG
og_description: 使用 Aspose.TeX for C# 將 latex 渲染為圖像並從 TeX 產生 PNG。遵循一步一步、適合串流的指南以獲得高解析度輸出。
og_image_alt: Tutorial showing how to convert LaTeX source to a PNG image using Aspose.TeX
  in C#
og_title: 將 latex 渲染為圖像 – 在 C# 中將 TeX 轉換為 PNG
schemas:
- author: Aspose
  dateModified: '2026-10-19'
  description: Learn how to render latex to image and generate PNG from TeX using
    Aspose.TeX for C#. This guide walks you through stream‑based conversion, high‑resolution
    output, and terminal input handling.
  headline: How to render latex to image – convert TeX to PNG in C#
  type: TechArticle
- questions:
  - answer: Absolutely. Aspose.TeX works in desktop, web, and service‑oriented apps;
      just replace the console streams with custom UI streams.
    question: Can I use Aspose.TeX for .NET in a non‑console application?
  - answer: Set `PngSaveOptions.Resolution` to the desired DPI (e.g., `Resolution
      = 600`) before invoking the rendering job.
    question: How can I customize the output image resolution?
  - answer: Yes, you can explore Aspose.TeX with a free trial on the **[Aspose.TeX
      free trial page](https://releases.aspose.com/)**.
    question: Is there a trial version available?
  - answer: Visit the Aspose.TeX community forum on **[Aspose.TeX forum](https://forum.aspose.com/c/tex/47)**
      for community support and discussions.
    question: Where can I find additional support and assistance?
  - answer: You can acquire a temporary license through the **[temporary license request
      page](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.TeX?
  type: FAQPage
second_title: Aspose.TeX .NET API
tags:
- render latex
- Aspose.TeX
- C# image conversion
title: 如何將 latex 渲染為圖像 – 在 C# 中將 TeX 轉換為 PNG
url: /zh-hant/net/advanced-io/stream-input-image-output-terminal-input-csharp/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 將 LaTeX 渲染為圖像 – 在 C# 中將 TeX 轉換為 PNG

在本綜合教學中，您將 **render latex to image** 從 TeX 原始字串使用 Aspose.TeX for C# 進行渲染。無論您是需要在網頁中嵌入數學公式、在雲端服務產生預覽圖像，或是自動化報告產生，我們都會帶您一步步處理串流、設定圖像輸出，並捕獲終端機輸入——全部不需要觸碰檔案系統。  

## 快速解答
- **Aspose.TeX 的功能是什麼？** 它會解析 TeX 原始碼並將其渲染為各種格式，包括 PNG。  
- **我可以在不寫入磁碟檔案的情況下將 TeX 轉換為 PNG 嗎？** 可以——您可以透過 `MemoryStream` 提供 TeX，並直接捕獲 PNG 位元組。  
- **支援哪些 .NET 版本？** 所有現代 .NET 版本（Framework 4.6+、.NET Core 3.1+、.NET 5/6）。  
- **在正式環境使用是否需要授權？** 正式環境需要商業授權；亦提供免費試用版。  
- **可以設定的圖像解析度為何？** `PngSaveOptions.Resolution` 屬性可讓您指定 DPI（例如 300 dpi）。  

## 如何使用 Aspose.TeX 從 TeX 建立 LaTeX PNG？

`MemoryStream` 提供基於記憶體的串流，避免檔案系統 I/O。`PngSaveOptions` 設定 PNG 參數，如解析度與壓縮。`ImageDevice` 在記憶體中捕獲渲染後的圖像資料。將您的 TeX 原始碼載入串流，設定所需 DPI，執行渲染作業，並取得 PNG 位元組陣列。此方式適用於任何想要轉換為 PNG 的 TeX 片段。  

## 什麼是「convert tex to png」？

將 TeX 轉換為 PNG 意指將 TeX 標記字串（用於科學文件的語言）渲染為點陣圖像。當您需要在網頁、行動應用程式，或任何無法原生渲染 TeX 的環境中嵌入數學公式或完整的 TeX 頁面時，這非常有用。  

## 為何使用 Aspose.TeX 從 TeX 產生 PNG？

Aspose.TeX 支援渲染 **超過 60 個 TeX 指令**，且可處理最多 **300 頁** 的文件而不需將整個檔案載入記憶體，提供 300 dpi 或更高解析度的高品質 PNG。此函式庫純 .NET，讓您無需在伺服器上安裝完整的 TeX 發行套件，其支援串流的 API 讓您全程在記憶體中操作——非常適合雲端原生微服務。  

## 前置條件
- 基本的 C# 知識。  
- 已安裝 Aspose.TeX for .NET – 您可從 **[Aspose.TeX for .NET download page](https://releases.aspose.com/tex/net/)** 下載。  
- C# 開發環境（Visual Studio、VS Code、Rider 等）。  

## 匯入命名空間

在 C# 檔案的頂部加入必要的 `using` 陳述式，以便存取 Aspose.TeX 類別：

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Image;
using System.IO;
using System.Text;
```

## 步驟 1：設定轉換選項

`PngSaveOptions` 讓您在渲染前設定 PNG 專屬參數，如解析度與壓縮。

```csharp
// ExStart:TakeMainInputFromStream-AuxFromFileSystem-TakeTerminalInputFromConsole-AlternativeImagesStorage
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
options.JobName = "stream-in-image-out";
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
options.TerminalIn = new InputConsoleTerminal();
options.TerminalOut = new OutputConsoleTerminal();
options.SaveOptions = new PngSaveOptions() { Resolution = 300 };
```

## 步驟 2：建立影像裝置並執行作業

`ImageDevice` 接收渲染後的頁面，並將每頁儲存為 PNG 位元組陣列。

```csharp
ImageDevice device = new ImageDevice();
TeXJob job = new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
    "\\hrule height 10pt width 95pt\\vskip10pt\\hrule height 5pt")),
    device, options);
job.Run();
```

## 步驟 3：在主控台提供輸入

當主控台出現提示時，輸入 **ABC**，按 **Enter**，再輸入 **\end** 並再次按 **Enter**。此示範在 TeX 引擎執行時如何捕獲終端機輸入。  

## 步驟 4：微調輸出

作業完成後，您可以在主控台寫入換行，並從裝置取得原始 PNG 位元組。`result` 陣列每頁保存一個 PNG 圖像。

```csharp
options.TerminalOut.Writer.WriteLine();
byte[][] result = device.Result;
// ExEnd:TakeMainInputFromStream-AuxFromFileSystem-TakeTerminalInputFromConsole-AlternativeImagesStorage
```

現在您可以將 `result[0]` 儲存為檔案、透過網路傳送，或直接嵌入 UI 元件中。  

## 常見問題與解決方案

| 問題 | 發生原因 | 解決方法 |
|------|----------|----------|
| **沒有 PNG 輸出** | `SaveOptions` 未設定或解析度為零。 | 確保 `options.SaveOptions = new PngSaveOptions() { Resolution = 300 };` |
| **主控台卡住** | TeX 輸入永遠未收到 `\end`。 | 務必以 `\end`（或 `\stop`）結束 TeX 串流。 |
| **圖像尺寸不正確** | 預設 DPI 為 96。 | 在 `PngSaveOptions` 中提升 `Resolution`。 |
| **找不到檔案系統路徑** | 工作目錄字串錯誤。 | 使用絕對路徑或在執行前確認目錄是否存在。 |

## 常見問答

**Q: 我可以在非主控台應用程式中使用 Aspose.TeX for .NET 嗎？**  
A: 當然可以。Aspose.TeX 可在桌面、網頁與服務導向的應用程式中使用；只需將主控台串流換成自訂 UI 串流即可。  

**Q: 如何自訂輸出圖像的解析度？**  
A: 在呼叫渲染作業之前，將 `PngSaveOptions.Resolution` 設為所需的 DPI（例如 `Resolution = 600`）。  

**Q: 是否提供試用版？**  
A: 有，您可在 **[Aspose.TeX free trial page](https://releases.aspose.com/)** 取得免費試用。  

**Q: 我可以在哪裡取得更多支援與協助？**  
A: 前往 **[Aspose.TeX forum](https://forum.aspose.com/c/tex/47)** 社群論壇，獲得社群支援與討論。  

**Q: 如何取得 Aspose.TeX 的臨時授權？**  
A: 您可透過 **[temporary license request page](https://purchase.aspose.com/temporary-license/)** 申請臨時授權。  

## 結論

您現在已了解如何使用 Aspose.TeX for C# **render latex to image**。透過設定串流、建立 `ImageDevice`，以及處理終端機輸入，您可以從任何 TeX 原始碼產生高解析度的 PNG——非常適合報告、網頁預覽或自動化流程。嘗試不同的 TeX 片段、調整 DPI，或將產生的位元組陣列整合至自訂 UI，以獲得無縫體驗。  

---

**最後更新：** 2026-10-19  
**測試環境：** Aspose.TeX 24.11 for .NET  
**作者：** Aspose  

## 相關教學
- [使用 Aspose.TeX for .NET 將 LaTeX 轉換為 PNG – 處理檔案系統與 ZIP 輸入](/tex/net/file-input-output/required-inputs-from-filesystem-and-zip/)
- [使用 Aspose.TeX 渲染 LaTeX 為 PNG（C#）](/tex/net/render-latex-figures/png-latex-figure-renderer-csharp/)
- [Aspose.TeX 在 .NET 中的 LaTeX PDF 轉換 – 兩種簡易方法](/tex/net/latex-conversion/to-pdf/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}