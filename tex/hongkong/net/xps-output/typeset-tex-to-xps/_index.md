---
title: 在 .NET 中將 TeX 排版為 XPS
linktitle: 在 .NET 中將 TeX 排版為 XPS
second_title: Aspose.TeX .NET API
description: 使用 Aspose.TeX 輕鬆將 TeX 文件轉換為 .NET 中的 XPS。探索我們的逐步指南，以獲得無縫整合體驗。
weight: 10
url: /zh-hant/net/xps-output/typeset-tex-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 .NET 中將 TeX 排版為 XPS

## 介紹

歡迎閱讀我們關於使用強大的 Aspose.TeX 函式庫在 .NET 中將 TeX 排版為 XPS 的逐步指南。如果您希望在 .NET 應用程式中將 TeX 文件無縫轉換為 XPS 格式，那麼您來對地方了。在本教程中，我們將引導您完成整個過程，分解每個步驟以確保順利實施。

## 先決條件

在我們深入學習本教程之前，請確保您具備以下先決條件：

-  Aspose.TeX for .NET：確保您已安裝 Aspose.TeX 函式庫。你可以下載它[這裡](https://releases.aspose.com/tex/net/).

- 文件：透過參考文件來熟悉該庫[這裡](https://reference.aspose.com/tex/net/).

- 輸入和輸出目錄：按照範例程式碼中的指定設定輸入和輸出目錄。

現在您已完成所有設置，讓我們繼續執行逐步指南。

## 導入命名空間

在您的 .NET 應用程式中，首先匯入必要的命名空間。這可確保您可以存取將 TeX 排版為 XPS 所需的 Aspose.TeX 功能。

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
```

## 第 1 步：設定轉換選項

定義轉換選項，在 ObjectTeX 引擎擴充上指定 ObjectTeX 格式。此外，還可以設定作業名稱、輸入和輸出目錄以及終端輸出詳細資訊。

```csharp
//根據 ObjectTeX 引擎擴充功能建立預設 ObjectTeX 格式的轉換選項。
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
//指定作業名稱。
options.JobName = "external-file-stream";
//指定用於輸入的檔案系統工作目錄。
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
//指定輸出的檔案系統工作目錄。
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
//指定終端輸出必須寫入輸出工作目錄中的檔案。
//檔案名稱為 <作業名稱>.trm。
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## 步驟 2：建立 XPS 文件流

開啟一個流來寫入排版的 XPS 文件。檔案名稱不一定與作業名稱相同。

```csharp
using (Stream stream = File.Open(Path.Combine("Your Output Directory", options.JobName + ".xps"), FileMode.Create))
```

## 第 3 步：執行 TeX 作業

啟動並執行 TeX 作業，指定文件名稱、XpsDevice 和轉換選項。

```csharp
new TeXJob("hello-world", new XpsDevice(stream), options).Run();
```

恭喜！您已使用 Aspose.TeX 在 .NET 中成功將 TeX 排版為 XPS。請根據您的具體要求隨意探索更多功能和選項。

## 結論

在本教學中，我們介紹了使用 Aspose.TeX 將 TeX 文件無縫轉換為 .NET 中的 XPS 格式的基本步驟。透過遵循本指南，您可以深入了解該程式庫的功能以及如何將它們用於您的專案。

## 常見問題解答

### Q1：Aspose.TeX 與.NET Core 相容嗎？

A1：是的，Aspose.TeX 與 .NET Core 完全相容。

### Q2：我可以將Aspose.TeX用於商業項目嗎？

A2：當然！ Aspose.TeX 可用於商業和個人用途。

### Q3：在哪裡可以找到更多範例和資源？

 A3：探索 Aspose.TeX 文檔[這裡](https://reference.aspose.com/tex/net/)了解更多範例和詳細資源。

### Q4：如何獲得 Aspose.TeX 的支持？

 A4：造訪 Aspose.TeX 支援論壇[這裡](https://forum.aspose.com/c/tex/47)獲得社區的協助。

### Q5: 有免費試用嗎？

 A5：是的，您可以免費試用[這裡](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
