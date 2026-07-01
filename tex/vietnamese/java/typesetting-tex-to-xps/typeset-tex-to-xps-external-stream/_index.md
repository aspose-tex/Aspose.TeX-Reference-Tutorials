---
date: 2026-02-20
description: Tìm hiểu cách chuyển đổi TeX sang XPS trong Java bằng Aspose.TeX. Hướng
  dẫn từng bước này cho bạn biết cách chuyển đổi tệp TeX và tạo luồng tài liệu XPS
  một cách hiệu quả.
linktitle: How to Convert TeX to XPS in Java with External Stream
second_title: Aspose.TeX Java API
title: Cách chuyển đổi TeX sang XPS trong Java bằng luồng bên ngoài
url: /vi/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Chuyển Đổi TeX sang XPS trong Java bằng Luồng Ngoại

## Giới thiệu

Nếu bạn cần **chuyển đổi các tệp TeX** thành đầu ra XPS chất lượng cao từ một ứng dụng Java, Aspose.TeX for Java sẽ giúp công việc trở nên đơn giản. Trong hướng dẫn này, bạn sẽ thấy **cách chuyển đổi TeX** sang tài liệu XPS bằng một luồng đầu ra bên ngoài, rất hữu ích khi bạn muốn truyền kết quả trực tiếp tới phản hồi HTTP, dịch vụ lưu trữ đám mây, hoặc bất kỳ đích tùy chỉnh nào khác. Hãy cùng đi qua toàn bộ quy trình, từ việc thiết lập môi trường đến ghi tệp XPS cuối cùng.

## Câu trả lời nhanh
- **Hướng dẫn này đề cập đến gì?** Chuyển đổi TeX sang XPS bằng Aspose.TeX với luồng bên ngoài.  
- **Thư viện chính cần thiết là gì?** Aspose.TeX for Java.  
- **Có cần giấy phép không?** Cần một giấy phép tạm thời hoặc đầy đủ cho việc sử dụng trong môi trường sản xuất.  
- **Có thể tạo luồng tài liệu XPS không?** Có – ví dụ sẽ ghi XPS trực tiếp vào một `OutputStream`.  
- **Phiên bản Java nào được hỗ trợ?** Bất kỳ JDK 8+ nào (hướng dẫn sử dụng JDK 11 làm tham chiếu).

## Cách Chuyển Đổi TeX sang XPS Bằng Luồng Ngoại

Phần này lặp lại từ khóa chính trong một tiêu đề riêng, giúp người đọc và các công cụ AI dễ dàng tìm thấy giải pháp chính xác.

## Yêu cầu trước

Trước khi bắt đầu viết mã, hãy đảm bảo bạn có những thứ sau:

- Java Development Kit (JDK): Đảm bảo rằng Java đã được cài đặt trên hệ thống của bạn. Bạn có thể tải về từ [đây](https://www.oracle.com/java/technologies/javase-downloads.html).

- Aspose.TeX for Java: Tải xuống và cài đặt Aspose.TeX for Java. Bạn có thể tìm liên kết tải về [đây](https://releases.aspose.com/tex/java/).

## Nhập Gói

Bắt đầu bằng việc nhập các gói cần thiết để khởi động quá trình chuyển đổi TeX‑to‑XPS. Thêm đoạn mã sau vào dự án Java của bạn:

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

## Bước 1: Cấu Hình Tùy Chọn Chuyển Đổi

Tạo các tùy chọn chuyển đổi cho định dạng ObjectTeX mặc định bằng đoạn mã sau:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

Điều này thiết lập nền tảng cho quá trình dàn trang.

## Bước 2: Xác Định Tên Công Việc và Thư Mục

Đặt tên công việc và chỉ định thư mục làm việc đầu vào và đầu ra:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Hãy thay thế các placeholder như "Your Input Directory" bằng đường dẫn thư mục thực tế của bạn.

## Bước 3: Cấu Hình Đầu Ra Terminal

Chỉ định rằng đầu ra terminal sẽ được ghi vào một tệp trong thư mục làm việc đầu ra:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

Bước này đảm bảo các log chi tiết được ghi lại để dễ dàng gỡ lỗi.

## Bước 4: Mở Luồng Đầu Ra

Mở một luồng để ghi tài liệu XPS đã dàn trang:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

Thay thế "Your Output Directory" bằng đường dẫn phù hợp.

## Bước 5: Chạy Công Việc

Thực thi công việc chuyển đổi TeX sang XPS:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

Quá trình hoàn tất, và bạn sẽ tìm thấy tài liệu XPS đã tạo trong thư mục đầu ra đã chỉ định.

## Tại Sao Điều Này Quan Trọng

Sử dụng một `OutputStream` bên ngoài cho phép bạn kiểm soát hoàn toàn nơi dữ liệu XPS được đưa tới — dù là gửi trực tiếp tới client web, lưu trữ trên đám mây, hay truyền vào một pipeline xử lý khác. Điều này loại bỏ nhu cầu tạo các tệp trung gian và giảm tải I/O, rất hữu ích trong các môi trường có lưu lượng cao hoặc không có máy chủ.

## Các Vấn Đề Thường Gặp và Giải Pháp

| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|-------------|----------------|
| **FileNotFoundException** khi mở luồng | Đường dẫn thư mục đầu ra không đúng hoặc không tồn tại. | Kiểm tra lại đường dẫn, tạo thư mục trước khi ghi, hoặc sử dụng `Files.createDirectories`. |
| **NullPointerException** trên `options.getOutputWorkingDirectory()` | `setOutputWorkingDirectory` chưa được gọi hoặc trả về `null`. | Đảm bảo gọi `options.setOutputWorkingDirectory` trước khi sử dụng. |
| **LicenseException** khi chạy | Chạy mà không có giấy phép Aspose.TeX hợp lệ. | Áp dụng giấy phép tạm thời hoặc vĩnh viễn bằng `License license = new License(); license.setLicense("Aspose.TeX.lic");`. |

## Câu Hỏi Thường Gặp

**H: Tôi có thể dùng Aspose.TeX for Java với các định dạng tài liệu khác không?**  
Đ: Aspose.TeX chủ yếu tập trung vào xử lý tài liệu liên quan đến TeX. Đối với các định dạng khác, hãy khám phá danh mục sản phẩm phong phú của Aspose.

**H: Có phiên bản dùng thử không?**  
Đ: Có, bạn có thể trải nghiệm Aspose.TeX bằng cách tải bản dùng thử miễn phí [đây](https://releases.aspose.com/).

**H: Tôi có thể tìm tài liệu chi tiết ở đâu?**  
Đ: Tham khảo tài liệu [đây](https://reference.aspose.com/tex/java/) để biết thông tin chi tiết và các ví dụ.

**H: Làm sao để nhận hỗ trợ hoặc trợ giúp?**  
Đ: Truy cập diễn đàn Aspose.TeX [đây](https://forum.aspose.com/c/tex/47) để nhận hỗ trợ cộng đồng và thảo luận.

**H: Tôi có thể lấy giấy phép tạm thời để thử nghiệm không?**  
Đ: Có, bạn có thể mua giấy phép tạm thời [đây](https://purchase.aspose.com/temporary-license/).

## Kết Luận

Chúc mừng! Bạn vừa học được **cách chuyển đổi TeX** sang tài liệu XPS trong Java bằng Aspose.TeX và một luồng bên ngoài. Kỹ thuật này cho phép bạn kiểm soát hoàn toàn nơi đầu ra XPS được đưa tới — dù là hệ thống tệp, phản hồi web, hay bucket đám mây. Hãy tự do thử nghiệm với các nguồn TeX khác nhau, điều chỉnh `TeXOptions` để sử dụng phông chữ tùy chỉnh, hoặc kết nối luồng này vào một pipeline tạo tài liệu lớn hơn.

---

**Cập nhật lần cuối:** 2026-02-20  
**Đã kiểm tra với:** Aspose.TeX for Java 24.11 (phiên bản mới nhất tại thời điểm viết)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}