---
title: เรนเดอร์ตัวเลข LaTeX เป็น PNG ด้วย Aspose.TeX (C#)
linktitle: เรนเดอร์ตัวเลข LaTeX เป็น PNG ด้วย Aspose.TeX (C#)
second_title: Aspose.TeX .NET API
description: สำรวจคำแนะนำที่ครอบคลุมเกี่ยวกับการเรนเดอร์ตัวเลข LaTeX เป็น PNG โดยใช้ Aspose.TeX ใน C# เรียนรู้ทีละขั้นตอนพร้อมตัวอย่างโค้ด
weight: 10
url: /th/net/render-latex-figures/png-latex-figure-renderer-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เรนเดอร์ตัวเลข LaTeX เป็น PNG ด้วย Aspose.TeX (C#)

## การแนะนำ

หากคุณกำลังเจาะลึกโลกแห่งการเรียงพิมพ์และการสร้างเอกสารใน .NET คุณน่าจะคุ้นเคยกับความท้าทายในการแสดงภาพตัวเลข LaTeX ในคำแนะนำทีละขั้นตอนนี้ เราจะสำรวจวิธีใช้ Aspose.TeX สำหรับ .NET เพื่อเรนเดอร์ตัวเลข LaTeX เป็นรูปแบบ PNG โดยใช้ C# Aspose.TeX มอบโซลูชันที่ทรงพลังและยืดหยุ่นสำหรับการจัดการเอกสาร LaTeX ทำให้เป็นเครื่องมืออันล้ำค่าสำหรับนักพัฒนาที่ทำงานเกี่ยวกับการสร้างและการจัดรูปแบบเอกสาร

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  Aspose.TeX สำหรับ .NET Library: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.TeX สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/tex/net/).

## นำเข้าเนมสเปซ

ในโค้ด C# ของคุณ ให้เริ่มด้วยการนำเข้าเนมสเปซที่จำเป็น ขั้นตอนนี้ช่วยให้แน่ใจว่าคุณสามารถเข้าถึงคลาสและฟังก์ชันที่จำเป็นได้

```csharp
using Aspose.TeX.Features;
```

## เรนเดอร์ตัวเลข LaTeX เป็น PNG

### ขั้นตอนที่ 1: ตั้งค่าตัวเลือกการแสดงผล

เริ่มต้นด้วยการสร้างตัวเลือกการเรนเดอร์และการตั้งค่าพารามิเตอร์ เช่น ความละเอียดของภาพ คำนำ ปัจจัยการปรับขนาด สีพื้นหลัง และอื่นๆ

```csharp
FigureRendererOptions options = new PngFigureRendererOptions() { Resolution = 150 };
options.Preamble = "\\usepackage{pict2e}";
options.Scale = 3000;
options.BackgroundColor = System.Drawing.Color.White;
options.LogStream = new System.IO.MemoryStream();
options.ShowTerminal = true;
```

### ขั้นตอนที่ 2: กำหนดสตรีมเอาท์พุตและขนาด

สร้างสตรีมเอาต์พุตสำหรับรูปภาพ PNG และตัวแปรเพื่อจัดเก็บขนาดของรูปภาพที่ได้

```csharp
System.Drawing.SizeF size = new System.Drawing.SizeF();
using (System.IO.Stream stream = System.IO.File.Open(
   System.IO.Path.Combine("Your Output Directory", "text-and-formula.png"), System.IO.FileMode.Create))
{
    // รหัสสำหรับการเรนเดอร์อยู่ที่นี่
}
```

### ขั้นตอนที่ 3: เรียกใช้การเรนเดอร์

ใช้กระบวนการเรนเดอร์โดยใช้ไลบรารี Aspose.TeX ระบุโค้ด LaTeX, สตรีมเอาต์พุต, ตัวเลือกการเรนเดอร์ และตัวแปรขนาด

```csharp
new PngFigureRenderer().Render(@"\setlength{\unitlength}{0.8cm}
\begin{picture}(6,5)
    % LaTeX figure code goes here
\end{picture}", stream, options, out size);
```

### ขั้นตอนที่ 4: แสดงผล

สุดท้ายนี้ ให้แสดงผลลัพธ์ รวมถึงรายงานข้อผิดพลาดและขนาดของภาพที่เรนเดอร์

```csharp
System.Console.Out.WriteLine(options.ErrorReport);
System.Console.Out.WriteLine();
System.Console.Out.WriteLine("Size: " + size);
```

## บทสรุป

ด้วย Aspose.TeX สำหรับ .NET การเรนเดอร์ตัวเลข LaTeX เป็นรูปแบบ PNG จะกลายเป็นกระบวนการที่ราบรื่น บทช่วยสอนนี้ได้อธิบายขั้นตอนสำคัญต่างๆ ให้คุณทราบ ตั้งแต่การตั้งค่าตัวเลือกการเรนเดอร์ไปจนถึงการแสดงผลลัพธ์สุดท้าย

## คำถามที่พบบ่อย

### คำถามที่ 1: Aspose.TeX เข้ากันได้กับคำสั่ง LaTeX ทั้งหมดหรือไม่

 A1: Aspose.TeX รองรับคำสั่ง LaTeX ที่หลากหลาย แต่ขอแนะนำให้อ้างอิงถึง[เอกสารประกอบ](https://reference.aspose.com/tex/net/) สำหรับข้อมูลโดยละเอียด

### คำถามที่ 2: ฉันสามารถลองใช้ Aspose.TeX ก่อนซื้อได้หรือไม่

 A2: ได้ คุณสามารถทดลองใช้เวอร์ชันทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 3: ฉันจะรับการสนับสนุนสำหรับ Aspose.TeX ได้อย่างไร

 A3: เยี่ยมชม[ฟอรั่ม Aspose.TeX](https://forum.aspose.com/c/tex/47)สำหรับการสนับสนุนและการอภิปรายของชุมชน

### คำถามที่ 4: ฉันจะหาใบอนุญาตชั่วคราวสำหรับ Aspose.TeX ได้ที่ไหน

 A4: มีใบอนุญาตชั่วคราว[ที่นี่](https://purchase.aspose.com/temporary-license/).

### คำถามที่ 5: โครงสร้างราคาของ Aspose.TeX เป็นอย่างไรบ้าง

A5: สำรวจรายละเอียดราคาและทำการซื้อ[ที่นี่](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
