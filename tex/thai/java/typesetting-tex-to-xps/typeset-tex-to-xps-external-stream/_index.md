---
date: 2026-02-20
description: เรียนรู้วิธีแปลง TeX เป็น XPS ใน Java ด้วย Aspose.TeX คู่มือแบบขั้นตอนนี้จะแสดงให้คุณเห็นวิธีแปลงไฟล์
  TeX และสร้างสตรีมเอกสาร XPS อย่างมีประสิทธิภาพ
linktitle: How to Convert TeX to XPS in Java with External Stream
second_title: Aspose.TeX Java API
title: วิธีแปลง TeX เป็น XPS ใน Java ด้วยสตรีมภายนอก
url: /th/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีแปลง TeX เป็น XPS ใน Java ด้วยสตรีมภายนอก

## บทนำ

หากคุณต้องการ **แปลงไฟล์ TeX** ให้เป็นผลลัพธ์ XPS คุณภาพสูงจากแอปพลิเคชัน Java, Aspose.TeX for Java ทำให้การทำงานนี้เป็นเรื่องง่าย ในบทแนะนำนี้คุณจะได้เห็น **วิธีแปลง TeX** เป็นเอกสาร XPS โดยใช้สตรีมผลลัพธ์ภายนอก ซึ่งเหมาะอย่างยิ่งเมื่อคุณต้องการส่งผลลัพธ์โดยตรงไปยังการตอบสนอง, บริการจัดเก็บคลาวด์, หรือปลายทางที่กำหนดเองอื่น ๆ เราจะเดินผ่านกระบวนการทั้งหมด ตั้งแต่การตั้งค่าสภาพแวดล้อมจนถึงการเขียนไฟล์ XPS สุดท้าย

## คำตอบสั้น ๆ
- **บทแนะนำนี้ครอบคลุมอะไร?** การแปลง TeX เป็น XPS ด้วย Aspose.TeX พร้อมสตรีมภายนอก  
- **ไลบรารีหลักที่ต้องใช้คืออะไร?** Aspose.TeX for Java  
- **ต้องมีลิขสิทธิ์หรือไม่?** จำเป็นต้องมีลิขสิทธิ์ชั่วคราวหรือเต็มสำหรับการใช้งานในสภาพแวดล้อมการผลิต  
- **สามารถสร้างสตรีมเอกสาร XPS ได้หรือไม่?** ได้ – ตัวอย่างเขียน XPS โดยตรงไปยัง `OutputStream`  
- **เวอร์ชัน Java ที่รองรับคืออะไร?** JDK 8 ขึ้นไป (บทแนะนำใช้ JDK 11 เป็นตัวอ้างอิง)

## วิธีแปลง TeX เป็น XPS โดยใช้สตรีมภายนอก

ส่วนนี้ทำซ้ำคีย์เวิร์ดหลักในหัวข้อเฉพาะ เพื่อให้ผู้อ่านและเครื่องมือ AI สามารถค้นหาโซลูชันที่ต้องการได้อย่างง่ายดาย

## ข้อกำหนดเบื้องต้น

ก่อนจะลงมือเขียนโค้ด, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

