---
title: تقديم أرقام LaTeX إلى SVG في Java
linktitle: تقديم أرقام LaTeX إلى SVG في Java
second_title: Aspose.TeX جافا API
description: تعرف على كيفية عرض أشكال LaTeX إلى SVG في Java بسهولة باستخدام Aspose.TeX. اتبع هذا الدليل خطوة بخطوة لتحقيق التكامل السلس.
weight: 14
url: /ar/java/customizing-output/render-lafigures-svg/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تقديم أرقام LaTeX إلى SVG في Java

## مقدمة

يمكن أن يكون إنشاء أشكال LaTeX وعرضها في Java مهمة معقدة ولكنها حاسمة لمختلف التطبيقات. في هذا البرنامج التعليمي، سوف نستكشف كيفية عرض أشكال LaTeX إلى SVG باستخدام Aspose.TeX لـ Java. يوفر Aspose.TeX وظائف قوية للتعامل مع مستندات LaTeX وتحويلها إلى تنسيقات مختلفة، بما في ذلك SVG.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:

- بيئة تطوير Java: تأكد من إعداد بيئة تطوير Java على نظامك.
-  Aspose.TeX لـ Java: قم بتنزيل وتثبيت مكتبة Aspose.TeX لـ Java من[رابط التحميل](https://releases.aspose.com/tex/java/).
- الفهم الأساسي لـ LaTeX: تعرف على بناء جملة LaTeX الأساسي وإنشاء الأشكال.

## حزم الاستيراد

للبدء، قم باستيراد الحزم الضرورية من Aspose.TeX. ستوفر هذه الحزم الأدوات اللازمة لعرض أرقام LaTeX إلى SVG.

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

قم بإنشاء خيارات العرض، وتحديد المعلمات مثل التمهيد، وعامل القياس، ولون الخلفية، ودفق السجل، ورؤية مخرجات المحطة الطرفية.

```java
SvgFigureRendererOptions options = new SvgFigureRendererOptions();
options.setPreamble("\\usepackage{pict2e}");
options.setScale(3000);
options.setBackgroundColor(Color.WHITE);
options.setLogStream(new ByteArrayOutputStream());
options.showTerminal(true);
```

## الخطوة 2: تحديد شكل LaTeX ودليل الإخراج

حدد شكل LaTeX الذي تريد عرضه وحدد دليل الإخراج لملف SVG.

```java
com.aspose.tex.Size2D size = new com.aspose.tex.Size2D.Float();
final OutputStream stream = new FileOutputStream("Your Output Directory" + "text-and-formula.svg");
```

## الخطوة 3: تشغيل العرض

 قم بتشغيل عملية العرض باستخدام`SvgFigureRenderer` فصل.

```java
new SvgFigureRenderer().render("\\setlength{\\unitlength}{0.8cm}\r\n" +
    // محتوى شكل LaTeX
    "\\begin{picture}(6,5)\r\n" +
    // ... (تفاصيل الشكل)
    "\\end{picture}", stream, options, size);
```

## الخطوة 4: إغلاق دفق الإخراج

تأكد من إغلاق دفق الإخراج بعد التقديم.

```java
if (stream != null)
    stream.close();
```

## الخطوة 5: عرض النتائج

اعرض أي تقارير أخطاء وأبعاد صورة SVG الناتجة.

```java
System.out.println(options.getErrorReport());
System.out.println();
System.out.println("Size: " + size.getWidth() + "x" + size.getHeight());
```

باتباع هذه الخطوات، يمكنك عرض أشكال LaTeX إلى SVG بسلاسة باستخدام Aspose.TeX لـ Java.

## خاتمة

يمكن تحقيق عرض أرقام LaTeX إلى SVG في Java بكفاءة باستخدام Aspose.TeX. يرشدك هذا الدليل خطوة بخطوة خلال العملية، بدءًا من إعداد خيارات العرض وحتى عرض النتائج النهائية. قم بتجربة أشكال LaTeX المختلفة لتعزيز فهمك وتطبيقك لهذه الميزة القوية.

## الأسئلة الشائعة

### س1: هل يمكنني تقديم أشكال LaTeX بتعبيرات رياضية معقدة باستخدام Aspose.TeX؟

ج1: نعم، يدعم Aspose.TeX عرض أشكال LaTeX ذات التعبيرات الرياضية المعقدة.

### س2: هل يتوفر ترخيص مؤقت لـ Aspose.TeX لـ Java؟

 ج2: نعم، يمكنك الحصول على ترخيص مؤقت من[هنا](https://purchase.aspose.com/temporary-license/).

### س3: كيف يمكنني الحصول على دعم Aspose.TeX لـ Java؟

 ج3: قم بزيارة[منتدى Aspose.TeX](https://forum.aspose.com/c/tex/47) للدعم المجتمعي.

### س4: ما هي التنسيقات التي يمكنني تحويل أشكال LaTeX إليها باستخدام Aspose.TeX؟

ج4: يسمح Aspose.TeX بالتحويل إلى تنسيقات مختلفة، بما في ذلك SVG وPNG والمزيد.

### س5: أين يمكنني العثور على الوثائق التفصيلية لـ Aspose.TeX for Java؟

 ج5: راجع[وثائق Aspose.TeX](https://reference.aspose.com/tex/java/) للحصول على معلومات شاملة.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
