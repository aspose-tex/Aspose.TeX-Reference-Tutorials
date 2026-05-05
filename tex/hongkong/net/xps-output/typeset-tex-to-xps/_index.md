---
date: 2025-12-30
description: 學習如何於 .NET 使用 Aspose.TeX 將 TeX 轉換成 XPS。跟隨此一步一步的指引，確保無縫整合及可靠輸出。
linktitle: How to Convert TeX to XPS in .NET
second_title: Aspose.TeX .NET API
title: 如何在 .NET 中將 TeX 轉換為 XPS
url: /zh-hant/net/xps-output/typeset-tex-to-xps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 .NET 中將 TeX 轉換為 XPS

## 如何將 TeX 轉換為 XPS – 介紹

歡迎閱讀我們完整且一步一步的教學，教您 **如何將 TeX** 文件在 .NET 環境中轉換為 XPS 格式。透過功能強大的 Aspose.TeX 函式庫，您可以將 TeX 轉 XPS 的功能整合至任何 .NET 應用程式——無論是桌面工具、Web 服務，或是自動化報表管線。接下來的章節，我們將逐項說明所有必要設定，提供完整程式碼範例，並解釋每個步驟的意義，讓您能自信地完成實作。

## 快速解答
- **本教學涵蓋什麼內容？** 使用 Aspose.TeX for .NET 將 TeX 檔案轉換為 XPS。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **需要授權嗎？** 免費試用可用於測試；正式環境需購買商業授權。  
- **實作需要多長時間？** 基本轉換通常在 15 分鐘內完成。  
- **在哪裡取得此函式庫？** 可從官方 Aspose.TeX 發行頁面下載。

## 前置條件

在深入教學之前，請先確保具備以下前置條件：

- Aspose.TeX for .NET：確定已安裝 Aspose.TeX 函式庫。您可以在[此處](https://releases.aspose.com/tex/net/)下載。  
- 文件說明：請參考[此處](https://reference.aspose.com/tex/net/)的文件說明，以熟悉函式庫的使用方式。  
- 輸入與輸出目錄：依範例程式碼設定好您的輸入與輸出目錄。  

現在所有環境皆已就緒，讓我們繼續一步一步的教學。

## 匯入命名空間

在您的 .NET 應用程式中，首先匯入必要的命名空間。這樣即可取得 Aspose.TeX 所需的排版功能。

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
```

## 步驟 1：設定轉換選項

定義轉換選項，指定 ObjectTeX 引擎的 ObjectTeX 格式。亦請設定工作名稱、輸入與輸出目錄，以及終端輸出細節。

```csharp
// Create conversion options for default ObjectTeX format upon ObjectTeX engine extension.
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
// Specify a job name.
options.JobName = "external-file-stream";
// Specify a file system working directory for input.
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
// Specify a file system working directory for output.
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
// Specify that the terminal output must be written to a file in the output working directory.
// The file name is <job_name>.trm.
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## 步驟 2：建立 XPS 文件串流

開啟串流以寫入排版後的 XPS 文件。檔名不一定與工作名稱相同。

```csharp
using (Stream stream = File.Open(Path.Combine("Your Output Directory", options.JobName + ".xps"), FileMode.Create))
```

## 步驟 3：執行 TeX 工作

啟動並執行 TeX 工作，指定文件名稱、XpsDevice 與轉換選項。

```csharp
new TeXJob("hello-world", new XpsDevice(stream), options).Run();
```

恭喜！您已成功使用 Aspose.TeX 在 .NET 中將 TeX 排版為 XPS。歡迎依照實際需求探索更多功能與選項。

## 結論

在本教學中，我們說明了如何在 .NET 環境下使用 Aspose.TeX 無縫將 TeX 文件轉換為 XPS 格式。透過本指南，您已掌握函式庫的核心能力，並能將其應用於各種專案。

## 常見問題

### Q1：Aspose.TeX 是否相容於 .NET Core？
A1：是的，Aspose.TeX 完全相容於 .NET Core。

### Q2：我可以在商業專案中使用 Aspose.TeX 嗎？
A2：當然可以！Aspose.TeX 可用於商業與個人用途。

### Q3：在哪裡可以找到更多範例與資源？
A3：請探索 Aspose.TeX 文件說明[此處](https://reference.aspose.com/tex/net/)，可取得更多範例與詳細資源。

### Q4：如何取得 Aspose.TeX 的支援？
A4：請前往 Aspose.TeX 支援論壇[此處](https://forum.aspose.com/c/tex/47)取得社群協助。

### Q5：是否提供免費試用？
A5：是的，您可在[此處](https://releases.aspose.com/)取得免費試用。

## 常見問答

**Q：我可以自訂 XPS 輸出（例如頁面大小或邊距）嗎？**  
A：可以。您可以調整 XpsDevice 設定或修改 TeX 原始碼，以在轉換前控制頁面版面。

**Q：如果輸入的 TeX 檔案有錯誤會發生什麼情況？**  
A：轉換過程會將錯誤細節寫入終端輸出檔案（`*.trm`），請檢視此檔案以診斷並修正問題。

**Q：是否可以在一次執行中轉換多個 TeX 檔案？**  
A：您可以對 TeX 原始檔集合進行迴圈，為每個檔案建立獨立的 TeXJob，同時重複使用相同的 `TeXOptions` 實例。

**Q：Aspose.TeX 是否支援如 `amsmath` 或 `graphicx` 等 LaTeX 套件？**  
A：大多數標準 LaTeX 套件皆受支援。請參閱官方文件以取得完整相容套件清單。

**Q：如何在產生的 XPS 檔案中嵌入字型？**  
A：Aspose.TeX 會自動嵌入 TeX 引擎使用的字型。請確保執行轉換的機器已安裝所需字型。

---

**最後更新：** 2025-12-30  
**測試環境：** Aspose.TeX for .NET 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}