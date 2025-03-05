---
title: 覆蓋作業名稱並將終端輸出寫入磁碟 (C#)
linktitle: 覆蓋作業名稱並將終端輸出寫入磁碟 (C#)
second_title: Aspose.TeX .NET API
description: 探索如何使用 Aspose.TeX for .NET 覆寫作業名稱並擷取終端輸出。請遵循我們的無縫 TeX 檔案管理綜合指南。
type: docs
weight: 10
url: /zh-hant/net/job-output/override-job-name-disk-output-csharp/
---
## 介紹

歡迎閱讀本逐步指南，了解如何使用 Aspose.TeX for .NET 以 C# 程式語言覆寫作業名稱並將終端輸出寫入磁碟。 Aspose.TeX for .NET 是一個功能強大的函式庫，可讓您無縫地使用 TeX 文件，在本教學中，我們將專注於一項特定任務：覆蓋作業名稱和捕獲終端輸出。

## 先決條件

在我們深入學習本教程之前，請確保您具備以下先決條件：

-  Aspose.TeX for .NET 函式庫：確保您已安裝 Aspose.TeX for .NET 函式庫。您可以從[Aspose.TeX 網站](https://releases.aspose.com/tex/net/).

- .NET 開發環境：擁有一個可用的 .NET 開發環境，包括整合開發環境 (IDE)，例如 Visual Studio。

- 基本 C# 知識：熟悉 C# 程式語言的基礎。

- 輸入和輸出目錄：為 TeX 檔案準備輸入和輸出目錄。

## 導入命名空間

在您的 C# 程式碼中，請確保包含存取 Aspose.TeX 功能所需的命名空間：

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

## 第 1 步：建立轉換選項

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

使用 ConsoleAppOptions 建立 TeXOptions，並將 ObjectTeX 指定為 TeXConfig。

## 第 2 步：指定作業名稱

```csharp
options.JobName = "overridden-job-name";
```

指定作業名稱以覆蓋預設名稱。

## 步驟 3：指定輸入工作目錄

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

設定 TeX 檔案的輸入工作目錄。

## 步驟 4：指定輸出工作目錄

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

定義輸出工作目錄以儲存處理後的 TeX 檔案。

## 第 5 步：將終端輸出寫入磁碟

```csharp
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

配置要寫入輸出目錄中的檔案的終端輸出。

## 第 6 步：運行作業

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

建立 TeXJob，指定作業名稱、輸出裝置 (XpsDevice) 和選項。最後，運行作業。

## 結論

恭喜！您已成功學習如何在 C# 中使用 Aspose.TeX for .NET 覆寫作業名稱並將終端輸出寫入磁碟。此功能對於有效管理 TeX 處理任務非常有價值。

## 常見問題解答

### Q1：我可以將 Aspose.TeX for .NET 與其他 .NET 函式庫一起使用嗎？

A1：是的，Aspose.TeX for .NET 可以與其他 .NET 函式庫無縫整合。

### 問題 2：Aspose.TeX for .NET 是否有免費試用版？

 A2：是的，您可以下載免費試用版[這裡](https://releases.aspose.com/).

### 問題 3：如何獲得 Aspose.TeX for .NET 支援？

A3：訪問[Aspose.TeX 論壇](https://forum.aspose.com/c/tex/47)獲得社區和支持。

### 問題 4：Aspose.TeX for .NET 是否有臨時授權？

 A4：是的，您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).

### Q5：在哪裡可以找到 Aspose.TeX for .NET 的文件？

 A5：文件可用[這裡](https://reference.aspose.com/tex/net/).