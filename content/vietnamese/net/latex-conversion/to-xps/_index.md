---
title: LaTeX sang XPS trong .NET - Chuyển đổi dễ dàng với Aspose.TeX
linktitle: LaTeX sang XPS trong .NET - Chuyển đổi dễ dàng với Aspose.TeX
second_title: API Aspose.TeX .NET
description: Dễ dàng chuyển đổi LaTeX sang XPS trong .NET bằng Aspose.TeX. Chất lượng cao, có thể tùy chỉnh và hiệu quả.
type: docs
weight: 13
url: /vi/net/latex-conversion/to-xps/
---
## Giới thiệu

Bạn đang tìm kiếm một cách liền mạch để chuyển đổi tài liệu LaTeX sang định dạng XPS trong các ứng dụng .NET của mình? Aspose.TeX for .NET cung cấp một giải pháp mạnh mẽ cho nhiệm vụ này, giúp quá trình chuyển đổi trở nên đơn giản và hiệu quả. Hướng dẫn từng bước này sẽ hướng dẫn bạn quy trình chuyển đổi LaTeX sang XPS bằng Aspose.TeX, đảm bảo bạn đạt được kết quả chính xác và chất lượng cao.

## Điều kiện tiên quyết

Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

- Kiến thức làm việc về phát triển C# và .NET.
-  Đã cài đặt thư viện Aspose.TeX cho .NET. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/tex/net/).
- Hiểu biết về cú pháp và cấu trúc LaTeX.

## Nhập không gian tên

Hãy bắt đầu bằng cách nhập các vùng tên cần thiết cho ứng dụng .NET của chúng ta. Các không gian tên này rất quan trọng để tương tác với các chức năng của Aspose.TeX.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
using System.Text;
```

## Bước 1: Thiết lập tùy chọn chuyển đổi

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectLaTeX);
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

Tại đây, chúng tôi khởi tạo các tùy chọn chuyển đổi và đặt thư mục làm việc đầu vào cho các tệp LaTeX của bạn.

## Bước 2: Đặt chế độ tương tác

```csharp
options.Interaction = Interaction.NonstopMode;
```

Chỉ định chế độ tương tác, trong đó chúng tôi đặt chế độ này ở chế độ không ngừng để chuyển đổi không bị gián đoạn.

## Bước 3: Đặt tên công việc (Tùy chọn)

```csharp
// options.JobName = "my-job-name";
```

Bạn có thể đặt tên công việc tùy chỉnh nếu cần.

## Bước 4: Đặt ngày trong tiêu đề (Tùy chọn)

```csharp
// options.DateTime = new System.DateTime(2022, 12, 18);
```

Buộc công cụ TeX xuất ra một ngày cụ thể trong tiêu đề.

## Bước 5: Bỏ qua các gói bị thiếu

```csharp
options.IgnoreMissingPackages = true;
```

Đặt thành true nếu bạn muốn công cụ bỏ qua các gói bị thiếu mà không gặp lỗi.

## Bước 6: Vô hiệu hóa chữ ghép

```csharp
options.NoLigatures = true;
```

Đặt thành true để ngăn động cơ tạo ra các chữ ghép.

## Bước 7: Lặp lại công việc (Tùy chọn)

```csharp
// tùy chọn.Repeat = true;
```

Yêu cầu động cơ lặp lại công việc nếu cần.

## Bước 8: Chỉ định thư mục làm việc đầu ra

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Đặt thư mục làm việc đầu ra cho các tệp XPS đã chuyển đổi.

## Bước 9: Khởi tạo tùy chọn lưu cho XPS

```csharp
options.SaveOptions = new XpsSaveOptions(); // Giá trị mặc định. Sự phân công tùy ý.
```

Khởi tạo các tùy chọn để lưu ở định dạng XPS.

## Bước 10: Rasterize công thức (Tùy chọn)

```csharp
options.SaveOptions.RasterizeFormulas = true;
```

Đặt thành true nếu bạn muốn chuyển đổi các công thức toán học thành hình ảnh raster.

## Bước 11: Rasterize Đồ họa đi kèm (Tùy chọn)

```csharp
options.SaveOptions.RasterizeIncludedGraphics = true;
```

Đặt thành true nếu bạn muốn chuyển đổi đồ họa đi kèm có thành phần vectơ thành hình ảnh raster.

## Bước 12: Tập hợp phông chữ

```csharp
options.SaveOptions.SubsetFonts = true;
```

Đặt thành true để tạo tập hợp phông chữ con của thiết bị được sử dụng trong tài liệu.

## Bước 13: Chạy chuyển đổi LaTeX sang XPS

```csharp
new TeXJob(Path.Combine("Your Input Directory", "sample.ltx"), new XpsDevice(), options).Run();
```

Bắt đầu quá trình chuyển đổi LaTeX sang XPS.

## Bước 14: Chạy chuyển đổi LaTeX sang XPS bằng MemoryStream (Thay thế)

```csharp
// TeXJob mới(new MemoryStream(Encoding.ASCII.GetBytes(@"\documentclass{article} \begin{document} Xin chào cả thế giới! \end{document}")),
// XpsDevice mới(), tùy chọn).Run();
```

Bạn cũng có thể chạy chuyển đổi bằng MemoryStream cho nội dung LaTeX đầu vào.

## Bước 15: Chạy chuyển đổi LaTeX sang XPS bằng thiết bị đầu cuối đầu vào chính (Thay thế)

```csharp
// TeXJob mới(new XpsDevice(), options).Run();
```

Chạy chuyển đổi trực tiếp từ thiết bị đầu cuối đầu vào chính.

## Phần kết luận

Bằng cách làm theo các bước đơn giản này, bạn có thể dễ dàng chuyển đổi tài liệu LaTeX sang định dạng XPS bằng Aspose.TeX cho .NET. Thư viện mạnh mẽ này cung cấp các tùy chọn linh hoạt và tùy chỉnh để đáp ứng các yêu cầu cụ thể của bạn.

## Câu hỏi thường gặp

### Câu hỏi 1: Aspose.TeX có tương thích với các khung .NET mới nhất không?

Câu trả lời 1: Có, Aspose.TeX được cập nhật thường xuyên để đảm bảo khả năng tương thích với các khung .NET mới nhất.

### Q2: Tôi có thể tùy chỉnh định dạng đầu ra khác với XPS không?

 Câu trả lời 2: Aspose.TeX hỗ trợ nhiều định dạng đầu ra khác nhau. Tham khảo tài liệu[đây](https://reference.aspose.com/tex/net/) để biết chi tiết.

### Câu hỏi 3: Làm cách nào để có được giấy phép tạm thời cho Aspose.TeX?

 A3: Bạn có thể nhận được giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).

### Câu hỏi 4: Tôi có thể tìm kiếm hỗ trợ hoặc chia sẻ trải nghiệm của mình với Aspose.TeX ở đâu?

 Câu trả lời 4: Truy cập diễn đàn Aspose.TeX[đây](https://forum.aspose.com/c/tex/47) để hỗ trợ cộng đồng.

### Câu hỏi 5: Có tài liệu mẫu nào để thử nghiệm không?

 Câu trả lời 5: Khám phá các ví dụ về Aspose.TeX[đây](https://github.com/aspose-tex/Aspose.TeX-for-.NET).