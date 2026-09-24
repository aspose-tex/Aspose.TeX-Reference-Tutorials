---
date: 2026-09-24
description: Tìm hiểu cách cấu hình thư mục đầu vào TeX, streams, images và terminal
  input bằng Aspose.TeX cho .NET trong C#.
keywords:
- configure tex input directory
- add image stream tex
- add images from stream
lastmod: 2026-09-24
linktitle: Aspose.TeX Input và Output nâng cao
og_description: Cấu hình thư mục đầu vào TeX, thêm image streams và xử lý terminal
  input với Aspose.TeX cho .NET trong C#. Tìm hiểu từng bước.
og_image_alt: Guide showing how to configure TeX input directory and streams in Aspose.TeX
  for .NET
og_title: Cấu hình thư mục đầu vào TeX – Hướng dẫn Aspose.TeX nâng cao
schemas:
- author: Aspose
  dateModified: '2026-09-24'
  description: Learn how to configure TeX input directory, streams, images, and terminal
    input using Aspose.TeX for .NET in C#.
  headline: Configure TeX input directory – Advanced Aspose.TeX Input and Output
  type: TechArticle
- description: Learn how to configure TeX input directory, streams, images, and terminal
    input using Aspose.TeX for .NET in C#.
  name: Configure TeX input directory – Advanced Aspose.TeX Input and Output
  steps:
  - name: instantiate TeXInputOptions
    text: Assign the base folder that holds the primary TeX source.
  - name: add extra search paths
    text: If your project stores figures in a separate folder (e.g., *Images*), call
      `AddSearchPath` to include it.
  - name: hand the options to the processor
    text: Create a `TeXProcessor`, provide the configured options, and invoke `Process`
      or `Render`.
  type: HowTo
- questions:
  - answer: Yes—you can create a new `TeXInputOptions` instance with a different `BaseFolder`
      and pass it to a fresh `TeXProcessor` whenever you need to reconfigure.
    question: Can I change the input directory at runtime?
  - answer: Retrieve the image as a `byte[]`, wrap it in a `MemoryStream`, and call
      `TeXInputOptions.AddImage("image.png", stream)`. The name must match the reference
      in your `.tex` file.
    question: How do I add images that are stored in a database?
  - answer: Absolutely. Convert the incoming string to a `MemoryStream`, set it as
      the source for `TeXProcessor`, and render directly to your desired output format.
    question: Is it possible to process LaTeX code received from a web API without
      saving a file?
  - answer: Dispose of any streams you create, and for large workloads invoke `TeXProcessor.Cleanup()`
      to free native resources.
    question: Do I need to call any cleanup methods after processing?
  - answer: The two tutorial links above contain full code samples that demonstrate
      each scenario in detail, including error handling and performance tips.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.TeX .NET API
tags:
- Aspose.TeX
- input directory
- C# document processing
title: Cấu hình thư mục đầu vào TeX – Aspose.TeX Input và Output nâng cao
url: /vi/net/advanced-io/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cấu hình thư mục đầu vào TeX trong Aspose.TeX cho .NET

Aspose.TeX cho .NET cho phép bạn nhúng xử lý TeX đầy đủ tính năng trực tiếp vào các ứng dụng C# của mình. Trong hướng dẫn này, bạn sẽ học cách **cấu hình thư mục đầu vào TeX**, cung cấp nội dung LaTeX từ các luồng, và thêm hình ảnh mà không cần chạm vào hệ thống tệp. Nếu bạn cần kiểm soát chính xác nơi mà engine tìm các tệp `.tex` và tài nguyên, bạn đang ở đúng chỗ.

## Câu trả lời nhanh
- **“Cấu hình thư mục đầu vào tex” có nghĩa là gì?**  
  Nó cho Aspose.TeX biết nơi tìm tệp `.tex` chính, các tệp phụ trợ và đồ họa.
- **Lớp nào định nghĩa các đường dẫn đầu vào?**  
  `TeXInputOptions` lưu trữ thư mục cơ sở và bất kỳ vị trí tìm kiếm bổ sung nào.
- **Tôi có thể tải hình ảnh từ một luồng bộ nhớ không?**  
  Có—sử dụng `TeXInputOptions.AddImage` với một thể hiện `Stream`.
- **Có thể biên dịch mã LaTeX được cung cấp tại thời gian chạy không?**  
  Chắc chắn—chuyển một `MemoryStream` chứa văn bản nguồn cho bộ xử lý.
