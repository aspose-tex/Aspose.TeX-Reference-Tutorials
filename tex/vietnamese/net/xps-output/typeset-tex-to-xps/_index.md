---
date: 2025-12-30
description: Tìm hiểu cách chuyển đổi TeX sang XPS trong .NET bằng Aspose.TeX. Hãy
  làm theo hướng dẫn từng bước này để tích hợp liền mạch và nhận được kết quả đáng
  tin cậy.
linktitle: How to Convert TeX to XPS in .NET
second_title: Aspose.TeX .NET API
title: Cách chuyển đổi TeX sang XPS trong .NET
url: /vi/net/xps-output/typeset-tex-to-xps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Chuyển Đổi TeX sang XPS trong .NET

## Cách Chuyển Đổi TeX sang XPS – Giới Thiệu

Chào mừng bạn đến với hướng dẫn chi tiết, từng bước của chúng tôi về **cách chuyển đổi TeX** sang định dạng XPS trong môi trường .NET. Sử dụng thư viện mạnh mẽ Aspose.TeX, bạn sẽ có thể tích hợp việc chuyển đổi TeX‑to‑XPS vào bất kỳ ứng dụng .NET nào—cho dù đó là công cụ desktop, dịch vụ web, hay quy trình báo cáo tự động. Trong các phần tiếp theo, chúng tôi sẽ hướng dẫn qua mọi cài đặt cần thiết, trình bày mã nguồn chính xác mà bạn cần, và giải thích lý do mỗi thành phần quan trọng, để bạn có thể triển khai giải pháp một cách tự tin.

## Câu Trả Lời Nhanh
- **Bài hướng dẫn này đề cập đến gì?** Chuyển đổi các tệp TeX sang XPS bằng Aspose.TeX cho .NET.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí đủ cho việc thử nghiệm; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Thời gian triển khai mất bao lâu?** Thông thường dưới 15 phút cho một chuyển đổi cơ bản.  
- **Tôi có thể tải thư viện ở đâu?** Tải xuống từ trang phát hành chính thức của Aspose.TeX.

## Yêu Cầu Trước

Trước khi bắt đầu hướng dẫn, hãy chắc chắn rằng bạn đã chuẩn bị các yêu cầu sau:

- Aspose.TeX cho .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.TeX. Bạn có thể tải xuống [tại đây](https://releases.aspose.com/tex/net/).
- Tài liệu: Làm quen với thư viện bằng cách tham khảo tài liệu [tại đây](https://reference.aspose.com/tex/net/).
- Thư mục Đầu vào và Đầu ra: Thiết lập các thư mục đầu vào và đầu ra theo như trong mã mẫu.

Bây giờ bạn đã có mọi thứ sẵn sàng, hãy tiếp tục với hướng dẫn từng bước.

## Nhập Các Namespace

Trong ứng dụng .NET của bạn, bắt đầu bằng việc nhập các namespace cần thiết. Điều này đảm bảo bạn có quyền truy cập vào các chức năng của Aspose.TeX cần thiết cho việc dàn trang TeX sang XPS.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
```

## Bước 1: Đặt Các Tùy Chọn Chuyển Đổi

Xác định các tùy chọn chuyển đổi, chỉ định định dạng ObjectTeX trên phần mở rộng của engine ObjectTeX. Đồng thời, đặt tên công việc, thư mục đầu vào và đầu ra, và chi tiết đầu ra terminal.

```csharp
// Create conversion options for default ObjectTeX format upon ObjectTeX engine extension.
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
// Specify a job name.
options.JobName = "external-file-stream";
// Specify a file system working directory for input.
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
// Specify a file system working directory for output.
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
// Specify that the terminal output must be written to a file in the output working directory.
// The file name is <job_name>.trm.
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## Bước 2: Tạo Luồng Tài Liệu XPS

Mở một luồng để ghi tài liệu XPS đã dàn trang. Tên tệp không nhất thiết phải giống với tên công việc.

```csharp
using (Stream stream = File.Open(Path.Combine("Your Output Directory", options.JobName + ".xps"), FileMode.Create))
```

## Bước 3: Chạy Công Việc TeX

Khởi tạo và chạy công việc TeX, chỉ định tên tài liệu, XpsDevice và các tùy chọn chuyển đổi.

```csharp
new TeXJob("hello-world", new XpsDevice(stream), options).Run();
```

Chúc mừng! Bạn đã thành công dàn trang TeX sang XPS trong .NET bằng Aspose.TeX. Hãy tự do khám phá thêm các tính năng và tùy chọn dựa trên yêu cầu cụ thể của bạn.

## Kết Luận

Trong hướng dẫn này, chúng tôi đã trình bày các bước cần thiết để chuyển đổi tài liệu TeX sang định dạng XPS trong .NET một cách liền mạch bằng Aspose.TeX. Bằng cách theo dõi hướng dẫn, bạn đã nắm bắt được những hiểu biết quý giá về khả năng của thư viện và cách tận dụng chúng cho dự án của mình.

## Câu Hỏi Thường Gặp

### Q1: Aspose.TeX có tương thích với .NET Core không?
A1: Có, Aspose.TeX hoàn toàn tương thích với .NET Core.

### Q2: Tôi có thể sử dụng Aspose.TeX cho các dự án thương mại không?
A2: Chắc chắn! Aspose.TeX có sẵn cho cả mục đích thương mại và cá nhân.

### Q3: Tôi có thể tìm các ví dụ và tài nguyên bổ sung ở đâu?
A3: Khám phá tài liệu Aspose.TeX [tại đây](https://reference.aspose.com/tex/net/) để xem thêm các ví dụ và tài nguyên chi tiết.

### Q4: Làm sao tôi có thể nhận hỗ trợ cho Aspose.TeX?
A4: Truy cập diễn đàn hỗ trợ Aspose.TeX [tại đây](https://forum.aspose.com/c/tex/47) để nhận sự trợ giúp từ cộng đồng.

### Q5: Có bản dùng thử miễn phí không?
A5: Có, bạn có thể truy cập bản dùng thử miễn phí [tại đây](https://releases.aspose.com/).

## Các Câu Hỏi Thường Gặp

**Q: Tôi có thể tùy chỉnh đầu ra XPS (ví dụ: kích thước trang hoặc lề) không?**  
A: Có. Bạn có thể điều chỉnh cài đặt XpsDevice hoặc sửa đổi nguồn TeX để kiểm soát bố cục trang trước khi chuyển đổi.

**Q: Điều gì sẽ xảy ra nếu tệp TeX đầu vào chứa lỗi?**  
A: Quá trình chuyển đổi sẽ ghi chi tiết lỗi vào tệp đầu ra terminal (`*.trm`). Xem lại tệp này để chẩn đoán và sửa các vấn đề.

**Q: Có thể chuyển đổi nhiều tệp TeX trong một lần chạy không?**  
A: Bạn có thể lặp qua một tập hợp các tệp nguồn TeX, tạo một TeXJob riêng cho mỗi tệp trong khi tái sử dụng cùng một đối tượng `TeXOptions`.

**Q: Aspose.TeX có hỗ trợ các gói LaTeX như `amsmath` hoặc `graphicx` không?**  
A: Hầu hết các gói LaTeX tiêu chuẩn đều được hỗ trợ. Kiểm tra tài liệu chính thức để xem danh sách đầy đủ các gói tương thích.

**Q: Làm thế nào để nhúng phông chữ vào tệp XPS được tạo?**  
A: Aspose.TeX tự động nhúng các phông chữ được engine TeX sử dụng. Đảm bảo các phông chữ cần thiết đã được cài đặt trên máy thực hiện chuyển đổi.

---

**Cập nhật lần cuối:** 2025-12-30  
**Kiểm thử với:** Aspose.TeX cho .NET 24.11  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}