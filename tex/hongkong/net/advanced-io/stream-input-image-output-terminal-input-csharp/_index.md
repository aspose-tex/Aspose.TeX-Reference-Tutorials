---
date: 2025-12-20
description: 學習如何使用 Aspose.TeX for C# 將 TeX 轉換為 PNG。本指南將向您展示如何從 TeX 生成圖像、處理串流以及捕獲終端輸入。
linktitle: Convert TeX to PNG – Master Streams, Images, & Terminal Input in Aspose.TeX
  for C#
second_title: Aspose.TeX .NET API
title: 將 TeX 轉換為 PNG – 掌握 Aspose.TeX for C# 中的串流、圖像與終端輸入
url: /zh-hant/net/advanced-io/stream-input-image-output-terminal-input-csharp/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 轉換 TeX 為 PNG – 主控串流、圖像與終端機輸入於 Aspose.TeX for C#

## 介紹

在本完整教學中，您將學會 **如何使用 Aspose.TeX for C# 將 TeX 轉換為 PNG**。無論是為了報告、網頁預覽，或是自動化文件流程需要 **從 TeX 產生圖像**，本指南都會一步步說明如何處理串流、管理圖像，並捕捉終端機輸入——全部以單一、易於跟隨的範例示範。

## 快速答覆
- **Aspose.TeX 的功能是什麼？** 它會解析 TeX 原始碼，並將其渲染成多種格式，包括 PNG。  
- **可以不寫入磁碟就將 TeX 轉換為 PNG 嗎？** 可以——您可以透過 `MemoryStream` 輸入 TeX，直接取得 PNG 位元組。  
- **支援哪些 .NET 版本？** 所有現代 .NET 版本（Framework 4.6+、.NET Core 3.1+、.NET 5/6）。  
- **正式環境需要授權嗎？** 生產環境必須購買商業授權；亦提供免費試用版。  
- **可以設定什麼影像解析度？** `PngSaveOptions.Resolution` 屬性可指定 DPI（例如 300 dpi）。

## 什麼是「convert tex to png」？

將 TeX 轉換為 PNG 意指把 TeX 標記字串（科學文件常用語言）渲染成點陣圖。當您想在網頁、行動應用程式，或任何無法原生呈現 TeX 的環境中嵌入數學公式或完整的 TeX 頁面時，這項功能就非常有用。

## 為什麼要使用 Aspose.TeX 產生 TeX 圖像？

- **無外部相依性** – Aspose.TeX 為純 .NET 函式庫，伺服器上不需安裝 TeX 發行版。  
- **支援串流的 API** – 可直接與 `MemoryStream` 搭配，特別適合雲端服務與微服務。  
- **細緻控制** – 您可以設定影像解析度、輸出目錄，甚至捕捉互動式終端機輸入。  

## 前置作業

在開始撰寫程式碼前，請先確認您已具備：

- 基本的 C# 知識。  
- 已安裝 Aspose.TeX for .NET – 可於 **[此處](https://releases.aspose.com/tex/net/)** 下載。  
- C# 開發環境（Visual Studio、VS Code、Rider 等）。  

## 匯入命名空間

在 C# 檔案的最上方加入必要的 `using` 陳述式，以便存取 Aspose.TeX 類別：

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Image;
using System.IO;
using System.Text;
```

## 步驟 1：設定轉換選項

配置轉換管線。此處我們告訴 Aspose.TeX 將應用程式視為主控台應用程式，指定輸入/輸出資料夾、路由終端機 I/O，並要求以 300 dpi 輸出 PNG。

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

## 步驟 2：建立 ImageDevice 並執行工作

`ImageDevice` 會捕捉渲染後的 PNG 資料。我們透過 `MemoryStream` 輸入簡單的 TeX 片段，執行工作，讓 Aspose.TeX 完成繁重的渲染工作。

```csharp
ImageDevice device = new ImageDevice();
TeXJob job = new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
    "\\hrule height 10pt width 95pt\\vskip10pt\\hrule height 5pt")),
    device, options);
job.Run();
```

## 步驟 3：在主控台提供輸入

當主控台出現提示時，輸入 **ABC**，按 **Enter**，再輸入 **\end** 並再次按 **Enter**。此步驟示範在 TeX 引擎執行期間，如何捕捉終端機輸入。

## 步驟 4：微調輸出

工作完成後，您可以在主控台寫入換行，並從裝置取得原始 PNG 位元組。`result` 陣列每一頁對應一個 PNG 影像。

```csharp
options.TerminalOut.Writer.WriteLine();
byte[][] result = device.Result;
// ExEnd:TakeMainInputFromStream-AuxFromFileSystem-TakeTerminalInputFromConsole-AlternativeImagesStorage
```

現在您可以將 `result[0]` 儲存為檔案、傳送至網路，或直接嵌入 UI 元件中。

## 常見問題與解決方案

| 問題 | 為何會發生 | 解決方式 |
|------|------------|----------|
| **沒有 PNG 輸出** | 未設定 `SaveOptions` 或解析度為 0。 | 確認 `options.SaveOptions = new PngSaveOptions() { Resolution = 300 };` |
| **主控台卡住** | TeX 輸入未收到 `\end`。 | 必須以 `\end`（或 `\stop`）結束 TeX 串流。 |
| **影像尺寸不正確** | 預設 DPI 為 96。 | 在 `PngSaveOptions` 中提升 `Resolution`。 |
| **找不到檔案系統路徑** | 工作目錄字串錯誤。 | 使用絕對路徑或在執行前確認目錄是否存在。 |

## 常見問答

### Q1：可以在非主控台應用程式中使用 Aspose.TeX for .NET 嗎？

A1：當然可以！Aspose.TeX 可在桌面、Web 與服務導向的應用程式中使用。只要將主控台終端機換成自訂串流或 UI 控制項即可。

### Q2：如何自訂輸出影像的解析度？

A2：在範例中，解析度是透過 `PngSaveOptions.Resolution` 設定。將整數值改為其他數字（例如 `Resolution = 600`）即可取得更高品質的 PNG。

### Q3：有提供試用版嗎？

A3：有，您可於 **[此處](https://releases.aspose.com/)** 取得 Aspose.TeX 的免費試用版。

### Q4：在哪裡可以取得更多支援與協助？

A4：請前往 Aspose.TeX 論壇 **[此處](https://forum.aspose.com/c/tex/47)** 取得社群支援與討論。

### Q5：如何取得 Aspose.TeX 的臨時授權？

A5：您可於 **[此處](https://purchase.aspose.com/temporary-license/)** 取得臨時授權。

## 結論

您現在已了解如何使用 Aspose.TeX for C# **將 TeX 轉換為 PNG**。透過設定串流、建立 `ImageDevice`，以及處理終端機輸入，您可以從任何 TeX 原始碼產生高解析度影像，適用於報告、網頁預覽或自動化流程。接下來可嘗試不同的 TeX 片段、調整 DPI，或將位元組直接整合至自訂 UI 中。

---

**最後更新：** 2025-12-20  
**測試版本：** Aspose.TeX 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}