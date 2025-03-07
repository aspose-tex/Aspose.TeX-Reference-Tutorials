---
title: Sắp chữ TeX thành XPS trong .NET
linktitle: Sắp chữ TeX thành XPS trong .NET
second_title: API Aspose.TeX .NET
description: Dễ dàng chuyển đổi tài liệu TeX sang XPS trong .NET với Aspose.TeX. Khám phá hướng dẫn từng bước của chúng tôi để có trải nghiệm tích hợp liền mạch.
weight: 10
url: /vi/net/xps-output/typeset-tex-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Sắp chữ TeX thành XPS trong .NET

## Giới thiệu

Chào mừng bạn đến với hướng dẫn từng bước của chúng tôi về cách sắp chữ TeX sang XPS trong .NET bằng thư viện Aspose.TeX mạnh mẽ. Nếu bạn đang tìm cách chuyển đổi liền mạch các tài liệu TeX sang định dạng XPS trong các ứng dụng .NET của mình thì bạn đã đến đúng nơi. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn toàn bộ quy trình, chia nhỏ từng bước để đảm bảo quá trình triển khai diễn ra suôn sẻ.

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

-  Aspose.TeX for .NET: Đảm bảo rằng bạn đã cài đặt thư viện Aspose.TeX. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/tex/net/).

- Tài liệu: Làm quen với thư viện bằng cách tham khảo tài liệu[đây](https://reference.aspose.com/tex/net/).

- Thư mục đầu vào và đầu ra: Thiết lập thư mục đầu vào và đầu ra của bạn như được chỉ định trong mã ví dụ.

Bây giờ bạn đã thiết lập xong mọi thứ, hãy tiếp tục với hướng dẫn từng bước.

## Nhập không gian tên

Trong ứng dụng .NET của bạn, hãy bắt đầu bằng cách nhập các vùng tên cần thiết. Điều này đảm bảo rằng bạn có quyền truy cập vào các chức năng Aspose.TeX cần thiết để sắp chữ TeX thành XPS.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
```

## Bước 1: Đặt tùy chọn chuyển đổi

Xác định các tùy chọn chuyển đổi, chỉ định định dạng ObjectTeX trên phần mở rộng công cụ ObjectTeX. Ngoài ra, hãy đặt tên công việc, thư mục đầu vào và đầu ra cũng như chi tiết đầu ra của thiết bị đầu cuối.

```csharp
// Tạo các tùy chọn chuyển đổi cho định dạng ObjectTeX mặc định khi mở rộng công cụ ObjectTeX.
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
// Chỉ định tên công việc.
options.JobName = "external-file-stream";
// Chỉ định thư mục làm việc của hệ thống tệp cho đầu vào.
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
// Chỉ định thư mục làm việc của hệ thống tệp cho đầu ra.
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
// Chỉ định rằng đầu ra của thiết bị đầu cuối phải được ghi vào một tệp trong thư mục làm việc đầu ra.
// Tên file là <job_name>.trm.
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## Bước 2: Tạo luồng tài liệu XPS

Mở một luồng để viết tài liệu XPS sắp chữ. Tên tệp không nhất thiết phải giống với tên công việc.

```csharp
using (Stream stream = File.Open(Path.Combine("Your Output Directory", options.JobName + ".xps"), FileMode.Create))
```

## Bước 3: Chạy công việc TeX

Bắt đầu và chạy công việc TeX, chỉ định tên tài liệu, XpsDevice và các tùy chọn chuyển đổi.

```csharp
new TeXJob("hello-world", new XpsDevice(stream), options).Run();
```

Chúc mừng! Bạn đã sắp chữ thành công TeX sang XPS trong .NET bằng Aspose.TeX. Hãy thoải mái khám phá thêm các tính năng và tùy chọn dựa trên yêu cầu cụ thể của bạn.

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã trình bày các bước cần thiết để chuyển đổi liền mạch tài liệu TeX sang định dạng XPS trong .NET bằng Aspose.TeX. Bằng cách làm theo hướng dẫn này, bạn đã có được những hiểu biết sâu sắc có giá trị về các khả năng của thư viện và cách tận dụng chúng cho các dự án của mình.

## Câu hỏi thường gặp

### Câu hỏi 1: Aspose.TeX có tương thích với .NET Core không?

Câu trả lời 1: Có, Aspose.TeX hoàn toàn tương thích với .NET Core.

### Câu hỏi 2: Tôi có thể sử dụng Aspose.TeX cho các dự án thương mại không?

A2: Chắc chắn rồi! Aspose.TeX có sẵn cho cả mục đích thương mại và cá nhân.

### Câu hỏi 3: Tôi có thể tìm thêm ví dụ và tài nguyên ở đâu?

 Câu trả lời 3: Khám phá tài liệu Aspose.TeX[đây](https://reference.aspose.com/tex/net/)để biết thêm ví dụ và tài nguyên chi tiết.

### Câu hỏi 4: Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.TeX?

 Câu trả lời 4: Truy cập diễn đàn hỗ trợ Aspose.TeX[đây](https://forum.aspose.com/c/tex/47) để nhận được sự giúp đỡ từ cộng đồng.

### Câu 5: Có bản dùng thử miễn phí không?

 Câu trả lời 5: Có, bạn có thể truy cập bản dùng thử miễn phí[đây](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
