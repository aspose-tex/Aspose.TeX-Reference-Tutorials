---
date: 2025-12-03
description: 學習如何在 Java 中使用 Aspose.TeX 建立 TeX 格式，設定 TeX 輸入與輸出目錄，並建立自訂 TeX 格式以確保排版一致性。
language: zh-hant
linktitle: Create Custom TeX Formats for Consistent Typesetting in Java
second_title: Aspose.TeX Java API
title: 如何在 Java 中建立 TeX 格式以實現一致的排版
url: /java/custom-format/creating-custom-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中建立 TeX 格式以實現一致的排版

在多份文件之間保持排版一致性常常令人頭疼——尤其是當你需要一次又一次使用相同的版面規則時。**在本教學中，你將學會如何使用 Aspose.TeX for Java 建立 TeX 格式**，並且會看到如何**設定 TeX 輸入與輸出目錄**，讓引擎知道從哪裡讀取原始檔案、以及將產生的結果寫入哪裡。完成後，你就能產生自訂的 TeX 格式，確保所有基於 Java 的文件流程都有統一的樣式。

## 快速回答
- **「建立自訂 TeX 格式」是什麼意思？** 它告訴 Aspose.TeX 引擎編譯一組可重複使用的巨集、字型與版面規則。
- **需要授權嗎？** 開發階段可使用免費試用版；正式上線則需購買商業授權。
- **需要哪個 JDK 版本？** Java 8 或以上。
- **可以在執行時變更輸入資料夾嗎？** 可以——使用 `setInputWorkingDirectory`。
- **輸出資料夾可以設定嗎？** 當然可以——使用 `setOutputWorkingDirectory`。

## 什麼是自訂 TeX 格式？
自訂 TeX 格式是預先編譯好的 TeX 巨集、套件與設定的集合，執行時由引擎載入。與其在每份文件都重新解析相同的樣式檔，你只需一次編譯成格式檔（例如 `customtex.fmt`），之後重複使用，既大幅提升效能，又能保證渲染結果完全相同。

## 為什麼要設定 TeX 輸入與輸出目錄？
設定**TeX 輸入目錄**讓引擎知道從哪裡找 `.tex` 原始檔、字型與輔助資源。**TeX 輸出目錄**則決定編譯後的 PDF、日誌與輔助檔案寫入的位置。正確配置這兩條路徑可避免「找不到檔案」的錯誤，並保持專案目錄整潔。

## 前置作業
在開始撰寫程式碼之前，請先確保你已具備：

