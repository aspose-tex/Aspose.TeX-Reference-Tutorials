---
date: 2026-02-07
description: เรียนรู้วิธีสร้างใบแจ้งหนี้ที่พิมพ์ได้ด้วย Java โดยการแปลงไฟล์ LaTeX
  เป็น XPS ด้วย Aspose.TeX for Java ง่าย รวดเร็ว และใช้ Java อย่างเต็มที่
linktitle: Step by Step Conversion - LaTeX to XPS Format in Java
second_title: Aspose.TeX Java API
title: java สร้างใบแจ้งหนี้ที่พิมพ์ได้ – แปลง LaTeX เป็น XPS ด้วย Java
url: /th/java/converting-lato-xps/simple-xps-conversion/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# java create printable invoices – Step by Step Conversion: LaTeX to XPS Format in Java

## บทนำ

หากคุณต้องการ **java create printable invoices** จากแหล่งที่มาของ LaTeX ภายในแอปพลิเคชัน Java คุณมาถูกที่แล้ว ด้วย **Aspose.TeX for Java** คุณสามารถเรนเดอร์ไฟล์ LaTeX จัดการสูตรคณิตศาสตร์ที่ซับซ้อน และส่งออกไฟล์ XPS คุณภาพสูงที่พิมพ์ได้ตรงตามที่คุณคาดหวัง ในไม่กี่นาทีต่อไป เราจะพาคุณผ่านกระบวนการทำงานทั้งหมด อธิบายว่าทำไมวิธีนี้จึงเหมาะสำหรับการสร้างใบแจ้งหนี้ และแสดงวิธีปรับแต่งการแปลงสำหรับไลน์การรายงานของคุณ

## คำตอบอย่างรวดเร็ว
- **ควรใช้ไลบรารีอะไร?** Aspose.TeX for Java  
- **การดำเนินการใช้เวลานานเท่าไหร่?** ประมาณ 10‑15 นาทีสำหรับการตั้งค่าเบื้องต้น  
- **ข้อกำหนดเบื้องต้นคืออะไร?** JDK 8+, Aspose.TeX JAR, และ IDE (Eclipse/IntelliJ)  
- **ฉันสามารถเรนเดอร์สูตรที่ซับซ้อนได้หรือไม่?** ได้ – Aspose.TeX รองรับสภาพแวดล้อมคณิตศาสตร์ของ LaTeX อย่างเต็มรูปแบบ  
- **ต้องการใบอนุญาตสำหรับการใช้งานจริงหรือไม่?** ใช่, จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการใช้งานที่ไม่ใช่แบบทดลอง  

## วิธีการ java create printable invoices ด้วยการแปลง LaTeX เป็น XPS

ด้านล่างเป็นการอธิบายแบบสนทนาของแต่ละขั้นตอนที่คุณต้องทำ โปรดหยุดพัก ทดลองโค้ด และปรับการตั้งค่าให้ตรงกับรูปแบบใบแจ้งหนี้ของคุณ

## การแปลงแบบขั้นตอนต่อขั้นตอนคืออะไร?

*step by step conversion* คือกระบวนการที่มีการแนะนำและทำเป็นขั้นตอนย่อย ซึ่งแบ่งงานใหญ่—เช่นการแปลงไฟล์ต้นฉบับ LaTeX เป็นเอกสาร XPS—ออกเป็นการกระทำเล็ก ๆ ที่จัดการได้ง่าย โดยการทำตามแต่ละขั้นตอน คุณจะหลีกเลี่ยงข้อผิดพลาดทั่วไป รักษาโค้ดให้สะอาด และสามารถปรับแต่งการตั้งค่าแต่ละอย่าง (เช่นการจัดการฟอนต์หรือการเรสเตอร์ภาพ) ได้อย่างง่ายดายโดยไม่ต้องเขียนโค้ดทั้งหมดใหม่

## ทำไมต้องใช้ Aspose.TeX for Java สำหรับการเรนเดอร์ LaTeX?

- **Full LaTeX support** – จากบทความง่าย ๆ ถึงหนังสือที่มีแพ็กเกจกำหนดเอง  
- **No external binaries** – ทุกอย่างทำงานใน Java แท้ ๆ ซึ่งทำให้การปรับใช้ง่ายขึ้น  
- **Fine‑grained control** – ตัวเลือกช่วยให้คุณกำหนดวิธีการจัดการสูตร, กราฟิก, และฟอนต์  
- **Cross‑platform output** – ไฟล์ XPS แสดงผลอย่างสม่ำเสมอบนตัวดูไฟล์ Windows, macOS, และ Linux  

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน ตรวจสอบว่าคุณมี:

- Java Development Kit (JDK) 8 หรือใหม่กว่า ติดตั้งแล้ว.  
- ไลบรารี Aspose.TeX for Java (ดาวน์โหลดจาก [Aspose.TeX Java download page](https://releases.aspose.com/tex/java/)).  
- IDE ของ Java หรือเครื่องมือสร้าง (Maven/Gradle) เพื่อเพิ่ม JAR ไปยัง classpath ของโครงการของคุณ.  

## นำเข้าแพ็กเกจ

ขั้นตอนแรกคือการนำเข้าคลาสที่คุณต้องการ ใช้บล็อก import เหมือนที่แสดงไว้โดยตรง—เพื่อให้โค้ดคอมไพล์ได้โดยไม่มีการแก้ไข.

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

ต่อไปเราจะเดินผ่านขั้นตอนการแปลงโดยอธิบายวัตถุประสงค์ของแต่ละส่วนของโค้ด

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีอินพุตและเอาต์พุต

คุณต้องบอก Aspose.TeX ว่าจะหาไฟล์ต้นฉบับ `.ltx` ที่ไหนและจะเขียนไฟล์ XPS ที่ได้ที่ไหน.

```java
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

*Tip:* แทนที่ `"Your Input Directory"` และ `"Your Output Directory"` ด้วยพาธแบบเต็มหรือแบบสัมพันธ์ที่มีอยู่บนเครื่องของคุณ.

## ขั้นตอนที่ 2: กำหนดค่า TeX Options

ตัวเลือกเหล่านี้ควบคุมการทำงานของเอนจิน LaTeX ระหว่างการแปลง ปรับให้ตรงกับความต้องการของเอกสารของคุณ.

```java
options.setInteraction(Interaction.NonstopMode);
options.setDateTime(new GregorianCalendar(2022, Calendar.DECEMBER, 18).getTime());
options.ignoreMissingPackages(true);
options.noLigatures(true);
options.repeat(true);
```

- **Interaction mode** – `NonstopMode` ทำการประมวลผลต่อไปแม้ว่าจะพบข้อผิดพลาด.  
- **DateTime** – ตั้งค่าวันที่ที่ปรากฏในหน้าปกของเอกสาร.  
- **ignoreMissingPackages** – ป้องกันไม่ให้งานล้มเหลวเมื่อไม่พบแพ็กเกจ.  
- **noLigatures** – ปิดการใช้ลิการเจอร์แบบตัวอักษรพิเศษ หากคุณต้องการอักขระธรรมดา.  
- **repeat** – ให้เอนจินทำงานซ้ำเพื่ออ้างอิงข้าม.  

## ขั้นตอนที่ 3: เริ่มต้น XPS Save Options

สร้างอินสแตนซ์ `XpsSaveOptions` ที่จะเก็บการตั้งค่าเฉพาะของ XPS.

```java
options.setSaveOptions(new XpsSaveOptions());
```

## ขั้นตอนที่ 4: ปรับแต่ง XPS Save Options

ปรับจูนการจัดการสูตร, กราฟิก, และฟอนต์ของเอาต์พุต XPS.

```java
options.getSaveOptions().rasterizeFormulas(true);
options.getSaveOptions().rasterizeIncludedGraphics(true);
options.getSaveOptions().subsetFonts(true);
```

- **rasterizeFormulas** – แปลงนิพจน์คณิตศาสตร์เป็นภาพ เพื่อให้แสดงผลอย่างถูกต้องบนตัวดู XPS ใด ๆ.  
- **rasterizeIncludedGraphics** – บังคับให้กราฟิกที่ฝังอยู่ถูกเรสเตอร์ ซึ่งอาจเพิ่มความเข้ากันได้.  
- **subsetFonts** – ฝังเฉพาะ glyph ที่ใช้ในเอกสารเท่านั้น ลดขนาดไฟล์.  

## ขั้นตอนที่ 5: รันการแปลง LaTeX เป็น XPS

สุดท้าย ให้ดำเนินการงานแปลง `TeXJob` เชื่อมไฟล์อินพุต, อุปกรณ์เอาต์พุต (`XpsDevice`), และตัวเลือกทั้งหมดที่คุณกำหนด.

```java
new TeXJob("Your Input Directory" + "sample.ltx", new XpsDevice(), options).run();
```

หลังจากเรียก `run()` เสร็จสิ้น คุณจะพบ `sample.xps` ในไดเรกทอรีเอาต์พุตที่คุณระบุไว้ก่อนหน้านี้ ไฟล์ XPS นี้สามารถส่งตรงไปยังเครื่องพิมพ์หรือฝังในชุดใบแจ้งหนี้ PDF ได้

## ตัวอย่างเพิ่มเติม

### ใช้ InputStream (แปลงสตริง LaTeX โดยตรง)

หากคุณต้องการป้อนแหล่งที่มาของ LaTeX จากหน่วยความจำแทนไฟล์ ให้ห่อแหล่งที่มาด้วย `ByteArrayInputStream`.

```java
new TeXJob(new ByteArrayInputStream(
    "\\documentclass{article} \\begin{document} Hello, World! \\end{document}".getBytes("ASCII")),
    new XpsDevice(), options).run();
```

### ใช้ Main Input Terminal (ให้ Aspose.TeX ค้นหาไฟล์โดยอัตโนมัติ)

เมื่อคุณไม่จำเป็นต้องระบุพาธไฟล์อย่างชัดเจน คุณสามารถพึ่งพา terminal อินพุตเริ่มต้นได้

```java
new TeXJob(new XpsDevice(), options).run();
```

## กรณีการใช้งานทั่วไป & เคล็ดลับ

| สถานการณ์ | เหตุผลที่วิธีนี้ช่วยได้ |
|----------|--------------------------|
| **สร้างใบแจ้งหนี้ที่พิมพ์ได้** | XPS รักษาความแม่นยำของเลย์เอาต์บนเครื่องพิมพ์ Windows ทำให้เหมาะสำหรับการสร้างใบแจ้งหนี้คุณภาพสูง |
| **แปลงเอกสารวิชาการเป็นชุด** | API แบบขั้นตอนต่อขั้นตอนช่วยให้คุณวนลูปหลายไฟล์ `.ltx` ด้วยโค้ดที่เหลือน้อย |
| **ฝังสมการ LaTeX ในเครื่องมือรายงาน** | การเรสเตอร์สูตรทำให้แสดงผลได้อย่างถูกต้องแม้บนอุปกรณ์ที่มีพลังงานต่ำ |

**เคล็ดลับพิเศษ:** ห่อโลจิกการแปลงไว้ในเมธอดยูทิลิตี้ เพื่อให้คุณสามารถนำกลับใช้ได้ในหลายโมดูลของแอปพลิเคชันของคุณ

## คำถามที่พบบ่อย

**Q: ฉันสามารถแปลงเอกสาร LaTeX ที่มีสูตรซับซ้อนได้โดยใช้ Aspose.TeX หรือไม่?**  
A: แน่นอน เอนจินรองรับแพ็กเกจคณิตศาสตร์ AMS อย่างเต็มที่และจะเรสเตอร์สูตรเมื่อกำหนด `rasterizeFormulas(true)`  

**Q: มีเวอร์ชันทดลองสำหรับ Aspose.TeX for Java หรือไม่?**  
A: มี คุณสามารถดาวน์โหลดเวอร์ชันทดลองฟรีจาก [Aspose.TeX Java download page](https://releases.aspose.com/tex/java/).  

**Q: ฉันจะรับการสนับสนุนสำหรับ Aspose.TeX ได้อย่างไร?**  
A: เยี่ยมชม [Aspose.TeX forum](https://forum.aspose.com/c/tex/47) เพื่อรับความช่วยเหลือจากชุมชน หรือเปิดตั๋วสนับสนุนผ่านบัญชี Aspose ของคุณ  

**Q: มีใบอนุญาตชั่วคราวสำหรับ Aspose.TeX หรือไม่?**  
A: มี ใบอนุญาตชั่วคราวสามารถขอได้ผ่าน [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).  

**Q: ฉันสามารถหาเอกสารสำหรับ Aspose.TeX ได้ที่ไหน?**  
A: เอกสาร API อย่างครบถ้วนมีให้ที่ [Aspose.TeX Java reference](https://reference.aspose.com/tex/java/).  

---

**อัปเดตล่าสุด:** 2026-02-07  
**ทดสอบด้วย:** Aspose.TeX 24.11 for Java  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}