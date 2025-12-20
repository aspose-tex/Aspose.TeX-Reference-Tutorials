---
date: 2025-12-20
description: 學習如何使用 Aspose.TeX for .NET 建立 TeX 工作的 XPS 輸出，管理檔案系統的輸入/輸出，並產生高品質的 XPS
  文件。
linktitle: Create TeX Job XPS Output with Filesystems – Aspose.TeX for .NET
second_title: Aspose.TeX .NET API
title: 使用檔案系統產生 TeX 作業的 XPS 輸出 – Aspose.TeX for .NET
url: /zh-hant/net/file-input-output/filesystem-input-xps-output/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用檔案系統建立 TeX 工作 XPS 輸出 – Aspose.TeX for .NET

## 介紹

歡迎！在本教學中，你將學習 **如何建立 TeX 工作 XPS 輸出**，同時使用 Aspose.TeX for .NET 處理檔案系統的輸入與輸出。無論你是要建立批次處理器、Web 服務或桌面工具，以下步驟都會指引你設定引擎、指向檔案，並產生與原始 LaTeX 來源完全相同的 XPS 文件。

我們會將流程拆解為清晰的編號步驟，說明每行程式碼背後的「原因」，並提供你可立即運用的實用技巧。

## 快速解答
- **「create tex job xps」是什麼意思？** 它指的是設定一個 Aspose.TeX 工作，讀取 TeX 檔案並將結果寫入 XPS 文件。  
- **我需要授權嗎？** 測試時可使用臨時授權；正式環境則需完整授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。  
- **我可以更改輸出格式嗎？** 可以——將 `XpsDevice` 替換為其他裝置（PDF、PNG 等）。  
- **需要在主控台輸出嗎？** 不需要——你可以使用記憶體終端以靜默執行。

## 「create tex job xps」是什麼？

建立輸出 XPS 的 TeX 工作，即是初始化 Aspose.TeX 引擎，告訴它從哪裡讀取來源檔案，並將渲染的頁面導入 XPS 套件。XPS（XML Paper Specification）是一種固定版面格式，能保留排版與向量圖形，非常適合列印或進一步轉換。

## 為何使用 Aspose.TeX 產生 XPS 輸出？

- **高保真度：** 引擎能在 XPS 中精確還原 LaTeX 版面。  
- **無外部相依性：** 純 .NET 函式庫，無需本機 LaTeX 安裝。  
- **彈性 I/O：** 支援檔案系統目錄、記憶體串流或自訂提供者。  
- **可擴充性：** 適用於單檔轉換或大量批次處理流程。

## 前置條件

- **Aspose.TeX for .NET** – 從 [Aspose 官方網站](https://releases.aspose.com/tex/net/) 下載最新版本。  
- **.NET 開發環境** – Visual Studio、Rider 或搭配 .NET SDK 的 VS Code。  
- **輸入與輸出資料夾** – 在你的機器上建立兩個目錄（例如 `C:\\TeX\\Input` 與 `C:\\TeX\\Output`）。  
- **授權（測試可選）** – 可從 Aspose 入口網站取得臨時授權。

## 匯入命名空間

首先，將所需的命名空間匯入作用域，以便存取檔案系統輔助工具與 XPS 裝置。

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

這些命名空間提供 `InputFileSystemDirectory`、`OutputFileSystemDirectory` 與 `XpsDevice`，是 **create tex job xps** 工作流程的關鍵。

## 步驟 1：建立轉換選項

我們先建立一個 `TeXOptions` 物件，告訴引擎使用 ObjectTeX 設定（大多數 LaTeX 來源的預設）。

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

> **專業提示：** `ConsoleAppOptions` 為主控台式應用程式設定合理的預設值，若有需要，你之後仍可自訂選項。

## 步驟 2：指定輸入與輸出目錄

將引擎指向先前準備好的資料夾。將佔位字串替換為你機器上的實際路徑。

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

現在 TeX 工作知道 `.tex` 檔案的所在位置以及生成 XPS 檔案的輸出位置。

## 步驟 3：選擇輸出終端

終端決定狀態訊息的寫入位置。為了快速除錯，我們暫時使用主控台，但你也可以切換至記憶體終端以靜默執行。

```csharp
options.TerminalOut = new OutputConsoleTerminal(); // Default value. Arbitrary assignment.
```

> **為何重要：** 使用主控台終端能即時取得編譯警告或錯誤的回饋，從而加快除錯速度。

## 步驟 4：執行 TeX 工作

建立 `TeXJob` 實例，為其命名，附加 `XpsDevice`，然後執行。

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

當 `Run()` 完成後，你會在輸出目錄中看到 `hello-world.xps` 檔案。

## 步驟 5：微調主控台輸出

在工作完成後加入空白行，可讓主控台日誌更易閱讀，特別是批次執行多個工作時。

```csharp
options.TerminalOut.Writer.WriteLine();
```

## 常見問題與解決方案

| Issue | Cause | Fix |
|-------|-------|-----|
| **XPS 檔案為空** | 輸出目錄路徑不正確或無寫入權限。 | 確認傳遞給 `OutputFileSystemDirectory` 的路徑，並確保程序具有寫入權限。 |
| **編譯錯誤** | LaTeX 原始碼使用了 ObjectTeX 未捆綁的套件。 | 切換至完整 TeX 引擎設定 (`TeXConfig.FullTeX()`) 或將缺少的套件檔案加入輸入目錄。 |
| **主控台卡住** | 終端因互動提示而等待輸入。 | 在自動化腳本中使用 `OutputMemoryTerminal` 以抑制互動提示。 |

## 常見問答

**Q1: 我可以使用除 XPS 之外的其他輸出格式嗎？**  
A1: 可以，Aspose.TeX 支援 PDF、PNG、SVG 等格式。將 `new XpsDevice()` 替換為相應的裝置類別（例如 `new PdfDevice()`）。

**Q2: 是否提供測試用的臨時授權？**  
A2: 可以，您可從 [此連結](https://purchase.aspose.com/temporary-license/) 取得測試用的臨時授權。

**Q3: 我可以在哪裡找到更多文件？**  
A3: 請參考 [Aspose.TeX for .NET 文件](https://reference.aspose.com/tex/net/) 以取得詳細資訊。

**Q4: 我該如何取得社群支援或提問？**  
A4: 前往 [Aspose.TeX 論壇](https://forum.aspose.com/c/tex/47) 獲得社群支援與討論。

**Q5: 有提供範例專案嗎？**  
A5: 可在 Aspose.TeX 的 GitHub 倉庫中探索範例專案與程式碼片段。

## 結論

遵循上述步驟後，你已掌握如何使用 Aspose.TeX for .NET **建立 TeX 工作 XPS 輸出**、管理輸入與輸出資料夾，並針對開發與正式環境微調流程。歡迎嘗試其他輸出裝置，將此邏輯整合至更大的工作流程，或自動化批次轉換。

---

**最後更新：** 2025-12-20  
**測試環境：** Aspose.TeX 24.11 for .NET (latest at time of writing)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}