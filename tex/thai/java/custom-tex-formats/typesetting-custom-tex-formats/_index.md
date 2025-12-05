---
date: 2025-12-05
description: เรียนรู้วิธีการจัดรูปแบบ TeX ด้วย Aspose.TeX สำหรับ Java รวมถึงขั้นตอนการสร้างรูปแบบกำหนดเองและวิธีการขอรับใบอนุญาตชั่วคราวของ
  Aspose.
language: th
linktitle: How to Typeset TeX with Custom Formats in Java
second_title: Aspose.TeX Java API
title: วิธีจัดรูปแบบ TeX ด้วยรูปแบบกำหนดเองใน Java
url: /java/custom-tex-formats/typesetting-custom-tex-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการจัดรูป TeX ด้วยรูปแบบกำหนดเองใน Java

## บทนำ

หากคุณต้องการ **how to typeset tex** ภายในแอปพลิเคชัน Java, Aspose.TeX ให้วิธีที่สะอาดและมีประสิทธิภาพสูงในการทำงานกับไฟล์รูปแบบ TeX กำหนดเอง ในบทแนะนำนี้เราจะพาคุณผ่านทุกขั้นตอนที่ต้องการ—ตั้งแต่การตั้งค่าสภาพแวดล้อมจนถึงการรันงาน TeX ที่ใช้รูปแบบของคุณเอง ไม่ว่าคุณจะกำลังสร้างเครื่องมือการเผยแพร่ทางวิทยาศาสตร์หรือเครื่องมือสร้างรายงานแบบกำหนดเอง ขั้นตอนต่อไปนี้จะช่วยให้คุณเริ่มต้นได้อย่างรวดเร็ว

## คำตอบสั้น

- **คุณต้องการไลบรารีอะไร?** Aspose.TeX for Java  
- **ฉันสามารถใช้รูปแบบ TeX กำหนดเองได้หรือไม่?** ใช่ – เพียงชี้ `FormatProvider` ไปยังไฟล์ของคุณ  
- **ฉันต้องการไลเซนส์สำหรับการพัฒนาหรือไม่?** ไลเซนส์ชั่วคราว aspose ใช้สำหรับการทดสอบ; จำเป็นต้องมีไลเซนส์เต็มสำหรับการใช้งานจริง  
- **เวอร์ชัน Java ที่รองรับคืออะไร?** JDK 8 หรือสูงกว่า  
- **รูปแบบผลลัพธ์ที่ตัวอย่างสร้างคืออะไร?** XPS (คุณสามารถเปลี่ยนเป็น PDF, PNG ฯลฯ ได้)

## รูปแบบ TeX กำหนดเองคืออะไร?

รูปแบบ TeX กำหนดเองคือชุดแมโครและ primitive ที่คอมไพล์ล่วงหน้าเพื่อปรับแต่งเอนจิน TeX ให้สอดคล้องกับสไตล์เอกสารของคุณโดยเฉพาะ การจัดหาไฟล์ `.fmt` ของคุณเองทำให้คุณควบคุมฟอนต์, กฎการจัดหน้า, และการกำหนดคำสั่งได้โดยไม่ต้องแก้ไขโค้ด TeX ต้นฉบับทุกครั้ง

## ทำไมต้องใช้ Aspose.TeX สำหรับ Java?

- **Pure Java** – ไม่มีไบนารีเนทีฟ, ฝังง่ายในโครงการที่ใช้ JVM ใดก็ได้  
- **High fidelity** – สร้างผลลัพธ์ที่ตรงกับการแสดงผลสไตล์ LaTeX  
- **Extensible** – รองรับรูปแบบกำหนดเอง, อุปกรณ์ผลลัพธ์หลายประเภท, และการประมวลผลเป็นชุด  
- **License flexibility** – เริ่มต้นด้วยไลเซนส์ชั่วคราว aspose, แล้วอัปเกรดเมื่อเปิดใช้งานจริง  

## ข้อกำหนดเบื้องต้น

