---
date: 2026-09-24
description: เรียนรู้วิธีกำหนดค่าไดเรกทอรีอินพุตของ TeX, streams, images, และ terminal
  input ด้วย Aspose.TeX สำหรับ .NET ใน C#.
keywords:
- configure tex input directory
- add image stream tex
- add images from stream
lastmod: 2026-09-24
linktitle: ขั้นสูง Aspose.TeX Input and Output
og_description: กำหนดค่าไดเรกทอรีอินพุตของ TeX, เพิ่ม image streams, และจัดการ terminal
  input ด้วย Aspose.TeX สำหรับ .NET ใน C#. เรียนรู้แบบ step‑by‑step.
og_image_alt: Guide showing how to configure TeX input directory and streams in Aspose.TeX
  for .NET
og_title: กำหนดค่าไดเรกทอรีอินพุตของ TeX – ขั้นสูง Aspose.TeX guide
schemas:
- author: Aspose
  dateModified: '2026-09-24'
  description: Learn how to configure TeX input directory, streams, images, and terminal
    input using Aspose.TeX for .NET in C#.
  headline: Configure TeX input directory – Advanced Aspose.TeX Input and Output
  type: TechArticle
- description: Learn how to configure TeX input directory, streams, images, and terminal
    input using Aspose.TeX for .NET in C#.
  name: Configure TeX input directory – Advanced Aspose.TeX Input and Output
  steps:
  - name: instantiate TeXInputOptions
    text: Assign the base folder that holds the primary TeX source.
  - name: add extra search paths
    text: If your project stores figures in a separate folder (e.g., *Images*), call
      `AddSearchPath` to include it.
  - name: hand the options to the processor
    text: Create a `TeXProcessor`, provide the configured options, and invoke `Process`
      or `Render`.
  type: HowTo
- questions:
  - answer: Yes—you can create a new `TeXInputOptions` instance with a different `BaseFolder`
      and pass it to a fresh `TeXProcessor` whenever you need to reconfigure.
    question: Can I change the input directory at runtime?
  - answer: Retrieve the image as a `byte[]`, wrap it in a `MemoryStream`, and call
      `TeXInputOptions.AddImage("image.png", stream)`. The name must match the reference
      in your `.tex` file.
    question: How do I add images that are stored in a database?
  - answer: Absolutely. Convert the incoming string to a `MemoryStream`, set it as
      the source for `TeXProcessor`, and render directly to your desired output format.
    question: Is it possible to process LaTeX code received from a web API without
      saving a file?
  - answer: Dispose of any streams you create, and for large workloads invoke `TeXProcessor.Cleanup()`
      to free native resources.
    question: Do I need to call any cleanup methods after processing?
  - answer: The two tutorial links above contain full code samples that demonstrate
      each scenario in detail, including error handling and performance tips.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.TeX .NET API
tags:
- Aspose.TeX
- input directory
- C# document processing
title: กำหนดค่าไดเรกทอรีอินพุตของ TeX – ขั้นสูง Aspose.TeX Input and Output
url: /th/net/advanced-io/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# กำหนดค่าไดเรกทอรีอินพุต TeX ใน Aspose.TeX สำหรับ .NET

Aspose.TeX for .NET ให้คุณฝังการประมวลผล TeX แบบเต็มคุณลักษณะโดยตรงในแอปพลิเคชัน C# ของคุณ ในบทแนะนำนี้คุณจะได้เรียนรู้วิธี **กำหนดค่าไดเรกทอรีอินพุต TeX**, ป้อนเนื้อหา LaTeX จากสตรีม, และเพิ่มรูปภาพโดยไม่ต้องสัมผัสระบบไฟล์ หากคุณต้องการควบคุมอย่างแม่นยำว่าตัวประมวลผลมองหาไฟล์ `.tex` และทรัพยากรที่ไหน คุณมาถูกที่แล้ว

