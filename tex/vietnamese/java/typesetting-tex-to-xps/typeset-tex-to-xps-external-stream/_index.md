---
title: Sắp chữ TeX sang XPS trong Java bằng luồng ngoài
linktitle: Sắp chữ TeX sang XPS trong Java bằng luồng ngoài
second_title: API Java Aspose.TeX
description: Tìm hiểu cách sắp chữ TeX thành XPS trong Java bằng Aspose.TeX. Khám phá hướng dẫn từng bước để xử lý tài liệu liền mạch.
weight: 10
url: /vi/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Sắp chữ TeX sang XPS trong Java bằng luồng ngoài

## Giới thiệu

Trong thế giới phát triển Java, Aspose.TeX nổi bật như một công cụ mạnh mẽ để sắp chữ các tài liệu TeX thành nhiều định dạng khác nhau, bao gồm cả XPS. Nếu bạn đang tìm cách nâng cao khả năng xử lý tài liệu của ứng dụng Java thì hướng dẫn này được thiết kế riêng cho bạn. Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn quy trình sắp chữ TeX sang XPS bằng Aspose.TeX cho Java bằng luồng bên ngoài.

## Điều kiện tiên quyết

Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

-  Bộ công cụ phát triển Java (JDK): Đảm bảo rằng bạn đã cài đặt Java trên hệ thống của mình. Bạn có thể tải nó xuống từ[đây](https://www.oracle.com/java/technologies/javase-downloads.html).

-  Aspose.TeX cho Java: Tải xuống và cài đặt Aspose.TeX cho Java. Bạn có thể tìm thấy liên kết tải xuống[đây](https://releases.aspose.com/tex/java/).

## Gói nhập khẩu

Bắt đầu bằng cách nhập các gói cần thiết để bắt đầu hành trình chuyển đổi TeX sang XPS của bạn. Bao gồm đoạn mã sau vào dự án Java của bạn:

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

## Bước 1: Định cấu hình tùy chọn chuyển đổi

Bắt đầu bằng cách tạo các tùy chọn chuyển đổi cho định dạng ObjectTeX mặc định bằng mã sau:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

Điều này thiết lập nền tảng cho quá trình sắp chữ.

## Bước 2: Chỉ định tên công việc và thư mục

Xác định tên công việc và đặt thư mục làm việc đầu vào và đầu ra:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Đảm bảo bạn thay thế các phần giữ chỗ như "Thư mục đầu vào của bạn" bằng đường dẫn thư mục thực tế của bạn.

## Bước 3: Cấu hình đầu ra đầu cuối

Chỉ định rằng đầu ra của thiết bị đầu cuối phải được ghi vào một tệp trong thư mục làm việc đầu ra:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

Bước này đảm bảo nhật ký chi tiết được ghi lại để gỡ lỗi.

## Bước 4: Mở luồng đầu ra

Mở một luồng để viết tài liệu XPS sắp chữ:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

Thay thế "Thư mục đầu ra của bạn" bằng đường dẫn thích hợp.

## Bước 5: Chạy công việc

Thực hiện công việc chuyển đổi TeX sang XPS:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

Việc này hoàn tất quá trình và bạn sẽ tìm thấy tài liệu XPS sắp chữ của mình trong thư mục đầu ra được chỉ định.

## Phần kết luận

Chúc mừng! Bạn đã sắp chữ thành công TeX sang XPS trong Java bằng Aspose.TeX. Điều này mở ra vô số khả năng xử lý tài liệu trong các ứng dụng Java của bạn. Thử nghiệm với các tệp TeX khác nhau và khám phá các tính năng đa dạng do Aspose.TeX cung cấp.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể sử dụng Aspose.TeX cho Java với các định dạng tài liệu khác không?

Câu trả lời 1: Aspose.TeX chủ yếu tập trung vào xử lý tài liệu liên quan đến TeX. Đối với các định dạng khác, hãy khám phá phạm vi sản phẩm phong phú của Aspose.

### Q2: Có phiên bản dùng thử không?

 Câu trả lời 2: Có, bạn có thể trải nghiệm Aspose.TeX bằng cách tải xuống bản dùng thử miễn phí[đây](https://releases.aspose.com/).

### Câu hỏi 3: Tôi có thể tìm tài liệu đầy đủ ở đâu?

 A3: Tham khảo tài liệu[đây](https://reference.aspose.com/tex/java/) để biết thông tin chi tiết và ví dụ.

### Câu hỏi 4: Làm cách nào để nhận được hỗ trợ hoặc tìm kiếm hỗ trợ?

 Câu trả lời 4: Truy cập diễn đàn Aspose.TeX[đây](https://forum.aspose.com/c/tex/47)để được cộng đồng hỗ trợ và thảo luận.

### Câu hỏi 5: Tôi có thể xin giấy phép tạm thời cho mục đích thử nghiệm không?

 Câu trả lời 5: Có, bạn có thể lấy giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
