---
title: เรนเดอร์ตัวเลข LaTeX เป็น SVG ด้วย Aspose.TeX (C#)
linktitle: เรนเดอร์ตัวเลข LaTeX เป็น SVG ด้วย Aspose.TeX (C#)
second_title: Aspose.TeX .NET API
description: ปรับปรุงการแสดงผลเอกสารใน .NET ด้วย Aspose.TeX เรียนรู้วิธีเรนเดอร์ตัวเลข LaTeX เป็น SVG ใน C# เพื่อการบูรณาการนิพจน์ทางคณิตศาสตร์ได้อย่างราบรื่น
weight: 11
url: /th/net/render-latex-figures/svg-latex-figure-renderer-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เรนเดอร์ตัวเลข LaTeX เป็น SVG ด้วย Aspose.TeX (C#)

## การแนะนำ

หากคุณต้องการปรับปรุงความสามารถในการเรนเดอร์เอกสารใน .NET โดยใช้ตัวเลข LaTeX Aspose.TeX คือโซลูชันที่เหมาะกับคุณ ในคำแนะนำทีละขั้นตอนนี้ เราจะอธิบายขั้นตอนการเรนเดอร์ตัวเลข LaTeX ไปยัง SVG โดยใช้ Aspose.TeX ใน C# เมื่อสิ้นสุดบทช่วยสอนนี้ คุณจะมีความเข้าใจที่ชัดเจนเกี่ยวกับกระบวนการ ทำให้คุณสามารถรวมนิพจน์และตัวเลขทางคณิตศาสตร์คุณภาพสูงลงในเอกสารของคุณได้อย่างราบรื่น

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
-  ติดตั้ง Aspose.TeX สำหรับไลบรารี .NET แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/tex/net/).

## นำเข้าเนมสเปซ

ในโค้ด C# ของคุณ ตรวจสอบให้แน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็น:

```csharp
using Aspose.TeX.Features;
```

ตอนนี้ เราจะแบ่งบทแนะนำออกเป็นหลายขั้นตอน:

## ขั้นตอนที่ 1: สร้างตัวเลือกการเรนเดอร์

```csharp
FigureRendererOptions options = new SvgFigureRendererOptions();
options.Preamble = "\\usepackage{pict2e}";
options.Scale = 3000;
options.BackgroundColor = Color.White;
options.LogStream = new System.IO.MemoryStream();
options.ShowTerminal = true;
```

ที่นี่ เราได้ตั้งค่าตัวเลือกการเรนเดอร์ โดยระบุคำนำ ปัจจัยการปรับขนาด สีพื้นหลัง สตรีมบันทึก และระบุว่าจะแสดงเอาต์พุตเทอร์มินัลหรือไม่

## ขั้นตอนที่ 2: กำหนดขนาดและสตรีมเอาท์พุต

```csharp
SizeF size = new SizeF();
using (Stream stream = File.Open(Path.Combine("Your Output Directory", "text-and-formula.svg"), FileMode.Create))
{
    // เรียกใช้การเรนเดอร์
    new SvgFigureRenderer().Render("Your LaTeX Code", stream, options, out size);
}
```

แทนที่ "Your Output Directory" ด้วยไดเร็กทอรีที่คุณต้องการและระบุโค้ด LaTeX ของคุณเป็นสตริง

## ขั้นตอนที่ 3: แสดงผล

```csharp
Console.Out.WriteLine(options.ErrorReport);
Console.Out.WriteLine();
Console.Out.WriteLine("Size: " + size);
```

ขั้นตอนนี้จะแสดงรายงานข้อผิดพลาดและขนาดของภาพที่ได้

## บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีเรนเดอร์ตัวเลข LaTeX เป็น SVG โดยใช้ Aspose.TeX ใน C# เรียบร้อยแล้ว ตอนนี้คุณสามารถรวมนิพจน์และตัวเลขทางคณิตศาสตร์เข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น

## คำถามที่พบบ่อย

### คำถามที่ 1: Aspose.TeX ใช้งานได้ฟรีหรือไม่

 ตอบ 1: Aspose.TeX ให้ทดลองใช้ฟรี คุณสามารถเข้าถึงได้[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 2: ฉันจะหาเอกสารประกอบของ Aspose.TeX ได้ที่ไหน

 A2: โปรดดูเอกสารประกอบ[ที่นี่](https://reference.aspose.com/tex/net/).

### คำถามที่ 3: ฉันจะรับการสนับสนุนสำหรับ Aspose.TeX ได้อย่างไร

 A3: เยี่ยมชมฟอรั่มการสนับสนุน[ที่นี่](https://forum.aspose.com/c/tex/47).

### คำถามที่ 4: ฉันสามารถซื้อ Aspose.TeX ได้หรือไม่

 A4: ได้ คุณสามารถซื้อ Aspose.TeX ได้[ที่นี่](https://purchase.aspose.com/buy).

### คำถามที่ 5: ฉันจำเป็นต้องมีใบอนุญาตชั่วคราวหรือไม่

 A5: หากจำเป็น คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
