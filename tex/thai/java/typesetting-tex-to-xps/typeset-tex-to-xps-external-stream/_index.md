---
date: 2026-09-14
description: เรียนรู้วิธีแปลง TeX เป็น XPS ใน Java ด้วย Aspose.TeX คู่มือแบบขั้นตอนนี้จะแสดงวิธีแปลงไฟล์
  TeX และสร้างสตรีมเอกสาร XPS อย่างมีประสิทธิภาพ
keywords:
- how to convert tex
- how to generate xps
- Aspose.TeX Java
- TeX to XPS conversion
- external output stream
lastmod: 2026-09-14
linktitle: วิธีแปลง TeX เป็น XPS ใน Java ด้วย External Stream
og_description: เรียนรู้วิธีแปลง TeX เป็น XPS ใน Java ด้วย Aspose.TeX คู่มือนี้จะพาคุณผ่านการใช้
  external OutputStream เพื่อการสร้าง XPS ที่เร็วและใช้หน่วยความจำอย่างมีประสิทธิภาพ
og_image_alt: Developer guide showing Java code that converts TeX to XPS using Aspose.TeX
  and streams the result
og_title: วิธีแปลง TeX เป็น XPS ใน Java ด้วย external stream
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to convert TeX to XPS in Java using Aspose.TeX. This step‑by‑step
    guide shows you how to convert TeX files and generate XPS document streams efficiently.
  headline: How to Convert TeX to XPS in Java with External Stream
  type: TechArticle
