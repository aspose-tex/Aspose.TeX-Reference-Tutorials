---
title: แทนที่ชื่องานและเขียนเอาต์พุตเทอร์มินัลใน Java
linktitle: แทนที่ชื่องานและเขียนเอาต์พุตเทอร์มินัลใน Java
second_title: Aspose.TeX Java API
description: สำรวจคำแนะนำทีละขั้นตอนเกี่ยวกับการแทนที่ชื่องานและการเขียนเอาต์พุตเทอร์มินัลโดยใช้ Aspose.TeX สำหรับ Java เพิ่มประสิทธิภาพการประมวลผลเอกสารของคุณด้วยตัวเลือกการปรับแต่งอันทรงพลัง
weight: 10
url: /th/java/customizing-output/override-job-name-disk/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แทนที่ชื่องานและเขียนเอาต์พุตเทอร์มินัลใน Java

## การแนะนำ

Aspose.TeX สำหรับ Java มอบคุณสมบัติอันทรงพลังสำหรับการทำงานกับไฟล์ TeX ช่วยให้นักพัฒนาจัดการและปรับแต่งการประมวลผลเอกสาร TeX ได้ ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการแทนที่ชื่องานและการเขียนเอาต์พุตเทอร์มินัลไปยังระบบไฟล์โดยใช้ Aspose.TeX ใน Java

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ความรู้การทำงานของการเขียนโปรแกรม Java
-  ติดตั้ง Aspose.TeX สำหรับ Java แล้ว คุณสามารถดาวน์โหลดได้จาก[เอกสารประกอบ Java ของ Aspose.TeX](https://reference.aspose.com/tex/java/).

## แพ็คเกจนำเข้า

ในการเริ่มต้น ให้นำเข้าแพ็คเกจที่จำเป็นไปยังโปรเจ็กต์ Java ของคุณ ในไฟล์ Java ของคุณ ให้รวมการนำเข้าต่อไปนี้:

```java
package com.aspose.tex.OverridenJobNameAndTerminalOutputWrittenToDisk;

import java.io.IOException;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

## แทนที่ชื่องานและเขียนเอาต์พุตเทอร์มินัล

### ขั้นตอนที่ 1: สร้างตัวเลือกการแปลง

เริ่มต้นด้วยการสร้างตัวเลือกการแปลงสำหรับรูปแบบ ObjectTeX เริ่มต้นตามส่วนขยายเอ็นจิ้น ObjectTeX ใช้ข้อมูลโค้ดต่อไปนี้:

```java
//ExStart:OverrideJobName-WriteTerminalOutputToFileSystem
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

### ขั้นตอนที่ 2: ระบุชื่องานและไดเร็กทอรีการทำงาน

ระบุชื่องาน ไดเร็กทอรีการทำงานอินพุต และไดเร็กทอรีการทำงานของเอาต์พุต หากไม่ได้ระบุชื่องาน อาร์กิวเมนต์แรกของตัวสร้าง TeXJob จะถูกนำมาใช้เป็นชื่องาน ใช้ข้อมูลโค้ดต่อไปนี้:

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### ขั้นตอนที่ 3: เขียนเอาต์พุตเทอร์มินัลไปยังระบบไฟล์

 ระบุว่าต้องเขียนเอาต์พุตเทอร์มินัลลงในไฟล์ในไดเร็กทอรีการทำงานของเอาต์พุต ชื่อไฟล์จะเป็น`<job_name>.trm`. เพิ่มรหัสต่อไปนี้:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### ขั้นตอนที่ 4: รันงาน

รันงาน TeX โดยใช้ตัวเลือกและชื่องานที่ระบุ ต่อไปนี้คือวิธีที่คุณสามารถทำได้:

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
// ExEnd: OverrideJobName-WriteTerminalOutputToFileSystem
```

ยินดีด้วย! คุณได้แทนที่ชื่องานและเอาต์พุตเทอร์มินัลที่เขียนไปยังระบบไฟล์โดยใช้ Aspose.TeX ใน Java สำเร็จแล้ว

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจวิธีใช้ Aspose.TeX สำหรับ Java เพื่อแทนที่ชื่องานและบันทึกเอาต์พุตเทอร์มินัล คุณสมบัติเหล่านี้ช่วยให้นักพัฒนาสามารถควบคุมการประมวลผลเอกสาร TeX ได้อย่างละเอียด เพิ่มการปรับแต่งและความยืดหยุ่น

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถใช้ Aspose.TeX สำหรับ Java กับไลบรารี Java อื่นได้หรือไม่

ตอบ 1: ใช่ Aspose.TeX สำหรับ Java ได้รับการออกแบบมาเพื่อผสานรวมกับไลบรารี Java อื่นๆ ได้อย่างราบรื่น เพื่อเพิ่มความสามารถในการประมวลผลเอกสารของคุณ

### คำถามที่ 2: ฉันจะรับการสนับสนุนสำหรับ Aspose.TeX สำหรับ Java ได้ที่ไหน

 A2: เยี่ยมชม[ฟอรั่ม Aspose.TeX](https://forum.aspose.com/c/tex/47) สำหรับการสนับสนุนและความช่วยเหลือจากชุมชนในปัญหาใด ๆ ที่คุณอาจพบ

### คำถามที่ 3: Aspose.TeX สำหรับ Java มีรุ่นทดลองใช้ฟรีหรือไม่

 ตอบ 3: ได้ คุณสามารถเข้าถึง Aspose.TeX สำหรับ Java เวอร์ชันทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 4: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.TeX สำหรับ Java ได้อย่างไร

 A4: ทำตามนี้[ลิงค์](https://purchase.aspose.com/temporary-license/) เพื่อรับใบอนุญาตชั่วคราวเพื่อวัตถุประสงค์ในการทดสอบและประเมินผล

### คำถามที่ 5: ฉันจะซื้อ Aspose.TeX สำหรับ Java ได้ที่ไหน

 A5: เยี่ยมชม[หน้าซื้อ](https://purchase.aspose.com/buy) เพื่อรับใบอนุญาตสำหรับ Aspose.TeX สำหรับ Java
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
