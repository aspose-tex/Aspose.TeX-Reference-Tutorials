---
title: تقديم أرقام LaTeX إلى PNG في Java
linktitle: تقديم أرقام LaTeX إلى PNG في Java
second_title: Aspose.TeX جافا API
description: قم بعرض أشكال LaTeX إلى PNG بسهولة في Java باستخدام Aspose.TeX. اتبع هذا الدليل للتكامل السلس.
type: docs
weight: 12
url: /ar/java/customizing-output/render-lafigures-png/
---
## مقدمة

في عالم تطوير Java، قد يكون عرض أشكال LaTeX إلى PNG مهمة صعبة ولكنها أساسية. يأتي Aspose.TeX for Java للإنقاذ بفضل ميزاته القوية، مما يجعل هذه العملية فعالة وسلسة. سيرشدك هذا الدليل خطوة بخطوة خلال العملية الكاملة لعرض أشكال LaTeX إلى PNG باستخدام Aspose.TeX.

## المتطلبات الأساسية

قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

- تم تثبيت Java Development Kit (JDK) على نظامك.
-  تم تنزيل Aspose.TeX لمكتبة Java. يمكنك الحصول عليه من[رابط التحميل](https://releases.aspose.com/tex/java/).
- المعرفة الأساسية ببرمجة LaTeX وJava.

## حزم الاستيراد

للبدء، تحتاج إلى استيراد الحزم الضرورية من Aspose.TeX لـ Java. توفر هذه الحزم الأدوات والوظائف المطلوبة لعرض أشكال LaTeX إلى PNG.

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

## الخطوة 1: ضبط خيارات العرض

قم بإنشاء خيارات العرض، وتعيين المعلمات مثل دقة الصورة، والتمهيد، وعامل القياس، ولون الخلفية، ودفق السجل، ورؤية مخرجات المحطة الطرفية.

```java
PngFigureRendererOptions options = new PngFigureRendererOptions();
options.setResolution(96);
options.setPreamble("\\usepackage{pict2e}");
options.setScale(3000);
options.setBackgroundColor(Color.WHITE);
options.setLogStream(new ByteArrayOutputStream());
options.showTerminal(true);
```

## الخطوة 2: تحديد شكل LaTeX

حدد شكل LaTeX الذي تريد عرضه. يمكن أن يشمل ذلك معادلات رياضية معقدة أو رسوم بيانية أو أي محتوى LaTeX آخر.

```java
String latexFigure = "\\setlength{\\unitlength}{0.8cm}\r\n" +
                    "\\begin{picture}(6,5)\r\n" +
                    "\\thicklines\r\n" +
                    // ... (محتوى شكل LaTeX الخاص بك)
                    "\\end{picture}";
```

## الخطوة 3: العرض والحفظ

قم بتقديم شكل LaTeX إلى صورة PNG واحفظه في دليل الإخراج المحدد.

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + "text-and-formula.png");
try {
    new PngFigureRenderer().render(latexFigure, stream, options, size);
} finally {
    if (stream != null)
        stream.close();
}
```

## الخطوة 4: عرض النتائج

اعرض النتائج، بما في ذلك أي تقارير أخطاء وأبعاد الصورة الناتجة.

```java
System.out.println(options.getErrorReport());
System.out.println();
System.out.println("Size: " + size.getWidth() + "x" + size.getHeight());
// ExEnd:PngLaTeXFigorRenderer
```

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية عرض أشكال LaTeX إلى PNG في Java باستخدام Aspose.TeX. تعمل هذه الأداة القوية على تبسيط العملية، مما يسمح لك بدمج محتوى LaTeX بسلاسة في تطبيقات Java الخاصة بك.

## الأسئلة الشائعة

### س1: هل يمكنني استخدام Aspose.TeX لـ Java مع مكتبات Java الأخرى؟

ج1: نعم، تم تصميم Aspose.TeX for Java للعمل بشكل جيد مع مكتبات Java الأخرى، مما يوفر المرونة في عملية التطوير الخاصة بك.

### س2: هل تتوفر نسخة تجريبية مجانية من Aspose.TeX لـ Java؟

 ج2: نعم، يمكنك الوصول إلى نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).

### س3: كيف يمكنني الحصول على دعم Aspose.TeX لـ Java؟

 ج3: قم بزيارة[منتدى Aspose.TeX](https://forum.aspose.com/c/tex/47) لأي دعم أو استفسار.

### س4: ما هو الترخيص المؤقت وكيف يمكنني الحصول عليه؟

 ج4: يمكنك الحصول على ترخيص مؤقت لـ Aspose.TeX[هنا](https://purchase.aspose.com/temporary-license/).

### س5: أين يمكنني العثور على الوثائق التفصيلية لـ Aspose.TeX for Java؟

 ج5: الوثائق متاحة[هنا](https://reference.aspose.com/tex/java/).