- Java Development Kit (JDK): ตรวจสอบว่าคุณได้ติดตั้ง Java บนระบบของคุณแล้ว สามารถดาวน์โหลดได้จาก [ที่นี่](https://www.oracle.com/java/technologies/javase-downloads.html)

- Aspose.TeX for Java: ดาวน์โหลดและติดตั้ง Aspose.TeX for Java คุณสามารถค้นลิงก์ดาวน์โหลดได้ [ที่นี่](https://releases.aspose.com/tex/java/)

## นำเข้าแพ็กเกจ

เริ่มต้นด้วยการนำเข้าแพ็กเกจที่จำเป็นเพื่อเริ่มการแปลง TeX‑to‑XPS ของคุณ ใส่โค้ดส่วนต่อไปนี้ในโปรเจกต์ Java ของคุณ:

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

สร้างตัวเลือกการแปลงสำหรับรูปแบบ ObjectTeX เริ่มต้นโดยใช้โค้ดต่อไปนี้:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

ขั้นตอนนี้ตั้งค่าพื้นฐานสำหรับกระบวนการจัดรูปแบบ

## ขั้นตอนที่ 2: ระบุชื่องานและไดเรกทอรี

กำหนดชื่องานและตั้งค่าไดเรกทอรีทำงานสำหรับอินพุตและเอาต์พุต:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

อย่าลืมแทนที่ค่า placeholder เช่น "Your Input Directory" ด้วยเส้นทางไดเรกทอรีจริงของคุณ

## ขั้นตอนที่ 3: กำหนดค่าการแสดงผลบนเทอร์มินัล

ระบุให้การแสดงผลบนเทอร์มินัลถูกเขียนลงไฟล์ในไดเรกทอรีทำงานเอาต์พุต:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

ขั้นตอนนี้ช่วยให้บันทึกรายละเอียดสำหรับการดีบักได้ครบถ้วน

## ขั้นตอนที่ 4: เปิดสตรีมผลลัพธ์

เปิดสตรีมเพื่อเขียนเอกสาร XPS ที่จัดรูปแบบแล้ว:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

แทนที่ "Your Output Directory" ด้วยเส้นทางที่เหมาะสม

## ขั้นตอนที่ 5: รันงาน

ดำเนินการแปลง TeX เป็น XPS:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

ขั้นตอนนี้เสร็จสิ้นกระบวนการและคุณจะพบไฟล์ XPS ที่สร้างขึ้นในไดเรกทอรีเอาต์พุตที่ระบุ

## ทำไมเรื่องนี้ถึงสำคัญ

การใช้ `OutputStream` ภายนอกทำให้คุณควบคุมได้เต็มที่ว่าข้อมูล XPS จะไปที่ไหน—ไม่ว่าจะเป็นการส่งโดยตรงไปยังไคลเอนต์เว็บ, การเก็บไว้ในคลาวด์, หรือการต่อเข้ากับ pipeline การประมวลผลอื่น ๆ มันช่วยขจัดความจำเป็นของไฟล์กลางและลดภาระ I/O ซึ่งมีคุณค่าอย่างยิ่งในสภาพแวดล้อมที่ต้องการประสิทธิภาพสูงหรือแบบ server‑less

## ปัญหาที่พบบ่อยและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|----------|
| **FileNotFoundException** ขณะเปิดสตรีม | เส้นทางไดเรกทอรีเอาต์พุตไม่ถูกต้องหรือไม่มีอยู่ | ตรวจสอบเส้นทาง, สร้างไดเรกทอรีล่วงหน้า, หรือใช้ `Files.createDirectories` |
| **NullPointerException** ที่ `options.getOutputWorkingDirectory()` | ไม่ได้เรียก `setOutputWorkingDirectory` หรือค่ากลับเป็น `null` | ตรวจสอบให้แน่ใจว่าได้เรียก `options.setOutputWorkingDirectory` ก่อนใช้งาน |
| **LicenseException** ระหว่างรันไทม์ | รันโดยไม่มีลิขสิทธิ์ Aspose.TeX ที่ถูกต้อง | ใช้ลิขสิทธิ์ชั่วคราวหรือถาวรโดยเพิ่ม `License license = new License(); license.setLicense("Aspose.TeX.lic");` |

## คำถามที่พบบ่อย

**ถาม: สามารถใช้ Aspose.TeX for Java กับรูปแบบเอกสารอื่นได้หรือไม่?**  
ตอบ: Aspose.TeX มุ่งเน้นการประมวลผลเอกสารที่เกี่ยวข้องกับ TeX เป็นหลัก สำหรับรูปแบบอื่น ๆ ให้สำรวจผลิตภัณฑ์อื่นของ Aspose ที่มีให้เลือกหลากหลาย

**ถาม: มีเวอร์ชันทดลองให้ดาวน์โหลดหรือไม่?**  
ตอบ: มี, คุณสามารถทดลอง Aspose.TeX ได้โดยดาวน์โหลดเวอร์ชันทดลองฟรี [ที่นี่](https://releases.aspose.com/)

**ถาม: จะหาเอกสารอ้างอิงอย่างละเอียดได้จากที่ไหน?**  
ตอบ: ดูเอกสารอ้างอิง [ที่นี่](https://reference.aspose.com/tex/java/) เพื่อข้อมูลและตัวอย่างเพิ่มเติม

**ถาม: จะขอรับการสนับสนุนหรือความช่วยเหลือได้อย่างไร?**  
ตอบ: เยี่ยมชมฟอรั่ม Aspose.TeX [ที่นี่](https://forum.aspose.com/c/tex/47) เพื่อรับการสนับสนุนจากชุมชนและการสนทนาต่าง ๆ

**ถาม: สามารถขอรับลิขสิทธิ์ชั่วคราวสำหรับการทดสอบได้หรือไม่?**  
ตอบ: ได้, คุณสามารถขอรับลิขสิทธิ์ชั่วคราวได้ [ที่นี่](https://purchase.aspose.com/temporary-license/)

## สรุป

ขอแสดงความยินดี! คุณได้เรียนรู้ **วิธีแปลง TeX** เป็นเอกสาร XPS ใน Java ด้วย Aspose.TeX และสตรีมภายนอกแล้ว เทคนิคนี้ให้คุณควบคุมได้เต็มที่ว่าข้อมูล XPS จะถูกส่งไปที่ไหน—ไม่ว่าจะเป็นระบบไฟล์, การตอบสนองเว็บ, หรือคลาวด์บัคเก็ต อย่าลังเลที่จะทดลองกับแหล่ง TeX ต่าง ๆ, ปรับ `TeXOptions` สำหรับฟอนต์ที่กำหนดเอง, หรือเชื่อมสตรีมเข้ากับ pipeline การสร้างเอกสารขนาดใหญ่

---

**อัปเดตล่าสุด:** 2026-02-20  
**ทดสอบกับ:** Aspose.TeX for Java 24.11 (ล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}