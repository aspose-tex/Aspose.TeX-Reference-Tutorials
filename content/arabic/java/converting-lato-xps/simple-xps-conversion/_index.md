---
title: قم بتحويل LaTeX إلى تنسيق XPS في Java بسهولة
linktitle: قم بتحويل LaTeX إلى تنسيق XPS في Java بسهولة
second_title: Aspose.TeX جافا API
description: قم بتحويل LaTeX إلى XPS بسهولة في Java باستخدام Aspose.TeX. اتبع دليلنا خطوة بخطوة للتكامل السلس.
type: docs
weight: 10
url: /ar/java/converting-lato-xps/simple-xps-conversion/
---
## مقدمة

هل تتطلع إلى تحويل مستندات LaTeX إلى تنسيق XPS بسلاسة في تطبيقات Java الخاصة بك؟ يوفر Aspose.TeX for Java حلاً قويًا، مما يسمح لك بتحقيق ذلك بسهولة. في هذا الدليل المفصّل خطوة بخطوة، سنرشدك خلال عملية تحويل LaTeX إلى XPS باستخدام Aspose.TeX.

## المتطلبات الأساسية

قبل الغوص في عملية التحويل، تأكد من توفر المتطلبات الأساسية التالية:

- تم تثبيت Java Development Kit (JDK) على نظامك.
-  تم تنزيل Aspose.TeX لمكتبة Java. يمكنك العثور على رابط التحميل[هنا](https://releases.aspose.com/tex/java/).

## حزم الاستيراد

للبدء، قم باستيراد الحزم اللازمة لمشروع Java الخاص بك. تأكد من تضمين مكتبة Aspose.TeX في تبعيات مشروعك.

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

لنقم الآن بتقسيم عملية التحويل إلى خطوات متعددة باستخدام أمثلة التعليمات البرمجية المتوفرة.

## الخطوة 1: تعيين أدلة الإدخال والإخراج

```java
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

حدد الدلائل التي يوجد بها ملف إدخال LaTeX الخاص بك والمكان الذي تريد حفظ ملف XPS المحول فيه.

## الخطوة 2: تكوين خيارات TeX

قم بتكوين خيارات متنوعة لتخصيص عملية التحويل وفقًا لاحتياجاتك.

```java
options.setInteraction(Interaction.NonstopMode);
options.setDateTime(new GregorianCalendar(2022, Calendar.DECEMBER, 18).getTime());
options.ignoreMissingPackages(true);
options.noLigatures(true);
options.repeat(true);
```

اضبط وضع التفاعل والتاريخ في العنوان والتعامل مع الحزم المفقودة والأحرف المركبة والتكرار حسب الحاجة.

## الخطوة 3: تهيئة خيارات حفظ XPS

```java
options.setSaveOptions(new XpsSaveOptions());
```

قم بتهيئة خيارات الحفظ بتنسيق XPS.

## الخطوة 4: تخصيص خيارات حفظ XPS

```java
options.getSaveOptions().rasterizeFormulas(true);
options.getSaveOptions().rasterizeIncludedGraphics(true);
options.getSaveOptions().subsetFonts(true);
```

قم بتخصيص خيارات حفظ XPS للتحكم في تحويل الصيغ والرسومات المضمنة وإعداد الخطوط الفرعية.

## الخطوة 5: تشغيل تحويل LaTeX إلى XPS

```java
new TeXJob("Your Input Directory" + "sample.ltx", new XpsDevice(), options).run();
```

ابدأ عملية التحويل عن طريق تشغيل مهمة TeX باستخدام ملف الإدخال المحدد وجهاز الإخراج (XpsDevice) والخيارات.

## أمثلة إضافية

اكتشف طرق تحويل إضافية باستخدام مصادر إدخال مختلفة:

### استخدم تدفق الإدخال

```java
new TeXJob(new ByteArrayInputStream(
    "\\documentclass{article} \\begin{document} Hello, World! \\end{document}".getBytes("ASCII")),
    new XpsDevice(), options).run();
```

### استخدم محطة الإدخال الرئيسية

```java
new TeXJob(new XpsDevice(), options).run();
```

## خاتمة

مع Aspose.TeX لـ Java، أصبح تحويل LaTeX إلى XPS أمرًا في غاية السهولة. اتبع هذه الخطوات، وقم بتخصيص الخيارات، ودمج هذه الوظيفة بسلاسة في تطبيقات Java الخاصة بك.

## الأسئلة الشائعة

### س1: هل يمكنني تحويل مستندات LaTeX ذات الصيغ المعقدة باستخدام Aspose.TeX؟

ج1: بالتأكيد! يتعامل Aspose.TeX مع الصيغ المعقدة بسلاسة أثناء عملية التحويل.

### س2: هل هناك إصدار تجريبي متاح لـ Aspose.TeX لـ Java؟

 ج2: نعم، يمكنك العثور على النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).

### س3: كيف يمكنني الحصول على الدعم لـ Aspose.TeX؟

 ج3: قم بزيارة[منتدى Aspose.TeX](https://forum.aspose.com/c/tex/47) للمساعدة والدعم المجتمعي.

### س4: هل التراخيص المؤقتة متاحة لـ Aspose.TeX؟

 ج4: نعم، يمكنك الحصول على تراخيص مؤقتة[هنا](https://purchase.aspose.com/temporary-license/).

### س5: أين يمكنني العثور على الوثائق الخاصة بـ Aspose.TeX؟

 ج5: راجع[توثيق](https://reference.aspose.com/tex/java/) للحصول على إرشادات شاملة.