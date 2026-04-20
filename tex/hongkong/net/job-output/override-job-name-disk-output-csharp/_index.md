---
date: 2025-12-21
description: 學習如何在 C# 中使用 Aspose.TeX 捕獲控制台輸出、覆寫作業名稱、設定 TeX 輸入目錄，並將終端機輸出寫入檔案。
linktitle: Capture Console Output C# – Override Job Name & Write Output to Disk
second_title: Aspose.TeX .NET API
title: 捕捉 C# 主控台輸出 – 覆寫工作名稱並將輸出寫入磁碟
url: /zh-hant/net/job-output/override-job-name-disk-output-csharp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 捕捉 Console 輸出 C# – 覆寫作業名稱並將終端輸出寫入磁碟 (C#)

## 介紹

在本分步指南中，您將學習 **如何捕捉 console output C#**，以在使用 Aspose.TeX for .NET 時，透過覆寫作業名稱並將終端輸出導向檔案，完整掌控 TeX 處理流程——非常適合自動化建置、CI/CD 情境，或任何需要將 console 串流記錄下來以供日後分析的情況。

## 快速回答
- **「capture console output C#」是什麼意思？** 它會將 Aspose.TeX 產生的標準終端串流重新導向至您指定的檔案。  
- **為什麼要覆寫作業名稱？** 覆寫可確保檔名可預測，避免在同時執行多個作業時發生衝突。  
- **哪個 Aspose.TeX 類別負責寫入輸出？** `OutputFileTerminal`（透過 `options.TerminalOut` 使用）。  
- **我可以自訂 TeX 輸入資料夾嗎？** 可以——使用 `options.InputWorkingDirectory` 來 **設定 TeX 輸入目錄**。  
- **此作法是否相容 .NET Core？** 完全相容；相同的 API 同時支援 .NET Framework 與 .NET Core。

## 在 Aspose.TeX 中，「capture console output C#」是什麼意思？
捕捉 console 輸出即是將原本會顯示在終端視窗的所有內容（記錄訊息、警告、編譯細節）寫入永久檔案。這在除錯大型 TeX 專案或將 TeX 處理整合至自動化工作流程時特別有用。

## 為什麼要覆寫作業名稱並將終端輸出寫入檔案？
- **可預測的檔名：** 覆寫作業名稱讓您自行決定產生檔案的基礎名稱，方便撰寫後續處理腳本。  
- **可稽核性：** 儲存終端日誌可完整追蹤 TeX 編譯過程。  
- **平行執行：** 同時執行多個作業時，唯一的作業名稱可防止檔案衝突。  

## 前置條件

在開始之前，請確保您具備以下項目：

- Aspose.TeX for .NET 套件：確保已安裝 Aspose.TeX for .NET 套件。您可從 [Aspose.TeX 官方網站](https://releases.aspose.com/tex/net/) 下載。  
- .NET 開發環境：具備可運作的 .NET 開發環境，包含 Visual Studio 等整合開發環境 (IDE)。  
- 基本的 C# 知識：熟悉 C# 程式語言的基礎。  
- 輸入與輸出目錄：為您的 TeX 檔案準備好輸入與輸出資料夾。

## 匯入命名空間

在 C# 程式碼中，請務必加入存取 Aspose.TeX 功能所需的命名空間：

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

## 步驟 1：建立轉換選項

首先，我們建立一個 `TeXOptions` 實例，告訴 Aspose.TeX 我們正於 console 應用程式情境下執行。

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

使用 `ConsoleAppOptions` 建立 `TeXOptions`，並將 `ObjectTeX` 設為 `TeXConfig`。

## 步驟 2：指定作業名稱（覆寫預設）

覆寫作業名稱可讓我們掌控所有產生工件的基礎名稱。

```csharp
options.JobName = "overridden-job-name";
```

設定作業名稱以覆寫預設名稱。

## 步驟 3：設定 TeX 輸入目錄

告訴 Aspose.TeX 您的 `.tex` 原始檔所在位置。這就是 **設定 TeX 輸入目錄** 的步驟。

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

為 TeX 檔案設定輸入工作目錄。

## 步驟 4：指定輸出工作目錄

定義處理後的檔案與捕捉的 console 日誌要儲存的路徑。

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

設定輸出工作目錄以保存處理後的 TeX 檔案。

## 步驟 5：將終端輸出寫入檔案

現在，我們將 console 串流導向輸出目錄中的實體檔案，實作 **將終端輸出寫入檔案** 的需求。

```csharp
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

將終端輸出配置為寫入輸出目錄中的檔案。

## 步驟 6：執行作業

最後，我們建立一個 `TeXJob`，使用覆寫的作業名稱、XPS 輸出裝置以及先前配置的選項。執行作業將產生 XPS 檔案並捕捉 console 日誌。

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

建立 `TeXJob`，指定作業名稱、輸出裝置 (`XpsDevice`) 與選項，最後執行作業。

## 常見問題與除錯

| 症狀 | 可能原因 | 解決方式 |
|------|----------|----------|
| 未產生輸出檔案 | 輸出目錄路徑不正確或缺乏寫入權限 | 確認 `options.OutputWorkingDirectory` 指向有效資料夾，且程序具備寫入權限。 |
| 終端日誌為空 | `TerminalOut` 未設定或在之後被覆寫 | 確保在 `job.Run();` 之前已執行 `options.TerminalOut = new OutputFileTerminal(...);`。 |
| 作業因「找不到檔案」失敗 | 輸入目錄未正確設定 | 再次檢查傳遞給 `InputFileSystemDirectory` 的路徑，並確認 `.tex` 檔案確實存在於該目錄。 |

## 常見問答

### Q1：我可以將 Aspose.TeX for .NET 與其他 .NET 套件一起使用嗎？

A1：可以，Aspose.TeX for .NET 能夠無縫整合其他 .NET 套件。

### Q2：Aspose.TeX for .NET 有提供免費試用嗎？

A2：有，您可以在 [此處](https://releases.aspose.com/) 下載免費試用版。

### Q3：如何取得 Aspose.TeX for .NET 的支援？

A3：請前往 [Aspose.TeX 論壇](https://forum.aspose.com/c/tex/47) 取得社群與官方支援。

### Q4：是否有臨時授權可供 Aspose.TeX for .NET 使用？

A4：有，您可在 [此處](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

### Q5：哪裡可以找到 Aspose.TeX for .NET 的文件說明？

A5：文件說明可在 [此處](https://reference.aspose.com/tex/net/) 取得。

## 結論

恭喜！您已成功學會如何透過覆寫作業名稱、設定 TeX 輸入目錄，並將終端輸出寫入檔案，以 **capture console output C#** 的方式使用 Aspose.TeX for .NET。此技巧可簡化記錄流程、提升可追溯性，並讓自動化 TeX 處理管線更加穩健。

---

**最後更新：** 2025-12-21  
**測試環境：** Aspose.TeX 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}