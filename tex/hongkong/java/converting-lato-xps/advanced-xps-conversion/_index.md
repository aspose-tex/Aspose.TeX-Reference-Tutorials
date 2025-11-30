---
date: 2025-11-30
description: 學習如何使用 Aspose.TeX 在 Java 中將 LaTeX 轉換為 XPS。本指南涵蓋 Java 文件處理、先決條件以及逐步程式碼。
language: zh-hant
linktitle: How to Convert LaTeX to XPS in Java with Aspose.TeX
second_title: Aspose.TeX Java API
title: 如何在 Java 中使用 Aspose.TeX 將 LaTeX 轉換為 XPS
url: /java/converting-lato-xps/advanced-xps-conversion/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中使用 Aspose.TeX 將 LaTeX 轉換為 XPS

## 介紹

如果您需要在 Java 應用程式中 **將 LaTeX** 文件轉換為高品質的 XPS 檔案，您來對地方了。使用 **Aspose.TeX**，您可以將此轉換自動化，作為 **java document processing** 工作流程的一部分，省去手動步驟並確保輸出一致。本文將一步步說明從前置條件到完整可執行的程式碼範例。

## 快速回答
- **需要哪個函式庫？** Aspose.TeX for Java。  
- **涉及哪些格式？** 輸入 = LaTeX (`.ltx`)，輸出 = XPS。  
- **測試需要授權嗎？** 開發階段可使用免費試用版，正式上線需購買商業授權。  
- **程式碼行數多少？** 核心轉換邏輯不到 30 行。  
- **能在任何作業系統上執行嗎？** 可以 — Java 本身跨平台。

## 先決條件

在開始之前，請確保您已具備以下項目：

1. **Aspose.TeX for Java** – 從 [Aspose.TeX releases page](https://releases.aspose.com/tex/java/) 下載最新 JAR。  
2. **Java Development Kit (JDK 8 或更新版本)** – 設定您慣用的 IDE（IntelliJ、Eclipse、VS Code 等）。  
3. **LaTeX 原始檔** – 例如 `hello-world.ltx`，即將轉換為 XPS。  

上述項目為順利執行 **java document processing** 打下堅實基礎。

## 匯入套件

在 Java 類別的最上方加入必要的匯入，這樣才能使用 Aspose.TeX 的轉換引擎與檔案系統輔助工具。

```java
package com.aspose.tex.LaTeXXpsConversionAlternative;

import java.io.FileOutputStream;
import java.io.IOException;
import java.io.OutputStream;

import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;
import com.aspose.tex.rendering.XpsSaveOptions;
```

## 步驟 1：建立 XPS 串流

首先建立一個輸出串流，用來寫入 XPS 文件。將 `"Your Output Directory"` 替換為您想儲存結果的資料夾路徑。

```java
// ExStart:Conversion-LaTeXToXps-Alternative
// Create the stream to write the XPS file to.
final OutputStream xpsStream = new FileOutputStream("Your Output Directory" + "any-name.xps");
```

## 步驟 2：設定轉換選項

設定轉換選項，讓 Aspose.TeX 知道您使用的是 Object‑LaTeX 原始檔，並指定暫存檔案的存放位置。

```java
// Create conversion options for Object LaTeX format upon Object TeX engine extension.
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectLaTeX());
// Specify a file system working directory for the output.
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
// Initialize the options for saving in XPS format.
options.setSaveOptions(new XpsSaveOptions()); // Default value. Arbitrary assignment.
```

## 步驟 3：執行 LaTeX 轉 XPS

呼叫轉換引擎。`TeXJob` 會將輸入檔、XPS 裝置（寫入串流）以及剛才設定的選項結合起來。

```java
// Run LaTeX to XPS conversion.
new TeXJob("Your Input Directory" + "hello-world.ltx", new XpsDevice(xpsStream), options).run();
```

## 步驟 4：關閉 XPS 串流

務必關閉串流以釋放系統資源，並確保 XPS 檔案正確完成。

```java
finally {
    if (xpsStream != null)
        xpsStream.close();
}
// ExEnd:Conversion-LaTeXToXps-Alternative
```

恭喜！您已學會 **如何在 Java 環境中使用 Aspose.TeX 將 LaTeX 轉換為 XPS**。這段精簡程式碼可整合至更大的 **java document processing** 流程中——無論是產生報表、發票或其他可列印的輸出。

## 為何選擇 Aspose.TeX 進行此轉換？

- **不需外部 LaTeX 安裝** – Aspose.TeX 內部完成所有渲染。  
- **跨平台** – 可在 Windows、Linux、macOS 上執行，因為它是純 Java。  
- **細緻控制** – 透過選項可指定工作目錄、輸出格式等。  
- **高保真度** – XPS 輸出保留原始 LaTeX 的向量圖形與排版細節。

## 常見問題與技巧

| 症狀 | 可能原因 | 解決方式 |
|------|----------|----------|
| `FileNotFoundException` 發生在輸出時 | 輸出目錄路徑錯誤 | 使用絕對路徑或確保資料夾已存在 |
| XPS 檔案為空白 | 輸入的 `.ltx` 檔案為空或格式錯誤 | 確認 LaTeX 原始碼在 LaTeX 編輯器中能正確編譯 |
| 大檔案產生記憶體不足錯誤 | JVM 堆積空間不足 | 增加 `-Xmx` JVM 參數（例如 `-Xmx2g`） |

## 常見問答

### Q1: 可以免費使用 Aspose.TeX for Java 嗎？
A1: 可以，從 [here](https://releases.aspose.com/) 取得免費試用版。

### Q2: 哪裡可以找到 Aspose.TeX 的詳細文件？
A2: 請前往文件說明頁面 [here](https://reference.aspose.com/tex/java/)。

### Q3: 如何取得 Aspose.TeX 的技術支援？
A3: 請造訪 [Aspose.TeX Forum](https://forum.aspose.com/c/tex/47) 取得支援。

### Q4: 有臨時授權可以使用嗎？
A4: 有，您可以在此取得臨時授權 [here](https://purchase.aspose.com/temporary-license/)。

### Q5: 哪裡可以購買 Aspose.TeX for Java？
A5: 請前往購買頁面 [here](https://purchase.aspose.com/buy)。

---

**最後更新：** 2025-11-30  
**測試環境：** Aspose.TeX 24.11 for Java  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}