---
date: 2025-12-09
description: تعلم كيفية تحويل رسومات LaTeX إلى SVG في Java واكتشف خيارات تحويل LaTeX
  إلى PNG في Java باستخدام Aspose.TeX. اتبع هذا الدليل خطوة بخطوة للتكامل السلس.
linktitle: How to Render LaTeX Figures to SVG in Java
second_title: Aspose.TeX Java API
title: كيفية تحويل رسومات LaTeX إلى SVG في جافا
url: /ar/java/customizing-output/render-lafigures-svg/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تحويل رسومات LaTeX إلى SVG في Java

إن إنشاء وعرض رسومات LaTeX في تطبيق Java قد يبدو مهمة شاقة، لكنه احتياج شائع عندما تريد رسومات عالية الجودة وقابلة للتوسع للتقارير، الأوراق العلمية، أو محتوى الويب. في هذا الدرس ستتعلم **كيفية تحويل latex** إلى SVG مباشرة، وسترى أيضًا لماذا يمكن استخدام محرك Aspose.TeX نفسه في سير عمل **java convert latex png** عندما تكون الصور النقطية مطلوبة.

## إجابات سريعة
- **ما المكتبة التي يستخدمها الدرس؟** Aspose.TeX for Java  
- **ما صيغة الإخراج التي تم توضيحها؟** Scalable Vector Graphics (SVG)  
- **هل يمكنني أيضًا إنشاء صور PNG؟** نعم – يمكن لنفس المُحَوِّل إخراج PNG عن طريق تبديل فئة المُحَوِّل.  
- **هل أحتاج إلى ترخيص للاستخدام في الإنتاج؟** يتوفر ترخيص مؤقت للتقييم؛ يلزم الحصول على ترخيص كامل للمشاريع التجارية.  
- **ما نسخة Java المدعومة؟** أي بيئة تشغيل Java 8+ تعمل مع Aspose.TeX.

## ما هو “كيفية تحويل LaTeX” في Java؟
يعني تحويل LaTeX تحويل لغة الترميز المستخدمة في إعداد المستندات العلمية إلى تمثيل بصري يمكن لبرنامجك عرضه أو حفظه. يقوم Aspose.TeX بتحليل مصدر LaTeX، ومعالجة الحزم، وإنتاج رسومات بالصيغ التي تختارها – في حالتنا، SVG.

## لماذا تحويل رسومات LaTeX إلى SVG؟
- **القابلية للتوسع:** SVG يتوسع دون فقدان الجودة، مثالي لواجهات المستخدم المتجاوبة أو الطباعة عالية الدقة.  
- **قابلية التحرير:** ملفات SVG تظل قابلة للتحرير في برامج تحرير الرسومات المتجهة.  
- **الأداء:** الرسومات المتجهة غالبًا ما تكون أصغر حجمًا من المكافئات النقطية للرسومات الخطية والمخططات.  

## المتطلبات المسبقة
- بيئة تطوير Java (JDK 8 أو أحدث).  
- Aspose.TeX for Java – قم بتنزيله من [رابط التحميل الرسمي](https://releases.aspose.com/tex/java/).  
- معرفة أساسية بصياغة رسومات LaTeX (مثل بيئة `picture`).  

## استيراد الحزم
أولاً، استورد الفئات المطلوبة من Aspose.TeX إلى مشروعك.

```java
package com.aspose.tex.SvgLaTeXFigureRenderer;

import java.awt.Color;
import java.io.ByteArrayOutputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.OutputStream;

import com.aspose.tex.SvgFigureRenderer;
import com.aspose.tex.SvgFigureRendererOptions;

import util.Utils;
```

## الخطوة 1: إعداد خيارات التحويل
قم بتكوين كيفية معالجة المُحَوِّل لمصدر LaTeX، بما في ذلك التكبير والخلفية.

```java
SvgFigureRendererOptions options = new SvgFigureRendererOptions();
options.setPreamble("\\usepackage{pict2e}");
options.setScale(3000);
options.setBackgroundColor(Color.WHITE);
options.setLogStream(new ByteArrayOutputStream());
options.showTerminal(true);
```

## الخطوة 2: تعريف رسم LaTeX ودليل الإخراج
حدد الرسم الذي تريد تحويله ومكان حفظ ملف SVG.

```java
com.aspose.tex.Size2D size = new com.aspose.tex.Size2D.Float();
final OutputStream stream = new FileOutputStream("Your Output Directory" + "text-and-formula.svg");
```

## الخطوة 3: تشغيل التحويل
مرّر مصدر LaTeX إلى المُحَوِّل مع تدفق الإخراج، الخيارات، ومكان حجم العنصر النائب.

```java
new SvgFigureRenderer().render("\\setlength{\\unitlength}{0.8cm}\r\n" +
    // LaTeX figure content
    "\\begin{picture}(6,5)\r\n" +
    // ... (figure details)
    "\\end{picture}", stream, options, size);
```

## الخطوة 4: إغلاق تدفق الإخراج
دائمًا أغلق التدفق لتحرير موارد النظام.

```java
if (stream != null)
    stream.close();
```

## الخطوة 5: عرض النتائج
بعد التحويل، يمكنك فحص أي رسائل خطأ وأبعاد الصورة النهائية.

```java
System.out.println(options.getErrorReport());
System.out.println();
System.out.println("Size: " + size.getWidth() + "x" + size.getHeight());
```

باتباع هذه الخطوات، يمكنك تحويل رسومات LaTeX إلى SVG بسلاسة باستخدام Aspose.TeX for Java.

## المشكلات الشائعة والحلول
- **الحزم المفقودة:** إذا كان الرسم يستخدم حزمة LaTeX غير مدرجة في المقدمة الافتراضية، أضفها عبر `options.setPreamble("\\usepackage{...}")`.  
- **طول الوحدة غير الصحيح:** اضبط `\\setlength{\\unitlength}{...}` ليتناسب مع المقياس الذي تحتاجه.  
- **أخطاء أذونات الملفات:** تأكد من وجود دليل الإخراج وأن تطبيقك يمتلك صلاحية الكتابة.

## الأسئلة المتكررة

**س1: هل يمكنني تحويل رسومات LaTeX التي تحتوي على تعبيرات رياضية معقدة باستخدام Aspose.TeX؟**  
ج: نعم، يدعم Aspose.TeX بالكامل الترميز الرياضي المعقد وسيقوم بتحويله بدقة إلى SVG.

**س2: هل يتوفر ترخيص مؤقت لـ Aspose.TeX for Java؟**  
ج: نعم، يمكنك الحصول على ترخيص مؤقت من [هنا](https://purchase.aspose.com/temporary-license/).

**س3: كيف يمكنني الحصول على دعم لـ Aspose.TeX for Java؟**  
ج: زر [منتدى Aspose.TeX](https://forum.aspose.com/c/tex/47) للحصول على مساعدة من المجتمع.

**س4: ما الصيغ التي يمكنني تحويل رسومات LaTeX إليها باستخدام Aspose.TeX؟**  
ج: بالإضافة إلى SVG، يمكنك إخراج PNG، JPEG، PDF، وصيغ أخرى نقطية أو متجهة.

**س5: أين يمكنني العثور على الوثائق التفصيلية لـ Aspose.TeX for Java؟**  
ج: راجع [وثائق Aspose.TeX](https://reference.aspose.com/tex/java/) للحصول على تفاصيل شاملة حول API.

---

**آخر تحديث:** 2025-12-09  
**تم الاختبار مع:** Aspose.TeX 24.11 for Java  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}