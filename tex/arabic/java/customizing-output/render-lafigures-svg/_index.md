---
date: 2026-02-15
description: تعلم كيفية تحويل LaTeX إلى SVG وأيضًا تحويل LaTeX إلى PNG باستخدام Aspose.TeX
  للغة Java. يوضح لك هذا الدليل خطوة بخطوة كيفية إنشاء SVG من LaTeX في تطبيق Java.
linktitle: How to Render LaTeX Figures to SVG in Java
second_title: Aspose.TeX Java API
title: كيفية تحويل LaTeX إلى SVG في Java باستخدام Aspose.TeX
url: /ar/java/customizing-output/render-lafigures-svg/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تحويل LaTeX إلى SVG في Java باستخدام Aspose.TeX

إنشاء وعرض رسومات LaTeX في تطبيق Java قد يبدو مهمة صعبة، لكن **render latex to svg** أسهل مما تتصور. سواء كنت تحتاج إلى رسومات قابلة للتوسيع لتقارير علمية، أو لوحات تحكم ويب، أو ملفات PDF قابلة للطباعة، فإن تحويل LaTeX مباشرة إلى SVG يمنحك صورًا واضحة غير معتمدة على الدقة. في هذا الدرس ستتعرف أيضًا على كيفية **convert latex to png** عندما تكون الحاجة إلى إخراج نقطي.

## إجابات سريعة
- **ما المكتبة التي يستخدمها الدرس؟** Aspose.TeX for Java  
- **ما صيغة الإخراج التي يتم استعراضها؟** رسومات متجهية قابلة للتوسيع (SVG)  
- **هل يمكنني أيضًا إنشاء صور PNG؟** نعم – يمكن لنفس المُعالج إخراج PNG بتغيير فئة المُعالج.  
- **هل أحتاج إلى ترخيص للاستخدام في الإنتاج؟** يتوفر ترخيص مؤقت للتقييم؛ الترخيص الكامل مطلوب للمشاريع التجارية.  
- **ما نسخة Java المدعومة؟** أي بيئة تشغيل Java 8+ تعمل مع Aspose.TeX.  

## ما هو “render latex to svg” في Java؟
يعني تحويل LaTeX تحويل لغة الترميز المستخدمة في إعداد المستندات العلمية إلى تمثيل بصري يمكن لبرنامجك عرضه أو حفظه. تقوم Aspose.TeX بتحليل مصدر LaTeX، ومعالجة الحزم، وإنتاج رسومات بالصيغ التي تختارها – في حالتنا، SVG.

## لماذا تحويل رسومات LaTeX إلى SVG؟
- **القابلية للتوسيع:** SVG يتوسع دون فقدان الجودة، مثالي لواجهات المستخدم المتجاوبة أو للطباعة عالية الدقة.  
- **قابلية التعديل:** ملفات SVG تظل قابلة للتحرير في برامج تحرير الرسومات المتجهة.  
- **الأداء:** الرسومات المتجهة غالبًا ما تكون أصغر حجمًا من المكافئات النقطية للخطوط والرسوم التخطيطية.  

## متى قد تختار **convert latex to png** بدلاً من ذلك؟
الصيغ النقطية مثل PNG مفيدة عندما تحتاج إلى صورة bitmap لبيئات لا تدعم SVG (مثل بعض أدوات التقارير القديمة) أو عندما تريد تضمين الشكل في صيغة تقبل الصور النقطية فقط. يمكن لمحرك Aspose.TeX نفسه تغيير الإخراج بتغيير فئة واحدة.

## المتطلبات المسبقة
- بيئة تطوير Java (JDK 8 أو أحدث).  
- Aspose.TeX for Java – حمّله من [رابط التحميل الرسمي](https://releases.aspose.com/tex/java/).  
- إلمام أساسي بصياغة رسومات LaTeX (مثل بيئة `picture`).  

## استيراد الحزم
أولاً، استدعِ الفئات المطلوبة من Aspose.TeX إلى مشروعك.

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

## الخطوة 1: إعداد خيارات العرض
قم بتكوين كيفية معالجة المُعالج لمصدر LaTeX، بما في ذلك التكبير والخلفية.

```java
SvgFigureRendererOptions options = new SvgFigureRendererOptions();
options.setPreamble("\\usepackage{pict2e}");
options.setScale(3000);
options.setBackgroundColor(Color.WHITE);
options.setLogStream(new ByteArrayOutputStream());
options.showTerminal(true);
```

## الخطوة 2: تعريف شكل LaTeX ودليل الإخراج
حدد الشكل الذي تريد عرضه ومكان حفظ ملف SVG.

```java
com.aspose.tex.Size2D size = new com.aspose.tex.Size2D.Float();
final OutputStream stream = new FileOutputStream("Your Output Directory" + "text-and-formula.svg");
```

## الخطوة 3: تشغيل العرض
مرّر مصدر LaTeX إلى المُعالج مع تدفق الإخراج، الخيارات، ومحدد الحجم.

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
بعد الإخراج، يمكنك فحص أي رسائل خطأ وأبعاد الصورة النهائية.

```java
System.out.println(options.getErrorReport());
System.out.println();
System.out.println("Size: " + size.getWidth() + "x" + size.getHeight());
```

باتباع هذه الخطوات، يمكنك بسهولة **render latex to svg** باستخدام Aspose.TeX for Java، كما تتاح لك المرونة لتطبيق **convert latex to png** عند الحاجة.

## المشكلات الشائعة والحلول
- **الحزم المفقودة:** إذا كان الشكل يستخدم حزمة LaTeX غير مدرجة في المقدمة الافتراضية، أضفها عبر `options.setPreamble("\\usepackage{...}")`.  
- **طول الوحدة غير صحيح:** عدّل `\\setlength{\\unitlength}{...}` لتتناسب مع المقياس المطلوب.  
- **أخطاء أذونات الملفات:** تأكد من وجود دليل الإخراج وأن تطبيقك يملك صلاحية الكتابة.

## الأسئلة المتكررة

**س: هل يمكنني عرض رسومات LaTeX ذات التعبيرات الرياضية المعقدة باستخدام Aspose.TeX؟**  
ج: نعم، يدعم Aspose.TeX بالكامل الترميز الرياضي المعقد وسيعرضه بدقة إلى SVG.

**س: هل يتوفر ترخيص مؤقت لـ Aspose.TeX for Java؟**  
ج: نعم، يمكنك الحصول على ترخيص مؤقت من [هنا](https://purchase.aspose.com/temporary-license/).

**س: كيف يمكنني الحصول على دعم لـ Aspose.TeX for Java؟**  
ج: زر منتدى [Aspose.TeX](https://forum.aspose.com/c/tex/47) للحصول على مساعدة من المجتمع.

**س: ما الصيغ التي يمكنني تحويل رسومات LaTeX إليها باستخدام Aspose.TeX؟**  
ج: بالإضافة إلى SVG، يمكنك إخراج PNG، JPEG، PDF، وصيغ نقطية أو متجهة أخرى.

**س: أين يمكنني العثور على وثائق مفصلة لـ Aspose.TeX for Java؟**  
ج: راجع [وثائق Aspose.TeX](https://reference.aspose.com/tex/java/) للحصول على تفاصيل شاملة حول الـ API.

---

**آخر تحديث:** 2026-02-15  
**تم الاختبار مع:** Aspose.TeX 24.11 for Java  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}