## คำตอบด่วน
- **“configure tex input directory” หมายถึงอะไร?**  
  บอก Aspose.TeX ว่าจะหาไฟล์ `.tex` หลัก, ไฟล์ช่วยเหลือ, และกราฟิกได้จากที่ไหน
- **คลาสใดกำหนดเส้นทางอินพุต?**  
  `TeXInputOptions` เก็บโฟลเดอร์ฐานและตำแหน่งค้นหาเพิ่มเติมใด ๆ
- **ฉันสามารถโหลดรูปภาพจาก memory stream ได้หรือไม่?**  
  ได้—ใช้ `TeXInputOptions.AddImage` พร้อมอินสแตนซ์ `Stream`
- **สามารถคอมไพล์โค้ด LaTeX ที่ให้มาที่ runtime ได้หรือไม่?**  
  แน่นอน—ส่ง `MemoryStream` ที่มีข้อความต้นฉบับไปยังตัวประมวลผล
- **ต้องการใบอนุญาตสำหรับการใช้งานในผลิตจริงหรือไม่?**  
  ต้องมีใบอนุญาต Aspose.TeX ที่ถูกต้องสำหรับการใช้งานที่ไม่ใช่การประเมินผล

## TeXInputOptions คืออะไร?
`TeXInputOptions` เป็นอ็อบเจ็กต์การกำหนดค่าที่กำหนดโฟลเดอร์ฐานและเส้นทางค้นหาเพิ่มเติมสำหรับทรัพยากร TeX การตั้งค่าอย่างถูกต้องจะขจัดข้อผิดพลาด “file not found” และทำให้คุณจัดการสินทรัพย์ได้อย่างเป็นระเบียบ

## วิธีกำหนดค่าไดเรกทอรีอินพุต tex?
`TeXInputOptions` เป็นอ็อบเจ็กต์การกำหนดค่าที่ระบุโฟลเดอร์ฐานและเส้นทางค้นหาเพิ่มเติมสำหรับทรัพยากร TeX โหลดเอกสารหลักของคุณและบอกตัวประมวลผลให้มองหาทุกอย่างในไม่กี่บรรทัด คำตอบโดยตรงนี้อธิบายขั้นตอนสำคัญก่อนรายละเอียดเพิ่มเติมใด ๆ

สร้างอินสแตนซ์ `TeXInputOptions`, ตั้งค่า `BaseFolder` ให้เป็นโฟลเดอร์ที่มีไฟล์ `.tex` หลักของคุณ, เพิ่มโฟลเดอร์ย่อยใด ๆ ที่เก็บรูปภาพหรือไฟล์ช่วยเหลือ, แล้วส่งตัวเลือกไปยัง `TeXProcessor` ตัวประมวลผลจะทำการแก้ไขการอ้างอิงเชิงสัมพันธ์ทั้งหมดโดยอัตโนมัติ

### ขั้นตอนที่ 1: สร้างอินสแตนซ์ TeXInputOptions
กำหนดโฟลเดอร์ฐานที่เก็บซอร์ส TeX หลัก

### ขั้นตอนที่ 2: เพิ่มเส้นทางค้นหาเพิ่มเติม
หากโครงการของคุณเก็บรูปภาพในโฟลเดอร์แยก (เช่น *Images*), เรียก `AddSearchPath` เพื่อรวมโฟลเดอร์นั้น

### ขั้นตอนที่ 3: ส่งตัวเลือกไปยังตัวประมวลผล
สร้าง `TeXProcessor`, ให้ตัวเลือกที่กำหนดค่าแล้ว, แล้วเรียก `Process` หรือ `Render`

## วิธีเพิ่มรูปภาพด้วย Aspose.TeX
รูปภาพที่อ้างอิงในไฟล์ TeX สามารถจัดหาได้ทั้งจากโฟลเดอร์หรือโดยตรงจากสตรีม การจัดหาผ่านสตรีมเป็นประโยชน์เมื่อรูปภาพถูกเก็บในฐานข้อมูลหรือสร้างแบบเรียลไทม์ `AddImage(string name, Stream data)` ลงทะเบียนสตรีมรูปภาพด้วยชื่อไฟล์ที่กำหนดเพื่อใช้ในเอกสาร TeX วิธีนี้ช่วยให้คุณหลีกเลี่ยงไฟล์ชั่วคราวและเร่งการประมวลผล

