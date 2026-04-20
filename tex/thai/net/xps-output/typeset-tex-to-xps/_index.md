---
date: 2025-12-30
description: เรียนรู้วิธีแปลง TeX เป็น XPS ใน .NET ด้วย Aspose.TeX ปฏิบัติตามคู่มือขั้นตอนต่อขั้นตอนนี้เพื่อการบูรณาการที่ราบรื่นและผลลัพธ์ที่เชื่อถือได้.
linktitle: How to Convert TeX to XPS in .NET
second_title: Aspose.TeX .NET API
title: วิธีแปลง TeX เป็น XPS ใน .NET
url: /th/net/xps-output/typeset-tex-to-xps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีแปลง TeX เป็น XPS ใน .NET

## วิธีแปลง TeX เป็น XPS – บทนำ

ยินดีต้อนรับสู่คู่มือที่ครอบคลุมและเป็นขั้นตอนของเราเกี่ยวกับ **วิธีแปลง TeX** เอกสารเป็นรูปแบบ XPS ภายในสภาพแวดล้อม .NET โดยใช้ไลบรารี Aspose.TeX ที่ทรงพลัง คุณจะสามารถรวมการแปลง TeX‑to‑XPS เข้าไปในแอปพลิเคชัน .NET ใดก็ได้—ไม่ว่าจะเป็นเครื่องมือเดสก์ท็อป, บริการเว็บ, หรือกระบวนการรายงานอัตโนมัติ ในส่วนต่อไปนี้เราจะเดินผ่านการตั้งค่าที่จำเป็นทั้งหมด, แสดงโค้ดที่คุณต้องการ, และอธิบายว่าทำไมแต่ละส่วนจึงสำคัญ เพื่อให้คุณสามารถนำโซลูชันไปใช้ได้อย่างมั่นใจ.

## คำตอบอย่างรวดเร็ว
- **บทเรียนนี้ครอบคลุมอะไร?** การแปลงไฟล์ TeX เป็น XPS ด้วย Aspose.TeX สำหรับ .NET.  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **ฉันต้องการไลเซนส์หรือไม่?** การทดลองใช้ฟรีทำงานสำหรับการทดสอบ; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **การดำเนินการใช้เวลานานเท่าไหร่?** ปกติใช้เวลาน้อยกว่า 15 นาทีสำหรับการแปลงพื้นฐาน.  
- **ฉันสามารถดาวน์โหลดไลบรารีได้จากที่ไหน?** ดาวน์โหลดจากหน้าเผยแพร่อย่างเป็นทางการของ Aspose.TeX.

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะลงลึกในบทเรียนนี้, โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้พร้อมใช้งาน:

