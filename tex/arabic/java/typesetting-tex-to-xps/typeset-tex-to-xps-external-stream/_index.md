---
date: 2026-02-20
description: تعلم كيفية تحويل TeX إلى XPS في Java باستخدام Aspose.TeX. يوضح لك هذا
  الدليل خطوة بخطوة كيفية تحويل ملفات TeX وإنشاء تدفقات مستندات XPS بكفاءة.
linktitle: How to Convert TeX to XPS in Java with External Stream
second_title: Aspose.TeX Java API
title: كيفية تحويل TeX إلى XPS في Java باستخدام تدفق خارجي
url: /ar/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تحويل TeX إلى XPS في Java باستخدام تدفق خارجي

## المقدمة

إذا كنت بحاجة إلى **تحويل TeX** ملفات إلى مخرجات XPS عالية الجودة من تطبيق Java، فإن Aspose.TeX for Java يجعل المهمة بسيطة. في هذا الدرس ستشاهد بالضبط **كيفية تحويل TeX** إلى مستند XPS باستخدام تدفق إخراج خارجي، وهو مثالي عندما تريد توجيه النتيجة مباشرة إلى استجابة، خدمة تخزين سحابي، أو أي وجهة مخصصة. لنستعرض العملية بالكامل، من إعداد البيئة إلى كتابة ملف XPS النهائي.

## إجابات سريعة
- **ما الذي يغطيه هذا الدرس؟** تحويل TeX إلى XPS باستخدام Aspose.TeX مع تدفق خارجي.  
- **ما المكتبة الأساسية المطلوبة؟** Aspose.TeX for Java.  
- **هل أحتاج إلى ترخيص؟** يلزم ترخيص مؤقت أو كامل للاستخدام في الإنتاج.  
- **هل يمكنني إنشاء تدفقات مستند XPS؟** نعم – المثال يكتب XPS مباشرة إلى `OutputStream`.  
- **ما نسخة Java المدعومة؟** أي JDK 8+ (الدرس يستخدم JDK 11 كمرجع).

## كيفية تحويل TeX إلى XPS باستخدام تدفق خارجي

هذه الفقرة تكرر الكلمة المفتاحية الأساسية في عنوان مخصص، مما يسهل على القراء ومحركات الذكاء الاصطناعي العثور على الحل الدقيق.

## المتطلبات المسبقة

قبل الغوص في الشيفرة، تأكد من أن لديك ما يلي:

- Java Development Kit (JDK): تأكد من تثبيت Java على نظامك. يمكنك تنزيله من [here](https://www.oracle.com/java/technologies/javase-downloads.html).

- Aspose.TeX for Java: قم بتنزيل وتثبيت Aspose.TeX for Java. يمكنك العثور على رابط التنزيل [here](https://releases.aspose.com/tex/java/).

## استيراد الحزم

ابدأ باستيراد الحزم الضرورية لإطلاق رحلتك في تحويل TeX إلى XPS. أدرج المقتطف البرمجي التالي في مشروع Java الخاص بك:

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

ابدأ بإنشاء خيارات التحويل لتنسيق ObjectTeX الافتراضي باستخدام الشيفرة التالية:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

هذا يضع الأساس لعملية التنضيد.

## الخطوة 2: تحديد اسم المهمة والمسارات

حدد اسم المهمة واضبط مسارات الإدخال والإخراج العاملة:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

تأكد من استبدال العناصر النائبة مثل "Your Input Directory" بمسارات الدليل الفعلية الخاصة بك.

## الخطوة 3: تكوين مخرجات الطرفية

حدد أن مخرجات الطرفية يجب أن تُكتب إلى ملف في دليل العمل الخاص بالإخراج:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

هذه الخطوة تضمن التقاط سجلات مفصلة للتصحيح.

## الخطوة 4: فتح تدفق الإخراج

افتح تدفقًا لكتابة مستند XPS المنضد:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

استبدل "Your Output Directory" بالمسار المناسب.

## الخطوة 5: تشغيل المهمة

نفّذ مهمة تحويل TeX إلى XPS:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

هذا يكمل العملية، وستجد مستند XPS المُولد في دليل الإخراج المحدد.

## لماذا هذا مهم

استخدام `OutputStream` خارجي يمنحك تحكمًا كاملًا في مكان توجيه بيانات XPS — سواء كنت ترسلها مباشرة إلى عميل ويب، أو تخزنها في سحابة، أو تربطها في خط معالجة آخر. إنه يلغي الحاجة إلى ملفات وسيطة ويقلل من عبء I/O، وهو أمر ذو قيمة خاصة في بيئات عالية الإنتاجية أو بدون خادم.

## المشكلات الشائعة والحلول

| المشكلة | السبب | طريقة الحل |
|-------|----------------|------------|
| **FileNotFoundException** عند فتح التدفق | مسار دليل الإخراج غير صحيح أو غير موجود. | تحقق من المسار، أنشئ الدليل مسبقًا، أو استخدم `Files.createDirectories`. |
| **NullPointerException** على `options.getOutputWorkingDirectory()` | `setOutputWorkingDirectory` لم يتم استدعاؤه أو أعاد `null`. | تأكد من استدعاء `options.setOutputWorkingDirectory` قبل استخدامها. |
| **LicenseException** أثناء التشغيل | التشغيل بدون ترخيص Aspose.TeX صالح. | قم بتطبيق ترخيص مؤقت أو دائم باستخدام `License license = new License(); license.setLicense("Aspose.TeX.lic");`. |

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.TeX for Java مع صيغ مستندات أخرى؟**  
ج: يركز Aspose.TeX أساسًا على معالجة المستندات المتعلقة بـ TeX. بالنسبة للصيغ الأخرى، استكشف مجموعة منتجات Aspose الواسعة.

**س: هل هناك نسخة تجريبية متاحة؟**  
ج: نعم، يمكنك تجربة Aspose.TeX بتحميل النسخة التجريبية المجانية [here](https://releases.aspose.com/).

**س: أين يمكنني العثور على الوثائق الشاملة؟**  
ج: راجع الوثائق [here](https://reference.aspose.com/tex/java/) للحصول على معلومات مفصلة وأمثلة.

**س: كيف أحصل على الدعم أو أطلب المساعدة؟**  
ج: زر منتدى Aspose.TeX [here](https://forum.aspose.com/c/tex/47) للحصول على دعم المجتمع والنقاشات.

**س: هل يمكنني الحصول على ترخيص مؤقت لأغراض الاختبار؟**  
ج: نعم، يمكنك الحصول على ترخيص مؤقت [here](https://purchase.aspose.com/temporary-license/).

## الخلاصة

تهانينا! لقد تعلمت الآن **كيفية تحويل TeX** إلى مستند XPS في Java باستخدام Aspose.TeX وتدفق خارجي. هذه التقنية تمنحك تحكمًا كاملًا في مكان توجيه مخرجات XPS — سواء كان نظام ملفات، استجابة ويب، أو دلو سحابي. لا تتردد في تجربة مصادر TeX مختلفة، تعديل `TeXOptions` للخطوط المخصصة، أو ربط التدفق في خط أنابيب توليد مستندات أكبر.

---

**آخر تحديث:** 2026-02-20  
**تم الاختبار مع:** Aspose.TeX for Java 24.11 (latest at time of writing)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}