## วิธีประมวลผลสตรีมใน Aspose.TeX
เมื่อซอร์ส LaTeX ของคุณถูกสร้างแบบไดนามิก—อาจมาจากการป้อนข้อมูลของผู้ใช้หรือเว็บเซอร์วิส—คุณสามารถป้อนตรงไปยังตัวประมวลผลโดยไม่ต้องเขียนไฟล์ `TeXProcessor` ประมวลผลเนื้อหา TeX และสามารถรับ `MemoryStream` ที่มีโค้ด LaTeX ต้นฉบับได้ ห่อสตริง LaTeX ใน `MemoryStream`, ตั้งเป็นสตรีมต้นทางใน `TeXProcessor`, แล้วรันการแปลง เทคนิคนี้ทำงานได้ดีเช่นเดียวกับบริการคลาวด์‑เนทีฟที่การอ่าน/เขียนดิสก์มีค่าใช้จ่ายสูง

## ทำไมต้องใช้ Aspose.TeX สำหรับ I/O ขั้นสูง?
Aspose.TeX รองรับ **รูปแบบอินพุตและเอาต์พุตกว่า 30+** (รวมถึง PDF, PNG, SVG) และสามารถเรนเดอร์เอกสารหลายร้อยหน้าโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ การออกแบบแบบ stream‑first ลดภาระ I/O ได้ถึง 40 % เมื่อเทียบกับเวิร์กโฟลว์ที่อิงไฟล์ ทำให้เหมาะสำหรับแอปพลิเคชันเซิร์ฟเวอร์ที่ต้องการประมวลผลสูง

## ข้อกำหนดเบื้องต้น
- .NET 6.0 หรือใหม่กว่า (ไลบรารีนี้ยังทำงานกับ .NET Core 3.1+ และ .NET Framework 4.6.1+)
- แพคเกจ NuGet Aspose.TeX for .NET (เวอร์ชัน 24.11 หรือใหม่กว่า)
- ใบอนุญาต Aspose.TeX ที่ถูกต้องสำหรับการใช้งานในผลิตจริง

