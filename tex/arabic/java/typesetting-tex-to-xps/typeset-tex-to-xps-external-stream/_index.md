---
title: Typeset TeX إلى XPS في Java باستخدام الدفق الخارجي
linktitle: Typeset TeX إلى XPS في Java باستخدام الدفق الخارجي
second_title: Aspose.TeX جافا API
description: تعرف على كيفية كتابة TeX على XPS في Java باستخدام Aspose.TeX. استكشف الإرشادات خطوة بخطوة لمعالجة المستندات بسلاسة.
weight: 10
url: /ar/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Typeset TeX إلى XPS في Java باستخدام الدفق الخارجي

## مقدمة

في عالم تطوير Java، يبرز Aspose.TeX كأداة قوية لتنضيد مستندات TeX إلى تنسيقات مختلفة، بما في ذلك XPS. إذا كنت تتطلع إلى تحسين قدرات معالجة المستندات في تطبيق Java الخاص بك، فهذا البرنامج التعليمي مصمم خصيصًا لك. في هذا الدليل المفصّل خطوة بخطوة، سنرشدك خلال عملية تنضيد TeX إلى XPS باستخدام Aspose.TeX لـ Java مع دفق خارجي.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

-  Java Development Kit (JDK): تأكد من تثبيت Java على نظامك. يمكنك تنزيله من[هنا](https://www.oracle.com/java/technologies/javase-downloads.html).

-  Aspose.TeX لـ Java: قم بتنزيل Aspose.TeX لـ Java وتثبيته. يمكنك العثور على رابط التحميل[هنا](https://releases.aspose.com/tex/java/).

## حزم الاستيراد

ابدأ باستيراد الحزم اللازمة لبدء رحلة تحويل TeX إلى XPS. قم بتضمين مقتطف التعليمات البرمجية التالي في مشروع Java الخاص بك:

```java
package com.aspose.tex.TypesetXpsWrittenToExternalStream;

import java.io.FileOutputStream;
import java.io.IOException;
import java.io.OutputStream;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

## الخطوة 1: تكوين خيارات التحويل

ابدأ بإنشاء خيارات تحويل لتنسيق ObjectTeX الافتراضي باستخدام الكود التالي:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

وهذا يضع الأساس لعملية التنضيد.

## الخطوة 2: حدد اسم الوظيفة والأدلة

حدد اسم الوظيفة وقم بتعيين أدلة عمل الإدخال والإخراج:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

تأكد من استبدال العناصر النائبة مثل "دليل الإدخال الخاص بك" بمسارات الدليل الفعلية.

## الخطوة 3: تكوين الإخراج الطرفي

حدد أنه يجب كتابة مخرجات المحطة الطرفية في ملف في دليل عمل المخرجات:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

تضمن هذه الخطوة التقاط السجلات التفصيلية لتصحيح الأخطاء.

## الخطوة 4: افتح دفق الإخراج

افتح دفقًا لكتابة مستند XPS المنضدي:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

استبدل "دليل الإخراج الخاص بك" بالمسار المناسب.

## الخطوة 5: تشغيل المهمة

تنفيذ مهمة تحويل TeX إلى XPS:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

يؤدي هذا إلى إكمال العملية، وستجد مستند XPS الخاص بك في دليل الإخراج المحدد.

## خاتمة

تهانينا! لقد نجحت في كتابة TeX على XPS في Java باستخدام Aspose.TeX. وهذا يفتح عالمًا من الإمكانيات لمعالجة المستندات في تطبيقات Java الخاصة بك. قم بتجربة ملفات TeX المختلفة واستكشف الميزات المتنوعة التي يقدمها Aspose.TeX.

## الأسئلة الشائعة

### س1: هل يمكنني استخدام Aspose.TeX لـ Java مع تنسيقات المستندات الأخرى؟

ج1: يركز Aspose.TeX بشكل أساسي على معالجة المستندات المتعلقة بـ TeX. للحصول على تنسيقات أخرى، استكشف مجموعة منتجات Aspose الواسعة.

### س2: هل هناك نسخة تجريبية متاحة؟

 ج2: نعم، يمكنك تجربة Aspose.TeX عن طريق تنزيل النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).

### س3: أين يمكنني العثور على وثائق شاملة؟

 ج3: راجع الوثائق[هنا](https://reference.aspose.com/tex/java/) للحصول على معلومات وأمثلة مفصلة.

### س4: كيف يمكنني الحصول على الدعم أو طلب المساعدة؟

 ج4: قم بزيارة منتدى Aspose.TeX[هنا](https://forum.aspose.com/c/tex/47)لدعم المجتمع والمناقشات.

### س5: هل يمكنني الحصول على ترخيص مؤقت لأغراض الاختبار؟

 ج5: نعم، يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
