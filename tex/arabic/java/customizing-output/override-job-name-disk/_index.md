---
date: 2026-08-18
description: تعلم كيفية إعادة توجيه console output في Java باستخدام Aspose.TeX، كتابة
  terminal output إلى ملف، وتجاوز job name لتحسين logging.
keywords:
- redirect console output java
- Aspose.TeX Java
- Java logging
- override job name
lastmod: 2026-08-18
linktitle: كتابة Terminal Output إلى ملف وتجاوز Job Name في Java
og_description: إعادة توجيه console output في Java باستخدام Aspose.TeX وتجاوز job
  name لإنشاء log files متميزة. اتبع هذا الدليل خطوة بخطوة للحصول على logging موثوق.
og_image_alt: Screenshot of Java console output redirection using Aspose.TeX
og_title: إعادة توجيه console output في Java وتجاوز job name – دليل Aspose.TeX
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Learn how to redirect console output in Java using Aspose.TeX, write
    terminal output to a file, and override the job name for better logging.
  headline: How to redirect console output in Java and override job name
  type: TechArticle
- description: Learn how to redirect console output in Java using Aspose.TeX, write
    terminal output to a file, and override the job name for better logging.
  name: How to redirect console output in Java and override job name
  steps:
  - name: create conversion options
    text: '`TeXOptions` is the configuration object that controls how Aspose.TeX processes
      a TeX job. It holds settings such as output format, font handling, and terminal
      redirection.'
  - name: specify job name and working directories
    text: '`TeXJob` represents a single conversion task, linking input, output, and
      options together. Setting a custom job name ensures the generated log file is
      uniquely named. > **Why override the job name?** > Overriding the job name makes
      log files and generated artifacts easier to identify, especially whe'
  - name: write terminal output to file system
    text: '`setTerminalOut` tells Aspose.TeX where to write the console log file.
      The file will be named `<job_name>.trm` and placed in the output working directory
      you defined above. Configure the terminal output redirection:'
  - name: run the job
    text: '`run()` executes the conversion based on the supplied options and writes
      output files (including the `.trm` log) to the designated folder. Create a `TeXJob`
      with the desired input file (here we use a simple “hello‑world” example) and
      the XPS rendering device, then call `run()`: When the job finishes'
  type: HowTo
