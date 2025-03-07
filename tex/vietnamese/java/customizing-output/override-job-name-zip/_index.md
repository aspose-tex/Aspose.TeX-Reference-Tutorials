---
title: Ghi đè tên công việc và ghi đầu ra đầu cuối vào Zip trong Java
linktitle: Ghi đè tên công việc và ghi đầu ra đầu cuối vào Zip trong Java
second_title: API Java Aspose.TeX
description: Tìm hiểu cách ghi đè tên công việc và ghi đầu ra của thiết bị đầu cuối vào ZIP trong Java bằng Aspose.TeX. Hướng dẫn toàn diện dành cho nhà phát triển Java.
weight: 11
url: /vi/java/customizing-output/override-job-name-zip/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ghi đè tên công việc và ghi đầu ra đầu cuối vào Zip trong Java

## Giới thiệu

Trong thế giới phát triển Java, Aspose.TeX nổi bật như một công cụ mạnh mẽ để xử lý các định dạng tệp TeX. Trong hướng dẫn này, chúng ta sẽ đi sâu vào một tình huống cụ thể – ghi đè tên công việc và ghi kết quả đầu ra của thiết bị đầu cuối vào tệp zip. Hướng dẫn từng bước này sẽ hướng dẫn bạn qua quy trình sử dụng Aspose.TeX cho Java.

## Điều kiện tiên quyết

Trước khi chúng ta bắt tay vào hướng dẫn này, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
- Kiến thức cơ bản về lập trình Java.
-  Đã cài đặt Aspose.TeX cho Java. Nếu không, bạn có thể tải xuống từ[trang web giả định](https://releases.aspose.com/tex/java/).
- Hiểu biết về cách thiết lập môi trường phát triển Java.

## Gói nhập khẩu

Bắt đầu bằng cách nhập các gói cần thiết vào dự án Java của bạn. Điều này đảm bảo rằng bạn có quyền truy cập vào các chức năng Aspose.TeX cần thiết cho tác vụ.

```java
package com.aspose.tex.OverridenJobNameAndTerminalOutputWrittenToZip;

import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.io.OutputStream;

import com.aspose.tex.InputZipDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.OutputZipDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.PdfDevice;
import com.aspose.tex.rendering.PdfSaveOptions;

import util.Utils;
```

## Bước 1: Mở kho lưu trữ ZIP

Đầu tiên, mở một luồng trên kho lưu trữ ZIP sẽ đóng vai trò là thư mục làm việc đầu vào. Đây là kho lưu trữ mà dữ liệu của bạn sẽ được xử lý.

```java
// Mở luồng trên kho lưu trữ ZIP đầu vào
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
```

## Bước 2: Mở Lưu trữ ZIP đầu ra

Tiếp theo, mở một luồng trên kho lưu trữ ZIP sẽ đóng vai trò là thư mục làm việc đầu ra. Đây là nơi đầu ra của thiết bị đầu cuối sẽ được viết.

```java
// Mở luồng trên kho lưu trữ ZIP đầu ra
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "terminal-out-to-zip.zip");
```

## Bước 3: Đặt tùy chọn chuyển đổi

Tạo các tùy chọn chuyển đổi cho định dạng ObjectTeX mặc định khi mở rộng công cụ ObjectTeX. Chỉ định tên công việc và thư mục làm việc lưu trữ ZIP cho cả đầu vào và đầu ra.

```java
// Tạo tùy chọn TeX cho định dạng ObjectTeX
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("terminal-output-to-zip");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
```

## Bước 4: Chỉ định đầu ra đầu cuối

 Chỉ định rằng đầu ra của thiết bị đầu cuối phải được ghi vào một tệp trong thư mục làm việc đầu ra. Tên tập tin sẽ là`<job_name>.trm`.

```java
// Chỉ định cài đặt đầu ra của thiết bị đầu cuối
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

## Bước 5: Xác định các tùy chọn lưu và chạy công việc

Xác định các tùy chọn lưu, chẳng hạn như tùy chọn lưu PDF trong trường hợp này. Chạy công việc TeX để thực hiện chuyển đổi.

```java
// Xác định các tùy chọn lưu và chạy công việc
options.setSaveOptions(new PdfSaveOptions());
new TeXJob("hello-world", new PdfDevice(), options).run();
```

## Bước 6: Hoàn thiện kho lưu trữ ZIP đầu ra

Sau khi công việc hoàn thành, hãy hoàn thiện kho lưu trữ ZIP đầu ra để đảm bảo hoàn thành đúng cách.

```java
// Hoàn thiện kho lưu trữ ZIP đầu ra
((OutputZipDirectory) options.getOutputWorkingDirectory()).finish();
```

## Phần kết luận

Chúc mừng! Bạn đã học thành công cách ghi đè tên công việc và ghi đầu ra của thiết bị đầu cuối vào tệp ZIP trong Java bằng Aspose.TeX. Chức năng mạnh mẽ này tăng thêm tính linh hoạt và hiệu quả cho các dự án phát triển Java của bạn.

## Câu hỏi thường gặp

### Câu 1: Aspose.TeX là gì?

Câu trả lời 1: Aspose.TeX là thư viện Java cho phép các nhà phát triển làm việc với các định dạng tệp TeX, cung cấp các chức năng nâng cao để xử lý tài liệu.

### Câu hỏi 2: Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.TeX?

 A2: Bạn có thể nhận được giấy phép tạm thời từ[liên kết này](https://purchase.aspose.com/temporary-license/).

### Câu hỏi 3: Tôi có thể tìm tài liệu Aspose.TeX ở đâu?

 A3: Tài liệu có sẵn[đây](https://reference.aspose.com/tex/java/).

### Câu hỏi 4: Có phiên bản dùng thử miễn phí của Aspose.TeX không?

 A4: Có, bạn có thể tìm thấy phiên bản dùng thử miễn phí[đây](https://releases.aspose.com/).

### Câu hỏi 5: Tôi có thể tìm kiếm hỗ trợ hoặc đặt câu hỏi về Aspose.TeX ở đâu?

 A5: Tham quan[diễn đàn Aspose.TeX](https://forum.aspose.com/c/tex/47) để được hỗ trợ và thảo luận.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
