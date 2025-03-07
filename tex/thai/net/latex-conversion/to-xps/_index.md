---
title: LaTeX เป็น XPS ใน .NET - การแปลงอย่างง่ายดายด้วย Aspose.TeX
linktitle: LaTeX เป็น XPS ใน .NET - การแปลงอย่างง่ายดายด้วย Aspose.TeX
second_title: Aspose.TeX .NET API
description: แปลง LaTeX เป็น XPS ใน .NET ได้อย่างง่ายดายด้วย Aspose.TeX คุณภาพสูง ปรับแต่งได้ และมีประสิทธิภาพ
weight: 13
url: /th/net/latex-conversion/to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# LaTeX เป็น XPS ใน .NET - การแปลงอย่างง่ายดายด้วย Aspose.TeX

## การแนะนำ

คุณกำลังมองหาวิธีที่ราบรื่นในการแปลงเอกสาร LaTeX เป็นรูปแบบ XPS ในแอปพลิเคชัน .NET ของคุณหรือไม่? Aspose.TeX สำหรับ .NET มอบโซลูชันอันทรงพลังสำหรับงานนี้ ทำให้กระบวนการแปลงง่ายและมีประสิทธิภาพ คำแนะนำทีละขั้นตอนนี้จะแนะนำคุณตลอดกระบวนการแปลง LaTeX เป็น XPS โดยใช้ Aspose.TeX เพื่อให้มั่นใจว่าคุณจะได้ผลลัพธ์ที่แม่นยำและมีคุณภาพสูง

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ความรู้ด้านการทำงานของการพัฒนา C# และ .NET
-  ติดตั้ง Aspose.TeX สำหรับไลบรารี .NET แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/tex/net/).
- ความเข้าใจเกี่ยวกับไวยากรณ์และโครงสร้างของ LaTeX

## นำเข้าเนมสเปซ

เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นสำหรับแอปพลิเคชัน .NET ของเรา เนมสเปซเหล่านี้มีความสำคัญอย่างยิ่งต่อการโต้ตอบกับฟังก์ชัน Aspose.TeX

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
using System.Text;
```

## ขั้นตอนที่ 1: ตั้งค่าตัวเลือกการแปลง

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectLaTeX);
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

ที่นี่ เราจะเริ่มต้นตัวเลือกการแปลงและตั้งค่าไดเรกทอรีการทำงานของอินพุตสำหรับไฟล์ LaTeX ของคุณ

## ขั้นตอนที่ 2: ตั้งค่าโหมดการโต้ตอบ

```csharp
options.Interaction = Interaction.NonstopMode;
```

ระบุโหมดการโต้ตอบโดยที่เราตั้งค่าเป็นโหมดไม่หยุดเพื่อให้การแปลงไม่หยุดชะงัก

## ขั้นตอนที่ 3: ตั้งชื่องาน (ไม่บังคับ)

```csharp
// options.JobName = "ชื่องานของฉัน";
```

คุณสามารถตั้งชื่องานแบบกำหนดเองได้หากจำเป็น

## ขั้นตอนที่ 4: กำหนดวันที่ในชื่อเรื่อง (ไม่บังคับ)

```csharp
// options.DateTime = System.DateTime ใหม่ (2022, 12, 18);
```

บังคับให้กลไก TeX ส่งออกวันที่ที่ระบุในชื่อเรื่อง

## ขั้นตอนที่ 5: ละเว้นแพ็คเกจที่หายไป

```csharp
options.IgnoreMissingPackages = true;
```

ตั้งค่าเป็นจริงหากคุณต้องการให้เอ็นจิ้นข้ามแพ็คเกจที่หายไปโดยไม่มีข้อผิดพลาด

## ขั้นตอนที่ 6: ปิดการใช้งานลิเกเจอร์

```csharp
options.NoLigatures = true;
```

ตั้งค่าเป็นจริงเพื่อป้องกันไม่ให้เครื่องยนต์สร้างสายรัด

## ขั้นตอนที่ 7: ทำซ้ำงาน (ไม่บังคับ)

```csharp
// ตัวเลือก ทำซ้ำ = จริง;
```

ขอให้เครื่องยนต์ทำงานซ้ำหากจำเป็น

## ขั้นตอนที่ 8: ระบุไดเร็กทอรีการทำงานของเอาต์พุต

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

ตั้งค่าไดเร็กทอรีการทำงานของเอาต์พุตสำหรับไฟล์ XPS ที่แปลงแล้ว

## ขั้นตอนที่ 9: เริ่มต้นตัวเลือกการบันทึกสำหรับ XPS

```csharp
options.SaveOptions = new XpsSaveOptions(); // ค่าเริ่มต้น การมอบหมายตามอำเภอใจ
```

เริ่มต้นตัวเลือกสำหรับการบันทึกในรูปแบบ XPS

## ขั้นตอนที่ 10: แรสเตอร์สูตร (ไม่บังคับ)

```csharp
options.SaveOptions.RasterizeFormulas = true;
```

ตั้งค่าเป็นจริงหากคุณต้องการแปลงสูตรทางคณิตศาสตร์เป็นรูปภาพแรสเตอร์

## ขั้นตอนที่ 11: แรสเตอร์กราฟิกที่รวมไว้ (ไม่บังคับ)

```csharp
options.SaveOptions.RasterizeIncludedGraphics = true;
```

ตั้งค่าเป็นจริงหากคุณต้องการแปลงกราฟิกที่มีองค์ประกอบเวกเตอร์เป็นภาพแรสเตอร์

## ขั้นตอนที่ 12: แบบอักษรย่อย

```csharp
options.SaveOptions.SubsetFonts = true;
```

ตั้งค่าเป็นจริงเพื่อสร้างแบบอักษรชุดย่อยของอุปกรณ์ที่ใช้ในเอกสาร

## ขั้นตอนที่ 13: เรียกใช้การแปลง LaTeX เป็น XPS

```csharp
new TeXJob(Path.Combine("Your Input Directory", "sample.ltx"), new XpsDevice(), options).Run();
```

เริ่มต้นกระบวนการแปลง LaTeX เป็น XPS

## ขั้นตอนที่ 14: เรียกใช้การแปลง LaTeX เป็น XPS ด้วย MemoryStream (ทางเลือก)

```csharp
// new TeXJob(MemoryStream ใหม่(Encoding.ASCII.GetBytes(@"\documentclass{article} \begin{document} สวัสดีชาวโลก! \end{document}"))
// ใหม่ XpsDevice(), ตัวเลือก).Run();
```

คุณยังสามารถเรียกใช้การแปลงโดยใช้ MemoryStream สำหรับเนื้อหา LaTeX อินพุตได้อีกด้วย

## ขั้นตอนที่ 15: เรียกใช้การแปลง LaTeX เป็น XPS ด้วยเทอร์มินัลอินพุตหลัก (ทางเลือก)

```csharp
// ใหม่ TeXJob (XpsDevice ใหม่ () ตัวเลือก) เรียกใช้ ();
```

เรียกใช้การแปลงโดยตรงจากเทอร์มินัลอินพุตหลัก

## บทสรุป

ด้วยการทำตามขั้นตอนง่ายๆ เหล่านี้ คุณสามารถแปลงเอกสาร LaTeX เป็นรูปแบบ XPS ได้อย่างง่ายดายโดยใช้ Aspose.TeX สำหรับ .NET ไลบรารีอันทรงพลังนี้มีตัวเลือกความยืดหยุ่นและการปรับแต่งเพื่อตอบสนองความต้องการเฉพาะของคุณ

## คำถามที่พบบ่อย

### คำถามที่ 1: Aspose.TeX เข้ากันได้กับเฟรมเวิร์ก .NET ล่าสุดหรือไม่

ตอบ 1: ใช่ Aspose.TeX ได้รับการอัปเดตเป็นประจำเพื่อให้แน่ใจว่าเข้ากันได้กับเฟรมเวิร์ก .NET ล่าสุด

### คำถามที่ 2: ฉันสามารถปรับแต่งรูปแบบเอาต์พุตอื่นที่ไม่ใช่ XPS ได้หรือไม่

 A2: Aspose.TeX รองรับรูปแบบเอาต์พุตที่หลากหลาย โปรดดูเอกสารประกอบ[ที่นี่](https://reference.aspose.com/tex/net/) เพื่อดูรายละเอียด

### คำถามที่ 3: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.TeX ได้อย่างไร

 A3: คุณสามารถรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).

### คำถามที่ 4: ฉันจะขอความช่วยเหลือหรือแบ่งปันประสบการณ์ของฉันกับ Aspose.TeX ได้ที่ไหน

 A4: เยี่ยมชมฟอรั่ม Aspose.TeX[ที่นี่](https://forum.aspose.com/c/tex/47) เพื่อสนับสนุนชุมชน

### คำถามที่ 5: มีเอกสารตัวอย่างให้ทดสอบหรือไม่

 A5: สำรวจตัวอย่าง Aspose.TeX[ที่นี่](https://github.com/aspose-tex/Aspose.TeX-for-.NET).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
