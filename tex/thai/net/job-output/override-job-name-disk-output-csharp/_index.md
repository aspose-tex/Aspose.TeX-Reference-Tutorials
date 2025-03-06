---
title: แทนที่ชื่องานและเขียนเอาต์พุตเทอร์มินัลไปยังดิสก์ (C #)
linktitle: แทนที่ชื่องานและเขียนเอาต์พุตเทอร์มินัลไปยังดิสก์ (C #)
second_title: Aspose.TeX .NET API
description: สำรวจวิธีใช้ Aspose.TeX สำหรับ .NET เพื่อแทนที่ชื่องานและบันทึกเอาต์พุตเทอร์มินัล ปฏิบัติตามคำแนะนำที่ครอบคลุมของเราสำหรับการจัดการไฟล์ TeX ที่ราบรื่น
weight: 10
url: /th/net/job-output/override-job-name-disk-output-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แทนที่ชื่องานและเขียนเอาต์พุตเทอร์มินัลไปยังดิสก์ (C

## การแนะนำ

ยินดีต้อนรับสู่คำแนะนำทีละขั้นตอนเกี่ยวกับการใช้ Aspose.TeX สำหรับ .NET เพื่อแทนที่ชื่องานและเขียนเอาต์พุตเทอร์มินัลไปยังดิสก์ในภาษาการเขียนโปรแกรม C# Aspose.TeX สำหรับ .NET เป็นไลบรารีอันทรงพลังที่ช่วยให้คุณทำงานกับไฟล์ TeX ได้อย่างราบรื่น และในบทช่วยสอนนี้ เราจะเน้นที่งานเฉพาะ: การแทนที่ชื่องานและการบันทึกเอาต์พุตเทอร์มินัล

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  Aspose.TeX สำหรับไลบรารี .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.TeX สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์ Aspose.TeX](https://releases.aspose.com/tex/net/).

- สภาพแวดล้อมการพัฒนา .NET: มีสภาพแวดล้อมการพัฒนา .NET ที่ใช้งานได้ รวมถึงสภาพแวดล้อมการพัฒนาแบบรวม (IDE) เช่น Visual Studio

- ความรู้พื้นฐาน C#: ทำความคุ้นเคยกับพื้นฐานของภาษาการเขียนโปรแกรม C#

- ไดเรกทอรีอินพุตและเอาต์พุต: เตรียมไดเรกทอรีอินพุตและเอาต์พุตสำหรับไฟล์ TeX ของคุณ

## นำเข้าเนมสเปซ

ในโค้ด C# ของคุณ ตรวจสอบให้แน่ใจว่าได้รวมเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชัน Aspose.TeX:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

## ขั้นตอนที่ 1: สร้างตัวเลือกการแปลง

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

สร้าง TeXOptions ด้วย ConsoleAppOptions โดยระบุ ObjectTeX เป็น TeXConfig

## ขั้นตอนที่ 2: ระบุชื่องาน

```csharp
options.JobName = "overridden-job-name";
```

ระบุชื่องานเพื่อแทนที่ชื่อเริ่มต้น

## ขั้นตอนที่ 3: ระบุไดเรกทอรีการทำงานอินพุต

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

ตั้งค่าไดเร็กทอรีอินพุตสำหรับไฟล์ TeX ของคุณ

## ขั้นตอนที่ 4: ระบุไดเร็กทอรีการทำงานของเอาต์พุต

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

กำหนดไดเร็กทอรีการทำงานของเอาต์พุตเพื่อบันทึกไฟล์ TeX ที่ประมวลผล

## ขั้นตอนที่ 5: เขียนเอาต์พุตเทอร์มินัลไปยังดิสก์

```csharp
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

กำหนดค่าเอาต์พุตเทอร์มินัลที่จะเขียนลงในไฟล์ในไดเร็กทอรีเอาต์พุต

## ขั้นตอนที่ 6: รันงาน

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

สร้าง TeXJob โดยระบุชื่องาน อุปกรณ์เอาท์พุต (XpsDevice) และตัวเลือก สุดท้ายก็รันงาน

## บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีแทนที่ชื่องานและเขียนเอาต์พุตเทอร์มินัลไปยังดิสก์โดยใช้ Aspose.TeX สำหรับ .NET ใน C# เรียบร้อยแล้ว ความสามารถนี้มีคุณค่าสำหรับการจัดการงานประมวลผล TeX ของคุณอย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถใช้ Aspose.TeX สำหรับ .NET กับไลบรารี .NET อื่นๆ ได้หรือไม่

ตอบ 1: ได้ Aspose.TeX สำหรับ .NET สามารถรวมเข้ากับไลบรารี .NET อื่นๆ ได้อย่างราบรื่น

### คำถามที่ 2: Aspose.TeX สำหรับ .NET มีรุ่นทดลองใช้ฟรีหรือไม่

 A2: ได้ คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 3: ฉันจะรับการสนับสนุนสำหรับ Aspose.TeX สำหรับ .NET ได้อย่างไร

 A3: เยี่ยมชม[ฟอรั่ม Aspose.TeX](https://forum.aspose.com/c/tex/47) เพื่อรับชุมชนและการสนับสนุน

### คำถามที่ 4: Aspose.TeX สำหรับ .NET มีใบอนุญาตชั่วคราวหรือไม่

 A4: ได้ คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).

### คำถามที่ 5: ฉันจะหาเอกสารสำหรับ Aspose.TeX สำหรับ .NET ได้ที่ไหน

 A5: มีเอกสารประกอบให้[ที่นี่](https://reference.aspose.com/tex/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