- questions:
  - answer: Yes, Aspose.TeX integrates seamlessly with other Java libraries, allowing
      you to combine PDF, image, or database utilities in the same workflow.
    question: Can I use Aspose.TeX for Java with other Java libraries?
  - answer: Visit the [Aspose.TeX forum](https://forum.aspose.com/c/tex/47) for community
      help, or open a support ticket through the Aspose support portal.
    question: Where can I find support for Aspose.TeX for Java?
  - answer: Absolutely. You can download a fully functional trial from the [Aspose.TeX
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.TeX for Java?
  - answer: Use the temporary‑license request form at [Aspose temporary license](https://purchase.aspose.com/temporary-license/)
      to get a 30‑day evaluation license.
    question: How can I obtain a temporary license for testing?
  - answer: Purchase a license directly from the [Aspose.TeX buying page](https://purchase.aspose.com/buy).
    question: Where can I purchase a permanent license?
  type: FAQPage
second_title: Aspose.TeX Java API
tags:
- redirect console output
- Aspose.TeX
- Java console logging
- job name override
title: كيفية إعادة توجيه console output في Java وتجاوز job name
url: /ar/java/customizing-output/override-job-name-disk/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كتابة مخرجات الطرفية إلى ملف وتجاوز اسم المهمة في Java

## مقدمة

في هذا الدرس ستتعلم كيفية **إعادة توجيه مخرجات وحدة التحكم في Java** أثناء معالجة ملفات TeX باستخدام Aspose.TeX. سنوضح لك كيفية كتابة سجل الطرفية إلى ملف `.trm`، وتجاوز اسم المهمة الافتراضي، والحفاظ على تنظيم سجلاتك لتحويلات الدفعات أو خطوط الأنابيب الآلية. يدعم Aspose.TeX **أكثر من 30 تنسيقًا للمدخلات والمخرجات** ويمكنه معالجة المستندات التي تصل إلى **500 صفحة** دون تحميل الملف بالكامل في الذاكرة، مما يجعله مثاليًا للسيناريوهات ذات الحجم الكبير.

## إجابات سريعة

`options.setJobName(String name)` يحدد معرف مهمة مخصص سيُستخدم للملفات السجلية وملفات الإخراج التي يتم إنشاؤها.

- **هل يمكنني تغيير اسم المهمة؟** نعم – استدعِ `options.setJobName("my‑job")` قبل إنشاء `TeXJob`.  
- **أين تُحفظ مخرجات الطرفية؟** يتم حفظها كـ `<job_name>.trm` في دليل العمل الخاص بالإخراج الذي تحدده.  
- **هل أحتاج إلى ترخيص لهذه الميزة؟** تعمل الوظيفة مع أي ترخيص صالح لـ Aspose.TeX؛ كما يتوفر نسخة تجريبية مجانية.  
- **ما هو تنسيق ملف الإخراج؟** سجل نصي عادي للطرفية يعكس كل ما يُطبع على وحدة التحكم.  
- **هل هذا متوافق مع أجهزة إخراج أخرى؟** بالتأكيد – بمجرد كتابة السجل يمكنك إرساله إلى أي أداة معالجة نصوص.

## ما هو **كيفية التقاط وحدة التحكم** في سياق Aspose.TeX؟

التقاط مخرجات وحدة التحكم يعني إعادة توجيه كل ما يظهر عادةً على تدفق الإخراج القياسي (الطرفية) إلى ملف على القرص. مع Aspose.TeX يمكنك القيام بذلك بسهولة عن طريق تكوين `OutputFileTerminal` وتعيينه إلى خيارات التحويل.

## لماذا يتم تجاوز اسم المهمة؟

تجاوز اسم المهمة يمنح كل عملية تحويل معرفًا فريدًا. هذا يجعل ملفات السجل المُنشأة (`*.trm`) وغيرها من القطع الأثرية أسهل في المتابعة، خاصةً عند تشغيل مهام متعددة بالتوازي أو جدولة عمليات الدفعات. من خلال توفير اسم مميز، تتجنب أيضًا الكتابة فوق السجلات السابقة وتبسط سكريبتات ما بعد المعالجة التي تعتمد على أسماء ملفات متوقعة.

## المتطلبات المسبقة

- إتقان أساسي لبرمجة Java.  
- Aspose.TeX لـ Java مثبت (حمّل من [توثيق Aspose.TeX Java الرسمي](https://reference.aspose.com/tex/java/)).  
- بيئة تطوير Java IDE أو أداة بناء (Maven/Gradle) جاهزة لتجميع وتشغيل العينة.

## استيراد الحزم

لبدء العمل، استورد الحزم الضرورية في مشروع Java الخاص بك. في ملف Java الخاص بك، أدرج الاستيرادات التالية:

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

> **نصيحة احترافية:** احتفظ باستيراد `util.Utils` فقط إذا كنت بحاجة إلى طرق مساعدة من أدوات Aspose العينية؛ وإلا يمكنك إزالته للحفاظ على نظافة الكود.

## كيفية التقاط مخرجات وحدة التحكم في Java

فيما يلي دليل خطوة بخطوة يوضح بالضبط كيفية تكوين خيارات التحويل، وتجاوز اسم المهمة، وتوجيه مخرجات الطرفية إلى ملف على القرص. الخطوات التالية توضح استدعاءات API المطلوبة وتظهر كيفية إعداد البيئة بحيث يتم التقاط جميع رسائل وحدة التحكم دون تعديل الكود الأساسي لـ Aspose.TeX.

### الخطوة 1: إنشاء خيارات التحويل

`TeXOptions` هو كائن التكوين الذي يتحكم في كيفية معالجة Aspose.TeX لمهمة TeX. يحتوي على إعدادات مثل تنسيق الإخراج، ومعالجة الخطوط، وإعادة توجيه الطرفية.

```java
// ExStart:OverrideJobName-WriteTerminalOutputToFileSystem
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
// ExEnd:OverrideJobName-WriteTerminalOutputToFileSystem
```

### الخطوة 2: تحديد اسم المهمة وأدلة العمل

`TeXJob` يمثل مهمة تحويل واحدة، يربط بين الإدخال والإخراج والخيارات معًا. تحديد اسم مهمة مخصص يضمن أن ملف السجل المُنشأ يحمل اسمًا فريدًا.

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

> **لماذا يتم تجاوز اسم المهمة؟**  
> تجاوز اسم المهمة يجعل ملفات السجل والقطع الأثرية المُنشأة أسهل في التعرف عليها، خاصةً عندما تقوم بتشغيل مهام متعددة بالتوازي أو أتمتة معالجة الدفعات.

### الخطوة 3: كتابة مخرجات الطرفية إلى نظام الملفات

`setTerminalOut` يخبر Aspose.TeX أين يكتب ملف سجل وحدة التحكم. سيكون اسم الملف `<job_name>.trm` وسيُوضع في دليل العمل الخاص بالإخراج الذي حددته أعلاه.

قم بتكوين إعادة توجيه مخرجات الطرفية:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### الخطوة 4: تشغيل المهمة

`run()` ينفذ التحويل بناءً على الخيارات المقدمة ويكتب ملفات الإخراج (بما في ذلك سجل `.trm`) إلى المجلد المحدد.

أنشئ `TeXJob` باستخدام ملف الإدخال المطلوب (هنا نستخدم مثالًا بسيطًا “hello‑world”) وجهاز عرض XPS، ثم استدعِ `run()`:

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
```

عند انتهاء المهمة، ستجد ملفًا باسم `overridden-job-name.trm` داخل **دليل الإخراج الخاص بك** يحتوي على سجل الطرفية الكامل.

## المشكلات الشائعة & استكشاف الأخطاء

| المشكلة | السبب | الحل |
|-------|-------|-----|
| **لم يتم إنشاء ملف `.trm`** | `setTerminalOut` لم يتم استدعاؤه أو دليل الإخراج مفقود | تحقق من وجود دليل الإخراج وأنه تم تنفيذ `options.setTerminalOut(...)` قبل `job.run()`. |
| **اسم الملف ليس الاسم المتجاوز** | لم يتم تعيين اسم المهمة بشكل صحيح | تأكد من استدعاء `options.setJobName("your‑desired‑name")` **قبل** إنشاء `TeXJob`. |
| **ملف سجل فارغ** | استثناءات تم رميها قبل بدء التسجيل | غلف `job.run()` بكتلة try‑catch وتفحص تتبع الاستثناء للخطوط المفقودة أو مصدر TeX غير صحيح. |

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.TeX لـ Java مع مكتبات Java أخرى؟**  
ج: نعم، يندمج Aspose.TeX بسلاسة مع مكتبات Java الأخرى، مما يتيح لك الجمع بين أدوات PDF أو الصور أو قواعد البيانات في نفس سير العمل.

**س: أين يمكنني العثور على دعم Aspose.TeX لـ Java؟**  
ج: زر [منتدى Aspose.TeX](https://forum.aspose.com/c/tex/47) للحصول على مساعدة المجتمع، أو افتح تذكرة دعم عبر بوابة دعم Aspose.

**س: هل تتوفر نسخة تجريبية مجانية لـ Aspose.TeX لـ Java؟**  
ج: بالتأكيد. يمكنك تنزيل نسخة تجريبية كاملة الوظائف من [صفحة التجربة المجانية لـ Aspose.TeX](https://releases.aspose.com/).

**س: كيف يمكنني الحصول على ترخيص مؤقت للاختبار؟**  
ج: استخدم نموذج طلب الترخيص المؤقت على [ترخيص Aspose المؤقت](https://purchase.aspose.com/temporary-license/) للحصول على ترخيص تقييم لمدة 30 يومًا.

**س: أين يمكنني شراء ترخيص دائم؟**  
ج: اشترِ ترخيصًا مباشرةً من [صفحة شراء Aspose.TeX](https://purchase.aspose.com/buy).

---

**آخر تحديث:** 2026-08-18  
**تم الاختبار مع:** Aspose.TeX 24.11 لـ Java  
**المؤلف:** Aspose

## دروس ذات صلة

- [تحويل TeX إلى PDF، تجاوز اسم المهمة وكتابة مخرجات الطرفية إلى ZIP في Java](/tex/java/customizing-output/override-job-name-zip/)
- [كيفية استخدام أرشيفات ZIP للإدخال والإخراج في Aspose.TeX Java](/tex/java/zip-archives/zip-archives-input-output/)
- [كيفية تحويل TeX إلى PNG باستخدام إدخال تدفق ومعالجة الطرفية في Java](/tex/java/advanced-io/stream-input-image-output/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}