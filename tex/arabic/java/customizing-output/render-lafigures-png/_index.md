---
date: 2025-12-07
description: تعلم كيفية تحويل رسومات LaTeX إلى PNG في Java باستخدام Aspose.TeX – أسهل
  طريقة لإنشاء PNG من LaTeX. اتبع هذا الدليل خطوة بخطوة.
linktitle: How to Render LaTeX Figures to PNG in Java
second_title: Aspose.TeX Java API
title: كيفية تحويل رسومات LaTeX إلى PNG في Java
url: /ar/java/customizing-output/render-lafigures-png/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تحويل رسومات LaTeX إلى PNG في Java

## المقدمة

إذا كنت تتساءل **كيف يتم تحويل LaTeX** إلى صورة نقطية لتطبيقات Java الخاصة بك، فقد وجدت المكان المناسب. قد يكون تحويل *latex figure to png* عملية معقدة، خاصة عندما تحتاج إلى مخرجات عالية الجودة وتحكم كامل في خيارات التحويل. تجعل Aspose.TeX for Java سير العمل بأكمله بسيطًا، حيث يمكنك إنشاء PNG من LaTeX ببضع أسطر من الشيفرة فقط. في هذا البرنامج التعليمي سنستعرض العملية بالكامل—من إعداد البيئة إلى عرض الصورة النهائية—حتى تتمكن من دمج رسومات LaTeX الجميلة مباشرةً في مشاريع Java الخاصة بك.

## إجابات سريعة
- **ما المكتبة التي يجب استخدامها؟** Aspose.TeX for Java
- **هل يمكنني إنشاء PNG من LaTeX؟** نعم، مع تحكم كامل في الدقة
- **هل أحتاج إلى ترخيص للإنتاج؟** الترخيص التجاري مطلوب؛ يتوفر نسخة تجريبية مجانية
- **ما نسخة Java المدعومة؟** Java 8 وما فوق
- **كم يستغرق تنفيذ العملية؟** حوالي 10‑15 دقيقة لإنشاء رسم أساسي

## ما هو “how to render latex” في Java؟

يعني تحويل LaTeX في Java تحويل لغة الترميز المستخدمة في المستندات العلمية إلى تنسيق بصري (مثل PNG) يمكن عرضه في واجهات المستخدم الرسومية، التقارير، أو صفحات الويب. توفر Aspose.TeX محركًا عالي الأداء يقوم بتحليل شفرة LaTeX، ورسم الرسومات، وإخراجها كصور نقطية دون الحاجة إلى تثبيت LaTeX خارجي.

## لماذا نولد PNG من LaTeX باستخدام Aspose.TeX؟

- **بدون تبعيات خارجية** – كل شيء يعمل داخل JVM.
- **تحكم دقيق** في الدقة، التكبير، لون الخلفية، ومقدمة المستند.
- **معالجة أخطاء قوية** – سجلات مفصلة تساعدك على استكشاف أخطاء LaTeX.
- **متعدد المنصات** – يعمل على Windows وLinux وmacOS.

## المتطلبات المسبقة

قبل أن نغوص في الشيفرة، تأكد من وجود ما يلي:

