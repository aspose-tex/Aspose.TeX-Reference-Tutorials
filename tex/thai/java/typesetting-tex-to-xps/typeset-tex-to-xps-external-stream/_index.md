---
date: 2025-12-11
description: เรียนรู้วิธีแปลง TeX เป็น XPS ใน Java ด้วย Aspose.TeX คู่มือขั้นตอนต่อขั้นตอนนี้จะแสดงให้คุณเห็นวิธีสร้างสตรีมเอกสาร
  XPS อย่างมีประสิทธิภาพ
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

หากคุณต้องการ **แปลง TeX** เป็นไฟล์ XPS คุณภาพสูงจากแอปพลิเคชัน Java, Aspose.TeX for Java ทำให้การทำงานนี้ง่ายดาย ในบทเรียนนี้คุณจะได้เห็นอย่างชัดเจน **วิธีแปลง TeX** เป็นเอกสาร XPS โดยใช้สตรีมเอาต์พุตภายนอก ซึ่งเหมาะอย่างยิ่งเมื่อคุณต้องการส่งผลลัพธ์โดยตรงไปยังการตอบกลับ, บริการจัดเก็บข้อมูลบนคลาวด์, หรือปลายทางที่กำหนดเองอื่น ๆ เราจะเดินผ่านกระบวนการทั้งหมด ตั้งแต่การตั้งค่าสภาพแวดล้อมจนถึงการเขียนไฟล์ XPS สุดท้าย

## คำตอบอย่างรวดเร็ว
- **What does this tutorial cover?** การแปลง TeX เป็น XPS ด้วย Aspose.TeX พร้อมสตรีมภายนอก.  
- **Which primary library is required?** Aspose.TeX for Java.  
- **Do I need a license?** จำเป็นต้องมีใบอนุญาตชั่วคราวหรือเต็มสำหรับการใช้งานในผลิตภัณฑ์.  
- **Can I generate XPS document streams?** ได้ – ตัวอย่างเขียน XPS โดยตรงไปยัง `OutputStream`.  
- **What Java version is supported?** รองรับ JDK 8 ขึ้นไป (บทเรียนใช้ JDK 11 เป็นตัวอย่าง).

## ข้อกำหนดเบื้องต้น

ก่อนที่จะลงลึกในโค้ด, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