## สำรวจ Aspose.TeX: ประตูสู่การประมวลผลเอกสารขั้นสูง
เพื่อดูการกำหนดค่าในงานจริง ให้ทำตามคู่มือขั้นตอน‑ต่อ‑ขั้นตอนของเรา **[ระบุไดเรกทอรีอินพุตที่จำเป็นสำหรับ Aspose.TeX (C#)](./required-input-directory-csharp/)**. บทแนะนำนั้นจะพาคุณผ่านการสร้างอ็อบเจ็กต์ `TeXInputOptions` และการเรนเดอร์ผลลัพธ์ PDF.  
**[ระบุไดเรกทอรีอินพุตที่จำเป็นสำหรับ Aspose.TeX (C#)](./required-input-directory-csharp/)**

## เชี่ยวชาญสตรีม, รูปภาพ, และการป้อนข้อมูลแบบเทอร์มินัลใน Aspose.TeX สำหรับ C#
สำหรับการเจาะลึกการป้อน LaTeX จากหน่วยความจำ, การเพิ่มรูปภาพผ่านสตรีม, และการใช้การป้อนข้อมูลแบบเทอร์มินัล, ดูที่ **[เชี่ยวชาญสตรีม, รูปภาพ, และการป้อนข้อมูลแบบเทอร์มินัลใน Aspose.TeX สำหรับ C#](./stream-input-image-output-terminal-input-csharp/)**. มันแสดงวิธีรวม Aspose.TeX เข้ากับเว็บ API, บริการเบื้องหลัง, และเครื่องมือคอนโซล.  
**[เชี่ยวชาญสตรีม, รูปภาพ, และการป้อนข้อมูลแบบเทอร์มินัลใน Aspose.TeX สำหรับ C#](./stream-input-image-output-terminal-input-csharp/)**

## ปัญหาทั่วไปและวิธีแก้
- **ข้อผิดพลาด “File not found”** – ตรวจสอบว่า `BaseFolder` ชี้ไปยังไดเรกทอรีที่ถูกต้องและเส้นทางค้นหาเพิ่มเติมใด ๆ ถูกเพิ่มก่อนการเรนเดอร์
- **รูปภาพไม่โหลด** – ตรวจสอบว่าชื่อรูปภาพใน `AddImage` ตรงกับชื่อที่ใช้ในซอร์ส TeX อย่างแม่นยำ รวมทั้งนามสกุลไฟล์
- **การใช้หน่วยความจำพุ่งสูง** – เมื่อประมวลผลเอกสารขนาดใหญ่มาก, เรียก `TeXProcessor.Cleanup()` หลังการเรนเดอร์เพื่อปล่อยทรัพยากรที่ไม่ได้จัดการ

## คำถามที่พบบ่อย

**Q: ฉันสามารถเปลี่ยนไดเรกทอรีอินพุตใน runtime ได้หรือไม่?**  
A: ใช่—คุณสามารถสร้างอินสแตนซ์ `TeXInputOptions` ใหม่ที่มี `BaseFolder` แตกต่างและส่งไปยัง `TeXProcessor` ใหม่ทุกครั้งที่ต้องการกำหนดค่าใหม่

**Q: ฉันจะเพิ่มรูปภาพที่เก็บในฐานข้อมูลอย่างไร?**  
A: ดึงรูปภาพเป็น `byte[]`, ห่อไว้ใน `MemoryStream`, แล้วเรียก `TeXInputOptions.AddImage("image.png", stream)`. ชื่อต้องตรงกับการอ้างอิงในไฟล์ `.tex` ของคุณ

**Q: สามารถประมวลผลโค้ด LaTeX ที่ได้รับจากเว็บ API โดยไม่บันทึกไฟล์ได้หรือไม่?**  
A: แน่นอน. แปลงสตริงที่เข้ามาเป็น `MemoryStream`, ตั้งเป็นแหล่งข้อมูลสำหรับ `TeXProcessor`, และเรนเดอร์โดยตรงไปยังรูปแบบเอาต์พุตที่ต้องการ

**Q: ฉันต้องเรียกเมธอดทำความสะอาดใด ๆ หลังการประมวลผลหรือไม่?**  
A: ปิดการใช้งานสตรีมใด ๆ ที่คุณสร้าง, และสำหรับงานที่มีขนาดใหญ่ให้เรียก `TeXProcessor.Cleanup()` เพื่อปล่อยทรัพยากรเนทีฟ

**Q: ฉันจะหา ตัวอย่างขั้นสูงเพิ่มเติมได้จากที่ไหน?**  
A: ลิงก์บทแนะนำสองลิงก์ด้านบนมีตัวอย่างโค้ดเต็มที่แสดงแต่ละสถานการณ์อย่างละเอียด รวมถึงการจัดการข้อผิดพลาดและเคล็ดลับประสิทธิภาพ

---

**อัปเดตล่าสุด:** 2026-09-24  
**ทดสอบด้วย:** Aspose.TeX 24.11 for .NET  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [รับสตรีมไฟล์ TeX (C#) โดยใช้ Aspose.TeX API ไดเรกทอรีอินพุตที่จำเป็น](/tex/net/advanced-io/required-input-directory-csharp/)
- [สร้าง XPS จาก TeX ด้วย Filesystems – Aspose.TeX for .NET](/tex/net/file-input-output/filesystem-input-xps-output/)
- [แปลง LaTeX เป็น PNG ด้วย Aspose.TeX for .NET – ประมวลผลไฟล์ระบบและอินพุต ZIP](/tex/net/file-input-output/required-inputs-from-filesystem-and-zip/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}