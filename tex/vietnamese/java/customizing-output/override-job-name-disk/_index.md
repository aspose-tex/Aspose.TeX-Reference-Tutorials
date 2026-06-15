---
date: 2026-02-12
description: Tìm hiểu cách ghi lại đầu ra console trong Java bằng Aspose.TeX, ghi
  đầu ra terminal vào tệp và ghi đè tên công việc. Hướng dẫn chi tiết này cũng bao
  gồm cách chuyển hướng đầu ra console trong Java.
linktitle: Write Terminal Output to File and Override Job Name in Java
second_title: Aspose.TeX Java API
title: Cách lấy đầu ra console và ghi đè tên công việc trong Java
url: /vi/java/customizing-output/override-job-name-disk/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ghi Đầu Ra Terminal vào Tập Tin và Ghi Đè Tên Job trong Java

## Giới thiệu

Trong tutorial này, bạn sẽ khám phá **cách ghi lại console output** khi xử lý các tệp TeX bằng Aspose.TeX cho Java. Chúng tôi sẽ hướng dẫn cách ghi đầu ra terminal vào một tệp, ghi đè tên job mặc định, và chuyển hướng console output trong Java để các log dễ dàng tìm thấy và phân tích. Những kỹ thuật này rất quan trọng khi bạn cần ghi log đáng tin cậy cho các chuyển đổi batch hoặc các pipeline tài liệu tự động.

## Câu trả lời nhanh
- **Có thể thay đổi tên job không?** Có, sử dụng `options.setJobName(...)` trước khi chạy job.  
- **Đầu ra terminal được lưu ở đâu?** Nó được lưu dưới dạng `<job_name>.trm` trong thư mục làm việc đầu ra.  
- **Có cần giấy phép cho tính năng này không?** Chức năng này hoạt động với bất kỳ giấy phép Aspose.TeX hợp lệ nào; bản dùng thử miễn phí cũng có sẵn.  
- **Định dạng của tệp đầu ra là gì?** Log terminal dạng plain‑text phản ánh console output.  
- **Có tương thích với các thiết bị đầu ra khác không?** Hoàn toàn—sau khi log được ghi, bạn có thể xử lý nó bằng bất kỳ công cụ nào đọc tệp văn bản.

## **Cách ghi lại console** là gì trong ngữ cảnh của Aspose.TeX?

Ghi lại console output có nghĩa là chuyển hướng mọi thứ thường xuất hiện trên luồng đầu ra chuẩn (terminal) vào một tệp trên đĩa. Với Aspose.TeX, bạn có thể thực hiện điều này một cách dễ dàng bằng cách cấu hình một `OutputFileTerminal` và gán nó cho các tùy chọn chuyển đổi.

## Tại sao phải ghi đè tên job?

Ghi đè tên job cung cấp cho mỗi lần chuyển đổi một định danh duy nhất. Điều này giúp các tệp log (`*.trm`) và các artefact khác dễ dàng theo dõi hơn, đặc biệt khi chạy nhiều job song song hoặc lên lịch các quy trình batch.

## Yêu cầu trước

