---
date: 2026-03-24
description: 學習如何在 C# 中取得檔案串流，同時為 Aspose.TeX .NET 指定所需的輸入。請跟隨我們的逐步指南。
linktitle: Get File Stream C# in Aspose.TeX Required Input Directory
second_title: Aspose.TeX .NET API
title: 在 Aspose.TeX 中取得檔案串流（C#）所需的輸入目錄
url: /zh-hant/net/advanced-io/required-input-directory-csharp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.TeX 必要輸入目錄中取得檔案串流（C#）

## 簡介

如果您在使用 Aspose.TeX 時需要 **取得檔案串流 C#**，第一步就是告訴函式庫您的 TeX 原始檔案所在位置。本教學將逐步說明如何 **指定必要的輸入** 給 Aspose.TeX 引擎，將一個 `.tex` 檔案資料夾轉換成 API 可消耗的串流。完成本指南後，您將擁有一個可重複使用的 `RequiredInputDirectory` 類別，能乾淨地將檔案系統與 Aspose.TeX 串接起來。

## 快速回答
- **「get file stream C#」是什麼意思？** 它表示回傳一個 `System.IO.Stream` 物件，用於指定的檔案名稱。  
- **為什麼必須指定必要的輸入？** Aspose.TeX 會在輸入目錄中搜尋 TeX 檔案；若未指定，引擎無法解析 `\include{}` 或 `\input{}` 指令。  
- **哪些命名空間是必須的？** `Aspose.TeX.IO`、`System.Collections.Generic` 與 `System.IO`。  
- **需要特別的授權嗎？** 在正式環境使用時，需要 Aspose.TeX 的開發或試用授權。  
- **這個類別可以在不同專案間重複使用嗎？** 可以——編譯後即可在任何參考 Aspose.TeX 的 .NET 專案中使用。

## 什麼是 get file stream C#？

在 .NET 中，*檔案串流* 是繼承自 `System.IO.Stream` 的物件，提供對檔案原始位元組的讀寫存取。當 Aspose.TeX 要求取得檔案時，它期望您回傳此類串流，以便引擎直接從記憶體或磁碟讀取 TeX 原始碼。

## 為什麼要為 Aspose.TeX 指定必要的輸入？

Aspose.TeX 透過 **必要的輸入目錄** 來定位輔助檔案（圖片、樣式檔、被包含的 TeX 檔案）。明確定義此目錄可讓您：

1. 避免編譯期間出現「找不到檔案」的錯誤。  
2. 將專案的檔案存取邏輯與其他程式碼隔離。  
3. 透過模擬輸入目錄，讓單元測試更容易實作。

## 先決條件