- Java Development Kit (JDK): ตรวจสอบว่าคุณได้ติดตั้ง Java บนระบบของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [here](https://www.oracle.com/java/technologies/javase-downloads.html).
- Aspose.TeX for Java: ดาวน์โหลดและติดตั้ง Aspose.TeX for Java คุณสามารถค้นหาลิงก์ดาวน์โหลดได้ที่ [here](https://releases.aspose.com/tex/java/).

## นำเข้าแพ็กเกจ

เริ่มต้นด้วยการนำเข้าแพ็กเกจที่จำเป็นเพื่อเริ่มการแปลง TeX‑to‑XPS ของคุณ ใส่โค้ดสแนปช็อตต่อไปนี้ในโปรเจกต์ Java ของคุณ:

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

เริ่มต้นด้วยการสร้างตัวเลือกการแปลงสำหรับรูปแบบ ObjectTeX เริ่มต้นโดยใช้โค้ดต่อไปนี้:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

สิ่งนี้ตั้งค่าพื้นฐานสำหรับกระบวนการจัดรูปแบบ.

## ขั้นตอนที่ 2: ระบุชื่องานและไดเรกทอรี

กำหนดชื่องานและตั้งค่าไดเรกทอรีทำงานสำหรับอินพุตและเอาต์พุต:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

ตรวจสอบให้แน่ใจว่าคุณแทนที่ตัวแปรเช่น "Your Input Directory" ด้วยเส้นทางไดเรกทอรีจริงของคุณ.

## ขั้นตอนที่ 3: กำหนดค่าการแสดงผลเทอร์มินัล

ระบุว่าการแสดงผลของเทอร์มินัลควรเขียนลงไฟล์ในไดเรกทอรีทำงานของเอาต์พุต:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

ขั้นตอนนี้ทำให้แน่ใจว่าบันทึกรายละเอียดถูกจับไว้เพื่อการดีบัก.

## ขั้นตอนที่ 4: เปิดสตรีมเอาต์พุต

เปิดสตรีมเพื่อเขียนเอกสาร XPS ที่จัดรูปแบบแล้ว:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

แทนที่ "Your Output Directory" ด้วยเส้นทางที่เหมาะสม.

## ขั้นตอนที่ 5: เรียกใช้งาน

ดำเนินการแปลง TeX เป็น XPS:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

ขั้นตอนนี้เสร็จสมบูรณ์และคุณจะพบเอกสาร XPS ที่สร้างขึ้นในไดเรกทอรีเอาต์พุตที่ระบุ.

## ปัญหาทั่วไปและวิธีแก้ไข

| ปัญหา | สาเหตุ | วิธีแก้ไข |
|-------|--------|-----------|
| **FileNotFoundException** เมื่อเปิดสตรีม | เส้นทางไดเรกทอรีเอาต์พุตไม่ถูกต้องหรือไม่มีอยู่. | ตรวจสอบเส้นทาง, สร้างไดเรกทอรีล่วงหน้า, หรือใช้ `Files.createDirectories`. |
| **NullPointerException** บน `options.getOutputWorkingDirectory()` | `setOutputWorkingDirectory` ไม่ได้ถูกเรียกหรือคืนค่า `null`. | ตรวจสอบให้แน่ใจว่าคุณเรียก `options.setOutputWorkingDirectory` ก่อนใช้งาน. |
| **LicenseException** ระหว่างรันไทม์ | ทำงานโดยไม่มีใบอนุญาต Aspose.TeX ที่ถูกต้อง. | ใช้ใบอนุญาตชั่วคราวหรือถาวรโดยใช้ `License license = new License(); license.setLicense("Aspose.TeX.lic");`. |

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ Aspose.TeX for Java กับรูปแบบเอกสารอื่นได้หรือไม่?**  
A: Aspose.TeX มุ่งเน้นที่การประมวลผลเอกสารที่เกี่ยวข้องกับ TeX เป็นหลัก สำหรับรูปแบบอื่น ๆ ให้สำรวจผลิตภัณฑ์ที่หลากหลายของ Aspose.

**Q: มีเวอร์ชันทดลองหรือไม่?**  
A: ใช่, คุณสามารถทดลองใช้ Aspose.TeX ได้โดยดาวน์โหลดเวอร์ชันทดลองฟรี [here](https://releases.aspose.com/).

**Q: ฉันสามารถหาเอกสารประกอบที่ครบถ้วนได้จากที่ไหน?**  
A: ดูเอกสารประกอบที่ [here](https://reference.aspose.com/tex/java/) สำหรับข้อมูลและตัวอย่างโดยละเอียด.

**Q: ฉันจะรับการสนับสนุนหรือขอความช่วยเหลือได้อย่างไร?**  
A: เยี่ยมชมฟอรั่ม Aspose.TeX ที่ [here](https://forum.aspose.com/c/tex/47) เพื่อรับการสนับสนุนจากชุมชนและการสนทนา.

**Q: ฉันสามารถขอรับใบอนุญาตชั่วคราวเพื่อการทดสอบได้หรือไม่?**  
A: ได้, คุณสามารถรับใบอนุญาตชั่วคราวได้ที่ [here](https://purchase.aspose.com/temporary-license/).

## สรุป

ขอแสดงความยินดี! คุณเพิ่งเรียนรู้ **วิธีแปลง TeX** เป็นเอกสาร XPS ใน Java ด้วย Aspose.TeX และสตรีมภายนอก เทคนิคนี้ให้คุณควบคุมได้เต็มที่ว่าผลลัพธ์ XPS จะไปที่ไหน—ไม่ว่าจะเป็นระบบไฟล์, การตอบสนองเว็บ, หรือคลาวด์บัคเก็ต อย่าลังเลที่จะทดลองกับแหล่ง TeX ต่าง ๆ, ปรับ `TeXOptions` สำหรับฟอนต์ที่กำหนดเอง, หรือเชื่อมสตรีมเข้ากับ pipeline การสร้างเอกสารที่ใหญ่ขึ้น.

---

**อัปเดตล่าสุด:** 2025-12-11  
**ทดสอบด้วย:** Aspose.TeX for Java 24.11 (latest at time of writing)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}