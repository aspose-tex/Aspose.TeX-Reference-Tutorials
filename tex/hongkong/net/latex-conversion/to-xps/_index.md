---
date: 2025-12-23
description: 輕鬆學習如何在 .NET 中使用 Aspose.TeX 將 LaTeX 轉換為 XPS。高品質、可自訂且高效的轉換。
linktitle: How to Convert LaTeX to XPS in .NET – Easy Conversion with Aspose.TeX
second_title: Aspose.TeX .NET API
title: 在 .NET 中將 LaTeX 轉換為 XPS – 使用 Aspose.TeX 輕鬆轉換
url: /zh-hant/net/latex-conversion/to-xps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# LaTeX 轉 XPS（.NET）- 使用 Aspose.TeX 輕鬆轉換

## 簡介

如果你想了解 **如何將 latex** 文件轉換為 .NET 應用程式中的 XPS 格式，你來對地方了。Aspose.TeX for .NET 提供一個強大且直接的解決方案，為你處理繁重的工作。在本指南中，我們將逐步說明每個步驟，解釋每個設定的原因，並示範如何僅用幾行程式碼即可取得高品質、可自訂的 XPS 輸出。

## 快速答覆
- **什麼函式庫負責轉換？** Aspose.TeX for .NET  
- **支援的輸出格式？** XPS（亦支援 PDF、PNG 等）  
- **一般實作時間？** 基本轉換約 10–15 分鐘  
- **需要授權嗎？** 正式環境需要臨時授權；亦提供免費試用。  
- **可以在記憶體中執行轉換嗎？** 可以，使用稍後示範的 `MemoryStream`。

## 如何在 .NET 中將 LaTeX 轉換為 XPS
以下提供簡潔的逐步說明，涵蓋從前置條件到可選調整的所有內容，讓你能專注於應用程式的業務邏輯。

## 前置條件

在開始本教學之前，請確保已具備以下前置條件：

