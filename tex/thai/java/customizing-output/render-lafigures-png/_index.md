---
title: เรนเดอร์ตัวเลข LaTeX เป็น PNG ใน Java
linktitle: เรนเดอร์ตัวเลข LaTeX เป็น PNG ใน Java
second_title: Aspose.TeX Java API
description: เรนเดอร์ตัวเลข LaTeX เป็น PNG ได้อย่างง่ายดายใน Java ด้วย Aspose.TeX ปฏิบัติตามคำแนะนำนี้เพื่อการผสานรวมที่ราบรื่น
weight: 12
url: /th/java/customizing-output/render-lafigures-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เรนเดอร์ตัวเลข LaTeX เป็น PNG ใน Java

## การแนะนำ

ในโลกของการพัฒนา Java การแสดงตัวเลข LaTeX เป็น PNG อาจเป็นงานที่ท้าทายแต่จำเป็น Aspose.TeX สำหรับ Java เข้ามาช่วยเหลือด้วยฟีเจอร์อันทรงพลัง ทำให้กระบวนการนี้มีประสิทธิภาพและราบรื่น คำแนะนำทีละขั้นตอนนี้จะแนะนำคุณตลอดกระบวนการเรนเดอร์ตัวเลข LaTeX ไปยัง PNG โดยใช้ Aspose.TeX

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
-  ดาวน์โหลด Aspose.TeX สำหรับไลบรารี Java แล้ว คุณสามารถรับได้จาก[ลิ้งค์ดาวน์โหลด](https://releases.aspose.com/tex/java/).
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม LaTeX และ Java

## แพ็คเกจนำเข้า

ในการเริ่มต้น คุณต้องนำเข้าแพ็คเกจที่จำเป็นจาก Aspose.TeX สำหรับ Java แพ็คเกจเหล่านี้มีเครื่องมือและฟังก์ชันที่จำเป็นสำหรับการเรนเดอร์ตัวเลข LaTeX เป็น PNG

```java
package com.aspose.tex.PngLaTeXFigureRenderer;

import java.awt.Color;
import java.io.ByteArrayOutputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.OutputStream;

import com.aspose.tex.PngFigureRenderer;
import com.aspose.tex.PngFigureRendererOptions;

import util.Utils;
```

## ขั้นตอนที่ 1: ตั้งค่าตัวเลือกการแสดงผล

สร้างตัวเลือกการเรนเดอร์ การตั้งค่าพารามิเตอร์ เช่น ความละเอียดของภาพ คำนำ ปัจจัยการปรับขนาด สีพื้นหลัง สตรีมบันทึก และการมองเห็นเอาต์พุตเทอร์มินัล

```java
PngFigureRendererOptions options = new PngFigureRendererOptions();
options.setResolution(96);
options.setPreamble("\\usepackage{pict2e}");
options.setScale(3000);
options.setBackgroundColor(Color.WHITE);
options.setLogStream(new ByteArrayOutputStream());
options.showTerminal(true);
```

## ขั้นตอนที่ 2: กำหนดรูป LaTeX

กำหนดฟิกเกอร์ LaTeX ที่คุณต้องการเรนเดอร์ ซึ่งอาจรวมถึงสมการทางคณิตศาสตร์ที่ซับซ้อน ไดอะแกรม หรือเนื้อหา LaTeX อื่นๆ

```java
String latexFigure = "\\setlength{\\unitlength}{0.8cm}\r\n" +
                    "\\begin{picture}(6,5)\r\n" +
                    "\\thicklines\r\n" +
                    // ... (เนื้อหาฟิกเกอร์ LaTeX ของคุณ)
                    "\\end{picture}";
```

## ขั้นตอนที่ 3: เรนเดอร์และบันทึก

เรนเดอร์รูป LaTeX เป็นอิมเมจ PNG และบันทึกลงในไดเร็กทอรีเอาต์พุตที่ระบุ

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + "text-and-formula.png");
try {
    new PngFigureRenderer().render(latexFigure, stream, options, size);
} finally {
    if (stream != null)
        stream.close();
}
```

## ขั้นตอนที่ 4: แสดงผล

แสดงผลลัพธ์ รวมถึงรายงานข้อผิดพลาดและขนาดของภาพที่ได้

```java
System.out.println(options.getErrorReport());
System.out.println();
System.out.println("Size: " + size.getWidth() + "x" + size.getHeight());
// ExEnd:PngLaTeXFigureRenderer
```

## บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีเรนเดอร์ตัวเลข LaTeX เป็น PNG ใน Java โดยใช้ Aspose.TeX เรียบร้อยแล้ว เครื่องมืออันทรงพลังนี้ทำให้กระบวนการง่ายขึ้น ทำให้คุณสามารถรวมเนื้อหา LaTeX เข้ากับแอปพลิเคชัน Java ของคุณได้อย่างราบรื่น

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถใช้ Aspose.TeX สำหรับ Java กับไลบรารี Java อื่นได้หรือไม่

ตอบ 1: ใช่ Aspose.TeX สำหรับ Java ได้รับการออกแบบมาให้ทำงานได้ดีกับไลบรารี Java อื่นๆ โดยให้ความยืดหยุ่นในกระบวนการพัฒนาของคุณ

### คำถามที่ 2: Aspose.TeX สำหรับ Java มีให้ทดลองใช้ฟรีหรือไม่

 A2: ได้ คุณสามารถเข้าถึงเวอร์ชันทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 3: ฉันจะรับการสนับสนุนสำหรับ Aspose.TeX สำหรับ Java ได้อย่างไร

 A3: เยี่ยมชม[ฟอรั่ม Aspose.TeX](https://forum.aspose.com/c/tex/47) สำหรับการสนับสนุนหรือข้อสงสัยใด ๆ

### คำถามที่ 4: ใบอนุญาตชั่วคราวคืออะไร และฉันจะขอรับใบอนุญาตได้อย่างไร

 A4: คุณสามารถรับใบอนุญาตชั่วคราวสำหรับ Aspose.TeX ได้[ที่นี่](https://purchase.aspose.com/temporary-license/).

### คำถามที่ 5: ฉันจะหาเอกสารโดยละเอียดสำหรับ Aspose.TeX สำหรับ Java ได้ที่ไหน

 A5: มีเอกสารประกอบให้[ที่นี่](https://reference.aspose.com/tex/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
