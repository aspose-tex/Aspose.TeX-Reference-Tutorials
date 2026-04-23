---
date: 2026-02-15
description: تعلم كيفية تحويل TeX إلى PDF، وتجاوز أسماء الوظائف، وكتابة مخرجات الطرفية
  إلى ملف ZIP باستخدام Aspose.TeX للـ Java. دليل خطوة بخطوة لمطوري Java.
linktitle: Convert TeX to PDF, Override Job Name and Write Terminal Output to ZIP
  in Java
second_title: Aspose.TeX Java API
title: تحويل TeX إلى PDF، تجاوز اسم المهمة وكتابة مخرجات الطرفية إلى ملف ZIP في Java
url: /ar/java/customizing-output/override-job-name-zip/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحويل TeX إلى PDF، تجاوز اسم المهمة وكتابة مخرجات الطرفية إلى ملف ZIP في Java

## المقدمة

إذا كنت بحاجة إلى **تحويل TeX إلى PDF** مع التحكم الكامل في اسم المهمة وسجلات الطرفية، فإن Aspose.TeX for Java يجعل ذلك بسيطًا. في هذا الدرس سنستعرض سيناريو واقعي: تجاوز اسم المهمة، توجيه مخرجات الطرفية إلى أرشيف ZIP، وأخيرًا إنتاج مستند PDF. في النهاية ستحصل على قطعة كود قابلة لإعادة الاستخدام يمكنك إدراجها في أي مشروع Java.

## إجابات سريعة
- **ما الذي يحققه هذا الدرس؟** يوضح كيفية تحويل TeX إلى PDF، تعيين اسم مهمة مخصص، والتقاط مخرجات الطرفية في ملف ZIP.  
- **ما المكتبة المطلوبة؟** Aspose.TeX for Java (أحدث إصدار).  
- **هل أحتاج إلى ترخيص؟** ترخيص مؤقت يكفي للتقييم؛ الترخيص الكامل مطلوب للإنتاج.  
- **ما ملفات الإخراج التي يتم إنشاؤها؟** مستند PDF وملف سجل الطرفية `<job_name>.trm` داخل ملف ZIP الناتج.  
- **كم يستغرق تنفيذ العملية؟** تقريبًا 10‑15 دقيقة لنسخ الكود وتشغيله.

## ما معنى “تحويل TeX إلى PDF”؟
تحويل TeX إلى PDF يعني أخذ ملف مصدر TeX (أو مجموعة ملفات TeX) وتحويله إلى مستند PDF. توفر Aspose.TeX محركًا عالي الأداء يتعامل مع كامل خط أنابيب تجميع TeX دون الحاجة إلى توزيع LaTeX خارجي.

## لماذا نتجاوز اسم المهمة ونكتب مخرجات الطرفية إلى ZIP؟
- **الوضوح:** يظهر اسم المهمة المخصص في ملفات السجل، مما يسهل التعرف على عمليات التشغيل في خطوط الأنابيب الآلية.  
- **القابلية للنقل:** تخزين مخرجات الطرفية (`*.trm`) داخل ملف ZIP يجمع جميع المخرجات معًا، وهو مفيد لعمليات CI/CD أو المعالجة السحابية.  
- **التصحيح:** يحتوي سجل الطرفية على رسائل تجميع مفصلة تساعدك على استكشاف أخطاء TeX.

## لماذا هذا مهم
عند توليد PDF من TeX في بيئة إنتاج، غالبًا ما تحتاج إلى تنظيم مخرجات البناء. يسمح لك تجاوز اسم المهمة بوسم كل تشغيل بمعرف ذي معنى (مثل رقم بناء). تجميع سجل الطرفية في نفس ملف ZIP مع PDF يمنحك حزمة واحدة محمولة يمكن أرشفتها أو إرسالها إلى خدمات لاحقة دون فقدان السياق.

## حالات الاستخدام الشائعة
- **إنشاء تقارير آلية** – مهمة ليلية تُنشئ ملفات PDF من قوالب TeX وتخزن السجلات لأغراض التدقيق.  
- **خطوط CI/CD** – يمكن للمطورين عرض رسائل التجميع الدقيقة عندما يفشل بناء، دون الحاجة للبحث في ملفات سجل منفصلة.  
- **خدمات المستندات السحابية** – خدمة ويب تستقبل ملف ZIP يحتوي على مصادر TeX، تعالجها، وتعيد ملف ZIP يحتوي على PDF وسجل التجميع.

## المتطلبات المسبقة

قبل البدء، تأكد من وجود ما يلي:

- بيئة تطوير Java تعمل (JDK 8 أو أعلى).  
- Aspose.TeX for Java محملة من [موقع Aspose](https://releases.aspose.com/tex/java/).  
- إلمام أساسي بـ Java I/O streams.  

## استيراد الحزم

ابدأ باستيراد الفئات الضرورية. سيوفر لك ذلك الوصول إلى API الخاص بـ Aspose.TeX وأدوات I/O القياسية في Java.

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

نفتح أولًا تدفقًا يشير إلى ملف ZIP الذي يحتوي على ملفات مصدر TeX. يعمل هذا الأرشيف كـ **دليل عمل الإدخال** لمهمة التحويل.

```java
// Open a stream on the input ZIP archive
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
```

## الخطوة 2: فتح أرشيف ZIP الإخراج

بعد ذلك، ننشئ تدفقًا لملف ZIP الذي سيستقبل PDF المُولد وسجل الطرفية. هذا هو **دليل عمل الإخراج**.

```java
// Open a stream on the output ZIP archive
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "terminal-out-to-zip.zip");
```

## الخطوة 3: ضبط خيارات التحويل (بما في ذلك اسم المهمة)

هنا نقوم بتكوين خيارات التحويل لتنسيق ObjectTeX، نحدد اسم مهمة مخصص، ونربط أدلة ZIP الإدخال والإخراج.

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

## الخطوة 6: إنهاء أرشيف ZIP الإخراج

بعد انتهاء المهمة، يجب إغلاق تدفق ZIP بشكل صحيح لضمان صلاحية الأرشيف.

```java
// Finalize the output ZIP archive
((OutputZipDirectory) options.getOutputWorkingDirectory()).finish();
```

## نصائح وممارسات أفضل

- **إعادة استخدام التدفقات**: إذا كنت تعالج العديد من وظائف TeX متتالية، حافظ على فتح تدفقات الإدخال والإخراج وغير `JobName` فقط بين كل تشغيل.  
- **فحص السجلات**: افتح ملف `<job_name>.trm` بأي محرر نصوص لرؤية التحذيرات أو الأخطاء التي أظهرها مترجم TeX.  
- **الأداء**: للمستندات الكبيرة، فكر في زيادة حجم heap الخاص بـ JVM (`-Xmx2g`) لتجنب `OutOfMemoryError` أثناء تصيير PDF.  
- **الأمان**: عند التعامل مع مصادر TeX غير موثوقة، شغّل التحويل في بيئة معزولة لتقليل مخاطر الماكرو الضار.

## المشكلات الشائعة والحلول

| المشكلة | السبب المحتمل | الحل |
|-------|--------------|-----|
| **PDF فارغ** | لا يحتوي ZIP الإدخال على ملف `*.tex` صالح أو الملف غير موجود داخل المجلد `in`. | تحقق من بنية ZIP (`in/yourfile.tex`). |
| **ملف `.trm` مفقود** | لم يتم استدعاء `setTerminalOut` أو دليل الإخراج ليس `OutputZipDirectory`. | تأكد من تنفيذ `options.setTerminalOut(...)` قبل `run()`. |
| **`IOException` عند الإنهاء** | تم إغلاق تدفق الإخراج مسبقًا في مكان آخر. | استدعِ `finish()` مرة واحدة فقط، بعد إكمال المهمة. |
| **فشل التحويل بسبب أخطاء TeX** | يحتوي مصدر TeX على أخطاء تركيبية. | افتح سجل `<job_name>.trm` المولد لرؤية رسائل الخطأ التفصيلية. |

## الأسئلة المتكررة

**س: ما هو Aspose.TeX؟**  
ج: Aspose.TeX هي مكتبة Java تمكّن المطورين من **إنشاء PDF من مصادر TeX**، تعديل مستندات TeX، وإجراء تصيير متقدم دون الحاجة إلى تثبيت LaTeX خارجي.

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.TeX؟**  
ج: يمكنك الحصول على ترخيص مؤقت من [هذا الرابط](https://purchase.aspose.com/temporary-license/).

**س: أين يمكنني العثور على الوثائق الرسمية لـ Aspose.TeX؟**  
ج: الوثائق متاحة [هنا](https://reference.aspose.com/tex/java/).

**س: هل هناك نسخة تجريبية مجانية من Aspose.TeX؟**  
ج: نعم، يمكنك تنزيل النسخة التجريبية المجانية من [هنا](https://releases.aspose.com/).

**س: أين يمكنني طلب المساعدة إذا واجهت مشاكل؟**  
ج: زر منتدى [Aspose.TeX](https://forum.aspose.com/c/tex/47) للحصول على دعم المجتمع والمساعدة الرسمية.

## الخاتمة

لقد رأيت الآن كيفية **تحويل TeX إلى PDF**، تجاوز اسم المهمة، والتقاط مخرجات الطرفية داخل أرشيف ZIP باستخدام Aspose.TeX for Java. هذا النهج مفيد بشكل خاص في خطوط بناء آلية، حيث يبسط جمع السجلات مع القطع المولدة عملية التصحيح وتتبع التدقيق. لا تتردد في تعديل الكود ليتناسب مع بنية مشروعك، أو توسيعه إلى صيغ إخراج أخرى يدعمها Aspose.TeX.

---

**آخر تحديث:** 2026-02-15  
**تم الاختبار مع:** Aspose.TeX for Java 24.11 (أحدث إصدار وقت الكتابة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}