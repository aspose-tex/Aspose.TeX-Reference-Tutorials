---
title: เรียงพิมพ์ TeX เป็น PDF ใน Java พร้อมสตรีมภายนอก
linktitle: เรียงพิมพ์ TeX เป็น PDF ใน Java พร้อมสตรีมภายนอก
second_title: Aspose.TeX Java API
description: เรียนรู้วิธีเรียงพิมพ์ TeX เป็น PDF ใน Java โดยใช้สตรีมภายนอกด้วย Aspose.TeX ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการบูรณาการที่ราบรื่น
weight: 10
url: /th/java/typesetting-tex-to-pdf/typeset-tex-to-pdf-external-stream/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เรียงพิมพ์ TeX เป็น PDF ใน Java พร้อมสตรีมภายนอก

## การแนะนำ

ในโลกของการพัฒนา Java การสร้าง PDF จากไฟล์ TeX ถือเป็นข้อกำหนดทั่วไป Aspose.TeX สำหรับ Java ทำให้กระบวนการนี้ง่ายขึ้น โดยมอบโซลูชันที่มีประสิทธิภาพสำหรับการเรียงพิมพ์ TeX เป็น PDF ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนของการเรียงพิมพ์ TeX เป็น PDF โดยใช้สตรีมภายนอก ในตอนท้าย คุณจะมีความเข้าใจที่ชัดเจนเกี่ยวกับวิธีการใช้กระบวนการนี้ได้อย่างราบรื่นในแอปพลิเคชัน Java ของคุณ

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- Aspose.TeX สำหรับ Java: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.TeX สำหรับ Java แล้ว คุณสามารถดาวน์โหลดได้จาก[Aspose.TeX สำหรับเอกสารประกอบ Java](https://reference.aspose.com/tex/java/).

- ไดเรกทอรีอินพุตและเอาต์พุต: เตรียมไดเรกทอรีอินพุตและเอาต์พุต คุณสามารถใช้ลิงค์ดาวน์โหลดที่ให้มาเพื่อรับไฟล์ที่จำเป็น

## แพ็คเกจนำเข้า

เริ่มต้นด้วยการนำเข้าแพ็คเกจที่จำเป็นไปยังโปรเจ็กต์ Java ของคุณ:

```java
package com.aspose.tex.TypesetPdfWrittenToExternalStream;

import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.io.OutputStream;

import com.aspose.tex.InputZipDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.OutputZipDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.PdfDevice;
import com.aspose.tex.rendering.PdfSaveOptions;

import util.Utils;
```

## ขั้นตอนที่ 1: เปิดสตรีมอินพุตและเอาต์พุต

เริ่มต้นด้วยการเปิดสตรีมสำหรับไฟล์ ZIP อินพุต (ทำหน้าที่เป็นไดเร็กทอรีการทำงานของอินพุต) และไฟล์ ZIP เอาต์พุต (ทำหน้าที่เป็นไดเร็กทอรีการทำงานของเอาต์พุต) ตรวจสอบให้แน่ใจว่าได้แทนที่ "Your Input Directory" และ "Your Output Directory" ด้วยเส้นทางไดเรกทอรีจริงของคุณ

```java
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "typeset-pdf-to-external-stream.zip");
```

## ขั้นตอนที่ 2: กำหนดค่า TeXOptions

สร้างออบเจ็กต์ TeXOptions และกำหนดค่าตามความต้องการของคุณ ตั้งชื่องาน ไดเร็กทอรีการทำงานอินพุต ไดเร็กทอรีการทำงานของเอาต์พุต และตัวเลือกอื่นๆ

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("typeset-pdf-to-external-stream");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
options.setSaveOptions(new PdfSaveOptions());
```

## ขั้นตอนที่ 3: เรียงพิมพ์ TeX เป็น PDF

ตอนนี้ ให้เปิดสตรีมเพื่อเขียนเอาต์พุต PDF ไปยังตำแหน่งที่ต้องการ คุณสามารถเลือกที่จะเขียนลงในไฟล์ในเครื่องหรือโดยตรงไปยังไฟล์ ZIP เอาท์พุตก็ได้

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + "file-name.pdf");
try {
    new TeXJob("hello-world", new PdfDevice(stream), options).run();
} finally {
    stream.close();
}
```

## ขั้นตอนที่ 4: จบไฟล์ ZIP เอาท์พุต

เสร็จสิ้นไฟล์ ZIP เอาท์พุตเพื่อให้กระบวนการเรียงพิมพ์เสร็จสมบูรณ์

```java
((OutputZipDirectory)options.getOutputWorkingDirectory()).finish();
```

## บทสรุป

ยินดีด้วย! คุณพิมพ์ TeX เป็น PDF ใน Java ได้สำเร็จโดยใช้สตรีมภายนอกด้วย Aspose.TeX บทช่วยสอนนี้มอบรากฐานที่แข็งแกร่งสำหรับการรวมการแปลง TeX เป็น PDF เข้ากับแอปพลิเคชัน Java ของคุณได้อย่างราบรื่น

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถปรับแต่งชื่อไฟล์ PDF เอาต์พุตได้หรือไม่

 A1: ใช่ คุณสามารถแก้ไขไฟล์`options.setJobName("typeset-pdf-to-external-stream")` เพื่อตั้งชื่องานที่คุณต้องการ

### คำถามที่ 2: ฉันจะแก้ไขปัญหาทั่วไประหว่างการเรียงพิมพ์ได้อย่างไร

 A2: เยี่ยมชม[ฟอรั่ม Aspose.TeX](https://forum.aspose.com/c/tex/47) สำหรับการสนับสนุนและช่วยเหลือชุมชน

### คำถามที่ 3: Aspose.TeX สำหรับ Java มีรุ่นทดลองใช้ฟรีหรือไม่

 A3: ได้ คุณสามารถเข้าถึงรุ่นทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 4: ฉันจะหาเอกสารและตัวอย่างเพิ่มเติมได้ที่ไหน

 A4: สำรวจอย่างครอบคลุม[เอกสาร Aspose.TeX](https://reference.aspose.com/tex/java/) สำหรับข้อมูลโดยละเอียด

### คำถามที่ 5: ฉันสามารถขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.TeX ได้หรือไม่

 A5: ได้ คุณสามารถขอใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