- **Tôi có cần giấy phép cho việc sử dụng trong môi trường sản xuất không?**  
  Một giấy phép Aspose.TeX hợp lệ là bắt buộc cho các triển khai không phải đánh giá.

## TeXInputOptions là gì?
`TeXInputOptions` là đối tượng cấu hình định nghĩa thư mục cơ sở và các đường dẫn tìm kiếm bổ sung cho tài nguyên TeX. Thiết lập đúng sẽ loại bỏ lỗi “file not found” và giúp bạn tổ chức tài sản một cách hợp lý.

## Cách cấu hình thư mục đầu vào tex?
`TeXInputOptions` là một đối tượng cấu hình chỉ định thư mục cơ sở và các đường dẫn tìm kiếm bổ sung cho tài nguyên TeX. Tải tài liệu chính của bạn và cho bộ xử lý biết nơi tìm mọi thứ chỉ trong vài dòng. Câu trả lời trực tiếp này giải thích các bước thiết yếu trước bất kỳ chi tiết bổ sung nào.

Tạo một thể hiện `TeXInputOptions`, đặt `BaseFolder` thành thư mục chứa tệp `.tex` chính của bạn, thêm bất kỳ thư mục con nào chứa hình ảnh hoặc tệp phụ trợ, và truyền các tùy chọn này cho `TeXProcessor`. Engine sẽ tự động giải quyết tất cả các tham chiếu tương đối.

### Bước 1: khởi tạo TeXInputOptions
Gán thư mục cơ sở chứa nguồn TeX chính.

### Bước 2: thêm các đường dẫn tìm kiếm bổ sung
Nếu dự án của bạn lưu trữ hình ảnh trong một thư mục riêng (ví dụ: *Images*), gọi `AddSearchPath` để bao gồm nó.

### Bước 3: truyền các tùy chọn cho bộ xử lý
Tạo một `TeXProcessor`, cung cấp các tùy chọn đã cấu hình, và gọi `Process` hoặc `Render`.

## Cách thêm hình ảnh với Aspose.TeX
Các hình ảnh được tham chiếu trong tệp TeX có thể được cung cấp qua một thư mục hoặc trực tiếp từ một luồng. Cung cấp luồng rất hữu ích khi hình ảnh được lưu trong cơ sở dữ liệu hoặc được tạo ra ngay tại thời điểm chạy. `AddImage(string name, Stream data)` đăng ký một luồng hình ảnh với tên tệp được chỉ định để sử dụng trong tài liệu TeX. Phương pháp này giúp bạn tránh các tệp tạm thời và tăng tốc xử lý.

## Cách xử lý luồng trong Aspose.TeX
Khi nguồn LaTeX của bạn được tạo động—có thể từ đầu vào người dùng hoặc một dịch vụ web—bạn có thể truyền trực tiếp nó cho bộ xử lý mà không cần ghi ra tệp. `TeXProcessor` xử lý nội dung TeX và có thể nhận một `MemoryStream` chứa mã LaTeX nguồn. Đóng gói chuỗi LaTeX trong một `MemoryStream`, đặt nó làm luồng nguồn trong `TeXProcessor`, và chạy quá trình chuyển đổi. Kỹ thuật này cũng hoạt động tốt cho các dịch vụ đám mây nơi I/O đĩa tốn kém.

## Tại sao nên sử dụng Aspose.TeX cho I/O nâng cao?
Aspose.TeX hỗ trợ **hơn 30 định dạng đầu vào và đầu ra** (bao gồm PDF, PNG, SVG) và có thể render tài liệu hàng trăm trang mà không cần tải toàn bộ tệp vào bộ nhớ. Thiết kế “luồng trước” giảm tải I/O lên tới 40 % so với quy trình dựa trên tệp, làm cho nó trở thành lựa chọn lý tưởng cho các ứng dụng máy chủ có lưu lượng cao.

## Yêu cầu trước
- .NET 6.0 hoặc mới hơn (thư viện cũng hoạt động với .NET Core 3.1+ và .NET Framework 4.6.1+)
- Gói NuGet Aspose.TeX cho .NET (phiên bản 24.11 hoặc mới hơn)
- Giấy phép Aspose.TeX hợp lệ cho việc sử dụng trong môi trường sản xuất

