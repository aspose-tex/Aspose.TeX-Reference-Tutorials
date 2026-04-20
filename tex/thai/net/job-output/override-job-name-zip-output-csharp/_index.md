---
date: 2025-12-21
description: เรียนรู้วิธีแปลง TeX เป็น PDF, แทนที่ชื่องาน, และบันทึกผลลัพธ์ของเทอร์มินัลลงในไฟล์
  ZIP ด้วย Aspose.TeX สำหรับ .NET. สร้าง PDF จาก TeX ด้วย C#
linktitle: Convert TeX to PDF and Override Job Name – Write Output to ZIP (C#)
second_title: Aspose.TeX .NET API
title: แปลง TeX เป็น PDF และแทนที่ชื่องาน – เขียนผลลัพธ์เป็นไฟล์ ZIP (C#)
url: /th/net/job-output/override-job-name-zip-output-csharp/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลง TeX เป็น PDF และแทนที่ชื่อ Job – เขียนผลลัพธ์ลงใน ZIP (C#)

## บทนำ

ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีแปลง TeX เป็น PDF** พร้อมกับการแทนที่ชื่อ job และการจับผลลัพธ์ของเทอร์มินัลไว้ในไฟล์ ZIP. Aspose.TeX for .NET ทำให้การสร้าง PDF จาก TeX เป็นเรื่องง่าย ให้คุณควบคุมการตั้งค่า job และการจัดการผลลัพธ์ได้อย่างเต็มที่ ไม่ว่าคุณจะทำการสร้างรายงานอัตโนมัติหรือสร้าง pipeline การเผยแพร่ที่ใช้ TeX ขั้นตอนต่อไปนี้จะพาคุณจากไฟล์ต้นฉบับ TeX ธรรมดาไปสู่ไฟล์ PDF ที่พร้อมใช้งานและเก็บไว้ในคอนเทนเนอร์ ZIP.

## คำตอบสั้น

- **บทแนะนำนี้ครอบคลุมอะไร?** การแปลง TeX เป็น PDF, การแทนที่ชื่อ job ของ TeX, และการเขียนผลลัพธ์ของเทอร์มินัลลงไฟล์ ZIP ด้วย C#.
- **ไลบรารีที่ต้องการคืออะไร?** Aspose.TeX for .NET (โซลูชัน “สร้าง PDF ด้วย Aspose”).
- **ต้องใช้ไลเซนส์หรือไม่?** ไลเซนส์ชั่วคราวใช้ได้สำหรับการทดสอบ; ไลเซนส์เต็มจำเป็นสำหรับการใช้งานจริง.
- **ข้อกำหนดเบื้องต้นคืออะไร?** สภาพแวดล้อมการพัฒนา .NET, ติดตั้ง Aspose.TeX, และไฟล์ ZIP สำหรับเข้าและออก.
- **ใช้เวลานานเท่าไหร่ในการทำงาน?** ประมาณ 10–15 นาทีหลังจากตั้งค่าสภาพแวดล้อมเรียบร้อย.

## “แปลง tex เป็น pdf” คืออะไร?

การแปลง TeX เป็น PDF หมายถึงการนำเอกสารต้นฉบับ TeX มาประมวลผลด้วยเอนจิน TeX เพื่อสร้างไฟล์ PDF. Aspose.TeX มี API .NET ที่จัดการการแปลงนี้โดยไม่ต้องพึ่งพาการติดตั้ง TeX ภายนอก.

## ทำไมต้องแทนที่ชื่อ Job?

การแทนที่ชื่อ job ช่วยให้คุณควบคุมชื่อฐานที่ใช้สำหรับไฟล์ช่วยเหลือ (เช่น *.log, *.aux) และสตรีมผลลัพธ์ที่คุณเปลี่ยนเส้นทาง. สิ่งนี้เป็นประโยชน์อย่างยิ่งเมื่อคุณรันหลาย job ในไดเรกทอรีทำงานเดียวกันหรือเมื่อคุณต้องการโครงสร้างการตั้งชื่อไฟล์ที่คาดเดาได้สำหรับการประมวลผลต่อไป.

## ข้อกำหนดเบื้องต้น

- ความคุ้นเคยกับ C# และการพัฒนา .NET.
- ติดตั้ง Aspose.TeX for .NET (ผ่าน NuGet หรือแพคเกจแบบแมนนวล).
- ไฟล์ ZIP เข้า (input) ที่บรรจุไฟล์ต้นฉบับ TeX.
- ไฟล์ ZIP ว่าง (empty) ที่จะรับผลลัพธ์ของเทอร์มินัล.

## นำเข้า Namespaces

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Pdf;
using System.IO;
```

## วิธีแปลง TeX เป็น PDF และแทนที่ชื่อ Job

ด้านล่างเป็นคู่มือขั้นตอนต่อขั้นตอนที่พาคุณผ่านการเปิดสตรีม ZIP, การกำหนดค่าตัวเลือกการแปลง, การรัน TeX job, และการสรุป ZIP ผลลัพธ์.

### ขั้นตอนที่ 1: เปิดสตรีม ZIP เข้าและออก

```csharp
using (Stream inZipStream = File.Open(Path.Combine("Your Input Directory", "zip-in.zip"), FileMode.Open))
using (Stream outZipStream = File.Open(Path.Combine("Your Output Directory", "terminal-out-to-zip.zip"), FileMode.Create))
{
    // Code for step 1 goes here
}
```

*คำอธิบาย*: คำสั่ง `using` ทำให้แน่ใจว่าทั้งสองสตรีมถูกปล่อยทรัพยากรอย่างถูกต้อง. ZIP เข้า (`zip-in.zip`) เก็บไฟล์ต้นฉบับ TeX, ส่วน ZIP ออก (`terminal-out-to-zip.zip`) จะเก็บบันทึกเทอร์มินัลที่สร้างระหว่างการแปลง.

### ขั้นตอนที่ 2: ตั้งค่าตัวเลือกการแปลง (รวมถึง **override job name**)

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
options.JobName = "terminal-output-to-zip";
options.InputWorkingDirectory = new InputZipDirectory(inZipStream, "in");
options.OutputWorkingDirectory = new OutputZipDirectory(outZipStream);
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

*คำอธิบาย*:  
- `JobName` ถูกตั้งค่าเป็น `"terminal-output-to-zip"` – นี้จะแทนที่ชื่อ job เริ่มต้น.  
- `InputWorkingDirectory` และ `OutputWorkingDirectory` ชี้ไปที่สตรีม ZIP, ทำให้ Aspose.TeX สามารถอ่าน/เขียนโดยตรงจากไฟล์ ZIP.  
- `TerminalOut` เปลี่ยนเส้นทางเอาต์พุตคอนโซลของเอนจิน TeX ไปยังไฟล์ภายใน ZIP ผลลัพธ์.

### ขั้นตอนที่ 3: กำหนดตัวเลือกการบันทึก (สร้าง PDF จาก TeX)

```csharp
options.SaveOptions = new PdfSaveOptions();
```

*คำอธิบาย*: `PdfSaveOptions` บอก Aspose.TeX ให้สร้างไฟล์ PDF เป็นผลลัพธ์สุดท้าย.

### ขั้นตอนที่ 4: รัน TeX Job

```csharp
new TeXJob("hello-world", new PdfDevice(), options).Run();
```

*คำอธิบาย*: ตัวสร้าง `TeXJob` รับชื่อไฟล์ TeX หลัก (`hello-world.tex`), อุปกรณ์เป้าหมาย (`PdfDevice`), และ `options` ที่กำหนดไว้ก่อนหน้า. การเรียก `.Run()` จะเริ่มกระบวนการแปลง.

### ขั้นตอนที่ 5: สรุปไฟล์ ZIP ผลลัพธ์

```csharp
((OutputZipDirectory)options.OutputWorkingDirectory).Finish();
```

*คำอธิบาย*: คำสั่งนี้จะล้างข้อมูลที่ค้างอยู่และปิด ZIP ผลลัพธ์อย่างถูกต้อง, ทำให้บันทึกเทอร์มินัลและ PDF ที่สร้างขึ้นถูกเก็บอย่างสมบูรณ์.

## ปัญหาที่พบบ่อยและการแก้ไข

| อาการ | สาเหตุที่เป็นไปได้ | วิธีแก้ |
|---------|--------------|-----|
| PDF ไม่ถูกสร้าง | `options.SaveOptions` ไม่ได้ตั้งค่า | ตรวจสอบว่าขั้นตอน 3 ถูกดำเนินการ. |
| บันทึกเทอร์มินัลว่างเปล่า | `options.TerminalOut` ไม่ได้กำหนด | ตรวจสอบให้แน่ใจว่าขั้นตอน 2 มีบรรทัด `TerminalOut`. |
| ข้อผิดพลาด “File not found” | เส้นทางไปยัง ZIP เข้าไม่ถูกต้อง | ตรวจสอบเส้นทางไฟล์ในขั้นตอน 1 อีกครั้ง. |
| ชื่อ job ไม่ปรากฏในไฟล์ช่วยเหลือ | พิมพ์ผิด `options.JobName` | ยืนยันว่าชื่อคุณสมบัติคือ `JobName` อย่างถูกต้อง. |

## คำถามที่พบบ่อย

### Q1: ฉันสามารถใช้ Aspose.TeX for .NET กับภาษา .NET อื่น ๆ เช่น VB.NET ได้หรือไม่?

**A:** ใช่, Aspose.TeX for .NET รองรับทุกภาษา .NET รวมถึง VB.NET, F#, และ C#.

### Q2: ฉันสามารถหาเอกสารเพิ่มเติมสำหรับ Aspose.TeX for .NET ได้ที่ไหน?

**A:** เยี่ยมชม [documentation](https://reference.aspose.com/tex/net/) เพื่อดูข้อมูลโดยละเอียด.

### Q3: ฉันจะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.TeX ได้อย่างไร?

**A:** รับ [temporary license](https://purchase.aspose.com/temporary-license/) สำหรับการทดสอบ.

### Q4: มีฟอรั่มชุมชนสำหรับการสนับสนุน Aspose.TeX หรือไม่?

**A:** ใช่, เข้าร่วม [Aspose.TeX forum](https://forum.aspose.com/c/tex/47) เพื่อรับการสนับสนุนจากชุมชน.

### Q5: ฉันสามารถซื้อ Aspose.TeX for .NET ได้จากที่ไหน?

**A:** คุณสามารถซื้อ Aspose.TeX [ที่นี่](https://purchase.aspose.com/buy).

### Q6: วิธีนี้ทำงานบน .NET Core / .NET 5+ หรือไม่?

**A:** แน่นอน. Aspose.TeX รองรับ .NET Framework, .NET Core, และ .NET 5/6+. เพียงอ้างอิงแพคเกจ NuGet ที่เหมาะสม.

### Q7: ฉันสามารถปรับแต่งผลลัพธ์ PDF (เช่น เพิ่ม metadata) ได้หรือไม่?

**A:** ใช่. หลังจากการแปลง, คุณสามารถใช้ Aspose.PDF หรือคุณสมบัติของ `PdfSaveOptions` เพื่อฝัง metadata, ตั้งค่าระดับการบีบอัด, หรือปรับการตั้งค่าหน้ากระดาษ.

## สรุป

ตอนนี้คุณมีตัวอย่างที่สมบูรณ์และพร้อมใช้งานในสภาพแวดล้อมการผลิตที่ **แปลง TeX เป็น PDF**, **แทนที่ชื่อ job**, และ **เขียนผลลัพธ์ของเทอร์มินัลลงในไฟล์ ZIP** ด้วย Aspose.TeX for .NET. คุณสามารถปรับเปลี่ยนเส้นทาง, ชื่อ job, หรือรูปแบบผลลัพธ์ให้ตรงกับกระบวนการทำงานของคุณได้ตามต้องการ.

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.TeX 24.12 for .NET  
**Author:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
