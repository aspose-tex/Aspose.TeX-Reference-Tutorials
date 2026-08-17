---
date: 2026-03-26
description: 學習如何使用 Aspose.TeX for .NET 從 TeX 建立 XPS、管理檔案系統的輸入/輸出，並產生高品質的 XPS 文件。
linktitle: Create XPS from TeX with Filesystems – Aspose.TeX for .NET
second_title: Aspose.TeX .NET API
title: 使用檔案系統從 TeX 產生 XPS – Aspose.TeX for .NET
url: /zh-hant/net/file-input-output/filesystem-input-xps-output/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用檔案系統從 TeX 建立 XPS – Aspose.TeX for .NET

## 介紹

歡迎！在本教學中，您將學習 **如何從 TeX 建立 XPS**，同時使用 Aspose.TeX for .NET 處理檔案系統的輸入與輸出。無論您是要建構批次處理器、Web 服務，或是桌面工具，以下步驟都會指引您設定引擎、指向檔案，並產生與原始 LaTeX 來源完全相同的 XPS 文件。

我們會將整個流程拆解成清晰的編號步驟，說明每行程式碼背後的「為什麼」，並提供您立即可用的實用技巧。

## 快速回答
- **「從 TeX 建立 XPS」是什麼意思？** 這指的是設定 Aspose.TeX 工作，讀取 TeX 檔案並將結果寫入 XPS 文件。  
- **需要授權嗎？** 測試期間可使用臨時授權；正式上線則需正式授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。  
- **可以更換輸出格式嗎？** 可以 ─ 只要將 `XpsDevice` 換成其他裝置（PDF、PNG 等）。  
- **需要在主控台輸出訊息嗎？** 不需要 ─ 您可以使用記憶體終端機以靜默方式執行。

## 使用 Aspose.TeX 建立 XPS 的方法

建立一個輸出 XPS 的 TeX 工作，意味著要初始化 Aspose.TeX 引擎、告訴它從哪裡讀取來源檔案，並將渲染後的頁面寫入 XPS 包。XPS（XML Paper Specification）是一種固定版面格式，能保留排版與向量圖形，非常適合列印或進一步轉換。

## 什麼是「create tex job xps」？

建立一個輸出 XPS 的 TeX 工作，意味著要初始化 Aspose.TeX 引擎、告訴它從哪裡讀取來源檔案，並將渲染後的頁面寫入 XPS 包。XPS（XML Paper Specification）是一種固定版面格式，能保留排版與向量圖形，非常適合列印或進一步轉換。

## 為什麼使用 Aspose.TeX 產生 XPS？

- **高保真度：** 引擎能在 XPS 中精確還原 LaTeX 版面。  
- **無外部相依性：** 純 .NET 函式庫，無需本機 LaTeX 安裝。  
- **彈性 I/O：** 支援檔案系統目錄、記憶體串流或自訂提供者。  
- **可擴充性：** 適用於單一檔案轉換或大量批次處理管線。

## 前置條件

在開始之前，請確保您具備以下項目：

