---
title: แปลง LaTeX เป็นรูปแบบ XPS ใน Java ได้อย่างง่ายดาย
linktitle: แปลง LaTeX เป็นรูปแบบ XPS ใน Java ได้อย่างง่ายดาย
second_title: Aspose.TeX Java API
description: แปลง LaTeX เป็น XPS ได้อย่างง่ายดายใน Java โดยใช้ Aspose.TeX ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการบูรณาการที่ราบรื่น
weight: 10
url: /th/java/converting-lato-xps/simple-xps-conversion/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลง LaTeX เป็นรูปแบบ XPS ใน Java ได้อย่างง่ายดาย

## การแนะนำ

คุณต้องการแปลงเอกสาร LaTeX เป็นรูปแบบ XPS ในแอปพลิเคชัน Java ของคุณได้อย่างราบรื่นหรือไม่? Aspose.TeX สำหรับ Java มอบโซลูชันอันทรงพลัง ช่วยให้คุณบรรลุเป้าหมายนี้ได้อย่างง่ายดาย ในคำแนะนำทีละขั้นตอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการแปลง LaTeX เป็น XPS โดยใช้ Aspose.TeX

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่กระบวนการแปลง ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
-  ดาวน์โหลด Aspose.TeX สำหรับไลบรารี Java แล้ว คุณสามารถค้นหาลิงค์ดาวน์โหลด[ที่นี่](https://releases.aspose.com/tex/java/).

## แพ็คเกจนำเข้า

ในการเริ่มต้น ให้นำเข้าแพ็คเกจที่จำเป็นสำหรับโปรเจ็กต์ Java ของคุณ ตรวจสอบให้แน่ใจว่าคุณรวมไลบรารี Aspose.TeX ในการขึ้นต่อกันของโปรเจ็กต์ของคุณ

```java
package com.aspose.tex.LaTeXXpsConversionSimplest;

import java.io.ByteArrayInputStream;
import java.io.IOException;
import java.util.Calendar;
import java.util.GregorianCalendar;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.Interaction;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;
import com.aspose.tex.rendering.XpsSaveOptions;

import util.Utils;
```

ตอนนี้เรามาแบ่งกระบวนการแปลงออกเป็นหลายขั้นตอนโดยใช้ตัวอย่างโค้ดที่ให้มา

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีอินพุตและเอาต์พุต

```java
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

ระบุไดเร็กทอรีที่มีไฟล์อินพุต LaTeX ของคุณและตำแหน่งที่คุณต้องการบันทึกไฟล์ XPS ที่แปลงแล้ว

## ขั้นตอนที่ 2: กำหนดค่าตัวเลือก TeX

กำหนดค่าตัวเลือกต่างๆ เพื่อปรับแต่งกระบวนการแปลงตามความต้องการของคุณ

```java
options.setInteraction(Interaction.NonstopMode);
options.setDateTime(new GregorianCalendar(2022, Calendar.DECEMBER, 18).getTime());
options.ignoreMissingPackages(true);
options.noLigatures(true);
options.repeat(true);
```

ปรับโหมดการโต้ตอบ วันที่ในชื่อเรื่อง การจัดการพัสดุที่หายไป การผูก และการทำซ้ำตามต้องการ

## ขั้นตอนที่ 3: เริ่มต้นตัวเลือกการบันทึก XPS

```java
options.setSaveOptions(new XpsSaveOptions());
```

เริ่มต้นตัวเลือกสำหรับการบันทึกในรูปแบบ XPS

## ขั้นตอนที่ 4: ปรับแต่งตัวเลือกการบันทึก XPS

```java
options.getSaveOptions().rasterizeFormulas(true);
options.getSaveOptions().rasterizeIncludedGraphics(true);
options.getSaveOptions().subsetFonts(true);
```

ปรับแต่งตัวเลือกการบันทึก XPS เพื่อควบคุมการแปลงสูตร กราฟิกที่รวมไว้ และการตั้งค่าย่อยแบบอักษร

## ขั้นตอนที่ 5: เรียกใช้การแปลง LaTeX เป็น XPS

```java
new TeXJob("Your Input Directory" + "sample.ltx", new XpsDevice(), options).run();
```

เริ่มต้นกระบวนการแปลงโดยการรันงาน TeX ด้วยไฟล์อินพุต อุปกรณ์เอาต์พุต (XpsDevice) และตัวเลือกที่ระบุ

## ตัวอย่างเพิ่มเติม

สำรวจวิธีการแปลงเพิ่มเติมโดยใช้แหล่งอินพุตต่างๆ:

### ใช้อินพุตสตรีม

```java
new TeXJob(new ByteArrayInputStream(
    "\\documentclass{article} \\begin{document} Hello, World! \\end{document}".getBytes("ASCII")),
    new XpsDevice(), options).run();
```

### ใช้ขั้วต่ออินพุตหลัก

```java
new TeXJob(new XpsDevice(), options).run();
```

## บทสรุป

ด้วย Aspose.TeX สำหรับ Java การแปลง LaTeX เป็น XPS เป็นเรื่องง่าย ทำตามขั้นตอนเหล่านี้ ปรับแต่งตัวเลือก และรวมฟังก์ชันการทำงานนี้เข้ากับแอปพลิเคชัน Java ของคุณได้อย่างราบรื่น

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถแปลงเอกสาร LaTeX ด้วยสูตรที่ซับซ้อนโดยใช้ Aspose.TeX ได้หรือไม่

A1: แน่นอน! Aspose.TeX จัดการสูตรที่ซับซ้อนได้อย่างราบรื่นในระหว่างกระบวนการแปลง

### คำถามที่ 2: Aspose.TeX สำหรับ Java มีเวอร์ชันทดลองใช้งานหรือไม่

 A2: ใช่ คุณสามารถค้นหาเวอร์ชันทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 3: ฉันจะรับการสนับสนุนสำหรับ Aspose.TeX ได้อย่างไร

 A3: เยี่ยมชม[ฟอรั่ม Aspose.TeX](https://forum.aspose.com/c/tex/47) เพื่อช่วยเหลือและสนับสนุนชุมชน

### คำถามที่ 4: Aspose.TeX มีใบอนุญาตชั่วคราวหรือไม่

 A4: ได้ คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).

### คำถามที่ 5: ฉันจะหาเอกสารสำหรับ Aspose.TeX ได้ที่ไหน

 A5: โปรดดูที่[เอกสารประกอบ](https://reference.aspose.com/tex/java/) เพื่อรับคำแนะนำอย่างครอบคลุม
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
