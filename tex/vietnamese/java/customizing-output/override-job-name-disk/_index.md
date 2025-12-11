---
date: 2025-12-05
description: Tìm hiểu cách ghi đầu ra của terminal vào tệp và ghi đè tên công việc
  bằng Aspose.TeX cho Java. Hãy làm theo hướng dẫn từng bước này kèm theo các ví dụ
  mã đầy đủ.
linktitle: Write Terminal Output to File and Override Job Name in Java
second_title: Aspose.TeX Java API
title: Ghi đầu ra terminal vào tệp và ghi đè tên công việc trong Java
url: /vi/java/customizing-output/override-job-name-disk/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ghi Đầu Ra Terminal vào Tập Tin và Ghi Đè Tên Job trong Java

## Giới thiệu

Aspose.TeX for Java cung cấp các tính năng mạnh mẽ để làm việc với các tệp TeX, cho phép các nhà phát triển thao tác và tùy chỉnh quy trình xử lý tài liệu TeX. Trong hướng dẫn này, bạn sẽ học **cách ghi đầu ra terminal vào tệp** đồng thời ghi đè tên job mặc định — hai khả năng cho phép bạn kiểm soát chi tiết quá trình xử lý batch và ghi log.

## Câu trả lời nhanh
- **Tôi có thể thay đổi tên job không?** Có, sử dụng `options.setJobName(...)` trước khi chạy job.  
- **Đầu ra terminal được lưu ở đâu?** Nó được lưu dưới dạng `<job_name>.trm` trong thư mục làm việc đầu ra.  
- **Tôi có cần giấy phép cho tính năng này không?** Chức năng này hoạt động với bất kỳ giấy phép Aspose.TeX hợp lệ nào; cũng có bản dùng thử miễn phí.  
- **Định dạng của tệp đầu ra là gì?** Log terminal dạng văn bản thuần phản ánh đầu ra console.  
- **Điều này có tương thích với các thiết bị đầu ra khác không?** Hoàn toàn tương thích — một khi log được ghi, bạn có thể xử lý nó bằng bất kỳ công cụ nào đọc tệp văn bản.

## Yêu cầu trước

Trước khi chúng ta đi vào mã, hãy chắc chắn rằng bạn có những thứ sau:

