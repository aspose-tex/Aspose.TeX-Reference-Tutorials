---
title: แทนที่ชื่องานและเขียนเอาต์พุตเทอร์มินัลเป็น Zip ใน Java
linktitle: แทนที่ชื่องานและเขียนเอาต์พุตเทอร์มินัลเป็น Zip ใน Java
second_title: Aspose.TeX Java API
description: เรียนรู้วิธีแทนที่ชื่องานและเขียนเอาต์พุตเทอร์มินัลไปยัง ZIP ใน Java ด้วย Aspose.TeX บทช่วยสอนที่ครอบคลุมสำหรับนักพัฒนา Java
weight: 11
url: /th/java/customizing-output/override-job-name-zip/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แทนที่ชื่องานและเขียนเอาต์พุตเทอร์มินัลเป็น Zip ใน Java

## การแนะนำ

ในโลกของการพัฒนา Java นั้น Aspose.TeX มีความโดดเด่นในฐานะเครื่องมืออันทรงพลังสำหรับการจัดการรูปแบบไฟล์ TeX ในบทช่วยสอนนี้ เราจะเจาะลึกสถานการณ์เฉพาะ – การแทนที่ชื่องานและการเขียนเอาต์พุตเทอร์มินัลลงในไฟล์ zip คำแนะนำทีละขั้นตอนนี้จะแนะนำคุณตลอดกระบวนการโดยใช้ Aspose.TeX สำหรับ Java

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มบทช่วยสอนนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
-  ติดตั้ง Aspose.TeX สำหรับ Java ถ้าไม่เช่นนั้นคุณสามารถดาวน์โหลดได้จาก[เว็บไซต์กำหนด](https://releases.aspose.com/tex/java/).
- ความเข้าใจเกี่ยวกับวิธีการตั้งค่าสภาพแวดล้อมการพัฒนา Java

## แพ็คเกจนำเข้า

เริ่มต้นด้วยการนำเข้าแพ็คเกจที่จำเป็นไปยังโปรเจ็กต์ Java ของคุณ สิ่งนี้ทำให้แน่ใจได้ว่าคุณจะสามารถเข้าถึงฟังก์ชัน Aspose.TeX ที่จำเป็นสำหรับงานนี้ได้

```java
package com.aspose.tex.OverridenJobNameAndTerminalOutputWrittenToZip;

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

## ขั้นตอนที่ 1: เปิดไฟล์ ZIP

ขั้นแรก ให้เปิดสตรีมในไฟล์ ZIP ที่จะทำหน้าที่เป็นไดเร็กทอรีการทำงานของอินพุต นี่คือไฟล์เก็บถาวรที่จะใช้ประมวลผลข้อมูลของคุณ

```java
// เปิดสตรีมในไฟล์ ZIP อินพุต
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
```

## ขั้นตอนที่ 2: เปิดไฟล์ ZIP เอาท์พุต

จากนั้น เปิดสตรีมในไฟล์ ZIP ที่จะทำหน้าที่เป็นไดเร็กทอรีการทำงานของเอาต์พุต นี่คือที่ที่เอาต์พุตเทอร์มินัลจะถูกเขียน

```java
// เปิดสตรีมในไฟล์ ZIP เอาต์พุต
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "terminal-out-to-zip.zip");
```

## ขั้นตอนที่ 3: ตั้งค่าตัวเลือกการแปลง

สร้างตัวเลือกการแปลงสำหรับรูปแบบ ObjectTeX เริ่มต้นตามส่วนขยายเอ็นจิ้น ObjectTeX ระบุชื่องานและไดเร็กทอรีการทำงานของไฟล์ ZIP สำหรับทั้งอินพุตและเอาต์พุต

```java
// สร้างตัวเลือก TeX สำหรับรูปแบบ ObjectTeX
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("terminal-output-to-zip");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
```

## ขั้นตอนที่ 4: ระบุเอาต์พุตเทอร์มินัล

 ระบุว่าต้องเขียนเอาต์พุตเทอร์มินัลลงในไฟล์ในไดเร็กทอรีการทำงานของเอาต์พุต ชื่อไฟล์จะเป็น`<job_name>.trm`.

```java
// ระบุการตั้งค่าเอาท์พุตเทอร์มินัล
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

## ขั้นตอนที่ 5: กำหนดตัวเลือกการบันทึกและรันงาน

กำหนดตัวเลือกการบันทึก เช่น ตัวเลือกการบันทึก PDF ในกรณีนี้ รันงาน TeX เพื่อดำเนินการแปลง

```java
// กำหนดตัวเลือกการบันทึกและรันงาน
options.setSaveOptions(new PdfSaveOptions());
new TeXJob("hello-world", new PdfDevice(), options).run();
```

## ขั้นตอนที่ 6: จบไฟล์ ZIP เอาท์พุต

หลังจากงานเสร็จสิ้น ให้สรุปไฟล์ ZIP เอาท์พุตเพื่อให้แน่ใจว่าเสร็จสมบูรณ์อย่างเหมาะสม

```java
// จบไฟล์ ZIP เอาท์พุต
((OutputZipDirectory) options.getOutputWorkingDirectory()).finish();
```

## บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีแทนที่ชื่องานและเขียนเอาต์พุตเทอร์มินัลไปยังไฟล์ ZIP ใน Java โดยใช้ Aspose.TeX เรียบร้อยแล้ว ฟังก์ชันการทำงานอันทรงพลังนี้เพิ่มความยืดหยุ่นและประสิทธิภาพให้กับโครงการพัฒนา Java ของคุณ

## คำถามที่พบบ่อย

### คำถามที่ 1: Aspose.TeX คืออะไร

คำตอบ 1: Aspose.TeX เป็นไลบรารี Java ที่ช่วยให้นักพัฒนาสามารถทำงานกับรูปแบบไฟล์ TeX ได้ โดยมีฟังก์ชันการทำงานขั้นสูงสำหรับการประมวลผลเอกสาร

### คำถามที่ 2: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.TeX ได้อย่างไร

 A2: คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[ลิงค์นี้](https://purchase.aspose.com/temporary-license/).

### คำถามที่ 3: ฉันจะหาเอกสารประกอบของ Aspose.TeX ได้ที่ไหน

 A3: มีเอกสารประกอบให้[ที่นี่](https://reference.aspose.com/tex/java/).

### คำถามที่ 4: Aspose.TeX มีเวอร์ชันทดลองใช้ฟรีหรือไม่

 A4: ใช่ คุณสามารถค้นหาเวอร์ชันทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 5: ฉันสามารถขอรับการสนับสนุนหรือถามคำถามเกี่ยวกับ Aspose.TeX ได้ที่ไหน

 A5: เยี่ยมชม[ฟอรั่ม Aspose.TeX](https://forum.aspose.com/c/tex/47) สำหรับการสนับสนุนและการอภิปราย

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
