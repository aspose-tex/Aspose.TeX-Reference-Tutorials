---
date: 2025-12-11
description: Tìm hiểu cách chuyển đổi TeX sang XPS trong Java bằng Aspose.TeX. Hướng
  dẫn từng bước này cho bạn biết cách tạo luồng tài liệu XPS một cách hiệu quả.
linktitle: How to Convert TeX to XPS in Java with External Stream
second_title: Aspose.TeX Java API
title: Cách chuyển đổi TeX sang XPS trong Java với luồng bên ngoài
url: /vi/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Chuyển Đổi TeX sang XPS trong Java bằng Luồng Ngoại

## Giới thiệu

Nếu bạn cần **convert TeX** các tệp thành đầu ra XPS chất lượng cao từ một ứng dụng Java, Aspose.TeX for Java giúp công việc trở nên đơn giản. Trong hướng dẫn này, bạn sẽ thấy chính xác **how to convert TeX** sang tài liệu XPS bằng một luồng đầu ra bên ngoài, rất phù hợp khi bạn muốn truyền kết quả trực tiếp tới một phản hồi, dịch vụ lưu trữ đám mây, hoặc bất kỳ đích tùy chỉnh nào. Hãy cùng đi qua toàn bộ quy trình, từ thiết lập môi trường đến ghi tệp XPS cuối cùng.

## Câu trả lời nhanh
- **What does this tutorial cover?** Chuyển đổi TeX sang XPS bằng Aspose.TeX với một luồng bên ngoài.  
- **Which primary library is required?** Aspose.TeX for Java.  
- **Do I need a license?** Cần một giấy phép tạm thời hoặc đầy đủ cho việc sử dụng trong môi trường sản xuất.  
- **Can I generate XPS document streams?** Có – ví dụ ghi XPS trực tiếp vào một `OutputStream`.  
- **What Java version is supported?** Bất kỳ JDK 8+ nào (hướng dẫn sử dụng JDK 11 làm tham chiếu).

## Yêu cầu trước

Trước khi bắt đầu viết mã, hãy chắc chắn rằng bạn đã có những thứ sau:

- Java Development Kit (JDK): Đảm bảo rằng bạn đã cài đặt Java trên hệ thống của mình. Bạn có thể tải xuống từ [tại đây](https://www.oracle.com/java/technologies/javase-downloads.html).
- Aspose.TeX for Java: Tải xuống và cài đặt Aspose.TeX for Java. Bạn có thể tìm liên kết tải xuống [tại đây](https://releases.aspose.com/tex/java/).

## Nhập các Gói

Bắt đầu bằng việc nhập các gói cần thiết để khởi động hành trình chuyển đổi TeX‑to‑XPS của bạn. Bao gồm đoạn mã sau trong dự án Java của bạn:

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

## Bước 1: Cấu hình tùy chọn chuyển đổi

Bắt đầu bằng việc tạo các tùy chọn chuyển đổi cho định dạng ObjectTeX mặc định bằng đoạn mã sau:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

Điều này thiết lập nền tảng cho quá trình dàn trang.

## Bước 2: Xác định tên công việc và thư mục

Xác định một tên công việc và đặt thư mục làm việc đầu vào và đầu ra:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Đảm bảo bạn thay thế các placeholder như "Your Input Directory" bằng đường dẫn thư mục thực tế của bạn.

## Bước 3: Cấu hình đầu ra terminal

Chỉ định rằng đầu ra terminal nên được ghi vào một tệp trong thư mục làm việc đầu ra:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

Bước này đảm bảo các nhật ký chi tiết được ghi lại để gỡ lỗi.

## Bước 4: Mở luồng đầu ra

Mở một luồng để ghi tài liệu XPS đã dàn trang:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

Thay thế "Your Output Directory" bằng đường dẫn thích hợp.

## Bước 5: Chạy công việc

Thực thi công việc chuyển đổi TeX sang XPS:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

Quá trình này đã hoàn tất, và bạn sẽ tìm thấy tài liệu XPS đã tạo trong thư mục đầu ra đã chỉ định.

## Các vấn đề thường gặp và giải pháp

| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|-------------|----------------|
| **FileNotFoundException** khi mở luồng | Đường dẫn thư mục đầu ra không đúng hoặc không tồn tại. | Kiểm tra lại đường dẫn, tạo thư mục trước, hoặc sử dụng `Files.createDirectories`. |
| **NullPointerException** trên `options.getOutputWorkingDirectory()` | `setOutputWorkingDirectory` chưa được gọi hoặc trả về `null`. | Đảm bảo bạn gọi `options.setOutputWorkingDirectory` trước khi sử dụng. |
| **LicenseException** tại thời gian chạy | Chạy mà không có giấy phép Aspose.TeX hợp lệ. | Áp dụng giấy phép tạm thời hoặc vĩnh viễn bằng `License license = new License(); license.setLicense("Aspose.TeX.lic");`. |

## Câu hỏi thường gặp

**Q: Can I use Aspose.TeX for Java with other document formats?**  
A: Aspose.TeX chủ yếu tập trung vào xử lý tài liệu liên quan đến TeX. Đối với các định dạng khác, hãy khám phá danh mục sản phẩm phong phú của Aspose.

**Q: Is there a trial version available?**  
A: Có, bạn có thể trải nghiệm Aspose.TeX bằng cách tải xuống bản dùng thử miễn phí [tại đây](https://releases.aspose.com/).

**Q: Where can I find comprehensive documentation?**  
A: Tham khảo tài liệu [tại đây](https://reference.aspose.com/tex/java/) để biết thông tin chi tiết và các ví dụ.

**Q: How do I get support or seek assistance?**  
A: Truy cập diễn đàn Aspose.TeX [tại đây](https://forum.aspose.com/c/tex/47) để nhận hỗ trợ cộng đồng và thảo luận.

**Q: Can I obtain a temporary license for testing purposes?**  
A: Có, bạn có thể lấy giấy phép tạm thời [tại đây](https://purchase.aspose.com/temporary-license/).

## Kết luận

Chúc mừng! Bạn vừa học **how to convert TeX** sang tài liệu XPS trong Java bằng Aspose.TeX và một luồng bên ngoài. Kỹ thuật này cho phép bạn kiểm soát hoàn toàn nơi đầu ra XPS sẽ được gửi—cho dù là hệ thống tệp, phản hồi web, hay một bucket đám mây. Hãy thoải mái thử nghiệm với các nguồn TeX khác nhau, điều chỉnh `TeXOptions` để sử dụng phông chữ tùy chỉnh, hoặc kết nối luồng vào một pipeline tạo tài liệu lớn hơn.

---

**Cập nhật lần cuối:** 2025-12-11  
**Kiểm tra với:** Aspose.TeX for Java 24.11 (phiên bản mới nhất tại thời điểm viết)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}