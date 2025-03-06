---
title: อินพุตสตรีม เอาต์พุตรูปภาพ และอินพุตเทอร์มินัลใน Java
linktitle: อินพุตสตรีม เอาต์พุตรูปภาพ และอินพุตเทอร์มินัลใน Java
second_title: Aspose.TeX Java API
description: เรียนรู้อินพุตสตรีม เอาต์พุตรูปภาพ และอินพุตเทอร์มินัลใน Java โดยใช้ Aspose.TeX บทช่วยสอนที่ครอบคลุมสำหรับการบูรณาการอย่างราบรื่น
weight: 11
url: /th/java/advanced-io/stream-input-image-output/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# อินพุตสตรีม เอาต์พุตรูปภาพ และอินพุตเทอร์มินัลใน Java

## การแนะนำ

Aspose.TeX สำหรับ Java เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถทำงานกับไฟล์ TeX ได้ ซึ่งอำนวยความสะดวกในการสร้างและจัดการเอกสารคุณภาพสูง ในบทช่วยสอนนี้ เราจะสำรวจกระบวนการรับอินพุตสตรีม การสร้างเอาต์พุตรูปภาพ และการจัดการอินพุตเทอร์มินัลใน Java โดยใช้ Aspose.TeX

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
- ติดตั้ง Java Development Kit (JDK) บนเครื่องของคุณแล้ว
- ความคุ้นเคยกับไลบรารี Aspose.TeX
-  ติดตั้ง Aspose.TeX สำหรับ Java แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/tex/java/).

## แพ็คเกจนำเข้า

ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าแพ็คเกจที่จำเป็นสำหรับบทช่วยสอนนี้ ข้อมูลโค้ดต่อไปนี้สาธิตการนำเข้าที่จำเป็น:

```java
package com.aspose.tex.StreamInputImageOutputAndTerminalInput;

import java.io.ByteArrayInputStream;
import java.io.IOException;

import com.aspose.tex.InputConsoleTerminal;
import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputConsoleTerminal;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.ImageDevice;
import com.aspose.tex.rendering.PngSaveOptions;
```

## ขั้นตอนที่ 1: ตั้งค่าตัวเลือกการแปลง

สร้างตัวเลือกการแปลง TeX ด้วยรูปแบบ ObjectTeX เริ่มต้นตามส่วนขยายกลไก ObjectTeX ระบุชื่องาน ไดเร็กทอรีการทำงานอินพุต และไดเร็กทอรีการทำงานของเอาต์พุต

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("stream-in-image-out");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

## ขั้นตอนที่ 2: ระบุเทอร์มินัลอินพุตและเอาต์พุต

ระบุคอนโซลเป็นทั้งเทอร์มินัลอินพุตและเอาต์พุต

```java
options.setTerminalIn(new InputConsoleTerminal());
options.setTerminalOut(new OutputConsoleTerminal());
```

## ขั้นตอนที่ 3: กำหนดตัวเลือกการบันทึก

กำหนดตัวเลือกการบันทึกสำหรับภาพที่ส่งออก ในตัวอย่างนี้ เราใช้รูปแบบ PNG ที่มีความละเอียด 300 DPI

```java
PngSaveOptions pngOptions = new PngSaveOptions();
pngOptions.setResolution(300);
options.setSaveOptions(pngOptions);
```

## ขั้นตอนที่ 4: สร้างอุปกรณ์รูปภาพ

สร้างอุปกรณ์รูปภาพเพื่อสร้างภาพที่ส่งออก

```java
ImageDevice device = new ImageDevice();
```

## ขั้นตอนที่ 5: รันงาน

รันงาน TeX ด้วยอินพุต อุปกรณ์ และตัวเลือกที่ระบุ

```java
TeXJob job = new TeXJob(new ByteArrayInputStream(
        "\\hrule height 10pt width 95pt\\vskip10pt\\hrule height 5pt".getBytes("ASCII")),
        device, options);
job.run();
```

## ขั้นตอนที่ 6: จัดการอินพุตเทอร์มินัล

เมื่อคอนโซลแจ้งให้ป้อนข้อมูล ให้พิมพ์ "ABC" กด Enter จากนั้นพิมพ์ "\end" แล้วกด Enter อีกครั้ง

```java
// เพื่อให้ผลงานออกมาดูดียิ่งขึ้น
options.getTerminalOut().getWriter().newLine();
```

## ขั้นตอนที่ 7: ดึงข้อมูลเอาต์พุตรูปภาพ

คุณสามารถรับรูปภาพในรูปแบบของอาร์เรย์ของอาร์เรย์ไบต์ได้

```java
byte[][] result = device.getResult();
```

ซึ่งจะช่วยทำให้คำแนะนำทีละขั้นตอนสำหรับสตรีมอินพุต เอาต์พุตรูปภาพ และอินพุตเทอร์มินัลใน Java โดยใช้ Aspose.TeX เสร็จสมบูรณ์

## บทสรุป

Aspose.TeX สำหรับ Java ทำให้กระบวนการจัดการเอกสาร TeX ง่ายขึ้น โดยนำเสนอคุณสมบัติที่มีประสิทธิภาพสำหรับอินพุตสตรีม เอาต์พุตรูปภาพ และการโต้ตอบกับเทอร์มินัล เมื่อทำตามบทช่วยสอนนี้ คุณได้เรียนรู้วิธีผสานรวมฟังก์ชันการทำงานเหล่านี้เข้ากับแอปพลิเคชัน Java ของคุณได้อย่างราบรื่น

## คำถามที่พบบ่อย

### คำถามที่ 1: Aspose.TeX เข้ากันได้กับไลบรารี Java อื่นหรือไม่

ตอบ 1: ได้ Aspose.TeX สามารถรวมเข้ากับไลบรารี Java อื่นๆ ได้อย่างราบรื่นเพื่อปรับปรุงฟังก์ชันการทำงาน

### คำถามที่ 2: ฉันสามารถปรับแต่งรูปแบบภาพที่ส่งออกได้หรือไม่

A2: แน่นอน! Aspose.TeX มีตัวเลือกต่างๆ สำหรับการบันทึกภาพที่ส่งออก ช่วยให้ปรับแต่งได้ตามความต้องการของคุณ

### คำถามที่ 3: มีฟอรัมชุมชนสำหรับการสนับสนุน Aspose.TeX หรือไม่

 A3: ใช่ คุณสามารถค้นหาการสนับสนุนและโต้ตอบกับชุมชนได้ที่[ฟอรั่ม Aspose.TeX](https://forum.aspose.com/c/tex/47).

### คำถามที่ 4: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.TeX ได้อย่างไร

 A4: คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/).

### คำถามที่ 5: มีแหล่งข้อมูลเพิ่มเติมสำหรับเอกสาร Aspose.TeX หรือไม่

 A5: สำรวจอย่างครอบคลุม[เอกสารประกอบ](https://reference.aspose.com/tex/java/) สำหรับข้อมูลเชิงลึกและตัวอย่างโดยละเอียด
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
