---
date: 2025-12-07
description: تعلم كيفية تحويل TeX إلى PDF، وتجاوز أسماء الوظائف، وكتابة مخرجات الطرفية
  إلى ملف ZIP باستخدام Aspose.TeX for Java. دليل خطوة بخطوة لمطوري Java.
language: ar
linktitle: Convert TeX to PDF, Override Job Name and Write Terminal Output to ZIP
  in Java
second_title: Aspose.TeX Java API
title: تحويل TeX إلى PDF، تجاوز اسم المهمة وكتابة مخرجات الطرفية إلى ملف ZIP في Java
url: /java/customizing-output/override-job-name-zip/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحويل TeX إلى PDF، تجاوز اسم المهمة وكتابة مخرجات الطرفية إلى ZIP في Java

## المقدمة

إذا كنت بحاجة إلى **تحويل TeX إلى PDF** مع التحكم الكامل في اسم المهمة وسجلات الطرفية، فإن Aspose.TeX for Java يجعل ذلك بسيطًا. في هذا البرنامج التعليمي سنستعرض سيناريو واقعي: تجاوز اسم المهمة، توجيه مخرجات الطرفية إلى أرشيف ZIP، وأخيرًا إنتاج مستند PDF. في النهاية ستحصل على مقتطف شفرة يمكن إعادة استخدامه في أي مشروع Java.

## إجابات سريعة
- **ماذا يحقق هذا البرنامج التعليمي؟** يوضح كيفية تحويل TeX إلى PDF، تعيين اسم مهمة مخصص، والتقاط مخرجات الطرفية في ملف ZIP.  
- **ما المكتبة المطلوبة؟** Aspose.TeX for Java (أحدث إصدار).  
- **هل أحتاج إلى ترخيص؟** ترخيص مؤقت يكفي للتقييم؛ يلزم ترخيص كامل للإنتاج.  
- **ما الملفات الناتجة؟** مستند PDF وملف سجل طرفية `<job_name>.trm` داخل أرشيف ZIP الناتج.  
- **كم يستغرق التنفيذ؟** تقريبًا 10‑15 دقيقة لنسخ الشفرة وتشغيلها.

## ما معنى “تحويل TeX إلى PDF”؟
تحويل TeX إلى PDF يعني أخذ ملف مصدر TeX (أو مجموعة ملفات TeX) وتحويله إلى مستند PDF. توفر Aspose.TeX محركًا عالي الأداء يتعامل مع كامل خط أنابيب تجميع TeX دون الحاجة إلى توزيع LaTeX خارجي.

## لماذا نتجاوز اسم المهمة ونكتب مخرجات الطرفية إلى ZIP؟
- **الوضوح:** يظهر اسم المهمة المخصص في ملفات السجل، مما يسهل التعرف على عمليات التشغيل في خطوط الأنابيب الآلية.  
- **القابلية للنقل:** تخزين مخرجات الطرفية (`*.trm`) داخل ZIP يحافظ على جميع القطع الفنية معًا، وهو مفيد لعمليات CI/CD أو المعالجة السحابية.  
- **التصحيح:** يحتوي سجل الطرفية على رسائل تجميع مفصلة تساعدك على استكشاف أخطاء TeX.

## المتطلبات المسبقة

قبل أن تبدأ، تأكد من وجود ما يلي:

