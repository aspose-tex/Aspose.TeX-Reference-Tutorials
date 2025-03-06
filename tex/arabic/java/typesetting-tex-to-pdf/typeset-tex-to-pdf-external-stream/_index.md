---
title: Typeset TeX إلى PDF في Java باستخدام دفق خارجي
linktitle: Typeset TeX إلى PDF في Java باستخدام دفق خارجي
second_title: Aspose.TeX جافا API
description: تعرف على كيفية طباعة TeX على PDF في Java باستخدام التدفقات الخارجية باستخدام Aspose.TeX. اتبع دليلنا خطوة بخطوة للتكامل السلس.
weight: 10
url: /ar/java/typesetting-tex-to-pdf/typeset-tex-to-pdf-external-stream/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Typeset TeX إلى PDF في Java باستخدام دفق خارجي

## مقدمة

في عالم تطوير Java، يعد إنشاء ملفات PDF من ملفات TeX مطلبًا شائعًا. يعمل Aspose.TeX for Java على تبسيط هذه العملية، مما يوفر حلاً فعالاً لتنضيد TeX إلى PDF. في هذا البرنامج التعليمي، سنرشدك خلال خطوات التنضيد TeX إلى PDF باستخدام التدفقات الخارجية. وفي النهاية، سيكون لديك فهم واضح لكيفية تنفيذ هذه العملية بسلاسة في تطبيقات Java الخاصة بك.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

- Aspose.TeX لـ Java: تأكد من تثبيت مكتبة Aspose.TeX لـ Java. يمكنك تنزيله من[Aspose.TeX لتوثيق جافا](https://reference.aspose.com/tex/java/).

- أدلة الإدخال والإخراج: قم بإعداد أدلة الإدخال والإخراج. يمكنك استخدام رابط التنزيل المقدم للحصول على الملفات الضرورية.

## حزم الاستيراد

ابدأ باستيراد الحزم المطلوبة إلى مشروع Java الخاص بك:

```java
package com.aspose.tex.TypesetPdfWrittenToExternalStream;

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

## الخطوة 1: افتح تدفقات الإدخال والإخراج

ابدأ بفتح التدفقات لأرشيف ZIP للإدخال (يعمل كدليل عمل الإدخال) وأرشيف ZIP للإخراج (يعمل كدليل عمل الإخراج). تأكد من استبدال "دليل الإدخال الخاص بك" و"دليل المخرجات" بمسارات الدليل الفعلية.

```java
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "typeset-pdf-to-external-stream.zip");
```

## الخطوة 2: تكوين TeXOptions

قم بإنشاء كائن TeXOptions وقم بتكوينه وفقًا لمتطلباتك. قم بتعيين اسم المهمة ودليل عمل الإدخال ودليل عمل الإخراج والخيارات الأخرى.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("typeset-pdf-to-external-stream");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
options.setSaveOptions(new PdfSaveOptions());
```

## الخطوة 3: تحويل TeX إلى PDF

الآن، افتح دفقًا لكتابة ملف PDF الناتج إلى الموقع المطلوب. يمكنك اختيار كتابته إلى ملف محلي أو مباشرة إلى أرشيف ZIP الناتج.

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + "file-name.pdf");
try {
    new TeXJob("hello-world", new PdfDevice(stream), options).run();
} finally {
    stream.close();
}
```

## الخطوة 4: الانتهاء من إخراج أرشيف ZIP

قم بإنهاء أرشيف ZIP الناتج لإكمال عملية التنضيد.

```java
((OutputZipDirectory)options.getOutputWorkingDirectory()).finish();
```

## خاتمة

تهانينا! لقد نجحت في كتابة TeX إلى PDF في Java باستخدام تدفقات خارجية مع Aspose.TeX. يوفر هذا البرنامج التعليمي أساسًا قويًا لدمج تحويل TeX إلى PDF في تطبيقات Java الخاصة بك بسلاسة.

## الأسئلة الشائعة

### س1: هل يمكنني تخصيص اسم ملف PDF الناتج؟

 ج1: نعم، يمكنك تعديل`options.setJobName("typeset-pdf-to-external-stream")` لتعيين اسم الوظيفة المطلوبة.

### س2: كيف يمكنني استكشاف المشكلات الشائعة وإصلاحها أثناء التنضيد؟

 ج2: قم بزيارة[منتدى Aspose.TeX](https://forum.aspose.com/c/tex/47) لدعم المجتمع ومساعدته.

### س3: هل تتوفر نسخة تجريبية مجانية من Aspose.TeX لـ Java؟

 ج3: نعم، يمكنك الوصول إلى النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).

### س4: أين يمكنني العثور على وثائق وأمثلة إضافية؟

 ج4: اكتشف الشامل[وثائق Aspose.TeX](https://reference.aspose.com/tex/java/) للحصول على معلومات مفصلة.

### س5: هل يمكنني الحصول على ترخيص مؤقت لـ Aspose.TeX؟

 ج5: نعم، يمكنك طلب ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
