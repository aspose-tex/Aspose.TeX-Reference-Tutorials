---
date: 2025-12-13
description: تعلم كيفية تحويل LaTeX إلى PNG في Java باستخدام Aspose.TeX. يوضح لك هذا
  الدليل كيفية حفظ LaTeX كملف PNG، وتحديد دليل إدخال LaTeX، وإجراء تحويل موثوق من
  LaTeX إلى صورة.
linktitle: Handle LaTeX Input Files from File Systems in Java
second_title: Aspose.TeX Java API
title: تحويل LaTeX إلى PNG – معالجة ملفات إدخال LaTeX من أنظمة الملفات في Java
url: /ar/java/working-with-lainputs/file-system-input/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحويل LaTeX إلى PNG – التعامل مع ملفات إدخال LaTeX من أنظمة الملفات في Java

إذا كنت بحاجة إلى **convert LaTeX to PNG** أثناء العمل مع ملفات مخزنة على نظام ملفات محلي، فقد وصلت إلى المكان الصحيح. في هذا الدرس سنستعرض العملية بالكامل — من إعداد الأدلة المطلوبة إلى تحويل مستند LaTeX إلى صورة PNG — باستخدام مكتبة **Aspose.TeX** للـ Java. في النهاية، ستكون قادرًا على **save LaTeX as PNG**، وتحديد دليل إدخال LaTeX، ودمج التحويل في أي مشروع Java.

## إجابات سريعة
- **What does the tutorial cover?** تحويل ملف LaTeX إلى صورة PNG باستخدام Aspose.TeX.  
- **Do I need a license?** نعم، يلزم وجود ترخيص Aspose.TeX صالح للاستخدام في الإنتاج.  
- **Which Java version works?** أي بيئة تشغيل Java 8+ مدعومة.  
- **Can I change the output format?** نعم، يمكنك استبدال `PngSaveOptions` بصيغ أخرى مثل JPEG أو BMP.  
- **How long does the conversion take?** عادةً أقل من ثانية للمستندات القياسية.

## ما هو “convert latex to png”؟
تشير عبارة “Convert LaTeX to PNG” إلى عملية أخذ ملف مصدر `.tex` وتحويله إلى صورة نقطية (PNG). هذا مفيد عندما تحتاج إلى تضمين صيغ رياضية أو مستندات كاملة في صفحات الويب أو التقارير أو أي بيئة لا تستطيع عرض LaTeX مباشرة.

## لماذا تستخدم Aspose.TeX لتحويل LaTeX إلى صورة؟
توفر Aspose.TeX محرك **pure‑Java** يفهم كامل بنية TeX/LaTeX، يدعم تحميل الحزم، ويتيح تحكمًا دقيقًا في خيارات العرض. مقارنةً بأدوات سطر الأوامر العشوائية، يندمج مباشرةً في قاعدة شفرة Java الخاصة بك، يلغي الاعتماديات الخارجية، ويمنحك وصولًا برمجيًا إلى إعدادات الإخراج مثل DPI، لون الخلفية، وصيغة الصورة.

## المتطلبات المسبقة

قبل المتابعة، تأكد من وجود ما يلي:

1. **Aspose.TeX for Java** – حمّله من [here](https://releases.aspose.com/tex/java/).  
2. **ترخيص صالح** – احصل على ترخيص مؤقت من [here](https://purchase.aspose.com/temporary-license/).  
3. **أدلة عمل** – أنشئ مجلدات منفصلة لملفات `.tex` الخاصة بك (بما في ذلك أي حزم مطلوبة) ولإخراج صور PNG المولدة.

## استيراد الحزم

أضف الاستيرادات التالية في أعلى ملف Java المصدر الخاص بك:

```java
package com.aspose.tex.LaTeXRequiredInputFs;

import java.io.IOException;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.ImageDevice;
import com.aspose.tex.rendering.PngSaveOptions;

import util.Utils;
```

هذه الفئات تمنحك إمكانية التعامل مع نظام الملفات، تكوين التحويل، وعرض PNG.

## دليل خطوة بخطوة

### الخطوة 1: تعيين ترخيص Aspose.TeX
يجب تعيين الترخيص أولاً، وإلا سيعمل المكتبة في وضع التقييم.

```java
Utils.setLicense();
```

### الخطوة 2: تكوين خيارات التحويل
أنشئ كائن `TeXOptions` يخبر المحرك بمعالجة المصدر كمستند **Object LaTeX**.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectLaTeX());
```

### الخطوة 3: تحديد دليل العمل للإخراج
أخبر Aspose.TeX أين يكتب ملفات PNG المولدة.

```java
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### الخطوة 4: تحديد دليل الإدخال المطلوب
إذا كان مصدر LaTeX يعتمد على حزم خارجية (مثل `amsmath.sty`)، وجه المحرك إلى المجلد الذي يحتوي عليها.

```java
options.setRequiredInputDirectory(new InputFileSystemDirectory("Your Input Directory" + "packages"));
```

### الخطوة 5: تهيئة خيارات حفظ PNG
هنا نختار PNG كصيغة إخراج. يمكنك تعديل DPI أو الضغط، أو التحويل إلى صيغة أخرى باستخدام فئة `SaveOptions` مختلفة.

```java
options.setSaveOptions(new PngSaveOptions());
```

### الخطوة 6: تشغيل مهمة التحويل
أخيرًا، شغّل التحويل. الوسيط الأول هو المسار الكامل لملف `.tex` الذي يتضمن أي مراجع إدخال مطلوبة.

```java
new TeXJob("Your Input Directory" + "required-input-fs.tex", new ImageDevice(), options).run();
```

عند انتهاء المهمة، ستجد تمثيل PNG لمستند LaTeX الخاص بك في دليل الإخراج الذي حددته.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|--------|-----|
| **Missing packages** | ملف `required-input-fs.tex` يشير إلى حزمة غير موجودة في دليل الإدخال. | تأكد من وضع جميع ملفات `.sty` داخل مجلد `packages` وأن `setRequiredInputDirectory` يشير إليه. |
| **Blank output image** | يحتوي مصدر LaTeX على أخطاء تمنع العرض. | شغّل نفس ملف `.tex` عبر مترجم LaTeX قياسي لتحديد الأخطاء، ثم صحّحها. |
| **Incorrect DPI** | قد يكون DPI الافتراضي منخفضًا جدًا للمتطلبات عالية الدقة. | استخدم `options.getSaveOptions().setResolution(300);` قبل تشغيل المهمة (لا حاجة لكتلة كود إضافية). |

## الأسئلة المتكررة

**س: أين يمكنني العثور على وثائق Aspose.TeX؟**  
ج: الوثائق متاحة [here](https://reference.aspose.com/tex/java/).

**س: كيف يمكنني تحميل Aspose.TeX for Java؟**  
ج: يمكنك تحميله [here](https://releases.aspose.com/tex/java/).

**س: أين يمكنني الحصول على دعم Aspose.TeX؟**  
ج: زر منتدى الدعم [here](https://forum.aspose.com/c/tex/47).

**س: هل هناك نسخة تجريبية مجانية؟**  
ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية [here](https://releases.aspose.com/).

**س: كيف يمكنني شراء Aspose.TeX؟**  
ج: خيارات الشراء متاحة [here](https://purchase.aspose.com/buy).

## الخلاصة

لقد تعلمت الآن كيفية **convert LaTeX to PNG** باستخدام Aspose.TeX، وكيفية **specify the LaTeX input directory**، وكيفية **save LaTeX as PNG** ببضع أسطر من كود Java فقط. لا تتردد في تجربة خيارات عرض مختلفة، دمج العملية في سير عمل أكبر، أو التحويل إلى صيغ صور أخرى حسب الحاجة.

---

**Last Updated:** 2025-12-13  
**Tested With:** Aspose.TeX 24.11 for Java  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}