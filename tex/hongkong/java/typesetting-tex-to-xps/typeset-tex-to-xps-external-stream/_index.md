---
date: 2025-12-11
description: 學習如何在 Java 中使用 Aspose.TeX 將 TeX 轉換為 XPS。此一步一步的指南將向您展示如何高效產生 XPS 文件流。
linktitle: How to Convert TeX to XPS in Java with External Stream
second_title: Aspose.TeX Java API
title: 在 Java 中使用外部串流將 TeX 轉換為 XPS
url: /zh-hant/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中使用外部串流將 TeX 轉換為 XPS

## 介紹

如果您需要 **將 TeX** 檔案從 Java 應用程式轉換成高品質的 XPS 輸出，Aspose.TeX for Java 能讓這項工作變得簡單。在本教學中，您將會看到 **如何使用外部輸出串流** 將 TeX 轉換為 XPS 文件，這在您想直接將結果傳送至回應、雲端儲存服務或任何自訂目的地時非常理想。讓我們一步步走過整個流程，從環境設定到寫入最終的 XPS 檔案。

## 快速回答
- **本教學涵蓋什麼內容？** 使用 Aspose.TeX 透過外部串流將 TeX 轉換為 XPS。  
- **需要的主要函式庫是什麼？** Aspose.TeX for Java。  
- **是否需要授權？** 生產環境必須使用臨時或正式授權。  
- **可以產生 XPS 串流嗎？** 可以——範例直接將 XPS 寫入 `OutputStream`。  
- **支援哪個 Java 版本？** 任意 JDK 8 以上（教學以 JDK 11 為參考）。

## 前置條件

在深入程式碼之前，請確保您已具備以下項目：

- Java Development Kit (JDK)：確保系統已安裝 Java，可從 [此處](https://www.oracle.com/java/technologies/javase-downloads.html) 下載。  
- Aspose.TeX for Java：下載並安裝 Aspose.TeX for Java，可在 [此處](https://releases.aspose.com/tex/java/) 取得下載連結。

## 匯入套件

先匯入必要的套件，以展開 TeX 轉 XPS 的轉換旅程。將以下程式碼片段加入您的 Java 專案：

```java
package com.aspose.tex.TypesetXpsWrittenToExternalStream;

import java.io.FileOutputStream;
import java.io.IOException;
import java.io.OutputStream;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

## 步驟 1：設定轉換選項

使用以下程式碼建立預設 ObjectTeX 格式的轉換選項：

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

此步驟為排版過程奠定基礎。

## 步驟 2：指定工作名稱與目錄

定義工作名稱並設定輸入與輸出工作目錄：

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

請將「Your Input Directory」等佔位字串替換為實際的目錄路徑。

## 步驟 3：設定終端機輸出

指定將終端機輸出寫入輸出工作目錄中的檔案：

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

此步驟可確保詳細日誌被捕獲，方便除錯。

## 步驟 4：開啟輸出串流

開啟串流以寫入排版後的 XPS 文件：

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

將「Your Output Directory」替換為正確的路徑。

## 步驟 5：執行工作

執行 TeX 轉 XPS 的轉換工作：

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

完成後，您即可在指定的輸出目錄中找到產生的 XPS 文件。

## 常見問題與解決方案

| 問題 | 為何會發生 | 解決方式 |
|------|------------|----------|
| **FileNotFoundException** 在開啟串流時 | 輸出目錄路徑不正確或不存在。 | 核對路徑、事先建立目錄，或使用 `Files.createDirectories`。 |
| **NullPointerException** 於 `options.getOutputWorkingDirectory()` | 未呼叫 `setOutputWorkingDirectory` 或回傳 `null`。 | 確保在使用前先呼叫 `options.setOutputWorkingDirectory`。 |
| **LicenseException** 於執行時 | 未使用有效的 Aspose.TeX 授權。 | 以 `License license = new License(); license.setLicense("Aspose.TeX.lic");` 套用臨時或正式授權。 |

## 常見問答

**Q: 可以將 Aspose.TeX for Java 用於其他文件格式嗎？**  
A: Aspose.TeX 主要聚焦於 TeX 相關的文件處理。若需其他格式，請參考 Aspose 的完整產品系列。

**Q: 有提供試用版嗎？**  
A: 有，您可從 [此處](https://releases.aspose.com/) 下載免費試用版。

**Q: 哪裡可以找到完整的文件說明？**  
A: 請參閱文件說明 [此處](https://reference.aspose.com/tex/java/)，內含詳細資訊與範例。

**Q: 如何取得支援或協助？**  
A: 前往 Aspose.TeX 論壇 [此處](https://forum.aspose.com/c/tex/47) 取得社群支援與討論。

**Q: 可以取得測試用的臨時授權嗎？**  
A: 可以，請至 [此處](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

## 結論

恭喜！您已學會 **如何在 Java 中使用 Aspose.TeX 以及外部串流將 TeX 轉換為 XPS 文件**。此技巧讓您能完全掌控 XPS 輸出的去向——無論是檔案系統、Web 回應或雲端儲存。歡迎嘗試不同的 TeX 來源、調整 `TeXOptions` 以使用自訂字型，或將串流整合至更大的文件產生流程中。

---

**最後更新：** 2025-12-11  
**測試環境：** Aspose.TeX for Java 24.11（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}