- Java Development Kit (JDK) 8 أو أحدث مثبت.
- مكتبة Aspose.TeX for Java محملة من [صفحة التحميل الرسمية](https://releases.aspose.com/tex/java/).
- إلمام أساسي بصياغة LaTeX (مثل `\begin{picture}...\end{picture}`).

## استيراد الحزم

أولاً، استورد الفئات التي ستحتاجها من Aspose.TeX API. تتيح لك هذه الاستيرادات الوصول إلى محول PNG وخيارات التكوين الخاصة به.

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

## الخطوة 1: ضبط خيارات التحويل  

أنشئ كائنًا من `PngFigureRendererOptions` وقم بتكوين دقة الإخراج، عامل التكبير، لون الخلفية، وإعدادات مفيدة أخرى.

```java
PngFigureRendererOptions options = new PngFigureRendererOptions();
options.setResolution(96);
options.setPreamble("\\usepackage{pict2e}");
options.setScale(3000);
options.setBackgroundColor(Color.WHITE);
options.setLogStream(new ByteArrayOutputStream());
options.showTerminal(true);
```

## الخطوة 2: تعريف رسم LaTeX  

ضع شفرة LaTeX التي تريد تحويلها داخل سلسلة `String` في Java. يمكنك استبدال العنصر النائب بأي *latex figure to png* تحتاجه—المعادلات المعقدة، مخططات الدوائر، أو الرسومات المخصصة تعمل بنفس الطريقة.

```java
String latexFigure = "\\setlength{\\unitlength}{0.8cm}\r\n" +
                    "\\begin{picture}(6,5)\r\n" +
                    "\\thicklines\r\n" +
                    // ... (your LaTeX figure content)
                    "\\end{picture}";
```

## الخطوة 3: التحويل والحفظ  

حوّل سلسلة LaTeX إلى صورة PNG واكتبها إلى القرص. عدّل مسار الإخراج ليتناسب مع بنية مشروعك.

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

بعد التحويل، يمكنك فحص تقرير الأخطاء (إن وجد) وأبعاد الصورة المولدة.

```java
System.out.println(options.getErrorReport());
System.out.println();
System.out.println("Size: " + size.getWidth() + "x" + size.getHeight());
// ExEnd:PngLaTeXFigureRenderer
```

## المشكلات الشائعة والنصائح

- **حزم مفقودة في المقدمة** – إذا كان الرسم يستخدم حزمة LaTeX (مثل `pict2e`)، تأكد من إضافتها عبر `options.setPreamble()`.
- **الدقة مقابل التكبير** – `setResolution` يتحكم في DPI، بينما `setScale` يؤثر على حجم الصورة المرسومة. اضبطهما معًا للحصول على الجودة المرغوبة.
- **تيار السجل** – `ByteArrayOutputStream` يلتقط سجلات تجميع LaTeX؛ راجه عندما تواجه أخطاء في التحويل.

## الخاتمة

أصبح لديك الآن سير عمل كامل وجاهز للإنتاج **كيفية تحويل رسومات LaTeX** إلى PNG في Java باستخدام Aspose.TeX. من خلال تعديل خيارات التحويل، يمكنك إنشاء صور PNG عالية الجودة للتقارير، لوحات التحكم، أو أي واجهة مستخدم مبنية على Java.

## الأسئلة المتكررة

**س1: هل يمكنني استخدام Aspose.TeX for Java مع مكتبات Java أخرى؟**  
ج: نعم، يتكامل Aspose.TeX بسلاسة مع مكتبات مثل Apache POI، iText، أو أي إطار عمل رسومي مخصص.

**س2: هل تتوفر نسخة تجريبية مجانية لـ Aspose.TeX for Java؟**  
ج: بالتأكيد—حمّل نسخة تجريبية من [صفحة تحميل Aspose.TeX](https://releases.aspose.com/).

**س3: كيف يمكنني الحصول على دعم لـ Aspose.TeX for Java؟**  
ج: زر المنتدى الرسمي لـ [Aspose.TeX](https://forum.aspose.com/c/tex/47) للحصول على مساعدة المجتمع والدعم الرسمي.

**س4: ما هو الترخيص المؤقت، وكيف يمكنني الحصول عليه؟**  
ج: الترخيص المؤقت يتيح لك تقييم المنتج لفترة محدودة. اطلبه من [صفحة الترخيص المؤقت](https://purchase.aspose.com/temporary-license/).

**س5: أين يمكنني العثور على الوثائق التفصيلية لـ Aspose.TeX for Java؟**  
ج: مرجع API الكامل متوفر [هنا](https://reference.aspose.com/tex/java/).

---

**آخر تحديث:** 2025-12-07  
**تم الاختبار مع:** Aspose.TeX for Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}