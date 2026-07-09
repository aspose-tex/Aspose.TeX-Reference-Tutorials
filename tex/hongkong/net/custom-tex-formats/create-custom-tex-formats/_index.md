---
date: 2026-03-26
description: 了解如何在 .NET 中使用 Aspose.TeX 建立自訂 tex 格式，並設定 tex 輸入目錄以實現彈性文件產生。本步驟指南將示範如何配置格式提供者、設定
  tex 輸入目錄，以及產生 XPS 輸出。
linktitle: Creating Custom TeX Formats in .NET
second_title: Aspose.TeX .NET API
title: 如何在 .NET 中使用 Aspose.TeX 建立自訂 tex 格式
url: /zh-hant/net/custom-tex-formats/create-custom-tex-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 .NET 使用 Aspose.TeX 建立自訂 tex 格式

在 .NET 開發的動態世界中，**建立自訂 tex 格式** 檔案讓您能精細控制文件的排版。使用 Aspose.TeX for .NET，您可以自訂 TeX 引擎、指定特定的輸入資料夾，並僅透過幾行 C# 程式碼產生專業的 XPS 輸出。

## 快速解答
- **「建立自訂 tex 格式」是什麼意思？** 意指定義您自己的 TeX 引擎設定與格式檔，以控制排版流程。  
- **需要哪個函式庫？** Aspose.TeX for .NET。  
- **必須設定 tex 輸入目錄嗎？** 必須 – 您需要使用 `InputFileSystemDirectory` 來指定。  
- **可以產生什麼輸出？** 任何 Aspose.TeX 支援的裝置，例如 XPS、PDF 或 PNG。  
- **商業使用需要授權嗎？** 商業使用必須擁有有效的 Aspose.TeX 授權。

## 什麼是自訂 TeX 格式？

自訂 TeX 格式是一組預先編譯好的巨集與引擎設定，TeX 處理器會使用它來解讀您的來源檔案。建立自訂格式後，您可以嵌入公司品牌、強制執行文件標準，或加速重複性任務的編譯。

## 為何要設定 tex 輸入目錄？

設定 **tex 輸入目錄** 可告訴引擎在哪裡尋找輔助檔案、自訂字型或其他樣式檔。這有助於保持專案結構清晰，並防止編譯時出現「找不到檔案」的錯誤。

## 前置條件

在開始客製化之旅前，請確保您已具備：

1. **Aspose.TeX for .NET** – 從 [Aspose.TeX 官方網站](https://releases.aspose.com/tex/net/) 下載。  
2. 一個 **.NET 開發環境**（Visual Studio、VS Code 或 .NET CLI）。  
3. (可選) 若要在正式環境執行程式，需具備有效的 **Aspose.TeX 授權**。

## 匯入命名空間

首先，匯入能讓您存取 Aspose.TeX API 的命名空間。此步驟可確保編譯器識別我們即將使用的類別。

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using Aspose.TeX.ResourceProviders;
using System.IO;
using System.Text;
```

## 步驟 1：建立 Format Provider

`FormatProvider` 會指向包含您自訂格式檔 (`customtex.fmt`) 的資料夾。將 `"Your Output Directory"` 替換為您儲存已編譯格式的路徑。

```csharp
using (FormatProvider formatProvider =
    new FormatProvider(new InputFileSystemDirectory("Your Output Directory"), "customtex"))
{
```

## 步驟 2：設定轉換選項（並設定 tex 輸入目錄）

此處我們建立 `TeXOptions` 物件。留意 `InputWorkingDirectory` – 這就是 **設定 tex 輸入目錄** 的地方，讓引擎能找到任何支援檔案。

```csharp
    TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX(formatProvider));
    options.JobName = "typeset-with-custom-format";
    options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
    options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

## 步驟 3：執行工作

現在將簡單的 TeX 字串送入引擎，選擇輸出裝置（本例為 XPS），並執行工作。

```csharp
    new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
        "Congratulations! You have successfully typeset this text with your own TeX format!\\end")),
        new XpsDevice(), options).Run();
```

## 步驟 4：美化終端機輸出

加入空白行可讓 console 輸出更易閱讀，特別是當您在批次中執行多個工作時。

```csharp
    options.TerminalOut.Writer.WriteLine();
}
// ExEnd:TypesetWithCustomTeXFormat
```

恭喜！您已成功 **建立自訂 tex 格式**，並在 .NET 中使用它排版文件。

## 常見問題與解決方案

| 問題 | 原因 | 解決方式 |
|------|------|----------|
| *“找不到格式檔案”* | `FormatProvider` 中的路徑錯誤 | 確認「Your Output Directory」內含有 `customtex.fmt`，且路徑為絕對路徑或相對於可執行檔正確。 |
| *“找不到輸入檔案”* | `InputWorkingDirectory` 指向錯誤的資料夾 | 確保「Your Input Directory」內有 TeX 原始檔，或如範例所示以串流方式傳遞來源。 |
| *「終端機輸出亂碼」* | 編碼不匹配 | 若 TeX 原始檔包含非 ASCII 字元，請使用 `Encoding.UTF8`。 |
| *「XPS 檔案為空」* | 工作因先前的例外而未執行 | 檢查主控台的錯誤訊息；通常會指出缺少套件或 TeX 字串的語法錯誤。 |

## 常見問答

### Q1：我可以將 Aspose.TeX for .NET 與其他文件處理函式庫一起使用嗎？
A1：可以，Aspose.TeX 設計可與其他 Aspose 文件處理函式庫無縫整合，以實現完整的文件處理。

### Q2：是否提供 Aspose.TeX for .NET 的免費試用？
A2：是的，您可以在 [此處](https://releases.aspose.com/) 取得免費試用。

### Q3：我該如何取得 Aspose.TeX for .NET 的支援？
A3：請前往 [Aspose.TeX 論壇](https://forum.aspose.com/c/tex/47) 取得社群支援，或在 [此處](https://purchase.aspose.com/buy) 探索付費支援方案。

### Q4：是否提供 Aspose.TeX for .NET 的臨時授權？
A4：是的，您可以在 [此處](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

### Q5：我可以在哪裡找到 Aspose.TeX for .NET 的文件說明？
A5：請參考完整的文件說明 [此處](https://reference.aspose.com/tex/net/)。

**Additional Q&A**

**Q: 我可以輸出 PDF 而非 XPS 嗎？**  
**A:** 當然可以。將 `new XpsDevice()` 改為 `new PdfDevice()`，並相應調整輸出目錄。

**Q: 每次變更後都需要重新編譯格式檔嗎？**  
**A:** 是的。任何對巨集或引擎設定的變更都必須重新執行 `tex -ini` 以產生新的 `.fmt` 檔案。

## 結論

總而言之，Aspose.TeX for .NET 為 **建立自訂 tex 格式** 的情境提供了強大的解決方案，讓開發者對文件排版擁有前所未有的控制力。請嘗試不同的設定、正確設定 tex 輸入目錄，並將此工作流程整合至更大的 .NET 應用程式，以實現自動化、高品質的文件產出。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-03-26  
**測試環境：** Aspose.TeX 24.11 for .NET  
**作者：** Aspose