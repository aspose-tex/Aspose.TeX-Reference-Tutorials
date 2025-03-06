---
title: 覆蓋作業名稱並用 Java 編寫終端輸出
linktitle: 覆蓋作業名稱並用 Java 編寫終端輸出
second_title: Aspose.TeX Java API
description: 探索有關使用 Aspose.TeX for Java 覆寫作業名稱和編寫終端輸出的逐步指南。透過強大的自訂選項增強您的文件處理。
weight: 10
url: /zh-hant/java/customizing-output/override-job-name-disk/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 覆蓋作業名稱並用 Java 編寫終端輸出

## 介紹

Aspose.TeX for Java 提供了處理 TeX 檔案的強大功能，可讓開發人員操作和自訂 TeX 文件處理。在本教學中，我們將引導您完成使用 Java 中的 Aspose.TeX 覆寫作業名稱並將終端輸出寫入檔案系統的過程。

## 先決條件

在我們深入學習本教程之前，請確保您具備以下先決條件：

- Java 程式設計的實用知識。
-  Aspose.TeX for Java 已安裝。您可以從[Aspose.TeX Java 文檔](https://reference.aspose.com/tex/java/).

## 導入包

首先，將必要的套件匯入到您的 Java 專案中。在您的 Java 檔案中，包含以下匯入：

```java
package com.aspose.tex.OverridenJobNameAndTerminalOutputWrittenToDisk;

import java.io.IOException;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

## 覆蓋作業名稱並寫入終端輸出

### 第 1 步：建立轉換選項

首先為 ObjectTeX 引擎擴充功能上的預設 ObjectTeX 格式建立轉換選項。使用以下程式碼片段：

```java
//ExStart：OverrideJobName-WriteTerminalOutputToFileSystem
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

### 第 2 步：指定作業名稱和工作目錄

指定作業名稱、輸入工作目錄和輸出工作目錄。如果未指定作業名稱，TeXJob 建構函式的第一個參數將被視為作業名稱。使用以下程式碼片段：

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### 步驟 3：將終端輸出寫入檔案系統

指定終端輸出必須寫入輸出工作目錄中的檔案。檔案名稱將是`<job_name>.trm`。新增以下程式碼：

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### 第 4 步：運行作業

使用指定的選項和作業名稱執行 TeX 作業。您可以這樣做：

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
// ExEnd：OverrideJobName-WriteTerminalOutputToFileSystem
```

恭喜！您已使用 Java 中的 Aspose.TeX 成功覆寫作業名稱並將終端輸出寫入檔案系統。

## 結論

在本教學中，我們探討如何利用 Aspose.TeX for Java 覆寫作業名稱並擷取終端輸出。這些功能使開發人員能夠對 TeX 文件處理進行細粒度控制，從而增強客製化和靈活性。

## 常見問題解答

### Q1：我可以將 Aspose.TeX for Java 與其他 Java 函式庫一起使用嗎？

A1：是的，Aspose.TeX for Java 旨在與其他 Java 程式庫無縫集成，以增強您的文件處理能力。

### Q2：哪裡可以找到 Aspose.TeX for Java 的支援？

 A2：訪問[Aspose.TeX 論壇](https://forum.aspose.com/c/tex/47)對於您可能遇到的任何問題，尋求社區支持和協助。

### Q3：Aspose.TeX for Java 有免費試用版嗎？

 A3：是的，您可以存取 Aspose.TeX for Java 的免費試用版[這裡](https://releases.aspose.com/).

### Q4：如何取得 Aspose.TeX for Java 的臨時授權？

 A4：按照這個[關聯](https://purchase.aspose.com/temporary-license/)獲得用於測試和評估目的的臨時許可證。

### Q5: 哪裡可以購買 Aspose.TeX for Java？

 A5：訪問[購買頁面](https://purchase.aspose.com/buy)取得 Aspose.TeX for Java 的授權。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
