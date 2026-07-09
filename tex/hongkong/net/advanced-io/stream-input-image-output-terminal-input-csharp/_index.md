---
date: 2026-03-26
description: 學習如何使用 Aspose.TeX for C# 將 TeX 轉換為 PNG 以建立 LaTeX PNG。本指南會示範如何從 TeX 產生
  PNG、處理串流以及捕獲終端機輸入。
linktitle: Create latex png – Convert TeX to PNG with Aspose.TeX C#
second_title: Aspose.TeX .NET API
title: 產生 LaTeX PNG – 使用 Aspose.TeX C# 將 TeX 轉換為 PNG
url: /zh-hant/net/advanced-io/stream-input-image-output-terminal-input-csharp/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立 latex png – 使用 Aspose.TeX C# 將 TeX 轉換為 PNG

在本完整教學中，您將使用 Aspose.TeX for C# 從 TeX 原始字串 **建立 latex png**。無論您需要在網頁中嵌入數學公式、在雲端服務產生預覽圖像，或自動化報告產生，我們都會帶您了解如何處理串流、設定影像輸出，以及捕捉終端機輸入——全部不需觸碰檔案系統。

## 快速解答
- **Aspose.TeX 的功能是什麼？** 它會解析 TeX 原始碼並將其渲染為多種格式，包括 PNG。  
- **我可以在不寫入磁碟檔案的情況下將 TeX 轉換為 PNG 嗎？** 可以 – 您可以透過 `MemoryStream` 提供 TeX，直接取得 PNG 位元組。  
- **支援哪些 .NET 版本？** 所有現代 .NET 版本（Framework 4.6+、.NET Core 3.1+、.NET 5/6）。  
- **在正式環境使用是否需要授權？** 正式環境需要商業授權；提供免費試用版。  
- **可以設定什麼影像解析度？** `PngSaveOptions.Resolution` 屬性可讓您指定 DPI（例如 300 dpi）。

## 如何使用 Aspose.TeX 從 TeX 建立 latex png？
以下您將看到一步一步的範例，從記憶體串流讀取 TeX 片段、執行渲染工作，並回傳 PNG 位元組。相同的模式適用於任何需要 **convert tex to png** 的 TeX 文件。

## 「convert tex to png」是什麼？
將 TeX 轉換為 PNG 意指將 TeX 標記字串（用於科學文件的語言）渲染為點陣圖像。當您想在網頁、行動應用程式，或任何無法原生渲染 TeX 的環境中嵌入數學公式或完整的 TeX 頁面時，這非常有用。

## 為什麼使用 Aspose.TeX 從 tex 產生 png？
- **無需外部相依性** – Aspose.TeX 是純 .NET 函式庫，無需在伺服器上安裝 TeX 發行版。  
- **支援串流的 API** – 可直接使用 `MemoryStream`，非常適合雲端服務與微服務。  
- **細緻的控制** – 您可以設定影像解析度、輸出目錄，甚至捕捉互動式終端機輸入。  

## 前置條件
- 基本的 C# 知識。  
- 已安裝 Aspose.TeX for .NET – 您可在 **[此處](https://releases.aspose.com/tex/net/)** 下載。  
- C# 開發環境 (Visual Studio、VS Code、Rider 等)。  

## 匯入命名空間
在 C# 檔案的頂部加入必要的 `using` 陳述式，以便存取 Aspose.TeX 類別：

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Image;
using System.IO;
using System.Text;
```

## 步驟 1：設定轉換選項
設定轉換流程。此處我們告訴 Aspose.TeX 將應用程式視為主控台應用程式，指定輸入/輸出資料夾，導向終端機 I/O，並要求以 300 dpi 輸出 PNG。

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

## 步驟 2：建立 Image Device 並執行工作
`ImageDevice` 會捕捉渲染後的 PNG 資料。我們透過 `MemoryStream` 提供簡單的 TeX 片段，執行工作，讓 Aspose.TeX 完成繁重的處理。

```csharp
ImageDevice device = new ImageDevice();
TeXJob job = new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
    "\\hrule height 10pt width 95pt\\vskip10pt\\hrule height 5pt")),
    device, options);
job.Run();
```

## 步驟 3：在主控台提供輸入
當主控台出現提示時，輸入 **ABC**，按 **Enter**，再輸入 **\end** 並再次按 **Enter**。此示範在 TeX 引擎執行期間如何捕捉終端機輸入。

## 步驟 4：微調輸出
工作完成後，您可以在主控台寫入換行，並從裝置取得原始 PNG 位元組。`result` 陣列每頁保存一張 PNG 圖片。

```csharp
options.TerminalOut.Writer.WriteLine();
byte[][] result = device.Result;
// ExEnd:TakeMainInputFromStream-AuxFromFileSystem-TakeTerminalInputFromConsole-AlternativeImagesStorage
```

現在您可以將 `result[0]` 儲存為檔案、透過網路傳送，或直接嵌入 UI 元件中。

## 常見問題與解決方案

| 問題 | 發生原因 | 解決方式 |
|-------|----------------|-----|
| **沒有 PNG 輸出** | `SaveOptions` 未設定或解析度為零。 | 確保 `options.SaveOptions = new PngSaveOptions() { Resolution = 300 };` |
| **主控台卡住** | TeX 輸入永遠未收到 `\end`。 | 務必以 `\end`（或 `\stop`）結束 TeX 串流。 |
| **影像尺寸不正確** | 預設 DPI 為 96。 | 在 `PngSaveOptions` 中提升 `Resolution`。 |
| **檔案系統路徑未找到** | 工作目錄字串錯誤。 | 使用絕對路徑，或在執行前確認目錄是否存在。 |

## 常見問答

### Q1：我可以在非主控台應用程式中使用 Aspose.TeX for .NET 嗎？
A1：當然可以！Aspose.TeX 可在桌面、網頁以及服務導向的應用程式中使用。只要將主控台終端機換成自訂串流或 UI 控制項即可。

### Q2：如何自訂輸出影像的解析度？
A2：在範例中，解析度是透過 `PngSaveOptions.Resolution` 設定。將整數值（例如 `Resolution = 600`）改為更高，即可取得更高品質的 PNG。

### Q3：是否提供試用版？
A3：是的，您可在 **[此處](https://releases.aspose.com/)** 取得免費試用版，探索 Aspose.TeX。

### Q4：在哪裡可以取得更多支援與協助？
A4：前往 Aspose.TeX 論壇 **[此處](https://forum.aspose.com/c/tex/47)** 取得社群支援與討論。

### Q5：如何取得 Aspose.TeX 的臨時授權？
A5：您可於 **[此處](https://purchase.aspose.com/temporary-license/)** 取得臨時授權。

## 結論
您現在已了解如何使用 Aspose.TeX for C# **建立 latex png**。透過設定串流、建立 `ImageDevice`，以及處理終端機輸入，您可以從任何 TeX 原始碼產生高解析度影像——非常適合報告、網頁預覽或自動化流程。嘗試不同的 TeX 片段、調整 DPI，或將產生的位元組陣列整合至自訂 UI，獲得無縫體驗。

---

**最後更新：** 2026-03-26  
**測試環境：** Aspose.TeX 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}