- Aspose.TeX สำหรับ .NET: ตรวจสอบว่าคุณได้ติดตั้งไลบรารี Aspose.TeX แล้ว คุณสามารถดาวน์โหลดได้ [here](https://releases.aspose.com/tex/net/).
- เอกสารประกอบ: ทำความคุ้นเคยกับไลบรารีโดยอ้างอิงเอกสาร [here](https://reference.aspose.com/tex/net/).
- โฟลเดอร์อินพุตและเอาต์พุต: ตั้งค่าโฟลเดอร์อินพุตและเอาต์พุตของคุณตามที่ระบุในโค้ดตัวอย่าง.

เมื่อคุณได้ตั้งค่าทุกอย่างเรียบร้อยแล้ว, ไปต่อกับคู่มือแบบขั้นตอนต่อขั้นตอนกันเถอะ.

## นำเข้า Namespaces

ในแอปพลิเคชัน .NET ของคุณ, เริ่มต้นด้วยการนำเข้า namespaces ที่จำเป็น ซึ่งจะทำให้คุณเข้าถึงฟังก์ชันของ Aspose.TeX ที่ต้องใช้สำหรับการจัดรูปแบบ TeX เป็น XPS.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
```

## ขั้นตอนที่ 1: ตั้งค่าตัวเลือกการแปลง

กำหนดตัวเลือกการแปลงโดยระบุรูปแบบ ObjectTeX บนส่วนขยายของเอนจิน ObjectTeX นอกจากนี้ยังตั้งชื่องาน, โฟลเดอร์อินพุตและเอาต์พุต, และรายละเอียดการแสดงผลเทอร์มินัล.

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

## ขั้นตอนที่ 2: สร้างสตรีมเอกสาร XPS

เปิดสตรีมเพื่อเขียนเอกสาร XPS ที่จัดรูปแบบแล้ว ชื่อไฟล์ไม่จำเป็นต้องเหมือนกับชื่องาน.

```csharp
using (Stream stream = File.Open(Path.Combine("Your Output Directory", options.JobName + ".xps"), FileMode.Create))
```

## ขั้นตอนที่ 3: รันงาน TeX

เริ่มต้นและรันงาน TeX โดยระบุชื่อเอกสาร, XpsDevice, และตัวเลือกการแปลง.

```csharp
new TeXJob("hello-world", new XpsDevice(stream), options).Run();
```

ยินดีด้วย! คุณได้จัดรูปแบบ TeX เป็น XPS ใน .NET ด้วย Aspose.TeX อย่างสำเร็จแล้ว อย่าลังเลที่จะสำรวจคุณลักษณะและตัวเลือกเพิ่มเติมตามความต้องการของคุณ.

## สรุป

ในบทเรียนนี้ เราได้ครอบคลุมขั้นตอนสำคัญเพื่อแปลงเอกสาร TeX เป็นรูปแบบ XPS ใน .NET อย่างราบรื่นด้วย Aspose.TeX โดยการทำตามคู่มือนี้ คุณจะได้รับความเข้าใจที่มีค่าเกี่ยวกับความสามารถของไลบรารีและวิธีนำไปใช้ในโครงการของคุณ.

## คำถามที่พบบ่อย

### Q1: Aspose.TeX รองรับ .NET Core หรือไม่?
A1: ใช่, Aspose.TeX รองรับ .NET Core อย่างเต็มที่.

### Q2: ฉันสามารถใช้ Aspose.TeX ในโครงการเชิงพาณิชย์ได้หรือไม่?
A2: แน่นอน! Aspose.TeX มีให้ใช้ทั้งเชิงพาณิชย์และส่วนบุคคล.

### Q3: ฉันสามารถหา ตัวอย่างและแหล่งข้อมูลเพิ่มเติมได้จากที่ไหน?
A3: สำรวจเอกสาร Aspose.TeX [here](https://reference.aspose.com/tex/net/) เพื่อดูตัวอย่างและแหล่งข้อมูลโดยละเอียดเพิ่มเติม.

### Q4: ฉันจะรับการสนับสนุนสำหรับ Aspose.TeX อย่างไร?
A4: เยี่ยมชมฟอรั่มสนับสนุน Aspose.TeX [here](https://forum.aspose.com/c/tex/47) เพื่อรับความช่วยเหลือจากชุมชน.

### Q5: มีการทดลองใช้ฟรีหรือไม่?
A5: ใช่, คุณสามารถเข้าถึงการทดลองใช้ฟรีได้ [here](https://releases.aspose.com/).

## คำถามที่พบบ่อยเพิ่มเติม

**Q: ฉันสามารถปรับแต่งผลลัพธ์ XPS (เช่น ขนาดหน้า หรือขอบเขต) ได้หรือไม่?**  
**A:** ได้. คุณสามารถปรับการตั้งค่า XpsDevice หรือแก้ไขโค้ดต้นฉบับ TeX เพื่อควบคุมการจัดหน้า ก่อนทำการแปลง.

**Q: อะไรจะเกิดขึ้นหากไฟล์ TeX อินพุตมีข้อผิดพลาด?**  
**A:** กระบวนการแปลงจะเขียนรายละเอียดข้อผิดพลาดลงในไฟล์ผลลัพธ์เทอร์มินัล (`*.trm`). ตรวจสอบไฟล์นี้เพื่อวินิจฉัยและแก้ไขปัญหา.

**Q: สามารถแปลงไฟล์ TeX หลายไฟล์ในรอบเดียวได้หรือไม่?**  
**A:** คุณสามารถวนลูปผ่านชุดไฟล์ต้นฉบับ TeX, สร้าง TeXJob แยกสำหรับแต่ละไฟล์โดยใช้ `TeXOptions` ตัวเดียวกัน.

**Q: Aspose.TeX รองรับแพคเกจ LaTeX เช่น `amsmath` หรือ `graphicx` หรือไม่?**  
**A:** แพคเกจ LaTeX มาตรฐานส่วนใหญ่ได้รับการสนับสนุน ตรวจสอบเอกสารอย่างเป็นทางการเพื่อดูรายการเต็มของแพคเกจที่เข้ากันได้.

**Q: ฉันจะฝังฟอนต์ในไฟล์ XPS ที่สร้างขึ้นอย่างไร?**  
**A:** Aspose.TeX จะฝังฟอนต์ที่ใช้โดยเอนจิน TeX โดยอัตโนมัติ ตรวจสอบให้แน่ใจว่าฟอนต์ที่จำเป็นได้ถูกติดตั้งบนเครื่องที่ทำการแปลง.

---

**อัปเดตล่าสุด:** 2025-12-30  
**ทดสอบด้วย:** Aspose.TeX for .NET 24.11  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}