- **Aspose.TeX for Java** – 從 [Aspose.TeX 下載頁面](https://releases.aspose.com/tex/java/) 取得。
- **工作目錄** – 決定一個*輸入*資料夾（放置 `.tex` 檔案）與一個*輸出*資料夾（存放產生的 PDF）。在範例程式碼中，請將 `"Your Input Directory"` 與 `"Your Output Directory"` 替換為實際路徑。
- **Java Development Kit (JDK)** – 已安裝 8 版或更新，並在 IDE 或建置系統中正確設定。

## 匯入套件
首先匯入所需的類別。請保持此區塊與範例完全相同，因為它會載入 Aspose.TeX 核心 API 以及範例專案中使用的工具類別。

```java
package com.aspose.tex.CustomTeXFormatFileCreation;

import java.io.IOException;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;

import util.Utils;
```

## 建立自訂 TeX 格式的逐步指南

### 步驟 1：初始化 TeX 選項（建立「無格式」引擎）
我們先建立 `TeXOptions` 物件，告訴引擎目前尚未載入任何既有格式。這是**建立自訂 TeX 格式**的基礎。

```java
// Create TeX engine options for no format upon ObjectTeX engine extension.
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectIniTeX());
```

### 步驟 2：設定 TeX 輸入目錄
告訴 Aspose.TeX 在哪裡找原始檔案、樣式套件與其他輔助資源。將 `"Your Input Directory"` 替換為專案輸入資料夾的絕對或相對路徑。

```java
// Specify a file system working directory for the input.
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
```

> **小技巧：** 開發階段建議使用絕對路徑，以免 IDE 的工作目錄造成路徑混淆。

### 步驟 3：設定 TeX 輸出目錄
接著定義編譯後的 PDF 與日誌檔案寫入的位置。這就是**設定 TeX 輸出目錄**的步驟。

```java
// Specify a file system working directory for the output.
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### 步驟 4：執行格式建立指令
選項設定完成後，我們呼叫 Aspose.TeX 來編譯格式。第一個參數是新格式的名稱（`"customtex"`），第二個參數則是剛剛準備好的選項。

```java
// Run format creation.
TeXJob.createFormat("customtex", options);
```

此呼叫結束後，你會在輸出目錄中看到名為 `customtex.fmt`（或類似的二進位檔）的檔案。未來執行時只要載入此檔，即可加速處理。

### 步驟 5：清理終端機輸出（可選）
最後的程式碼會在主控台加入換行，讓任務完成後的終端機顯示更整潔。

```java
// For further output to look fine.
options.getTerminalOut().getWriter().newLine();
// ExEnd:CreateCustomTeXFormatFile
```

## 常見問題與解決方案
| 問題 | 原因 | 解決方式 |
|------|------|----------|
| **找不到 .tex 原始檔** | 輸入目錄路徑錯誤 | 確認傳入 `setInputWorkingDirectory` 的路徑與實際存放 `.tex` 檔案的資料夾相符。 |
| **輸出資料夾權限被拒** | 缺乏寫入權限 | 確保 Java 程式對 `setOutputWorkingDirectory` 指定的資料夾具有寫入權限。 |
| **格式建立卡住** | 載入的套件過多 | 只預先編譯必要的套件，避免載入整個 TeX 發行版。 |

## 常見問答

**Q: 可以在多個 Java 應用程式間共用同一個自訂格式嗎？**  
A: 可以。產生的 `.fmt` 檔案與平台無關，任何 Aspose.TeX 引擎實例都能載入。

**Q: 新增巨集後需要重新產生格式嗎？**  
A: 必須在修改巨集定義或套件清單後，重新執行 `TeXJob.createFormat`。

**Q: 能否在執行時程式化設定輸入與輸出目錄？**  
A: 完全可以——只要在呼叫 `TeXJob.createFormat` 或 `TeXJob.process` 前，分別呼叫 `options.setInputWorkingDirectory(...)` 與 `options.setOutputWorkingDirectory(...)` 即可。

**Q: 與預設的 `plain` 格式有何不同？**  
A: 預設格式每次都會載入一組通用巨集，會增加額外開銷。自訂格式則是預先編譯，速度更快，且能保證你所定義的版面配置。

**Q: 這在非 Windows 系統上可行嗎？**  
A: 可以。Aspose.TeX for Java 為跨平台產品，只要使用正確的檔案分隔符即可。

## 結論
現在你已掌握使用 Aspose.TeX for Java **建立自訂 TeX 格式**的完整流程。透過**設定 TeX 輸入目錄**與**設定 TeX 輸出目錄**，你可以完全掌控原始檔案的讀取位置與結果的寫入位置，從而在所有 Java 專案中實現可靠且可重複的排版。

---

**最後更新：** 2025-12-03  
**測試環境：** Aspose.TeX for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

## 常見問題

### Q1: 哪裡可以找到 Aspose.TeX for Java 的文件？

A1: 請參考 [Aspose.TeX for Java 文件](https://reference.aspose.com/tex/java/) 取得完整資訊。

### Q2: 如何下載 Aspose.TeX for Java？

A2: 可從 [Aspose.TeX for Java 下載頁面](https://releases.aspose.com/tex/java/) 取得程式庫。

### Q3: 哪裡可以購買 Aspose.TeX for Java？

A3: 請前往 [購買頁面](https://purchase.aspose.com/buy) 進行購買。

### Q4: 是否提供 Aspose.TeX for Java 的免費試用？

A4: 有，請點此取得免費試用版 [here](https://releases.aspose.com/)。

### Q5: 如何取得 Aspose.TeX for Java 的技術支援？

A5: 可在 [Aspose.TeX 論壇](https://forum.aspose.com/c/tex/47) 尋求協助。