- Kiến thức vững chắc về các nguyên tắc lập trình Java.  
- Aspose.TeX for Java đã được cài đặt (tải về từ [tài liệu chính thức Aspose.TeX Java](https://reference.aspose.com/tex/java/)).  
- Một IDE Java hoặc công cụ build (Maven/Gradle) sẵn sàng để biên dịch và chạy mẫu.

## Nhập Gói

Để bắt đầu, nhập các gói cần thiết vào dự án Java của bạn. Trong tệp Java, bao gồm các import sau:

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

> **Mẹo:** Giữ import `util.Utils` chỉ khi bạn cần các phương thức trợ giúp từ tiện ích mẫu Aspose; nếu không, bạn có thể loại bỏ nó để giữ mã sạch sẽ.

## Cách Ghi Đầu Ra Terminal vào Tập Tin trong Java

Dưới đây là hướng dẫn từng bước cho thấy cách cấu hình các tùy chọn chuyển đổi, ghi đè tên job, và chuyển đầu ra terminal vào một tệp trên đĩa.

### Bước 1: Tạo Các Tùy Chọn Chuyển Đổi

Đầu tiên, tạo một thể hiện `TeXOptions` sử dụng cấu hình ObjectTeX mặc định. Đối tượng này sẽ chứa tất cả các cài đặt cho quá trình chuyển đổi.

```java
// ExStart:OverrideJobName-WriteTerminalOutputToFileSystem
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
// ExEnd:OverrideJobName-WriteTerminalOutputToFileSystem
```

### Bước 2: Xác Định Tên Job và Thư Mục Làm Việc

Tiếp theo, đặt một tên job tùy chỉnh và xác định vị trí của các tệp đầu vào và đầu ra. Nếu bạn không đặt tên job, đối số đầu tiên của hàm khởi tạo `TeXJob` sẽ tự động trở thành tên job.

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

> **Tại sao phải ghi đè tên job?**  
> Ghi đè tên job giúp các tệp log và các artefact được tạo ra dễ nhận dạng hơn, đặc biệt khi bạn chạy nhiều job song song hoặc tự động hoá xử lý batch.

### Bước 3: Ghi Đầu Ra Terminal vào Hệ Thống Tập Tin

Yêu cầu Aspose.TeX ghi lại mọi thứ thường xuất hiện trên console và ghi chúng vào một tệp. Tệp sẽ được đặt tên `<job_name>.trm` và nằm trong thư mục làm việc đầu ra mà bạn đã định nghĩa ở trên.

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### Bước 4: Chạy Job

Cuối cùng, tạo một `TeXJob` với tệp đầu vào mong muốn (ở đây chúng tôi sử dụng ví dụ đơn giản “hello‑world”) và thiết bị render XPS. Sau đó gọi `run()` để thực thi quá trình chuyển đổi.

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
```

Khi job hoàn thành, bạn sẽ thấy một tệp có tên `overridden-job-name.trm` trong **Thư Mục Đầu Ra của Bạn** chứa toàn bộ log terminal.

## Những Sai Lầm Thường Gặp & Khắc Phục

| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|-------|-----|
| **Không tạo được tệp `.trm`** | `setTerminalOut` chưa được gọi hoặc thư mục đầu ra không tồn tại | Kiểm tra thư mục đầu ra tồn tại và `options.setTerminalOut(...)` được thực thi trước `job.run()`. |
| **Tên tệp không phải là tên đã ghi đè** | Tên job không được đặt đúng | Đảm bảo `options.setJobName("your‑desired‑name")` được gọi **trước** khi tạo `TeXJob`. |
| **Tệp log rỗng** | Ngoại lệ xảy ra trước khi bắt đầu ghi log | Bao bọc `job.run()` trong khối try‑catch và kiểm tra stack trace của ngoại lệ để tìm font thiếu hoặc nguồn TeX sai định dạng. |

## Câu Hỏi Thường Gặp

**Hỏi: Tôi có thể sử dụng Aspose.TeX cho Java cùng với các thư viện Java khác không?**  
**Đáp:** Có, Aspose.TeX được thiết kế để tích hợp liền mạch với các thư viện Java khác, cho phép bạn kết hợp các tiện ích PDF, hình ảnh hoặc cơ sở dữ liệu trong cùng một quy trình làm việc.

**Hỏi: Tôi có thể tìm hỗ trợ cho Aspose.TeX cho Java ở đâu?**  
**Đáp:** Truy cập [diễn đàn Aspose.TeX](https://forum.aspose.com/c/tex/47) để nhận trợ giúp từ cộng đồng, hoặc mở ticket hỗ trợ qua cổng hỗ trợ của Aspose.

**Hỏi: Có bản dùng thử miễn phí cho Aspose.TeX cho Java không?**  
**Đáp:** Chắc chắn. Bạn có thể tải bản dùng thử đầy đủ chức năng từ [trang dùng thử miễn phí Aspose.TeX](https://releases.aspose.com/).

**Hỏi: Làm thế nào để tôi có được giấy phép tạm thời để thử nghiệm?**  
**Đáp:** Sử dụng mẫu yêu cầu giấy phép tạm thời tại [Aspose temporary license](https://purchase.aspose.com/temporary-license/) để nhận giấy phép đánh giá 30 ngày.

**Hỏi: Tôi có thể mua giấy phép vĩnh viễn ở đâu?**  
**Đáp:** Mua giấy phép trực tiếp từ [trang mua Aspose.TeX](https://purchase.aspose.com/buy).

## Kết luận

Trong hướng dẫn này, chúng tôi đã trình bày cách **ghi đầu ra terminal vào tệp** và ghi đè tên job mặc định bằng Aspose.TeX cho Java. Những khả năng này cho phép bạn lưu giữ log chi tiết để gỡ lỗi, tự động hoá xử lý batch, và duy trì cấu trúc đầu ra sạch sẽ, có tổ chức — điều cần thiết cho các pipeline chuyển đổi tài liệu cấp sản xuất.

---

**Last Updated:** 2025-12-05  
**Tested With:** Aspose.TeX 24.11 for Java  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}