- 具備 C# 與 .NET 開發的基礎知識。  
- 已安裝 Aspose.TeX for .NET 函式庫。你可以在 **[此處](https://releases.aspose.com/tex/net/)** 下載。  
- 了解 LaTeX 語法與結構。

## 匯入命名空間

讓我們先為 .NET 應用程式匯入必要的命名空間。這些命名空間對於使用 Aspose.TeX 功能至關重要。

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
using System.Text;
```

## 步驟 1：設定轉換選項

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectLaTeX);
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

在此，我們會初始化轉換選項，並將引擎指向包含 `.ltx` 原始檔案的資料夾。

## 步驟 2：設定互動模式

```csharp
options.Interaction = Interaction.NonstopMode;
```

非停止模式會指示引擎即使遇到輕微警告也繼續處理，這對自動化流水線非常理想。

## 步驟 3：設定工作名稱（可選）

```csharp
// options.JobName = "my-job-name";
```

你可以指定自訂的工作名稱，以便在處理多個文件時辨識日誌。

## 步驟 4：在標題中設定日期（可選）

```csharp
// options.DateTime = new System.DateTime(2022, 12, 18);
```

強制在產生的標題頁顯示特定日期，對於可重現的報告很有用。

## 步驟 5：忽略缺少的套件

```csharp
options.IgnoreMissingPackages = true;
```

設定為 `true` 時，引擎會跳過缺少的 LaTeX 套件而非拋出錯誤，這可加速批次轉換。

## 步驟 6：停用連字

```csharp
options.NoLigatures = true;
```

停用連字可確保字元組合以原始輸入方式呈現，某些技術文件需要此設定。

## 步驟 7：重複工作（可選）

```csharp
// options.Repeat = true;
```

啟用此旗標會指示引擎再次執行相同工作——對於迭代除錯相當方便。

## 步驟 8：指定輸出工作目錄

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

定義產生的 XPS 檔案寫入的目錄位置。

## 步驟 9：初始化 XPS 儲存選項

```csharp
options.SaveOptions = new XpsSaveOptions(); // Default value. Arbitrary assignment.
```

建立 `XpsSaveOptions` 的實例，以微調 XPS 輸出。

## 步驟 10：光柵化公式（可選）

```csharp
options.SaveOptions.RasterizeFormulas = true;
```

設定為 `true` 時，數學公式會以光柵圖像呈現，這可提升與舊版 XPS 檢視器的相容性。

## 步驟 11：光柵化內嵌圖形（可選）

```csharp
options.SaveOptions.RasterizeIncludedGraphics = true;
```

將 LaTeX 原始檔中嵌入的向量圖形轉換為光柵圖像，以確保跨平台渲染一致。

## 步驟 12：子集字型

```csharp
options.SaveOptions.SubsetFonts = true;
```

子集化僅嵌入文件實際使用的字形，可減少檔案大小。

## 步驟 13：執行 LaTeX 轉 XPS 轉換

```csharp
new TeXJob(Path.Combine("Your Input Directory", "sample.ltx"), new XpsDevice(), options).Run();
```

此單行程式碼即啟動轉換程序，讀取 `sample.ltx` 並在輸出目錄產生 XPS 檔案。

## 步驟 14：使用 MemoryStream 執行 LaTeX 轉 XPS 轉換（備選方案）

```csharp
// new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(@"\documentclass{article} \begin{document} Hello, World! \end{document}")),
//     new XpsDevice(), options).Run();
```

如果你想直接從記憶體提供 LaTeX 原始碼（例如即時產生），請使用如範例所示的 `MemoryStream`。

## 步驟 15：使用主要輸入端點執行 LaTeX 轉 XPS 轉換（備選方案）

```csharp
// new TeXJob(new XpsDevice(), options).Run();
```

此重載允許你從預設輸入端點啟動轉換，適用於命令列情境。

## 常見問題與技巧

- **缺少套件：** 即使 `IgnoreMissingPackages` 設為 `true`，仍有部分套件是必需的。請確認你的 TeX 發行版中已安裝核心套件（例如 `amsmath`）。  
- **字型子集錯誤：** 若輸出 XPS 顯示亂碼，請嘗試停用 `SubsetFonts` 以嵌入完整字型。  
- **大型文件：** 對於非常龐大的 LaTeX 專案，可增加 JVM 堆積大小（若使用底層 TeX 引擎）或將文件分割成較小的區塊處理。

## 常見問答

**Q1：Aspose.TeX 是否相容於最新的 .NET 框架？**  
A：是的，Aspose.TeX 會定期更新，以支援 .NET 6、.NET 7 以及更新的版本。

**Q2：我可以自訂除 XPS 之外的輸出格式嗎？**  
A：Aspose.TeX 支援多種輸出格式。詳情請參閱完整 API 參考 **[此處](https://reference.aspose.com/tex/net/)**。

**Q3：如何取得 Aspose.TeX 的臨時授權？**  
A：你可以在 **[此處](https://purchase.aspose.com/temporary-license/)** 取得臨時授權。

**Q4：我可以在哪裡尋求協助或分享使用 Aspose.TeX 的經驗？**  
A：請加入社群論壇 **[此處](https://forum.aspose.com/c/tex/47)**，獲取技巧與支援。

**Q5：是否有可用於測試轉換的 LaTeX 範例文件？**  
A：有，請在 **[此處](https://github.com/aspose-tex/Aspose.TeX-for-.NET)** 探索 Aspose.TeX 範例。

## 結論

依照上述步驟操作後，你現在擁有一套完整、可投入生產環境的工作流程，能使用 Aspose.TeX for .NET **將 latex** 文件轉換為 XPS。此函式庫提供豐富的選項，讓你依需求客製化轉換，無論是產生發票、技術手冊或學術論文皆適用。

---

**最後更新：** 2025-12-23  
**測試環境：** Aspose.TeX 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}