---
title: Chuyển đổi định dạng LaTeX sang XPS trong Java một cách dễ dàng
linktitle: Chuyển đổi định dạng LaTeX sang XPS trong Java một cách dễ dàng
second_title: API Java Aspose.TeX
description: Chuyển đổi LaTeX sang XPS dễ dàng trong Java bằng Aspose.TeX. Hãy làm theo hướng dẫn từng bước của chúng tôi để tích hợp liền mạch.
type: docs
weight: 10
url: /vi/java/converting-lato-xps/simple-xps-conversion/
---
## Giới thiệu

Bạn đang muốn chuyển đổi liền mạch các tài liệu LaTeX sang định dạng XPS trong các ứng dụng Java của mình? Aspose.TeX cho Java cung cấp một giải pháp mạnh mẽ, cho phép bạn đạt được điều này một cách dễ dàng. Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn quy trình chuyển đổi LaTeX sang XPS bằng Aspose.TeX.

## Điều kiện tiên quyết

Trước khi đi sâu vào quá trình chuyển đổi, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

- Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn.
-  Đã tải xuống thư viện Aspose.TeX cho Java. Bạn có thể tìm thấy liên kết tải xuống[đây](https://releases.aspose.com/tex/java/).

## Gói nhập khẩu

Để bắt đầu, hãy nhập các gói cần thiết cho dự án Java của bạn. Đảm bảo rằng bạn đưa thư viện Aspose.TeX vào phần phụ thuộc của dự án.

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

Bây giờ, hãy chia quá trình chuyển đổi thành nhiều bước bằng cách sử dụng các mã ví dụ được cung cấp.

## Bước 1: Đặt thư mục đầu vào và đầu ra

```java
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Chỉ định các thư mục chứa tệp đầu vào LaTeX của bạn và nơi bạn muốn lưu tệp XPS đã chuyển đổi.

## Bước 2: Định cấu hình tùy chọn TeX

Định cấu hình các tùy chọn khác nhau để tùy chỉnh quá trình chuyển đổi theo nhu cầu của bạn.

```java
options.setInteraction(Interaction.NonstopMode);
options.setDateTime(new GregorianCalendar(2022, Calendar.DECEMBER, 18).getTime());
options.ignoreMissingPackages(true);
options.noLigatures(true);
options.repeat(true);
```

Điều chỉnh chế độ tương tác, ngày tháng trong tiêu đề, xử lý các gói bị thiếu, chữ ghép và lặp lại nếu cần.

## Bước 3: Khởi tạo tùy chọn lưu XPS

```java
options.setSaveOptions(new XpsSaveOptions());
```

Khởi tạo các tùy chọn để lưu ở định dạng XPS.

## Bước 4: Tùy chỉnh tùy chọn lưu XPS

```java
options.getSaveOptions().rasterizeFormulas(true);
options.getSaveOptions().rasterizeIncludedGraphics(true);
options.getSaveOptions().subsetFonts(true);
```

Tùy chỉnh các tùy chọn lưu XPS để kiểm soát việc chuyển đổi công thức, đồ họa đi kèm và cài đặt phông chữ.

## Bước 5: Chạy chuyển đổi LaTeX sang XPS

```java
new TeXJob("Your Input Directory" + "sample.ltx", new XpsDevice(), options).run();
```

Bắt đầu quá trình chuyển đổi bằng cách chạy tác vụ TeX với tệp đầu vào, thiết bị đầu ra (XpsDevice) và các tùy chọn được chỉ định.

## Ví dụ bổ sung

Khám phá các phương pháp chuyển đổi bổ sung bằng cách sử dụng các nguồn đầu vào khác nhau:

### Sử dụng luồng đầu vào

```java
new TeXJob(new ByteArrayInputStream(
    "\\documentclass{article} \\begin{document} Hello, World! \\end{document}".getBytes("ASCII")),
    new XpsDevice(), options).run();
```

### Sử dụng cổng đầu vào chính

```java
new TeXJob(new XpsDevice(), options).run();
```

## Phần kết luận

Với Aspose.TeX cho Java, việc chuyển đổi LaTeX sang XPS thật dễ dàng. Hãy làm theo các bước sau, tùy chỉnh các tùy chọn và tích hợp liền mạch chức năng này vào các ứng dụng Java của bạn.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể chuyển đổi tài liệu LaTeX có công thức phức tạp bằng Aspose.TeX không?

A1: Chắc chắn rồi! Aspose.TeX xử lý các công thức phức tạp một cách liền mạch trong quá trình chuyển đổi.

### Câu hỏi 2: Có phiên bản dùng thử cho Aspose.TeX cho Java không?

 A2: Có, bạn có thể tìm thấy phiên bản dùng thử miễn phí[đây](https://releases.aspose.com/).

### Câu hỏi 3: Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.TeX?

 A3: Tham quan[diễn đàn Aspose.TeX](https://forum.aspose.com/c/tex/47) để được hỗ trợ và hỗ trợ cộng đồng.

### Câu hỏi 4: Có giấy phép tạm thời cho Aspose.TeX không?

 A4: Có, bạn có thể lấy giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).

### Câu hỏi 5: Tôi có thể tìm tài liệu về Aspose.TeX ở đâu?

 A5: Hãy tham khảo[tài liệu](https://reference.aspose.com/tex/java/) để được hướng dẫn toàn diện.