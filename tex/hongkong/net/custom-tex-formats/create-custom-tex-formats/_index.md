---
date: 2025-12-18
description: 學習如何在 .NET 中使用 Aspose TeX 自訂格式，以自訂 TeX 進行排版，並產生高品質文件。
linktitle: Creating Custom TeX Formats in .NET
second_title: Aspose.TeX .NET API
title: Aspose TeX 自訂格式 – 在 .NET 中建立自訂 TeX 格式
url: /zh-hant/net/custom-tex-formats/create-custom-tex-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose TeX 自訂格式：在 .NET 中建立自訂 TeX 格式

## 介紹

在快速演變的 .NET 生態系統中，對文件排版擁有細緻的控制能顯著提升產生的 PDF、XPS 檔或其他輸出的外觀與感受。**Aspose TeX custom format** 讓您定義並使用自己的 TeX 格式檔，賦予您以*自訂 tex 排版*的完整能力，正好符合您的需求。本教學將逐步帶您完成所有步驟——從環境設定到使用個人化格式執行完整的 TeX 工作。

## 快速回答
- **「Aspose TeX custom format」能做什麼？** 它讓您建立並使用自訂的 TeX 格式檔，以實現客製化排版。  
- **試用需要授權嗎？** 提供免費試用；正式環境需購買商業授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7 以上。  
- **可以輸出到 XPS、PDF 或其他裝置嗎？** 可以——支援 Aspose.TeX 的任何裝置（例如 XpsDevice、PdfDevice）。  
- **設定需要多長時間？** 通常在安裝套件後 10 分鐘內即可完成。

## 什麼是 Aspose TeX Custom Format？

自訂 TeX 格式是一種已編譯的 TeX 引擎設定，內含預先載入的巨集、套件與參數。透過提供自己的格式檔，您可以加快編譯速度，並在 .NET 應用程式中強制執行專案特定的排版規則。

## 為什麼要使用自訂 TeX 格式？

- **效能：** 預先編譯的格式可減少大型文件的啟動時間。  
- **一致性：** 在公司層面強制排版標準，無需每次執行都重新撰寫巨集。  
- **彈性：** 新增專屬指令或調整預設值，以符合品牌需求。

## 前置條件

在開始撰寫程式碼前，請確保您已具備：

1. **Aspose.TeX for .NET Library** – 從 [Aspose.TeX 官方網站](https://releases.aspose.com/tex/net/) 下載並安裝。  
2. **.NET 開發環境** – Visual Studio 2022、搭配 C# 擴充功能的 VS Code，或任何支援 .NET 6+ 的 IDE。

## 匯入命名空間

為了啟動自訂流程，請在 .NET 專案中匯入必要的命名空間，以取得 Aspose.TeX 的功能。

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using Aspose.TeX.ResourceProviders;
using System.IO;
using System.Text;
```

## 步驟 1：建立 Format Provider

先建立一個指向自訂格式檔所在資料夾的 Format Provider。此 Provider 告訴引擎在哪裡尋找已編譯的 `.fmt` 檔案。

```csharp
using (FormatProvider formatProvider =
    new FormatProvider(new InputFileSystemDirectory("Your Output Directory"), "customtex"))
{
```

## 步驟 2：設定轉換選項

為自訂格式配置轉換選項。此處指定工作名稱、輸入與輸出工作目錄，並將自訂格式綁定至 ObjectTeX 引擎。

```csharp
    TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX(formatProvider));
    options.JobName = "typeset-with-custom-format";
    options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
    options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

## 步驟 3：執行工作

提供輸入文字、輸出裝置（本例為 XpsDevice）以及先前設定的選項，即可執行 TeX 工作。

```csharp
    new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
        "Congratulations! You have successfully typeset this text with your own TeX format!\\end")),
        new XpsDevice(), options).Run();
```

## 步驟 4：確保輸出整潔

為了讓終端機輸出更美觀，工作結束後加入一行空白。這個小技巧可讓 console 顯示更乾淨。

```csharp
    options.TerminalOut.Writer.WriteLine();
}
// ExEnd:TypesetWithCustomTeXFormat
```

### 常見問題與解決方案

| 症狀 | 可能原因 | 解決方式 |
|------|----------|----------|
| “format file not found” 錯誤 | `FormatProvider` 路徑錯誤 | 確認 `"Your Output Directory"` 內有 `customtex.fmt`，且路徑為絕對或相對於可執行檔正確。 |
| 沒有產生輸出 | 輸出目錄缺乏寫入權限 | 確保應用程式對 `"Your Output Directory"` 有寫入權限，或改用 `Path.GetTempPath()` 等可寫入的資料夾。 |
| 最終文件缺少巨集 | 自訂格式未包含所需套件 | 重新編譯 `.fmt` 檔，加入必要的 `\usepackage{...}`，再取代舊的格式檔。 |

## 結論

總結來說，**Aspose TeX custom format** 提供了一種高效、穩定的方式，讓您直接在 .NET 中客製化 TeX 排版。依循上述步驟，即可建立、設定並執行符合專案排版需求的自訂格式。您可以嘗試不同的巨集、輸出裝置與選項設定，充分發揮 .NET 應用程式中文檔產生的潛力。

## 常見問答

### Q1：我可以將 Aspose.TeX for .NET 與其他文件處理函式庫一起使用嗎？

A1：可以，Aspose.TeX 設計上能與其他 Aspose 文件處理函式庫無縫整合，提供完整的文件處理解決方案。

### Q2：Aspose.TeX for .NET 有免費試用嗎？

A2：有，您可在 [此處](https://releases.aspose.com/) 取得免費試用。

### Q3：如何取得 Aspose.TeX for .NET 的支援？

A3：請前往 [Aspose.TeX 論壇](https://forum.aspose.com/c/tex/47) 取得社群支援，或在 [此處](https://purchase.aspose.com/buy) 探索付費支援方案。

### Q4：Aspose.TeX for .NET 是否提供臨時授權？

A4：有，您可在 [此處](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

### Q5：在哪裡可以找到 Aspose.TeX for .NET 的文件說明？

A5：請參考完整文件說明 [此處](https://reference.aspose.com/tex/net/)。

## 其他常見問答

**Q：自訂格式也能輸出 PDF 嗎？**  
A：當然可以。只要將 `new XpsDevice()` 替換為 `new PdfDevice()`（或其他支援的裝置），其餘選項保持不變。

**Q：可以從嵌入資源載入自訂格式嗎？**  
A：可以。使用 `new FormatProvider(new InputEmbeddedResourceDirectory(typeof(Program).Assembly), "customtex")` 從資源載入。

**Q：如何偵錯失敗的 TeX 工作？**  
A：將 `options.TerminalOut.Writer` 設為 `StringWriter`，在 `Run()` 完成後檢查捕獲的日誌內容。

---

**最後更新：** 2025-12-18  
**測試環境：** Aspose.TeX 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}