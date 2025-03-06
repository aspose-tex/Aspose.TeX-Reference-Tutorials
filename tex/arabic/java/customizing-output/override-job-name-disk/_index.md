---
title: تجاوز اسم الوظيفة وكتابة الإخراج الطرفي في Java
linktitle: تجاوز اسم الوظيفة وكتابة الإخراج الطرفي في Java
second_title: Aspose.TeX جافا API
description: استكشف الدليل التفصيلي خطوة بخطوة حول تجاوز أسماء الوظائف وكتابة المخرجات الطرفية باستخدام Aspose.TeX لـ Java. عزز معالجة مستنداتك باستخدام خيارات التخصيص القوية.
weight: 10
url: /ar/java/customizing-output/override-job-name-disk/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تجاوز اسم الوظيفة وكتابة الإخراج الطرفي في Java

## مقدمة

يوفر Aspose.TeX for Java ميزات قوية للعمل مع ملفات TeX، مما يسمح للمطورين بمعالجة وتخصيص معالجة مستندات TeX. في هذا البرنامج التعليمي، سنرشدك خلال عملية تجاوز اسم الوظيفة وكتابة المخرجات الطرفية إلى نظام الملفات باستخدام Aspose.TeX في Java.

## المتطلبات الأساسية

قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

- معرفة عملية ببرمجة جافا.
-  تم تثبيت Aspose.TeX لـ Java. يمكنك تنزيله من[وثائق جافا Aspose.TeX](https://reference.aspose.com/tex/java/).

## حزم الاستيراد

للبدء، قم باستيراد الحزم الضرورية إلى مشروع Java الخاص بك. في ملف Java الخاص بك، قم بتضمين الواردات التالية:

```java
package com.aspose.tex.OverridenJobNameAndTerminalOutputWrittenToDisk;

import java.io.IOException;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

## تجاوز اسم الوظيفة واكتب مخرجات المحطة الطرفية

### الخطوة 1: إنشاء خيارات التحويل

ابدأ بإنشاء خيارات تحويل لتنسيق ObjectTeX الافتراضي بناءً على امتداد محرك ObjectTeX. استخدم مقتطف الكود التالي:

```java
//ExStart:OverrideJobName-WriteTerminalOutputToFileSystem
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

### الخطوة 2: حدد اسم الوظيفة وأدلة العمل

حدد اسم الوظيفة، ودليل عمل الإدخال، ودليل عمل الإخراج. إذا لم يتم تحديد اسم المهمة، فسيتم اعتبار الوسيطة الأولى لمنشئ TeXJob كاسم المهمة. استخدم مقتطف الكود التالي:

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### الخطوة 3: كتابة الإخراج الطرفي لنظام الملفات

 حدد أنه يجب كتابة الإخراج الطرفي إلى ملف في دليل عمل الإخراج. سيكون اسم الملف`<job_name>.trm`. أضف الكود التالي:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### الخطوة 4: تشغيل المهمة

قم بتشغيل مهمة TeX باستخدام الخيارات المحددة واسم الوظيفة. وإليك كيف يمكنك القيام بذلك:

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
// ExEnd:OverrideJobName-WriteTerminalOutputToFileSystem
```

تهانينا! لقد نجحت في تجاوز اسم المهمة وكتابة المخرجات الطرفية إلى نظام الملفات باستخدام Aspose.TeX في Java.

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا كيفية استخدام Aspose.TeX لـ Java لتجاوز اسم المهمة والتقاط مخرجات الوحدة الطرفية. تعمل هذه الميزات على تمكين المطورين من التحكم الدقيق في معالجة مستندات TeX، مما يعزز التخصيص والمرونة.

## الأسئلة الشائعة

### س1: هل يمكنني استخدام Aspose.TeX لـ Java مع مكتبات Java الأخرى؟

ج1: نعم، تم تصميم Aspose.TeX for Java للتكامل بسلاسة مع مكتبات Java الأخرى لتحسين قدرات معالجة المستندات لديك.

### س2: أين يمكنني العثور على دعم لـ Aspose.TeX لـ Java؟

 ج2: قم بزيارة[منتدى Aspose.TeX](https://forum.aspose.com/c/tex/47) لدعم المجتمع والمساعدة في أي مشاكل قد تواجهها.

### س3: هل تتوفر نسخة تجريبية مجانية من Aspose.TeX لـ Java؟

 ج3: نعم، يمكنك الوصول إلى الإصدار التجريبي المجاني من Aspose.TeX لـ Java[هنا](https://releases.aspose.com/).

### س4: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.TeX لـ Java؟

 ج4: اتبع هذا[وصلة](https://purchase.aspose.com/temporary-license/) للحصول على ترخيص مؤقت لأغراض الاختبار والتقييم.

### س5: أين يمكنني شراء Aspose.TeX لـ Java؟

 ج5: قم بزيارة[صفحة الشراء](https://purchase.aspose.com/buy) للحصول على ترخيص Aspose.TeX لـ Java.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