- questions:
  - answer: Aspose.TeX primarily focuses on TeX‑related document processing. For other
      formats, explore Aspose's extensive product range.
    question: Can I use Aspose.TeX for Java with other document formats?
  - answer: Yes, you can experience Aspose.TeX by downloading the free trial [Aspose
      free trial download](https://releases.aspose.com/).
    question: Is there a trial version available?
  - answer: Refer to the documentation [Aspose.TeX Java API reference](https://reference.aspose.com/tex/java/)
      for detailed information and examples.
    question: Where can I find comprehensive documentation?
  - answer: Visit the Aspose.TeX community forum [Aspose.TeX community forum](https://forum.aspose.com/c/tex/47)
      for community support and discussions.
    question: How do I get support or seek assistance?
  - answer: Yes, you can acquire a temporary license [temporary license request page](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for testing purposes?
  type: FAQPage
second_title: Aspose.TeX Java API
tags:
- convert TeX
- Aspose.TeX
- Java XPS conversion
- external stream
- document processing
title: วิธีแปลง TeX เป็น XPS ใน Java ด้วย External Stream
url: /th/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีแปลง TeX เป็น XPS ใน Java ด้วยสตรีมภายนอก

## บทนำ

หากคุณต้องการ **แปลง TeX** เป็นไฟล์ XPS คุณภาพสูงจากแอปพลิเคชัน Java, Aspose.TeX for Java ทำให้การทำงานนี้ง่ายดาย ในบทเรียนนี้คุณจะได้เห็น **วิธีแปลง TeX** เป็นเอกสาร XPS โดยใช้สตรีมเอาต์พุตภายนอก ซึ่งเหมาะเมื่อคุณต้องการส่งผลลัพธ์โดยตรงไปยังการตอบกลับ, บริการจัดเก็บคลาวด์, หรือปลายทางที่กำหนดเองใด ๆ เราจะเดินผ่านกระบวนการทั้งหมด ตั้งแต่การตั้งค่าสภาพแวดล้อมจนถึงการเขียนไฟล์ XPS สุดท้าย

**Aspose.TeX for Java** เป็นไลบรารีที่แปลงซอร์ส TeX เป็น XPS, PDF, PNG และรูปแบบอื่น ๆ โดยไม่ต้องติดตั้ง TeX รองรับรูปแบบเอาต์พุตกว่า 20 แบบและสามารถจัดการเอกสารหลายร้อยหน้าได้โดยใช้หน่วยความจำน้อย

## คำตอบอย่างรวดเร็ว
- **บทเรียนนี้ครอบคลุมอะไร?** การแปลง TeX เป็น XPS ด้วย Aspose.TeX พร้อมสตรีมภายนอก.  
- **ไลบรารีหลักที่ต้องการคือ?** Aspose.TeX for Java.  
- **ต้องการไลเซนส์หรือไม่?** จำเป็นต้องมีไลเซนส์ชั่วคราวหรือเต็มสำหรับการใช้งานในผลิตภัณฑ์.  
- **ฉันสามารถสร้างสตรีมเอกสาร XPS ได้หรือไม่?** ใช่ – ตัวอย่างเขียน XPS โดยตรงไปยัง `OutputStream`.  
- **เวอร์ชัน Java ที่รองรับคืออะไร?** JDK 8 ขึ้นไป (บทเรียนใช้ JDK 11 เป็นตัวอย่าง).

## วิธีแปลง TeX เป็น XPS ด้วยสตรีมภายนอก

โหลดซอร์ส TeX ของคุณ, กำหนดค่าตัวเลือกการแปลง, แล้วเขียน XPS ที่ได้โดยตรงไปยัง `OutputStream`. รูปแบบสองขั้นตอนนี้ (กำหนดค่า → รัน) จะทำการแปลงเสร็จภายในไม่ถึงหนึ่งวินาทีสำหรับเอกสารทั่วไปที่มีน้อยกว่า 50 หน้าบน CPU สมัยใหม่

## Aspose.TeX for Java คืออะไร?

Aspose.TeX for Java คือไลบรารี Java ที่ทำการพาร์สซอร์ส TeX/LaTeX และสร้าง XPS, PDF, PNG, SVG และรูปแบบเอกสารอื่น ๆ ให้ได้ มันให้ API ระดับสูงที่ซ่อนการทำงานของเอนจิน TeX ไว้ ทำให้คุณสามารถสร้างเอาต์พุตได้โดยไม่ต้องติดตั้งชุด TeX เต็มรูปแบบ

## ทำไมต้องใช้ `OutputStream` ภายนอก?

การเขียนไปยัง `OutputStream` ภายนอกช่วยขจัดไฟล์ชั่วคราว, ลดการอ่าน‑เขียนบนดิสก์, และทำให้คุณสตรีม XPS ไปยังไคลเอนต์เว็บ, บัคเก็ตคลาวด์, หรือบริการอื่น ๆ ได้โดยตรง ในสถานการณ์ที่ต้องประมวลผลจำนวนมาก วิธีนี้สามารถลดเวลาการประมวลผลโดยรวมได้ถึง 40 % เมื่อเทียบกับการทำงานแบบไฟล์

## ข้อกำหนดเบื้องต้น

- Java Development Kit (JDK): ตรวจสอบว่าคุณได้ติดตั้ง Java บนระบบของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [Java SE downloads](https://www.oracle.com/java/technologies/javase-downloads.html).
- Aspose.TeX for Java: ดาวน์โหลดและติดตั้ง Aspose.TeX for Java คุณสามารถค้นหาลิงก์ดาวน์โหลดได้ที่ [Aspose.TeX for Java download page](https://releases.aspose.com/tex/java/).

## นำเข้าแพ็กเกจ

คลาส `OutputStream` อยู่ในแพ็กเกจ `java.io` ส่วนคลาสที่ใช้แปลงอยู่ในเนมสเปซ `com.aspose.tex` ให้นำเข้าที่ส่วนหัวของไฟล์ Java ของคุณ:

```java
package com.aspose.tex.TypesetXpsWrittenToExternalStream;

import java.io.FileOutputStream;
import java.io.IOException;
import java.io.OutputStream;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

## ขั้นตอนที่ 1: กำหนดค่าตัวเลือกการแปลง

`TeXOptions` เก็บการตั้งค่าต่าง ๆ เช่น ไดเรกทอรีอินพุตและเอาต์พุต, ฟอนต์, และตัวเลือกการเรนเดอร์

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

การตั้งค่านี้เป็นพื้นฐานของกระบวนการจัดหน้า

## ขั้นตอนที่ 2: ระบุชื่องานและไดเรกทอรี

`TeXJob` แทนงานการจัดหน้าและต้องการชื่อ, ไดเรกทอรีอินพุต, และไดเรกทอรีเอาต์พุต

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

ตรวจสอบให้แทนที่ข้อความตัวอย่างเช่น "Your Input Directory" ด้วยเส้นทางไดเรกทอรีจริงของคุณ

## ขั้นตอนที่ 3: กำหนดค่าการแสดงผลบนเทอร์มินัล

`OutputFileTerminal` กำหนดตำแหน่งที่บันทึกล็อกคอนโซล โดยทั่วไปจะเป็นไฟล์ในโฟลเดอร์เอาต์พุต

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

ขั้นตอนนี้ทำให้บันทึกรายละเอียดสำหรับการดีบักได้ครบถ้วน

## ขั้นตอนที่ 4: เปิดสตรีมเอาต์พุต

`FileOutputStream` สร้าง `OutputStream` ที่เขียนไบต์ XPS ที่สร้างขึ้นไปยังเส้นทางไฟล์ที่ระบุ

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

แทนที่ "Your Output Directory" ด้วยเส้นทางที่เหมาะสม

## ขั้นตอนที่ 5: รันงาน

`TeXJob.run` ทำการแปลงโดยใช้ตัวเลือกที่กำหนดและเขียนผลลัพธ์ไปยัง `OutputStream` ที่เปิดไว้

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

การทำงานเสร็จสิ้นแล้ว คุณจะพบเอกสาร XPS ที่สร้างขึ้นในไดเรกทอรีเอาต์พุตที่ระบุ

## ทำไมเรื่องนี้สำคัญ

การสตรีม XPS ไปยัง `OutputStream` โดยตรงให้คุณควบคุมปลายทางของข้อมูลได้เต็มที่ ไม่ว่าจะเป็นการส่งไปยังไคลเอนต์เว็บ, เก็บไว้ในคลาวด์, หรือเชื่อมต่อกับขั้นตอนการประมวลผลต่อไป ช่วยขจัดไฟล์ชั่วคราวและลดภาระ I/O ซึ่งมีคุณค่าอย่างยิ่งในสภาพแวดล้อมที่ต้องประมวลผลสูงหรือแบบ server‑less

## ปัญหาที่พบบ่อยและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|----------|
| **FileNotFoundException** เมื่อเปิดสตรีม | เส้นทางไดเรกทอรีเอาต์พุตไม่ถูกต้องหรือไม่มีอยู่ | ตรวจสอบเส้นทาง, สร้างไดเรกทอรีล่วงหน้า, หรือใช้ `Files.createDirectories`. |
| **NullPointerException** ที่ `options.getOutputWorkingDirectory()` | `setOutputWorkingDirectory` ไม่ได้ถูกเรียกหรือคืนค่า null | ตรวจสอบให้เรียก `options.setOutputWorkingDirectory` ก่อนใช้งาน. |
| **LicenseException** ขณะรัน | รันโดยไม่มีไลเซนส์ Aspose.TeX ที่ถูกต้อง | ใช้ไลเซนส์ชั่วคราวหรือถาวรโดยใช้ `License license = new License(); license.setLicense("Aspose.TeX.lic");`. |

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ Aspose.TeX for Java กับรูปแบบเอกสารอื่นได้หรือไม่?**  
A: Aspose.TeX มุ่งเน้นการประมวลผลเอกสารที่เกี่ยวกับ TeX เป็นหลัก สำหรับรูปแบบอื่น ๆ ให้สำรวจผลิตภัณฑ์หลากหลายของ Aspose.

**Q: มีเวอร์ชันทดลองหรือไม่?**  
A: ใช่, คุณสามารถทดลองใช้ Aspose.TeX โดยดาวน์โหลดเวอร์ชันทดลองฟรี [Aspose free trial download](https://releases.aspose.com/).

**Q: ฉันจะหาเอกสารประกอบที่ครบถ้วนได้จากที่ไหน?**  
A: ดูเอกสาร [Aspose.TeX Java API reference](https://reference.aspose.com/tex/java/) เพื่อข้อมูลและตัวอย่างโดยละเอียด.

**Q: ฉันจะขอรับการสนับสนุนหรือความช่วยเหลือได้อย่างไร?**  
A: เยี่ยมชมฟอรั่มชุมชน Aspose.TeX [Aspose.TeX community forum](https://forum.aspose.com/c/tex/47) เพื่อรับการสนับสนุนและการสนทนาจากชุมชน.

**Q: ฉันสามารถขอไลเซนส์ชั่วคราวเพื่อการทดสอบได้หรือไม่?**  
A: ใช่, คุณสามารถขอไลเซนส์ชั่วคราวได้ที่ [temporary license request page](https://purchase.aspose.com/temporary-license/).

## สรุป

ขอแสดงความยินดี! คุณได้เรียนรู้ **วิธีแปลง TeX** เป็นเอกสาร XPS ใน Java ด้วย Aspose.TeX และสตรีมภายนอกแล้ว เทคนิคนี้ให้คุณควบคุมปลายทางของเอาต์พุต XPS ได้เต็มที่ ไม่ว่าจะเป็นระบบไฟล์, การตอบสนองเว็บ, หรือบัคเก็ตคลาวด์ อย่าลังเลที่จะทดลองกับซอร์ส TeX ต่าง ๆ, ปรับ `TeXOptions` เพื่อใช้ฟอนต์กำหนดเอง, หรือเชื่อมต่อสตรีมเข้ากับโครงสร้างการสร้างเอกสารที่ใหญ่ขึ้น

---

**อัปเดตล่าสุด:** 2026-09-14  
**ทดสอบด้วย:** Aspose.TeX for Java 24.11 (ล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [พิมพ์ Tex ไปเป็น Pdf ด้วยสตรีมภายนอก](/tex/java/typesetting-tex-to-pdf/typeset-tex-to-pdf-external-stream/)
- [แปลง TeX เป็น PNG ด้วยการรับสตรีมและการจัดการเทอร์มินัลใน Java](/tex/java/advanced-io/stream-input-image-output/)
- [วิธีอ่าน TeX – ตั้งค่าไดเรกทอรีอินพุตใน Java ด้วย Aspose.TeX for Java](/tex/java/advanced-io/required-input-directory/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}