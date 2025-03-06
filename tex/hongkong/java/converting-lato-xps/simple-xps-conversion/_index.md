---
title: 在 Java 中輕鬆將 LaTeX 轉換為 XPS 格式
linktitle: 在 Java 中輕鬆將 LaTeX 轉換為 XPS 格式
second_title: Aspose.TeX Java API
description: 使用 Aspose.TeX 在 Java 中輕鬆將 LaTeX 轉換為 XPS。請按照我們的逐步指南進行無縫整合。
weight: 10
url: /zh-hant/java/converting-lato-xps/simple-xps-conversion/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 中輕鬆將 LaTeX 轉換為 XPS 格式

## 介紹

您是否希望在 Java 應用程式中將 LaTeX 文件無縫轉換為 XPS 格式？ Aspose.TeX for Java 提供了強大的解決方案，讓您輕鬆實現這一目標。在本逐步指南中，我們將引導您完成使用 Aspose.TeX 將 LaTeX 轉換為 XPS 的過程。

## 先決條件

在深入轉換過程之前，請確保滿足以下先決條件：

- 您的系統上安裝了 Java 開發工具包 (JDK)。
- 下載 Aspose.TeX for Java 函式庫。你可以找到下載鏈接[這裡](https://releases.aspose.com/tex/java/).

## 導入包

首先，導入 Java 專案所需的套件。確保您的專案依賴項中包含 Aspose.TeX 庫。

```java
package com.aspose.tex.LaTeXXpsConversionSimplest;

import java.io.ByteArrayInputStream;
import java.io.IOException;
import java.util.Calendar;
import java.util.GregorianCalendar;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.Interaction;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;
import com.aspose.tex.rendering.XpsSaveOptions;

import util.Utils;
```

現在，讓我們使用提供的程式碼範例將轉換過程分解為多個步驟。

## 第1步：設定輸入和輸出目錄

```java
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

指定 LaTeX 輸入檔所在的目錄以及要儲存轉換後的 XPS 檔案的目錄。

## 第 2 步：配置 TeX 選項

配置各種選項以根據您的需求自訂轉換過程。

```java
options.setInteraction(Interaction.NonstopMode);
options.setDateTime(new GregorianCalendar(2022, Calendar.DECEMBER, 18).getTime());
options.ignoreMissingPackages(true);
options.noLigatures(true);
options.repeat(true);
```

根據需要調整互動模式、標題中的日期、遺失包的處理、連字和重複。

## 步驟 3：初始化 XPS 儲存選項

```java
options.setSaveOptions(new XpsSaveOptions());
```

初始化以 XPS 格式儲存的選項。

## 第 4 步：自訂 XPS 儲存選項

```java
options.getSaveOptions().rasterizeFormulas(true);
options.getSaveOptions().rasterizeIncludedGraphics(true);
options.getSaveOptions().subsetFonts(true);
```

自訂 XPS 儲存選項以控制公式、包含的圖形和字體子集的轉換。

## 第 5 步：運行 LaTeX 到 XPS 的轉換

```java
new TeXJob("Your Input Directory" + "sample.ltx", new XpsDevice(), options).run();
```

透過使用指定的輸入檔案、輸出裝置 (XpsDevice) 和選項執行 TeX 作業來啟動轉換過程。

## 其他範例

使用不同的輸入來源探索其他轉換方法：

### 使用輸入流

```java
new TeXJob(new ByteArrayInputStream(
    "\\documentclass{article} \\begin{document} Hello, World! \\end{document}".getBytes("ASCII")),
    new XpsDevice(), options).run();
```

### 使用主輸入端子

```java
new TeXJob(new XpsDevice(), options).run();
```

## 結論

借助 Aspose.TeX for Java，將 LaTeX 轉換為 XPS 變得輕而易舉。請按照以下步驟操作，自訂選項，並將此功能無縫整合到您的 Java 應用程式中。

## 常見問題解答

### Q1：我可以使用Aspose.TeX轉換具有複雜公式的LaTeX文件嗎？

A1：當然！ Aspose.TeX 在轉換過程中無縫處理複雜的公式。

### Q2：Aspose.TeX for Java 有試用版嗎？

 A2：是的，您可以找到免費試用版[這裡](https://releases.aspose.com/).

### Q3：如何獲得 Aspose.TeX 的支持？

A3：訪問[Aspose.TeX 論壇](https://forum.aspose.com/c/tex/47)尋求幫助和社區支持。

### Q4：Aspose.TeX 是否有臨時許可證？

 A4：是的，您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).

### Q5：哪裡可以找到Aspose.TeX的文件？

 A5：請參閱[文件](https://reference.aspose.com/tex/java/)進行全面指導。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