## Khám phá Aspose.TeX: cánh cửa vào xử lý tài liệu nâng cao
Để xem cấu hình hoạt động, hãy làm theo hướng dẫn từng bước **[Chỉ định Thư mục Đầu vào Yêu cầu cho Aspose.TeX (C#)](./required-input-directory-csharp/)**. Hướng dẫn đó sẽ dẫn bạn qua việc tạo đối tượng `TeXInputOptions` và render ra PDF.  
**[Chỉ định Thư mục Đầu vào Yêu cầu cho Aspose.TeX (C#)](./required-input-directory-csharp/)**

## Thành thạo luồng, hình ảnh và đầu vào kiểu terminal trong Aspose.TeX cho C#
Để tìm hiểu sâu hơn về việc cung cấp LaTeX từ bộ nhớ, thêm hình ảnh qua luồng, và sử dụng đầu vào kiểu terminal, hãy xem **[Thành thạo Luồng, Hình ảnh & Đầu vào Terminal trong Aspose.TeX cho C#](./stream-input-image-output-terminal-input-csharp/)**. Nó cho thấy cách tích hợp Aspose.TeX vào API web, dịch vụ nền, và công cụ dòng lệnh.  
**[Thành thạo Luồng, Hình ảnh & Đầu vào Terminal trong Aspose.TeX cho C#](./stream-input-image-output-terminal-input-csharp/)**

## Các vấn đề thường gặp và giải pháp
- **Lỗi “File not found”** – Kiểm tra `BaseFolder` trỏ đúng thư mục và các đường dẫn tìm kiếm bổ sung đã được thêm trước khi render.
- **Hình ảnh không tải** – Đảm bảo tên hình ảnh trong `AddImage` khớp chính xác với tên được sử dụng trong nguồn TeX, bao gồm cả phần mở rộng tệp.
- **Sự tăng đột biến của bộ nhớ** – Khi xử lý tài liệu rất lớn, gọi `TeXProcessor.Cleanup()` sau khi render để giải phóng tài nguyên không quản lý.

## Câu hỏi thường gặp

**H: Tôi có thể thay đổi thư mục đầu vào tại thời gian chạy không?**  
Đ: Có—bạn có thể tạo một thể hiện `TeXInputOptions` mới với `BaseFolder` khác và truyền nó cho một `TeXProcessor` mới mỗi khi cần cấu hình lại.

**H: Làm thế nào để thêm hình ảnh được lưu trong cơ sở dữ liệu?**  
Đ: Lấy hình ảnh dưới dạng `byte[]`, đóng gói nó trong một `MemoryStream`, và gọi `TeXInputOptions.AddImage("image.png", stream)`. Tên phải khớp với tham chiếu trong tệp `.tex` của bạn.

**H: Có thể xử lý mã LaTeX nhận được từ API web mà không lưu thành tệp không?**  
Đ: Chắc chắn. Chuyển chuỗi nhận được thành `MemoryStream`, đặt làm nguồn cho `TeXProcessor`, và render trực tiếp sang định dạng đầu ra mong muốn.

**H: Tôi có cần gọi bất kỳ phương thức dọn dẹp nào sau khi xử lý không?**  
Đ: Hủy các luồng bạn tạo, và đối với khối lượng công việc lớn, gọi `TeXProcessor.Cleanup()` để giải phóng tài nguyên gốc.

**H: Tôi có thể tìm các ví dụ nâng cao hơn ở đâu?**  
Đ: Hai liên kết hướng dẫn ở trên chứa các mẫu mã đầy đủ minh họa từng kịch bản chi tiết, bao gồm xử lý lỗi và mẹo tối ưu hiệu năng.

---

**Cập nhật lần cuối:** 2026-09-24  
**Kiểm tra với:** Aspose.TeX 24.11 cho .NET  
**Tác giả:** Aspose

## Các hướng dẫn liên quan

- [Lấy Luồng Tệp TeX (C#) Sử dụng API Aspose.TeX – Thư mục Đầu vào Yêu cầu](/tex/net/advanced-io/required-input-directory-csharp/)
- [Tạo XPS từ TeX với Hệ thống Tệp – Aspose.TeX cho .NET](/tex/net/file-input-output/filesystem-input-xps-output/)
- [Chuyển LaTeX sang PNG Sử dụng Aspose.TeX cho .NET – Xử lý Đầu vào Hệ thống Tệp & ZIP](/tex/net/file-input-output/required-inputs-from-filesystem-and-zip/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}