- **Aspose.TeX for .NET** – 從 [Aspose 官方網站](https://releases.aspose.com/tex/net/) 下載最新版本。  
- **.NET 開發環境** – Visual Studio、Rider，或安裝 .NET SDK 的 VS Code。  
- **輸入與輸出資料夾** – 在機器上建立兩個目錄（例如 `C:\TeX\Input` 與 `C:\TeX\Output`）。  
- **授權（測試用可選）** – 可從 Aspose 入口網站取得臨時授權。

## 匯入命名空間

首先，將所需的命名空間匯入作用域，以便存取檔案系統輔助工具與 XPS 裝置。

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

這些命名空間提供 `InputFileSystemDirectory`、`OutputFileSystemDirectory` 與 `XpsDevice`，是 **從 TeX 建立 XPS** 工作流程的關鍵。

## 步驟 1：建立轉換選項

我們先建立一個 `TeXOptions` 物件，告訴引擎使用 ObjectTeX 設定（大多數 LaTeX 來源的預設）。

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

> **專業提示：** `ConsoleAppOptions` 為主控台型應用程式設定了合理的預設值，之後若有需要仍可自行調整選項。

## 步驟 2：指定輸入與輸出目錄

將引擎指向先前建立的資料夾。請將佔位字串替換為您機器上的實際路徑。

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

現在 TeX 工作知道在哪裡尋找 `.tex` 檔案，以及要把產生的 XPS 檔案放到哪裡。

## 步驟 3：選擇輸出終端機

終端機負責寫入狀態訊息。為了快速除錯，我們先使用主控台；若需要靜默執行，可改用記憶體終端機。

```csharp
options.TerminalOut = new OutputConsoleTerminal(); // Default value. Arbitrary assignment.
```

> **為什麼重要：** 使用主控台終端機可以即時看到編譯警告或錯誤，讓除錯速度更快。

## 步驟 4：執行 TeX 工作

建立 `TeXJob` 實例，給予易讀的名稱，掛上 `XpsDevice`，然後執行。

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

當 `Run()` 完成後，您會在輸出目錄中看到 `hello-world.xps` 檔案。

## 步驟 5：微調主控台輸出

在工作結束後加入一行空白，可讓主控台日誌更易閱讀，特別是一次執行多個工作時。

```csharp
options.TerminalOut.Writer.WriteLine();
```

## 常見使用情境

| 情境 | 為何使用 XPS？ | 程式碼片段的作用 |
|----------|----------|-----------------------|
| **批次轉換學術論文** | 保留精確版面以供存檔列印。 | 基於檔案系統的方法讓您指向一個 `.tex` 檔案資料夾，並輸出相對應的 XPS 檔案集合。 |
| **即時渲染 LaTeX 的 Web 服務** | XPS 可直接串流至支援的瀏覽器。 | 將 `XpsDevice` 換成記憶體串流，即可在不寫入磁碟的情況下回傳文件。 |
| **桌面排版工具** | 在轉 PDF 前需要固定版面預覽。 | 同一個工作稍後可串接 PDF 裝置，以產生最終發佈檔案。 |

## 常見問題與解決方案

| 問題 | 原因 | 解決方法 |
|-------|-------|-----|
| **XPS 檔案為空** | 輸出目錄路徑錯誤或無寫入權限。 | 確認傳給 `OutputFileSystemDirectory` 的路徑正確，且程序具備寫入權限。 |
| **編譯錯誤** | LaTeX 原始碼使用了 ObjectTeX 未內建的套件。 | 改用完整 TeX 引擎設定 (`TeXConfig.FullTeX()`) 或將缺少的套件檔案放入輸入目錄。 |
| **主控台卡住** | 終端機因互動提示等待輸入。 | 使用 `OutputMemoryTerminal` 抑制互動提示，適合自動化腳本。 |

## 常見問答

**Q1：可以改用其他輸出格式嗎？**  
A1：可以，Aspose.TeX 支援 PDF、PNG、SVG 等格式。只要將 `new XpsDevice()` 換成相應的裝置類別（例如 `new PdfDevice()`）即可。

**Q2：是否提供測試用的臨時授權？**  
A2：有，您可從 [此連結](https://purchase.aspose.com/temporary-license/) 取得測試用臨時授權。

**Q3：在哪裡可以找到更多文件？**  
A3：請參考 [Aspose.TeX for .NET 文件](https://reference.aspose.com/tex/net/) 取得詳細資訊。

**Q4：如何取得社群支援或提問？**  
A4：前往 [Aspose.TeX 論壇](https://forum.aspose.com/c/tex/47) 與社群互動。

**Q5：有提供範例專案嗎？**  
A5：可在 Aspose.TeX 的 GitHub 倉庫中找到範例專案與程式碼片段。

## 結論

依照上述步驟，您現在已掌握如何使用 Aspose.TeX for .NET **從 TeX 建立 XPS**，並能管理輸入與輸出資料夾，針對開發與正式環境進行微調。歡迎嘗試其他輸出裝置、將此邏輯整合至更大型工作流程，或自動化批次轉換。

---

**最後更新：** 2026-03-26  
**測試環境：** Aspose.TeX 24.11 for .NET（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}