1. **Java Development Kit (JDK)** – JDK 8 หรือใหม่กว่า ติดตั้งแล้ว ดาวน์โหลดจากเว็บไซต์อย่างเป็นทางการ [Java website](https://www.oracle.com/java/technologies/javase-downloads.html) หากยังไม่ได้  
2. **Aspose.TeX library for Java** – ดาวน์โหลด JAR ล่าสุดจาก [Aspose.TeX for Java download page](https://releases.aspose.com/tex/java/)  
3. **ไฟล์รูปแบบ TeX กำหนดเองของคุณ** – วางไฟล์ `.fmt` ที่คอมไพล์แล้ว (เช่น `customtex.fmt`) ในโฟลเดอร์ที่จะเป็นไดเรกทอรีผลลัพธ์  

> **เคล็ดลับ:** หากคุณกำลังประเมินผลิตภัณฑ์, ขอ *temporary license aspose* จากพอร์ทัลของ Aspose; จะลบลายน้ำการประเมินออกในช่วงเวลาจำกัด

## นำเข้าแพ็กเกจ

ก่อนอื่นให้เพิ่มการนำเข้าที่จำเป็นลงในโครงการ Java ของคุณ คลาสเหล่านี้ให้คุณเข้าถึง FormatProvider, การกำหนดค่างาน, และอุปกรณ์การเรนเดอร์

```java
package com.aspose.tex.TypesetWithCustomTeXFormat;

import java.io.ByteArrayInputStream;
import java.io.IOException;

import com.aspose.tex.FormatProvider;
import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

## คู่มือขั้นตอนต่อขั้นตอน

### ขั้นตอนที่ 1: สร้าง Format Provider

`FormatProvider` ชี้ไปยังไดเรกทอรีที่มีไฟล์รูปแบบ TeX กำหนดเองของคุณ แทนที่ `"Your Output Directory"` ด้วยพาธจริงที่ไฟล์ `customtex.fmt` อยู่

```java
final FormatProvider formatProvider = new FormatProvider(
        new InputFileSystemDirectory("Your Output Directory"), "customtex");
```

### ขั้นตอนที่ 2: ตั้งค่าตัวเลือกการแปลง

กำหนดค่างานให้ใช้เอนจิน ObjectTeX (เอนจินที่เข้าใจรูปแบบกำหนดเอง) ที่นี่เรายังตั้งชื่องานและระบุไดเรกทอรีทำงานสำหรับอินพุต/เอาต์พุตด้วย

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX(formatProvider));
options.setJobName("typeset-with-custom-format");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### ขั้นตอนที่ 3: รันงาน TeX

สร้างอินสแตนซ์ `TeXJob`, ป้อนสคริปต์ TeX ง่าย ๆ ให้มัน, แล้วบอกให้เรนเดอร์ผลลัพธ์ด้วย `XpsDevice` สคริปต์จะจบด้วย `\end` เพื่อปิดเอกสาร

```java
new TeXJob(new ByteArrayInputStream(
        "Congratulations! You have successfully typeset this text with your own TeX format!\\end".getBytes("ASCII")),
        new XpsDevice(), options).run();
```

### ขั้นตอนที่ 4: สรุปผลลัพธ์

หลังจากงานเสร็จสิ้น ให้เพิ่มการขึ้นบรรทัดใหม่ในเอาต์พุตของเทอร์มินัลเพื่อให้คอนโซลดูเป็นระเบียบ

```java
options.getTerminalOut().getWriter().newLine();
```

### ขั้นตอนที่ 5: ปิด Format Provider

เมื่อทำงานเสร็จแล้ว ปิด provider เพื่อปล่อยไฟล์แฮนด์เดิลและคืนทรัพยากร

```java
formatProvider.close();
```

## ปัญหาที่พบบ่อยและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|--------|
| **“Format file not found”** | พาธผิดใน `FormatProvider` | ตรวจสอบว่าไดเรกทอรีและชื่อไฟล์ (`customtex.fmt`) ถูกต้องและเข้าถึงได้ |
| **Encoding errors** | ตัวอักษรที่ไม่ใช่ ASCII ในสตริง TeX | ใช้การเข้ารหัส UTF‑8 (`"UTF-8"` แทน `"ASCII"`) |
| **Output not generated** | ไดเรกทอรีผลลัพธ์ไม่มีสิทธิ์เขียน | ตรวจสอบให้กระบวนการ Java มีสิทธิ์เขียนใน `"Your Output Directory"` |
| **License watermark** | ใช้ไลเซนส์ประเมินเท่านั้น | ใช้ *temporary license aspose* สำหรับการทดสอบหรือซื้อไลเซนส์เต็มสำหรับการใช้งานจริง |

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ Aspose.TeX ร่วมกับไลบรารี Java อื่น ๆ ได้หรือไม่?**  
A: แน่นอน. API เป็น Pure Java ทำงานร่วมกับไลบรารีเช่น Apache PDFBox, iText, หรือ Spring Boot ได้อย่างไม่มีปัญหา  

**Q: ฉันจะหาลิขสิทธิ์ชั่วคราว aspose สำหรับการประเมินได้จากที่ไหน?**  
A: ขอได้จาก [Aspose temporary license page](https://purchase.aspose.com/temporary-license/) ซึ่งจะลบลายน้ำการประเมินออกได้สูงสุด 30 วัน  

**Q: Aspose.TeX รองรับรูปแบบผลลัพธ์อื่นนอกจาก XPS หรือไม่?**  
A: รองรับ. คุณสามารถเปลี่ยน `new XpsDevice()` เป็น `new PdfDevice()`, `new PngDevice()` ฯลฯ ตามความต้องการของคุณ  

**Q: ฉันจะดีบักงาน TeX ที่ล้มเหลวอย่างไร?**  
A: เปิดการบันทึกแบบละเอียดโดยเรียก `options.setLogLevel(LogLevel.DEBUG);` แล้วตรวจสอบเอาต์พุตของคอนโซลเพื่อดูข้อความข้อผิดพลาดโดยละเอียด  

**Q: มีรุ่นทดลองใช้ฟรีหรือไม่?**  
A: มี – ดาวน์โหลดไบนารีรุ่นทดลองจาก [Aspose.TeX download page](https://releases.aspose.com/tex/java/)  

## สรุป

คุณได้เรียนรู้ **how to typeset tex** ในแอปพลิเคชัน Java ด้วยรูปแบบ TeX กำหนดเองโดยใช้ Aspose.TeX แล้ว ด้วยการทำตามขั้นตอนข้างต้น คุณสามารถผสานการจัดรูปแบบคุณภาพสูงเข้าไปในเวิร์กโฟลว์ Java ใด ๆ ทดลองใช้ไฟล์รูปแบบของคุณเอง และย้ายจากต้นแบบสู่การผลิตด้วยไลเซนส์ที่เหมาะสม  

---

**Last Updated:** 2025-12-05  
**Tested With:** Aspose.TeX for Java 24.10  
**Author:** Aspose  
**Related Resources:** [Aspose.TeX API Reference](https://docs.aspose.com/tex/java/) | [Download Free Trial](https://releases.aspose.com/tex/java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}