- **Aspose.TeX for .NET Library** – 從[發佈頁面](https://releases.aspose.com/tex/net/)下載。  
- **.NET 開發環境** – Visual Studio 2022、Rider，或任何支援 .NET 6+ 的 IDE。

現在，讓我們匯入所需的命名空間。

## 匯入命名空間

在 C# 檔案的最上方加入以下 `using` 陳述式，讓編譯器能找到所需的型別：

```csharp
using Aspose.TeX.IO;
using System.Collections.Generic;
using System.IO;
```

## 如何在必要的輸入目錄中取得檔案串流 C#

以下提供 `RequiredInputDirectory` 類別的逐步說明。每一步都包含簡短說明與您應直接複製到專案中的程式碼區塊。

### 步驟 1：建立 `RequiredInputDirectory` 類別

此類別實作兩個介面——`IInputWorkingDirectory`（Aspose.TeX 用來定位檔案）與 `IFileCollector`（用來收集加入的檔名）。

```csharp
public class RequiredInputDirectory : IInputWorkingDirectory, IFileCollector
{
    private Dictionary<string, Dictionary<string, string>> _fileNames =
        new Dictionary<string, Dictionary<string, string>>();

    public RequiredInputDirectory()
    {
    }
```

### 步驟 2：實作 `StoreFileName` 方法

此方法會記錄您傳入的每個檔名，並依副檔名分組，以便快速查找。

```csharp
public void StoreFileName(string fileName)
{
    string extension = Path.GetExtension(fileName);
    string name = Path.GetFileNameWithoutExtension(fileName);

    Dictionary<string, string> files;
    if (!_fileNames.TryGetValue(extension, out files))
        _fileNames.Add(extension, files = new Dictionary<string, string>());

    files[name] = fileName;
}
```

### 步驟 3：實作 `IInputWorkingDirectory` 介面 – GetFile

當 Aspose.TeX 請求檔案時，此方法回傳 **檔案串流**（若您在其他地方處理串流則回傳 `null`）。`fullName` 輸出讓引擎知道實際解析出的完整路徑。

```csharp
public Stream GetFile(string fileName, out string fullName, bool searchSubdirectories = false)
{
    fullName = fileName;
    return null; // Here we actually return a stream for the file requested by its name.
}
```

### 步驟 4：依副檔名收集檔案集合

引擎可能會要求取得所有特定副檔名的檔案（例如「.tex」）。此方法會以字串陣列回傳這些檔名。

```csharp
public string[] GetFileNamesByExtension(string extension, string path = null)
{
    Dictionary<string, string> files;
    if (!_fileNames.TryGetValue(extension, out files))
        return new string[0];

    return new List<string>(files.Values).ToArray();
}
```

### 步驟 5：釋放資源

在長時間執行的服務中，釋放內部字典可防止記憶體洩漏。

```csharp
public void Dispose()
{
    _fileNames.Clear();
}
```

有了這五段程式碼，您現在即可擁有一個完整功能的 `RequiredInputDirectory` 類別，能以 **取得檔案串流 C#** 的方式 **指定必要的輸入** 給 Aspose.TeX 處理器。

## 常見問題與解決方案

| 問題 | 為何會發生 | 快速修正 |
|------|------------|----------|
| `GetFile` 回傳 `null` 且編譯失敗 | 此方法僅為佔位；若要讓引擎讀取檔案，必須開啟真實的 `FileStream`。 | 將 `return null;` 改為 `return File.OpenRead(fullName);`（確保路徑正確）。 |
| 雖然檔案存在卻找不到 | 收集器未收到正確的檔名或副檔名。 | 在將目錄傳遞給 Aspose.TeX 之前，先為每個檔案呼叫 `StoreFileName`。 |
| 大量大型 `.tex` 檔案導致記憶體使用激增 | 字典將所有檔名保留在記憶體中。 | 在處理完成後立即 `Dispose` `RequiredInputDirectory`，或改用串流方式。 |

## 常見問與答

**Q: 在哪裡可以找到 Aspose.TeX for .NET 的文件說明？**  
A: 文件說明可於[此處](https://reference.aspose.com/tex/net/)取得。

**Q: 我要如何下載 Aspose.TeX for .NET 套件？**  
A: 可從[發佈頁面](https://releases.aspose.com/tex/net/)下載。

**Q: 我可以從哪裡取得 Aspose.TeX for .NET 的支援？**  
A: 請前往[Aspose.TeX 論壇](https://forum.aspose.com/c/tex/47)尋求社群協助。

**Q: 有提供免費試用版嗎？**  
A: 有，您可以在[此處](https://releases.aspose.com/)探索免費試用版。

**Q: 我要如何取得 Aspose.TeX for .NET 的臨時授權？**  
A: 可於[此處](https://purchase.aspose.com/temporary-license/)取得臨時授權。

## 其他常見問與答

**Q: 這個類別能在 .NET Core 專案中使用嗎？**  
A: 當然可以——`IInputWorkingDirectory` 與 `IFileCollector` 為平台無關的介面。

**Q: 必須手動向 Aspose.TeX 註冊目錄嗎？**  
A: 必須，請將 `RequiredInputDirectory` 實例傳入 `TeXDocument` 建構子或相關 API 呼叫。

**Q: 支援哪些 .NET 版本？**  
A: Aspose.TeX 相容 .NET 5、.NET 6 以及更新版本，同時支援 .NET Framework 4.6.2 以上。

---

**最後更新：** 2026-03-24  
**測試環境：** Aspose.TeX 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}