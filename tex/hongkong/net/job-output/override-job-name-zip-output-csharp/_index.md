---
date: 2025-12-21
description: 學習如何使用 Aspose.TeX for .NET 將 TeX 轉換為 PDF、覆寫作業名稱，並將終端輸出寫入 ZIP 檔案。使用 C#
  從 TeX 產生 PDF。
linktitle: Convert TeX to PDF and Override Job Name – Write Output to ZIP (C#)
second_title: Aspose.TeX .NET API
title: 將 TeX 轉換為 PDF 並覆寫作業名稱 – 輸出寫入 ZIP (C#)
url: /zh-hant/net/job-output/override-job-name-zip-output-csharp/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 將 TeX 轉換為 PDF 並覆寫工作名稱 – 輸出寫入 ZIP（C#）

## 介紹

在本教學中，您將學習 **如何將 TeX 轉換為 PDF**，同時覆寫工作名稱並將終端機輸出捕獲至 ZIP 壓縮檔。Aspose.TeX for .NET 讓從 TeX 產生 PDF 變得簡單，並提供完整的工作設定與輸出處理控制。無論是自動化報表產生或建構基於 TeX 的出版流程，以下步驟都能協助您從純 TeX 原始檔產出可直接使用的 PDF，並存放於 ZIP 容器中。

## 快速答覆
- **本教學涵蓋什麼內容？** 使用 C# 將 TeX 轉換為 PDF、覆寫 TeX 工作名稱，以及將終端機輸出寫入 ZIP 檔案。
- **需要哪個程式庫？** Aspose.TeX for .NET（「使用 Aspose 建立 PDF」解決方案）。
- **需要授權嗎？** 測試可使用臨時授權；正式環境需購買正式授權。
- **主要前置條件是什麼？** .NET 開發環境、已安裝 Aspose.TeX，以及輸入/輸出 ZIP 檔案。
- **實作大約需要多久？** 環境設定完成後，約 10–15 分鐘即可完成。

## 什麼是「convert tex to pdf」？
將 TeX 轉換為 PDF 意指將 TeX 原始文件交由 TeX 引擎處理，產生 PDF 格式的渲染結果。Aspose.TeX 提供受管理的 .NET API，無需外部 TeX 發行版即可完成此轉換。

## 為什麼要覆寫工作名稱？
覆寫工作名稱可讓您自行決定輔助檔案（例如 *.log、*.aux）的基礎名稱，以及任何您重新導向的輸出串流。這在同一工作目錄下執行多個工作或需要可預測的檔名規則以供後續處理時特別有用。

## 前置條件

- 熟悉 C# 與 .NET 開發。
- 已安裝 Aspose.TeX for .NET（透過 NuGet 或手動套件）。
- 包含 TeX 原始檔的輸入 ZIP 壓縮檔。
- 用於接收終端機輸出的空白 ZIP 壓縮檔。

## 匯入命名空間

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Pdf;
using System.IO;
```

## 如何將 TeX 轉換為 PDF 並覆寫工作名稱

以下為逐步說明，帶您開啟 ZIP 串流、設定轉換選項、執行 TeX 工作，最後完成輸出 ZIP。

### 步驟 1：開啟輸入與輸出 ZIP 串流

```csharp
using (Stream inZipStream = File.Open(Path.Combine("Your Input Directory", "zip-in.zip"), FileMode.Open))
using (Stream outZipStream = File.Open(Path.Combine("Your Output Directory", "terminal-out-to-zip.zip"), FileMode.Create))
{
    // Code for step 1 goes here
}
```

*說明*：`using` 陳述式確保兩個串流都能正確釋放。輸入 ZIP（`zip-in.zip`）內含 TeX 原始檔，輸出 ZIP（`terminal-out-to-zip.zip`）則用來存放轉換過程產生的終端機日誌。

### 步驟 2：設定轉換選項（包含 **覆寫工作名稱**）

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
options.JobName = "terminal-output-to-zip";
options.InputWorkingDirectory = new InputZipDirectory(inZipStream, "in");
options.OutputWorkingDirectory = new OutputZipDirectory(outZipStream);
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

*說明*：  
- `JobName` 設為 `"terminal-output-to-zip"` – 這會覆寫預設的工作名稱。  
- `InputWorkingDirectory` 與 `OutputWorkingDirectory` 指向 ZIP 串流，使 Aspose.TeX 能直接從壓縮檔讀寫。  
- `TerminalOut` 將 TeX 引擎的主控台輸出重新導向至輸出 ZIP 內的檔案。

### 步驟 3：定義儲存選項（從 TeX 產生 PDF）

```csharp
options.SaveOptions = new PdfSaveOptions();
```

*說明*：`PdfSaveOptions` 告訴 Aspose.TeX 最終產出 PDF 檔案。

### 步驟 4：執行 TeX 工作

```csharp
new TeXJob("hello-world", new PdfDevice(), options).Run();
```

*說明*：`TeXJob` 建構子接收主 TeX 檔案名稱（`hello-world.tex`）、目標裝置（`PdfDevice`）以及先前設定的 `options`。呼叫 `.Run()` 即開始轉換程序。

### 步驟 5：完成輸出 ZIP 壓縮檔

```csharp
((OutputZipDirectory)options.OutputWorkingDirectory).Finish();
```

*說明*：此呼叫會將任何未寫入的資料刷新，並正確關閉輸出 ZIP，確保終端機日誌與產生的 PDF 均正確存放。

## 常見問題與除錯

| 症狀 | 可能原因 | 解決方式 |
|---------|--------------|-----|
| PDF 未產生 | `options.SaveOptions` 未設定 | 確認已執行步驟 3。 |
| 終端機日誌為空 | `options.TerminalOut` 未指派 | 確認步驟 2 包含 `TerminalOut` 行。 |
| 出現「找不到檔案」錯誤 | 輸入 ZIP 路徑不正確 | 再次檢查步驟 1 的檔案路徑。 |
| 輔助檔案未顯示工作名稱 | `options.JobName` 拼寫錯誤 | 確認屬性名稱正確為 `JobName`。 |

## 常見問答

### Q1：我可以在 VB.NET 等其他 .NET 語言中使用 Aspose.TeX for .NET 嗎？
**A：** 可以，Aspose.TeX for .NET 相容所有 .NET 語言，包括 VB.NET、F# 與 C#。

### Q2：在哪裡可以找到 Aspose.TeX for .NET 的更多文件？
**A：** 前往 [documentation](https://reference.aspose.com/tex/net/) 獲取詳細資訊。

### Q3：如何取得 Aspose.TeX 的臨時授權？
**A：** 取得 [temporary license](https://purchase.aspose.com/temporary-license/) 以供測試使用。

### Q4：有 Aspose.TeX 的社群論壇嗎？
**A：** 有，請加入 [Aspose.TeX forum](https://forum.aspose.com/c/tex/47) 交流支援。

### Q5：在哪裡可以購買 Aspose.TeX for .NET？
**A：** 您可於此處 [here](https://purchase.aspose.com/buy) 購買。

### Q6：此方法能在 .NET Core / .NET 5+ 上執行嗎？
**A：** 完全支援。Aspose.TeX 支援 .NET Framework、.NET Core 以及 .NET 5/6+，只要引用相應的 NuGet 套件即可。

### Q7：我可以自訂 PDF 輸出（例如加入中繼資料）嗎？
**A：** 可以。轉換完成後，您可使用 Aspose.PDF 或 `PdfSaveOptions` 的屬性加入中繼資料、設定壓縮等頁面設定。

## 結論

現在您已掌握一個完整、可投入生產環境的範例，**將 TeX 轉換為 PDF**、**覆寫工作名稱**，並 **將終端機輸出寫入 ZIP 壓縮檔**，全程使用 Aspose.TeX for .NET。您可以依需求自行調整路徑、工作名稱或輸出格式，以符合自己的工作流程。

---

**最後更新：** 2025-12-21  
**測試版本：** Aspose.TeX 24.12 for .NET  
**作者：** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
