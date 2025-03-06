---
title: تجاوز اسم الوظيفة واكتب الإخراج الطرفي إلى Zip في Java
linktitle: تجاوز اسم الوظيفة واكتب الإخراج الطرفي إلى Zip في Java
second_title: Aspose.TeX جافا API
description: تعرف على كيفية تجاوز أسماء الوظائف وكتابة مخرجات الوحدة الطرفية إلى ZIP في Java باستخدام Aspose.TeX. برنامج تعليمي شامل لمطوري جافا.
weight: 11
url: /ar/java/customizing-output/override-job-name-zip/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تجاوز اسم الوظيفة واكتب الإخراج الطرفي إلى Zip في Java

## مقدمة

في عالم تطوير Java، يبرز Aspose.TeX كأداة قوية للتعامل مع تنسيقات ملفات TeX. في هذا البرنامج التعليمي، سنتعمق في سيناريو محدد - تجاوز أسماء الوظائف وكتابة مخرجات الوحدة الطرفية في ملف مضغوط. سيرشدك هذا الدليل خطوة بخطوة خلال العملية باستخدام Aspose.TeX لـ Java.

## المتطلبات الأساسية

قبل أن نبدأ في هذا البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- المعرفة الأساسية ببرمجة جافا.
-  تم تثبيت Aspose.TeX لجافا. إذا لم يكن الأمر كذلك، يمكنك تنزيله من[موقع أسبوز](https://releases.aspose.com/tex/java/).
- فهم كيفية إعداد بيئة تطوير Java.

## حزم الاستيراد

ابدأ باستيراد الحزم الضرورية إلى مشروع Java الخاص بك. وهذا يضمن أن لديك إمكانية الوصول إلى وظائف Aspose.TeX المطلوبة للمهمة.

```java
package com.aspose.tex.OverridenJobNameAndTerminalOutputWrittenToZip;

import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.io.OutputStream;

import com.aspose.tex.InputZipDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.OutputZipDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.PdfDevice;
import com.aspose.tex.rendering.PdfSaveOptions;

import util.Utils;
```

## الخطوة 1: افتح أرشيفات ZIP

أولاً، افتح دفقًا على أرشيف ZIP الذي سيكون بمثابة دليل عمل الإدخال. هذا هو الأرشيف الذي ستتم معالجة بياناتك منه.

```java
// افتح دفقًا على أرشيف ZIP للإدخال
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
```

## الخطوة 2: افتح أرشيف ZIP للإخراج

بعد ذلك، افتح الدفق على أرشيف ZIP الذي سيكون بمثابة دليل عمل الإخراج. هذا هو المكان الذي سيتم فيه كتابة الإخراج الطرفي.

```java
// افتح دفقًا على أرشيف ZIP الناتج
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "terminal-out-to-zip.zip");
```

## الخطوة 3: ضبط خيارات التحويل

قم بإنشاء خيارات تحويل لتنسيق ObjectTeX الافتراضي عند امتداد محرك ObjectTeX. حدد اسم المهمة وأدلة عمل أرشيف ZIP لكل من الإدخال والإخراج.

```java
// قم بإنشاء خيارات TeX لتنسيق ObjectTeX
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("terminal-output-to-zip");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
```

## الخطوة 4: تحديد الإخراج الطرفي

 حدد أنه يجب كتابة الإخراج الطرفي إلى ملف في دليل عمل الإخراج. سيكون اسم الملف`<job_name>.trm`.

```java
// تحديد إعدادات الإخراج الطرفية
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

## الخطوة 5: تحديد خيارات الحفظ وتشغيل المهمة

حدد خيارات الحفظ، مثل خيارات حفظ PDF في هذه الحالة. قم بتشغيل مهمة TeX لتنفيذ التحويل.

```java
// تحديد خيارات الحفظ وتشغيل المهمة
options.setSaveOptions(new PdfSaveOptions());
new TeXJob("hello-world", new PdfDevice(), options).run();
```

## الخطوة 6: الانتهاء من إخراج أرشيف ZIP

بعد اكتمال المهمة، قم بإنهاء أرشيف ZIP الناتج لضمان الإكمال الصحيح.

```java
// قم بإنهاء أرشيف ZIP الناتج
((OutputZipDirectory) options.getOutputWorkingDirectory()).finish();
```

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية تجاوز أسماء المهام وكتابة المخرجات الطرفية إلى ملف ZIP في Java باستخدام Aspose.TeX. تضيف هذه الوظيفة القوية المرونة والكفاءة إلى مشاريع تطوير Java الخاصة بك.

## الأسئلة الشائعة

### س1: ما هو Aspose.TeX؟

ج1: Aspose.TeX هي مكتبة Java تسمح للمطورين بالعمل مع تنسيقات ملفات TeX، مما يوفر وظائف متقدمة لمعالجة المستندات.

### س2: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.TeX؟

 ج2: يمكنك الحصول على ترخيص مؤقت من[هذا الرابط](https://purchase.aspose.com/temporary-license/).

### س3: أين يمكنني العثور على وثائق Aspose.TeX؟

 ج3: الوثائق متاحة[هنا](https://reference.aspose.com/tex/java/).

### س4: هل هناك نسخة تجريبية مجانية من Aspose.TeX؟

 ج4: نعم، يمكنك العثور على النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).

### س5: أين يمكنني طلب الدعم أو طرح الأسئلة حول Aspose.TeX؟

 ج5: قم بزيارة[منتدى Aspose.TeX](https://forum.aspose.com/c/tex/47) للدعم والمناقشات.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
