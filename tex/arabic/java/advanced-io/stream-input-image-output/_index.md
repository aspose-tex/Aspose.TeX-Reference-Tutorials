---
title: دفق الإدخال، إخراج الصورة، والإدخال الطرفي في جافا
linktitle: دفق الإدخال، إخراج الصورة، والإدخال الطرفي في جافا
second_title: Aspose.TeX جافا API
description: تعلم إدخال التدفق وإخراج الصور والإدخال الطرفي في Java باستخدام Aspose.TeX. برنامج تعليمي شامل للتكامل السلس.
weight: 11
url: /ar/java/advanced-io/stream-input-image-output/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# دفق الإدخال، إخراج الصورة، والإدخال الطرفي في جافا

## مقدمة

Aspose.TeX for Java هي مكتبة قوية تسمح للمطورين بالعمل مع ملفات TeX، مما يسهل إنشاء المستندات عالية الجودة ومعالجتها. في هذا البرنامج التعليمي، سوف نستكشف عملية أخذ مدخلات التدفق، وإنشاء مخرجات الصور، والتعامل مع الإدخال الطرفي في Java باستخدام Aspose.TeX.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:

- الفهم الأساسي لبرمجة جافا.
- تم تثبيت Java Development Kit (JDK) على جهازك.
- الإلمام بمكتبة Aspose.TeX.
-  تم تثبيت Aspose.TeX لـ Java. يمكنك تنزيله[هنا](https://releases.aspose.com/tex/java/).

## حزم الاستيراد

تأكد من أن لديك الحزم المطلوبة المستوردة لهذا البرنامج التعليمي. يوضح مقتطف الكود التالي عمليات الاستيراد الضرورية:

```java
package com.aspose.tex.StreamInputImageOutputAndTerminalInput;

import java.io.ByteArrayInputStream;
import java.io.IOException;

import com.aspose.tex.InputConsoleTerminal;
import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputConsoleTerminal;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.ImageDevice;
import com.aspose.tex.rendering.PngSaveOptions;
```

## الخطوة 1: إعداد خيارات التحويل

قم بإنشاء خيارات تحويل TeX باستخدام تنسيق ObjectTeX الافتراضي عند امتداد محرك ObjectTeX. حدد اسم الوظيفة، ودليل عمل الإدخال، ودليل عمل الإخراج.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("stream-in-image-out");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

## الخطوة 2: تحديد محطات الإدخال والإخراج

حدد وحدة التحكم لتكون طرفي الإدخال والإخراج.

```java
options.setTerminalIn(new InputConsoleTerminal());
options.setTerminalOut(new OutputConsoleTerminal());
```

## الخطوة 3: تحديد خيارات الحفظ

تحديد خيارات الحفظ لصورة الإخراج. في هذا المثال، نستخدم تنسيق PNG بدقة 300 نقطة في البوصة.

```java
PngSaveOptions pngOptions = new PngSaveOptions();
pngOptions.setResolution(300);
options.setSaveOptions(pngOptions);
```

## الخطوة 4: إنشاء جهاز الصور

قم بإنشاء جهاز صورة لإنشاء صورة الإخراج.

```java
ImageDevice device = new ImageDevice();
```

## الخطوة 5: تشغيل المهمة

قم بتشغيل مهمة TeX باستخدام الإدخال والجهاز والخيارات المحددة.

```java
TeXJob job = new TeXJob(new ByteArrayInputStream(
        "\\hrule height 10pt width 95pt\\vskip10pt\\hrule height 5pt".getBytes("ASCII")),
        device, options);
job.run();
```

## الخطوة 6: التعامل مع الإدخال الطرفي

عندما تطالبك وحدة التحكم بالإدخال، اكتب "ABC"، ثم اضغط على Enter، ثم اكتب "\end" واضغط على Enter مرة أخرى.

```java
// لمزيد من الإخراج لتبدو جيدة.
options.getTerminalOut().getWriter().newLine();
```

## الخطوة 7: استرداد إخراج الصورة

يمكنك الحصول على الصور في شكل مجموعة من صفائف البايت.

```java
byte[][] result = device.getResult();
```

يكمل هذا الدليل خطوة بخطوة لإدخال الدفق وإخراج الصورة والإدخال الطرفي في Java باستخدام Aspose.TeX.

## خاتمة

يعمل Aspose.TeX for Java على تبسيط عملية التعامل مع مستندات TeX، مما يوفر ميزات قوية لإدخال التدفق وإخراج الصور والتفاعل الطرفي. باتباع هذا البرنامج التعليمي، تعلمت كيفية دمج هذه الوظائف بسلاسة في تطبيقات Java الخاصة بك.

## الأسئلة الشائعة

### س1: هل Aspose.TeX متوافق مع مكتبات Java الأخرى؟

ج1: نعم، يمكن دمج Aspose.TeX بسلاسة مع مكتبات Java الأخرى لتحسين الأداء الوظيفي.

### س2: هل يمكنني تخصيص تنسيق الصورة الناتجة؟

ج2: بالتأكيد! يوفر Aspose.TeX خيارات متنوعة لحفظ الصور الناتجة، مما يسمح بالتخصيص بناءً على تفضيلاتك.

### س3: هل يوجد منتدى مجتمعي لدعم Aspose.TeX؟

 ج3: نعم، يمكنك العثور على الدعم والتفاعل مع المجتمع على[منتدى Aspose.TeX](https://forum.aspose.com/c/tex/47).

### س4: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.TeX؟

 ج4: يمكنك الحصول على ترخيص مؤقت من[هنا](https://purchase.aspose.com/temporary-license/).

### س5: هل هناك أي موارد إضافية لتوثيق Aspose.TeX؟

 ج5: اكتشف الشامل[توثيق](https://reference.aspose.com/tex/java/) للحصول على رؤى وأمثلة مفصلة.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
