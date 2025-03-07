---
title: Kết xuất số liệu LaTeX thành SVG bằng Aspose.TeX (C#)
linktitle: Kết xuất số liệu LaTeX thành SVG bằng Aspose.TeX (C#)
second_title: API Aspose.TeX .NET
description: Nâng cao khả năng hiển thị tài liệu trong .NET với Aspose.TeX. Tìm hiểu cách hiển thị số liệu LaTeX thành SVG trong C# để tích hợp liền mạch các biểu thức toán học.
weight: 11
url: /vi/net/render-latex-figures/svg-latex-figure-renderer-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kết xuất số liệu LaTeX thành SVG bằng Aspose.TeX (C#)

## Giới thiệu

Nếu bạn đang tìm cách nâng cao khả năng kết xuất tài liệu của mình trong .NET bằng cách sử dụng số liệu LaTeX, Aspose.TeX là giải pháp phù hợp cho bạn. Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn cách hiển thị số liệu LaTeX thành SVG bằng Aspose.TeX trong C#. Khi kết thúc hướng dẫn này, bạn sẽ hiểu rõ ràng về quy trình, giúp bạn có thể kết hợp liền mạch các biểu thức và số liệu toán học chất lượng cao vào tài liệu của mình.

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#.
-  Đã cài đặt thư viện Aspose.TeX cho .NET. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/tex/net/).

## Nhập không gian tên

Trong mã C# của bạn, hãy đảm bảo nhập các không gian tên cần thiết:

```csharp
using Aspose.TeX.Features;
```

Bây giờ, hãy chia hướng dẫn thành nhiều bước:

## Bước 1: Tạo tùy chọn kết xuất

```csharp
FigureRendererOptions options = new SvgFigureRendererOptions();
options.Preamble = "\\usepackage{pict2e}";
options.Scale = 3000;
options.BackgroundColor = Color.White;
options.LogStream = new System.IO.MemoryStream();
options.ShowTerminal = true;
```

Ở đây, chúng tôi thiết lập các tùy chọn hiển thị, chỉ định phần mở đầu, hệ số tỷ lệ, màu nền, luồng nhật ký và liệu có hiển thị đầu ra của thiết bị đầu cuối hay không.

## Bước 2: Xác định kích thước và luồng đầu ra

```csharp
SizeF size = new SizeF();
using (Stream stream = File.Open(Path.Combine("Your Output Directory", "text-and-formula.svg"), FileMode.Create))
{
    // Chạy kết xuất.
    new SvgFigureRenderer().Render("Your LaTeX Code", stream, options, out size);
}
```

Thay thế "Thư mục đầu ra của bạn" bằng thư mục bạn muốn và cung cấp mã LaTeX dưới dạng chuỗi.

## Bước 3: Hiển thị kết quả

```csharp
Console.Out.WriteLine(options.ErrorReport);
Console.Out.WriteLine();
Console.Out.WriteLine("Size: " + size);
```

Bước này hiển thị mọi báo cáo lỗi và kích thước của hình ảnh thu được.

## Phần kết luận

Chúc mừng! Bạn đã học thành công cách hiển thị số liệu LaTeX thành SVG bằng Aspose.TeX trong C#. Giờ đây, bạn có thể tích hợp liền mạch các biểu thức và số liệu toán học vào các ứng dụng .NET của mình.

## Câu hỏi thường gặp

### Câu hỏi 1: Aspose.TeX có được sử dụng miễn phí không?

 Câu trả lời 1: Aspose.TeX cung cấp bản dùng thử miễn phí. Bạn có thể truy cập nó[đây](https://releases.aspose.com/).

### Câu hỏi 2: Tôi có thể tìm tài liệu Aspose.TeX ở đâu?

 A2: Tham khảo tài liệu[đây](https://reference.aspose.com/tex/net/).

### Câu hỏi 3: Làm cách nào để nhận được hỗ trợ cho Aspose.TeX?

 A3: Truy cập diễn đàn hỗ trợ[đây](https://forum.aspose.com/c/tex/47).

### Câu 4: Tôi có thể mua Aspose.TeX không?

 Câu trả lời 4: Có, bạn có thể mua Aspose.TeX[đây](https://purchase.aspose.com/buy).

### Câu hỏi 5: Tôi có cần giấy phép tạm thời không?

 A5: Nếu được yêu cầu, bạn có thể xin giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
