---
title: 覆蓋作業名稱並將終端輸出寫入 Zip (C#)
linktitle: 覆蓋作業名稱並將終端輸出寫入 Zip (C#)
second_title: Aspose.TeX .NET API
description: 了解如何使用 Aspose.TeX for .NET 覆寫作業名稱並將終端輸出寫入 ZIP 檔案。包含 C# 範例的逐步指南。
weight: 11
url: /zh-hant/net/job-output/override-job-name-zip-output-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 覆蓋作業名稱並將終端輸出寫入 Zip (C#)

## 介紹

在本教學中，我們將探討如何使用 Aspose.TeX for .NET 覆寫作業名稱並將終端輸出寫入 ZIP 檔案。 Aspose.TeX 是一個功能強大的程式庫，允許開發人員在其 .NET 應用程式中使用 TeX 文件。在這個特定的範例中，我們將專注於一項常見任務 - 將終端輸出寫入 ZIP 文件，並能夠覆蓋作業名稱。

## 先決條件

在我們開始之前，請確保您具備以下先決條件：

- C# 的應用知識
- 已安裝 Aspose.TeX for .NET
- 輸入工作目錄的 ZIP 檔案
- 用於終端輸出的輸出 ZIP 檔案

## 導入命名空間

在深入研究程式碼之前，請確保在 C# 專案中包含必要的命名空間：

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Pdf;
using System.IO;
```

現在，讓我們將該範例分解為多個步驟來引導您完成整個過程。

## 第 1 步：開啟輸入和輸出 ZIP 串流

```csharp
using (Stream inZipStream = File.Open(Path.Combine("Your Input Directory", "zip-in.zip"), FileMode.Open))
using (Stream outZipStream = File.Open(Path.Combine("Your Output Directory", "terminal-out-to-zip.zip"), FileMode.Create))
{
    //步驟 1 的程式碼位於此處
}
```

## 第 2 步：設定轉換選項

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
options.JobName = "terminal-output-to-zip";
options.InputWorkingDirectory = new InputZipDirectory(inZipStream, "in");
options.OutputWorkingDirectory = new OutputZipDirectory(outZipStream);
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## 第 3 步：定義儲存選項

```csharp
options.SaveOptions = new PdfSaveOptions();
```

## 第 4 步：執行 TeX 作業

```csharp
new TeXJob("hello-world", new PdfDevice(), options).Run();
```

## 第 5 步：最終確定輸出 ZIP 存檔

```csharp
((OutputZipDirectory)options.OutputWorkingDirectory).Finish();
```

## 結論

恭喜！您已成功學習如何使用 Aspose.TeX for .NET 覆寫作業名稱並將終端輸出寫入 ZIP 檔案。在處理 C# 應用程式中的 TeX 文件時，此技術非常有用。

## 常見問題解答

### Q1：我可以將 Aspose.TeX for .NET 與其他 .NET 語言（如 VB.NET）一起使用嗎？

A1：是的，Aspose.TeX for .NET 與所有 .NET 語言相容。

### 問題 2：在哪裡可以找到更多有關 Aspose.TeX for .NET 的文件？

 A2：訪問[文件](https://reference.aspose.com/tex/net/)獲取詳細資訊。

### Q3：如何取得 Aspose.TeX 的臨時授權？

 A3：獲得[臨時執照](https://purchase.aspose.com/temporary-license/)用於測試目的。

### Q4：有 Aspose.TeX 支持的社群論壇嗎？

 A4：是的，加入[Aspose.TeX 論壇](https://forum.aspose.com/c/tex/47)以獲得社區支持。

### Q5：哪裡可以購買 Aspose.TeX for .NET？

A5：可以購買Aspose.TeX[這裡](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