- Kiến thức cơ bản về lập trình Java.  
- Aspose.TeX cho Java đã được cài đặt (tải xuống từ tài liệu chính thức [Aspose.TeX Java documentation](https://reference.aspose.com/tex/java/)).  
- Một IDE Java hoặc công cụ build (Maven/Gradle) sẵn sàng để biên dịch và chạy mẫu.

## Nhập khẩu các gói

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

> **Mẹo:** Giữ import `util.Utils` chỉ khi bạn cần các phương thức trợ giúp từ tiện ích mẫu của Aspose; nếu không, bạn có thể loại bỏ nó để code gọn hơn.

## Cách Ghi lại Console Output trong Java

Dưới đây là hướng dẫn từng bước cho thấy cách cấu hình các tùy chọn chuyển đổi, ghi đè tên job, và chuyển đầu ra terminal vào một tệp trên đĩa.

### Bước 1: Tạo Conversion Options

Đầu tiên, tạo một thể hiện `TeXOptions` sử dụng cấu hình ObjectTeX mặc định. Đối tượng này sẽ chứa tất cả các cài đặt cho quá trình chuyển đổi.

```java
// ExStart:OverrideJobName-WriteTerminalOutputToFileSystem
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
// ExEnd:OverrideJobName-WriteTerminalOutputToFileSystem
```

### Bước 2: Đặt Tên Job và Thư Mục Làm Việc

Tiếp theo, đặt tên job tùy chỉnh và xác định vị trí các tệp đầu vào và đầu ra. Nếu bạn không đặt tên job, đối số đầu tiên của hàm khởi tạo `TeXJob` sẽ tự động trở thành tên job.

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

> **Tại sao phải ghi đè tên job?**  
> Ghi đè tên job làm cho các tệp log và artefact được tạo ra dễ nhận dạng hơn, đặc biệt khi bạn chạy nhiều job song song hoặc tự động hoá các quy trình batch.

### Bước 3: Ghi Đầu Ra Terminal vào Hệ Thống Tập Tin

Yêu cầu Aspose.TeX ghi lại mọi thứ thường xuất hiện trên console và ghi chúng vào một tệp. Tệp sẽ được đặt tên `<job_name>.trm` và nằm trong thư mục làm việc đầu ra mà bạn đã định nghĩa ở trên.

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### Bước 4: Chạy Job

Cuối cùng, tạo một `TeXJob` với tệp đầu vào mong muốn (ở đây chúng ta dùng ví dụ đơn giản “hello‑world”) và thiết bị render XPS. Sau đó gọi `run()` để thực thi chuyển đổi.

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
```

Khi job hoàn thành, bạn sẽ tìm thấy một tệp có tên `overridden-job-name.trm` trong **Your Output Directory** chứa toàn bộ log terminal.

## Những Sai Lầm Thường Gặp & Khắc Phục

| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|-------------|----------------|
| **Không tạo được tệp `.trm`** | `setTerminalOut` chưa được gọi hoặc thư mục đầu ra không tồn tại | Kiểm tra thư mục đầu ra tồn tại và `options.setTerminalOut(...)` được thực thi trước `job.run()`. |
| **Tên tệp không phải là tên đã ghi đè** | Tên job chưa được đặt đúng | Đảm bảo `options.setJobName("your‑desired‑name")` được gọi **trước** khi tạo `TeXJob`. |
| **Tệp log rỗng** | Các ngoại lệ xảy ra trước khi bắt đầu ghi log | Bao `job.run()` trong khối try‑catch và kiểm tra stack trace để tìm font thiếu hoặc nguồn TeX không hợp lệ. |

## Câu Hỏi Thường Gặp

**Q: Có thể sử dụng Aspose.TeX cho Java cùng với các thư viện Java khác không?**  
A: Có, Aspose.TeX được thiết kế để tích hợp liền mạch với các thư viện Java khác, cho phép bạn kết hợp các tiện ích PDF, hình ảnh hoặc cơ sở dữ liệu trong cùng một workflow.

**Q: Tôi có thể tìm hỗ trợ cho Aspose.TeX cho Java ở đâu?**  
A: Truy cập [Aspose.TeX forum](https://forum.aspose.com/c/tex/47) để nhận trợ giúp từ cộng đồng, hoặc mở ticket hỗ trợ qua cổng hỗ trợ của Aspose.

**Q: Có bản dùng thử miễn phí cho Aspose.TeX cho Java không?**  
A: Chắc chắn. Bạn có thể tải bản dùng thử đầy đủ chức năng từ [Aspose.TeX free trial page](https://releases.aspose.com/).

**Q: Làm sao để lấy giấy phép tạm thời để thử nghiệm?**  
A: Sử dụng mẫu yêu cầu giấy phép tạm thời tại [Aspose temporary license](https://purchase.aspose.com/temporary-license/) để nhận giấy phép đánh giá 30 ngày.

**Q: Tôi có thể mua giấy phép vĩnh viễn ở đâu?**  
A: Mua giấy phép trực tiếp từ [Aspose.TeX buying page](https://purchase.aspose.com/buy).

**Cập nhật lần cuối:** 2026-02-12  
**Đã kiểm tra với:** Aspose.TeX 24.11 cho Java  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}