---
title: เรียงพิมพ์ TeX เป็น XPS ใน Java พร้อมสตรีมภายนอก
linktitle: เรียงพิมพ์ TeX เป็น XPS ใน Java พร้อมสตรีมภายนอก
second_title: Aspose.TeX Java API
description: เรียนรู้วิธีเรียงพิมพ์ TeX เป็น XPS ใน Java โดยใช้ Aspose.TeX สำรวจคำแนะนำทีละขั้นตอนเพื่อการประมวลผลเอกสารที่ราบรื่น
type: docs
weight: 10
url: /th/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
---
## การแนะนำ

ในโลกของการพัฒนา Java นั้น Aspose.TeX มีความโดดเด่นในฐานะเครื่องมืออันทรงพลังสำหรับการเรียงพิมพ์เอกสาร TeX ในรูปแบบต่างๆ รวมถึง XPS หากคุณต้องการปรับปรุงความสามารถในการประมวลผลเอกสารของแอปพลิเคชัน Java บทช่วยสอนนี้เหมาะสำหรับคุณ ในคำแนะนำทีละขั้นตอนนี้ เราจะแนะนำคุณตลอดกระบวนการเรียงพิมพ์ TeX เป็น XPS โดยใช้ Aspose.TeX สำหรับ Java ด้วยสตรีมภายนอก

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java บนระบบของคุณ คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://www.oracle.com/java/technologies/javase-downloads.html).

-  Aspose.TeX สำหรับ Java: ดาวน์โหลดและติดตั้ง Aspose.TeX สำหรับ Java คุณสามารถค้นหาลิงค์ดาวน์โหลด[ที่นี่](https://releases.aspose.com/tex/java/).

## แพ็คเกจนำเข้า

เริ่มต้นด้วยการนำเข้าแพ็คเกจที่จำเป็นเพื่อเริ่มต้นเส้นทางการแปลง TeX เป็น XPS รวมข้อมูลโค้ดต่อไปนี้ในโครงการ Java ของคุณ:

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

เริ่มต้นด้วยการสร้างตัวเลือกการแปลงสำหรับรูปแบบ ObjectTeX เริ่มต้นโดยใช้รหัสต่อไปนี้:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

นี่เป็นการวางรากฐานสำหรับกระบวนการเรียงพิมพ์

## ขั้นตอนที่ 2: ระบุชื่องานและไดเรกทอรี

กำหนดชื่องานและตั้งค่าไดเร็กทอรีการทำงานอินพุตและเอาต์พุต:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

ตรวจสอบให้แน่ใจว่าคุณแทนที่ตัวยึดตำแหน่งเช่น "Your Input Directory" ด้วยเส้นทางไดเรกทอรีจริงของคุณ

## ขั้นตอนที่ 3: กำหนดค่าเอาต์พุตเทอร์มินัล

ระบุว่าเอาต์พุตเทอร์มินัลควรถูกเขียนลงในไฟล์ในไดเร็กทอรีการทำงานของเอาต์พุต:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

ขั้นตอนนี้ช่วยให้แน่ใจว่าบันทึกโดยละเอียดจะถูกบันทึกเพื่อการแก้ไขจุดบกพร่อง

## ขั้นตอนที่ 4: เปิดสตรีมเอาท์พุต

เปิดสตรีมเพื่อเขียนเอกสาร XPS แบบเรียงพิมพ์:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

แทนที่ "Your Output Directory" ด้วยเส้นทางที่เหมาะสม

## ขั้นตอนที่ 5: รันงาน

ดำเนินการงานการแปลง TeX เป็น XPS:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

การดำเนินการนี้เสร็จสิ้น และคุณจะพบเอกสาร typeset XPS ของคุณในไดเร็กทอรีเอาต์พุตที่ระบุ

## บทสรุป

ยินดีด้วย! คุณพิมพ์ TeX เป็น XPS ใน Java ได้สำเร็จโดยใช้ Aspose.TeX นี่เป็นการเปิดโลกแห่งความเป็นไปได้สำหรับการประมวลผลเอกสารในแอปพลิเคชัน Java ของคุณ ทดลองกับไฟล์ TeX ต่างๆ และสำรวจฟีเจอร์ที่หลากหลายที่นำเสนอโดย Aspose.TeX

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถใช้ Aspose.TeX สำหรับ Java กับรูปแบบเอกสารอื่นๆ ได้หรือไม่

ตอบ 1: Aspose.TeX มุ่งเน้นไปที่การประมวลผลเอกสารที่เกี่ยวข้องกับ TeX เป็นหลัก สำหรับรูปแบบอื่นๆ โปรดดูผลิตภัณฑ์ที่หลากหลายของ Aspose

### คำถามที่ 2: มีเวอร์ชันทดลองใช้งานหรือไม่

 ตอบ 2: ได้ คุณสามารถสัมผัสประสบการณ์ Aspose.TeX ได้ด้วยการดาวน์โหลดรุ่นทดลองใช้ฟรี[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 3: ฉันจะหาเอกสารประกอบที่ครอบคลุมได้จากที่ไหน?

 A3: โปรดดูเอกสารประกอบ[ที่นี่](https://reference.aspose.com/tex/java/) สำหรับข้อมูลโดยละเอียดและตัวอย่าง

### คำถามที่ 4: ฉันจะรับการสนับสนุนหรือขอความช่วยเหลือได้อย่างไร

 A4: เยี่ยมชมฟอรั่ม Aspose.TeX[ที่นี่](https://forum.aspose.com/c/tex/47)สำหรับการสนับสนุนและการอภิปรายของชุมชน

### คำถามที่ 5: ฉันสามารถขอรับใบอนุญาตชั่วคราวเพื่อการทดสอบได้หรือไม่

 A5: ได้ คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).