- بيئة تطوير Java تعمل (JDK 8 أو أعلى).  
- Aspose.TeX for Java تم تحميله من [موقع Aspose](https://releases.aspose.com/tex/java/).  
- إلمام أساسي بتدفقات I/O في Java.  

## استيراد الحزم

ابدأ باستيراد الفئات الضرورية. سيمكنك ذلك من الوصول إلى API الخاص بـ Aspose.TeX وأدوات I/O القياسية في Java.

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

## الخطوة 1: فتح أرشيف ZIP الإدخال

نفتح أولاً تدفقًا يشير إلى ملف ZIP الذي يحتوي على ملفات مصدر TeX. يعمل هذا الأرشيف كـ **دليل عمل الإدخال** لمهمة التحويل.

```java
// Open a stream on the input ZIP archive
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
```

## الخطوة 2: فتح أرشيف ZIP الإخراج

بعد ذلك، ننشئ تدفقًا لملف ZIP الذي سيستقبل PDF الناتج وسجل الطرفية. هذا هو **دليل عمل الإخراج**.

```java
// Open a stream on the output ZIP archive
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "terminal-out-to-zip.zip");
```

## الخطوة 3: ضبط خيارات التحويل (بما في ذلك اسم المهمة)

هنا نقوم بتكوين خيارات التحويل لتنسيق ObjectTeX، تحديد اسم مهمة مخصص، وربط أدلة ZIP الإدخال والإخراج.

```java
// Create TeX options for ObjectTeX format
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("terminal-output-to-zip");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
```

## الخطوة 4: توجيه مخرجات الطرفية إلى ملف داخل ZIP

نخبر Aspose.TeX بكتابة مخرجات الطرفية إلى ملف باسم `<job_name>.trm` داخل أرشيف ZIP الإخراج.

```java
// Specify terminal output settings
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

## الخطوة 5: تعريف خيارات الحفظ وتشغيل المهمة

حدد جهاز العرض المطلوب (PDF) ونفّذ المهمة. هذه الخطوة **تحول TeX إلى PDF** وتخزن النتيجة في ZIP الإخراج.

```java
// Define saving options and run the job
options.setSaveOptions(new PdfSaveOptions());
new TeXJob("hello-world", new PdfDevice(), options).run();
```

## الخطوة 6: إغلاق أرشيف ZIP الإخراج

بعد انتهاء المهمة، يجب إغلاق تدفق ZIP بشكل صحيح لضمان صلاحية الأرشيف.

```java
// Finalize the output ZIP archive
((OutputZipDirectory) options.getOutputWorkingDirectory()).finish();
```

## المشكلات الشائعة والحلول

| المشكلة | السبب المحتمل | الحل |
|-------|--------------|-----|
| **PDF فارغ** | لا يحتوي ZIP الإدخال على ملف `*.tex` صالح أو الملف غير موجود داخل المجلد `in`. | تحقق من بنية ZIP (`in/yourfile.tex`). |
| **ملف `.trm` مفقود** | لم يتم استدعاء `setTerminalOut` أو دليل الإخراج ليس `OutputZipDirectory`. | تأكد من تنفيذ `options.setTerminalOut(...)` قبل `run()`. |
| **`IOException` عند الإنهاء** | تم إغلاق تدفق الإخراج مسبقًا في مكان آخر. | استدعِ `finish()` مرة واحدة فقط، بعد إكمال المهمة. |
| **فشل التحويل بسبب أخطاء TeX** | يحتوي مصدر TeX على أخطاء تركيبية. | افتح سجل `<job_name>.trm` المولد لرؤية رسائل الخطأ التفصيلية. |

## الأسئلة المتكررة

**س: ما هو Aspose.TeX؟**  
ج: Aspose.TeX هي مكتبة Java تمكّن المطورين من **إنشاء PDF من مصادر TeX**، تعديل مستندات TeX، وإجراء عرض متقدم دون الحاجة إلى تثبيت LaTeX خارجي.

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.TeX؟**  
ج: يمكنك الحصول على ترخيص مؤقت من [هذا الرابط](https://purchase.aspose.com/temporary-license/).

**س: أين يمكنني العثور على الوثائق الرسمية لـ Aspose.TeX؟**  
ج: الوثائق متاحة [هنا](https://reference.aspose.com/tex/java/).

**س: هل هناك نسخة تجريبية مجانية من Aspose.TeX؟**  
ج: نعم، يمكنك تحميل النسخة التجريبية المجانية من [هنا](https://releases.aspose.com/).

**س: أين يمكنني طلب المساعدة إذا واجهت مشاكل؟**  
ج: زر منتدى [Aspose.TeX](https://forum.aspose.com/c/tex/47) للحصول على دعم المجتمع والمساعدة الرسمية.

## الخلاصة

لقد رأيت الآن كيف **تحول TeX إلى PDF**، تتجاوز اسم المهمة، وتلتقط مخرجات الطرفية داخل أرشيف ZIP باستخدام Aspose.TeX for Java. هذا النهج مفيد بشكل خاص في خطوط بناء آلية، حيث يبسط جمع السجلات مع القطع الفنية عملية التصحيح وتدقيق السجلات. لا تتردد في تعديل الشفرة لتناسب بنية مشروعك، أو توسيعها لتدعم صيغ إخراج أخرى يدعمها Aspose.TeX.

---

**آخر تحديث:** 2025-12-07  
**تم الاختبار مع:** Aspose.TeX for Java 24.11 (أحدث إصدار وقت الكتابة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}