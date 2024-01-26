---
title: .NET 中的 LaTeX 到 XPS - 使用 Aspose.TeX 輕鬆轉換
linktitle: .NET 中的 LaTeX 到 XPS - 使用 Aspose.TeX 輕鬆轉換
second_title: Aspose.TeX .NET API
description: 使用 Aspose.TeX 輕鬆將 .NET 中的 LaTeX 轉換為 XPS。高品質、可客製化、高效。
type: docs
weight: 13
url: /zh-hant/net/latex-conversion/to-xps/
---
## 介紹

您是否正在尋找一種在 .NET 應用程式中將 LaTeX 文件無縫轉換為 XPS 格式的方法？ Aspose.TeX for .NET 為這項任務提供了強大的解決方案，使轉換過程簡單且有效率。本逐步指南將引導您完成使用 Aspose.TeX 將 LaTeX 轉換為 XPS 的過程，確保您獲得準確且高品質的結果。

## 先決條件

在深入學習本教程之前，請確保您具備以下先決條件：

- 具備 C# 和 .NET 開發的實用知識。
- 安裝了 Aspose.TeX for .NET 函式庫。你可以下載它[這裡](https://releases.aspose.com/tex/net/).
- 了解 LaTeX 語法和結構。

## 導入命名空間

首先，我們為 .NET 應用程式導入必要的命名空間。這些命名空間對於與 Aspose.TeX 功能互動至關重要。

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
using System.Text;
```

## 第 1 步：設定轉換選項

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectLaTeX);
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

在這裡，我們初始化轉換選項並設定 LaTeX 檔案的輸入工作目錄。

## 第二步：設定互動模式

```csharp
options.Interaction = Interaction.NonstopMode;
```

指定交互模式，這裡我們將其設定為不間斷模式，以實現不間斷的轉換。

## 步驟 3：設定作業名稱（可選）

```csharp
// options.JobName = "我的工作名稱";
```

如果需要，您可以設定自訂作業名稱。

## 第 4 步：在標題中設定日期（可選）

```csharp
// options.DateTime = new System.DateTime(2022, 12, 18);
```

強制 TeX 引擎在標題中輸出特定日期。

## 第 5 步：忽略遺失的包裹

```csharp
options.IgnoreMissingPackages = true;
```

如果您希望引擎跳過遺失的套件而不出現錯誤，請設定為 true。

## 第 6 步：停用連字

```csharp
options.NoLigatures = true;
```

設定為 true 以防止引擎建立連字。

## 第 7 步：重複作業（可選）

```csharp
//選項.重複= true;
```

如果需要，請讓引擎重複該作業。

## 步驟 8：指定輸出工作目錄

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

設定轉換後的 XPS 檔案的輸出工作目錄。

## 步驟 9：初始化 XPS 的儲存選項

```csharp
options.SaveOptions = new XpsSaveOptions(); //預設值.任意分配。
```

初始化以 XPS 格式儲存的選項。

## 第 10 步：柵格化公式（可選）

```csharp
options.SaveOptions.RasterizeFormulas = true;
```

如果您希望將數學公式轉換為光柵圖像，請設定為 true。

## 第 11 步：光柵化包含的圖形（可選）

```csharp
options.SaveOptions.RasterizeIncludedGraphics = true;
```

如果您希望將包含向量元素的圖形轉換為光柵圖像，請設定為 true。

## 第 12 步：字體子集

```csharp
options.SaveOptions.SubsetFonts = true;
```

設定為 true 以使文件中使用裝置子集字型。

## 第 13 步：運行 LaTeX 到 XPS 的轉換

```csharp
new TeXJob(Path.Combine("Your Input Directory", "sample.ltx"), new XpsDevice(), options).Run();
```

啟動 LaTeX 到 XPS 的轉換過程。

## 步驟 14：使用 MemoryStream 執行 LaTeX 到 XPS 轉換（替代）

```csharp
// new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(@"\documentclass{article} \begin{document} 你好，世界！\end{document}")),
//新的 XpsDevice(), 選項).Run();
```

您也可以使用 MemoryStream 對輸入 LaTeX 內容執行轉換。

## 步驟 15：使用主輸入終端機執行 LaTeX 到 XPS 轉換（替代）

```csharp
// new TeXJob(new XpsDevice(), options).Run();
```

直接從主輸入終端運行轉換。

## 結論

遵循這些簡單的步驟，您可以使用 Aspose.TeX for .NET 輕鬆地將 LaTeX 文件轉換為 XPS 格式。這個強大的庫提供了靈活性和自訂選項來滿足您的特定要求。

## 常見問題解答

### Q1：Aspose.TeX 與最新的.NET 框架相容嗎？

A1：是的，Aspose.TeX 會定期更新，以確保與最新的 .NET 框架相容。

### Q2：我可以自訂XPS以外的輸出格式嗎？

 A2：Aspose.TeX支援多種輸出格式。參考文檔[這裡](https://reference.aspose.com/tex/net/)了解詳情。

### Q3：如何取得 Aspose.TeX 的臨時授權？

 A3：您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).

### Q4：我可以在哪裡尋求協助或分享我使用 Aspose.TeX 的經驗？

 A4：造訪 Aspose.TeX 論壇[這裡](https://forum.aspose.com/c/tex/47)以獲得社區支持。

### Q5: 有樣本檔案可供測試嗎？

 A5：探索 Aspose.TeX 範例[這裡](https://github.com/aspose-tex/Aspose.TeX-for-.NET).