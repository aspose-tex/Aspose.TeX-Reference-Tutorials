---
title: Sắp chữ TeX sang PDF bằng Java bằng luồng ngoài
linktitle: Sắp chữ TeX sang PDF bằng Java bằng luồng ngoài
second_title: API Java Aspose.TeX
description: Tìm hiểu cách sắp chữ TeX thành PDF trong Java bằng cách sử dụng các luồng bên ngoài với Aspose.TeX. Hãy làm theo hướng dẫn từng bước của chúng tôi để tích hợp liền mạch.
type: docs
weight: 10
url: /vi/java/typesetting-tex-to-pdf/typeset-tex-to-pdf-external-stream/
---
## Giới thiệu

Trong thế giới phát triển Java, việc tạo tệp PDF từ tệp TeX là một yêu cầu phổ biến. Aspose.TeX dành cho Java đơn giản hóa quy trình này, cung cấp giải pháp hiệu quả để sắp chữ TeX thành PDF. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn các bước sắp chữ TeX sang PDF bằng cách sử dụng các luồng bên ngoài. Cuối cùng, bạn sẽ hiểu rõ ràng về cách triển khai quy trình này một cách liền mạch trong các ứng dụng Java của mình.

## Điều kiện tiên quyết

Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

- Aspose.TeX cho Java: Đảm bảo rằng bạn đã cài đặt thư viện Aspose.TeX cho Java. Bạn có thể tải nó xuống từ[Tài liệu Aspose.TeX cho Java](https://reference.aspose.com/tex/java/).

- Thư mục đầu vào và đầu ra: Chuẩn bị các thư mục đầu vào và đầu ra. Bạn có thể sử dụng liên kết tải xuống được cung cấp để lấy các tệp cần thiết.

## Gói nhập khẩu

Bắt đầu bằng cách nhập các gói cần thiết vào dự án Java của bạn:

```java
package com.aspose.tex.TypesetPdfWrittenToExternalStream;

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

## Bước 1: Mở luồng đầu vào và đầu ra

Bắt đầu bằng cách mở các luồng cho kho lưu trữ ZIP đầu vào (đóng vai trò là thư mục làm việc đầu vào) và kho lưu trữ ZIP đầu ra (đóng vai trò là thư mục làm việc đầu ra). Đảm bảo thay thế "Thư mục đầu vào của bạn" và "Thư mục đầu ra của bạn" bằng đường dẫn thư mục thực tế của bạn.

```java
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "typeset-pdf-to-external-stream.zip");
```

## Bước 2: Định cấu hình TeXOptions

Tạo đối tượng TeXOptions và định cấu hình nó theo yêu cầu của bạn. Đặt tên lệnh, thư mục làm việc đầu vào, thư mục làm việc đầu ra và các tùy chọn khác.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("typeset-pdf-to-external-stream");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
options.setSaveOptions(new PdfSaveOptions());
```

## Bước 3: Sắp chữ TeX sang PDF

Bây giờ, hãy mở luồng để ghi tệp PDF đầu ra vào vị trí mong muốn. Bạn có thể chọn ghi nó vào một tệp cục bộ hoặc trực tiếp vào kho lưu trữ ZIP đầu ra.

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + "file-name.pdf");
try {
    new TeXJob("hello-world", new PdfDevice(stream), options).run();
} finally {
    stream.close();
}
```

## Bước 4: Hoàn thiện kho lưu trữ ZIP đầu ra

Hoàn tất kho lưu trữ ZIP đầu ra để hoàn tất quá trình sắp chữ.

```java
((OutputZipDirectory)options.getOutputWorkingDirectory()).finish();
```

## Phần kết luận

Chúc mừng! Bạn đã sắp chữ thành công TeX sang PDF trong Java bằng cách sử dụng các luồng bên ngoài với Aspose.TeX. Hướng dẫn này cung cấp nền tảng vững chắc để kết hợp chuyển đổi TeX sang PDF vào các ứng dụng Java của bạn một cách liền mạch.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể tùy chỉnh tên tệp PDF đầu ra không?

 A1: Có, bạn có thể sửa đổi`options.setJobName("typeset-pdf-to-external-stream")` để đặt tên công việc mong muốn của bạn.

### Câu hỏi 2: Làm cách nào để khắc phục các sự cố thường gặp trong quá trình sắp chữ?

 A2: Tham quan[diễn đàn Aspose.TeX](https://forum.aspose.com/c/tex/47) để được cộng đồng hỗ trợ và giúp đỡ.

### Câu hỏi 3: Có bản dùng thử miễn phí cho Aspose.TeX cho Java không?

 Câu trả lời 3: Có, bạn có thể truy cập bản dùng thử miễn phí[đây](https://releases.aspose.com/).

### Câu hỏi 4: Tôi có thể tìm tài liệu và ví dụ bổ sung ở đâu?

 A4: Khám phá toàn diện[Tài liệu Aspose.TeX](https://reference.aspose.com/tex/java/) để biết thông tin chi tiết.

### Câu hỏi 5: Tôi có thể xin giấy phép tạm thời cho Aspose.TeX không?

 A5: Có, bạn có thể yêu cầu giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).