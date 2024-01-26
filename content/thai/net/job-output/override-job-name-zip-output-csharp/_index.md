---
title: แทนที่ชื่องานและเขียนเอาต์พุตเทอร์มินัลเป็น Zip (C#)
linktitle: แทนที่ชื่องานและเขียนเอาต์พุตเทอร์มินัลเป็น Zip (C#)
second_title: Aspose.TeX .NET API
description: เรียนรู้วิธีแทนที่ชื่องานและเขียนเอาต์พุตเทอร์มินัลไปยังไฟล์ ZIP โดยใช้ Aspose.TeX สำหรับ .NET คำแนะนำทีละขั้นตอนพร้อมตัวอย่าง C#
type: docs
weight: 11
url: /th/net/job-output/override-job-name-zip-output-csharp/
---
## การแนะนำ

ในบทช่วยสอนนี้ เราจะสำรวจวิธีแทนที่ชื่องานและเขียนเอาต์พุตเทอร์มินัลไปยังไฟล์ ZIP โดยใช้ Aspose.TeX สำหรับ .NET Aspose.TeX เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถทำงานกับเอกสาร TeX ในแอปพลิเคชัน .NET ของตนได้ ในตัวอย่างนี้ เราจะเน้นไปที่งานทั่วไป นั่นคือการเขียนเอาต์พุตเทอร์มินัลไปยังไฟล์ ZIP ที่สามารถแทนที่ชื่องานได้

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ความรู้เกี่ยวกับการทำงานของ C#
- ติดตั้ง Aspose.TeX สำหรับ .NET แล้ว
- อินพุตไฟล์ ZIP สำหรับไดเร็กทอรีการทำงาน
- ไฟล์ ZIP เอาต์พุตสำหรับเอาต์พุตเทอร์มินัล

## นำเข้าเนมสเปซ

ก่อนที่จะเจาะลึกโค้ด ตรวจสอบให้แน่ใจว่าได้รวมเนมสเปซที่จำเป็นในโปรเจ็กต์ C# ของคุณ:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Pdf;
using System.IO;
```

ตอนนี้ เราจะแบ่งตัวอย่างออกเป็นหลายขั้นตอนเพื่อแนะนำคุณตลอดกระบวนการ

## ขั้นตอนที่ 1: เปิดสตรีม ZIP อินพุตและเอาต์พุต

```csharp
using (Stream inZipStream = File.Open(Path.Combine("Your Input Directory", "zip-in.zip"), FileMode.Open))
using (Stream outZipStream = File.Open(Path.Combine("Your Output Directory", "terminal-out-to-zip.zip"), FileMode.Create))
{
    // รหัสสำหรับขั้นตอนที่ 1 อยู่ที่นี่
}
```

## ขั้นตอนที่ 2: ตั้งค่าตัวเลือกการแปลง

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
options.JobName = "terminal-output-to-zip";
options.InputWorkingDirectory = new InputZipDirectory(inZipStream, "in");
options.OutputWorkingDirectory = new OutputZipDirectory(outZipStream);
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## ขั้นตอนที่ 3: กำหนดตัวเลือกการบันทึก

```csharp
options.SaveOptions = new PdfSaveOptions();
```

## ขั้นตอนที่ 4: รันงาน TeX

```csharp
new TeXJob("hello-world", new PdfDevice(), options).Run();
```

## ขั้นตอนที่ 5: จบไฟล์ ZIP เอาท์พุต

```csharp
((OutputZipDirectory)options.OutputWorkingDirectory).Finish();
```

## บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีแทนที่ชื่องานและเขียนเอาต์พุตเทอร์มินัลไปยังไฟล์ ZIP โดยใช้ Aspose.TeX สำหรับ .NET เรียบร้อยแล้ว เทคนิคนี้มีประโยชน์อย่างเหลือเชื่อเมื่อต้องจัดการกับเอกสาร TeX ในแอปพลิเคชัน C# ของคุณ

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถใช้ Aspose.TeX สำหรับ .NET กับภาษา .NET อื่นๆ เช่น VB.NET ได้หรือไม่

ตอบ 1: ใช่ Aspose.TeX สำหรับ .NET เข้ากันได้กับภาษา .NET ทั้งหมด

### คำถามที่ 2: ฉันจะหาเอกสารเพิ่มเติมเกี่ยวกับ Aspose.TeX สำหรับ .NET ได้ที่ไหน

 A2: เยี่ยมชม[เอกสารประกอบ](https://reference.aspose.com/tex/net/) สำหรับข้อมูลโดยละเอียด

### คำถามที่ 3: ฉันจะรับใบอนุญาตชั่วคราวสำหรับ Aspose.TeX ได้อย่างไร

 A3: ได้รับ[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) เพื่อวัตถุประสงค์ในการทดสอบ

### คำถามที่ 4: มีฟอรัมชุมชนสำหรับการสนับสนุน Aspose.TeX หรือไม่

 A4: ใช่ เข้าร่วม[ฟอรั่ม Aspose.TeX](https://forum.aspose.com/c/tex/47) เพื่อสนับสนุนชุมชน

### คำถามที่ 5: ฉันจะซื้อ Aspose.TeX สำหรับ .NET ได้ที่ไหน

 A5: คุณสามารถซื้อ Aspose.TeX ได้[ที่นี่](https://purchase.aspose.com/buy).