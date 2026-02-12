---
date: 2026-02-12
description: تعلم كيفية التقاط مخرجات وحدة التحكم في جافا باستخدام Aspose.TeX، كتابة
  مخرجات الطرفية إلى ملف، وتجاوز اسم المهمة. يغطي هذا الدليل خطوة بخطوة أيضًا إعادة
  توجيه مخرجات وحدة التحكم في جافا.
linktitle: Write Terminal Output to File and Override Job Name in Java
second_title: Aspose.TeX Java API
title: كيفية التقاط مخرجات وحدة التحكم وتجاوز اسم المهمة في جافا
url: /ar/java/customizing-output/override-job-name-disk/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كتابة مخرجات الطرفية إلى ملف وتجاوز اسم المهمة في Java

## مقدمة

في هذا الدرس، ستكتشف **كيفية التقاط مخرجات وحدة التحكم** أثناء معالجة ملفات TeX باستخدام Aspose.TeX for Java. سنستعرض كتابة مخرجات الطرفية إلى ملف، تجاوز اسم المهمة الافتراضي، وإعادة توجيه مخرجات وحدة التحكم في Java بحيث تكون السجلات سهلة الموقع والتحليل. هذه التقنيات أساسية عندما تحتاج إلى تسجيل موثوق لتحويلات الدُفعات أو خطوط أنابيب المستندات المؤتمتة.

## الإجابات السريعة
- **هل يمكنني تغيير اسم المهمة؟** نعم، استخدم `options.setJobName(...)` قبل تشغيل المهمة.  
- **أين تُحفظ مخرجات الطرفية؟** تُحفظ كملف `<job_name>.trm` في دليل العمل الخاص بالمخرجات.  
- **هل أحتاج إلى ترخيص لهذه الميزة؟** تعمل الوظيفة مع أي ترخيص صالح لـ Aspose.TeX؛ تتوفر نسخة تجريبية مجانية أيضًا.  
- **ما هو تنسيق ملف المخرجات؟** سجل نصي عادي للطرفية يعكس مخرجات وحدة التحكم.  
- **هل هذا متوافق مع أجهزة إخراج أخرى؟** بالتأكيد—بمجرد كتابة السجل يمكنك معالجته بأي أداة تقرأ ملفات النص.

## ما هو **كيفية التقاط مخرجات وحدة التحكم** في سياق Aspose.TeX؟

التقاط مخرجات وحدة التحكم يعني إعادة توجيه كل ما كان سيظهر عادةً على تدفق الإخراج القياسي (الطرفية) إلى ملف على القرص. مع Aspose.TeX يمكنك القيام بذلك بسهولة عن طريق تكوين `OutputFileTerminal` وتعيينه إلى خيارات التحويل.

## لماذا يتم تجاوز اسم المهمة؟

تجاوز اسم المهمة يمنح كل تشغيل تحويل معرفًا فريدًا. هذا يجعل ملفات السجل (`*.trm`) وغيرها من المخرجات أسهل في المتابعة، خاصةً عند تشغيل مهام متعددة بالتوازي أو جدولة عمليات الدُفعات.

## المتطلبات المسبقة

- إتقان أساسي لبرمجة Java.  
- Aspose.TeX for Java مثبت (حمّل من [توثيق Aspose.TeX Java الرسمي](https://reference.aspose.com/tex/java/)).  
- بيئة تطوير Java أو أداة بناء (Maven/Gradle) جاهزة لتجميع وتشغيل العينة.

## استيراد الحزم

لبدء العمل، استورد الحزم الضرورية إلى مشروع Java الخاص بك. في ملف Java، أدرج الاستيرادات التالية:

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

> **نصيحة احترافية:** احتفظ باستيراد `util.Utils` فقط إذا كنت بحاجة إلى طرق مساعدة من أدوات عينة Aspose؛ وإلا يمكنك إزالته للحفاظ على نظافة الكود.

## كيفية التقاط مخرجات وحدة التحكم في Java

فيما يلي دليل خطوة بخطوة يوضح بالضبط كيفية تكوين خيارات التحويل، تجاوز اسم المهمة، وتوجيه مخرجات الطرفية إلى ملف على القرص.

### الخطوة 1: إنشاء خيارات التحويل

أولاً، أنشئ كائن `TeXOptions` يستخدم الإعداد الافتراضي ObjectTeX. سيحتوي هذا الكائن على جميع الإعدادات لعملية التحويل.

```java
// ExStart:OverrideJobName-WriteTerminalOutputToFileSystem
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
// ExEnd:OverrideJobName-WriteTerminalOutputToFileSystem
```

### الخطوة 2: تحديد اسم المهمة وأدلة العمل

بعد ذلك، عيّن اسم مهمة مخصص وحدد مكان وجود ملفات الإدخال والإخراج. إذا لم تقم بتعيين اسم مهمة، يصبح الوسيط الأول في مُنشئ `TeXJob` هو اسم المهمة تلقائيًا.

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

> **لماذا يتم تجاوز اسم المهمة؟**  
> يجعل تجاوز اسم المهمة ملفات السجل والملفات الناتجة أسهل في التعرف عليها، خاصةً عندما تقوم بتشغيل مهام متعددة بالتوازي أو أتمتة معالجة الدُفعات.

### الخطوة 3: كتابة مخرجات الطرفية إلى نظام الملفات

أخبر Aspose.TeX بالتقاط كل ما كان سيظهر على وحدة التحكم وكتابته إلى ملف. سيُسمى الملف `<job_name>.trm` ويُوضع في دليل العمل الخاص بالمخرجات الذي حددته أعلاه.

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### الخطوة 4: تشغيل المهمة

أخيرًا، أنشئ كائن `TeXJob` مع ملف الإدخال المطلوب (هنا نستخدم مثال "hello‑world" البسيط) وجهاز العرض XPS. ثم استدعِ `run()` لتنفيذ التحويل.

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
```

عند انتهاء المهمة، ستجد ملفًا يُدعى `overridden-job-name.trm` داخل **دليل المخرجات الخاص بك** يحتوي على سجل الطرفية الكامل.

## المشكلات الشائعة & استكشاف الأخطاء وإصلاحها

| المشكلة | السبب | الحل |
|-------|-------|-----|
| **عدم إنشاء ملف `.trm`** | لم يتم استدعاء `setTerminalOut` أو دليل الإخراج غير موجود | تحقق من وجود دليل الإخراج وأن `options.setTerminalOut(...)` يتم تنفيذه قبل `job.run()`. |
| **اسم الملف ليس الاسم المتجاوز** | لم يتم تعيين اسم المهمة بشكل صحيح | تأكد من استدعاء `options.setJobName("your‑desired‑name")` **قبل** إنشاء `TeXJob`. |
| **ملف سجل فارغ** | تم رفع استثناءات قبل بدء التسجيل | غلف `job.run()` بكتلة try‑catch وتفحص تتبع الاستثناء للخطوط المفقودة أو مصدر TeX غير الصحيح. |

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.TeX for Java مع مكتبات Java أخرى؟**  
ج: نعم، تم تصميم Aspose.TeX لتتكامل بسلاسة مع مكتبات Java الأخرى، مما يتيح لك دمج أدوات PDF أو الصور أو قواعد البيانات في نفس سير العمل.

**س: أين يمكنني العثور على دعم Aspose.TeX for Java؟**  
ج: زر [منتدى Aspose.TeX](https://forum.aspose.com/c/tex/47) للحصول على مساعدة المجتمع، أو افتح تذكرة دعم عبر بوابة دعم Aspose.

**س: هل تتوفر نسخة تجريبية مجانية لـ Aspose.TeX for Java؟**  
ج: بالتأكيد. يمكنك تحميل نسخة تجريبية كاملة الوظائف من [صفحة التجربة المجانية لـ Aspose.TeX](https://releases.aspose.com/).

**س: كيف يمكنني الحصول على ترخيص مؤقت للاختبار؟**  
ج: استخدم نموذج طلب الترخيص المؤقت على [ترخيص Aspose المؤقت](https://purchase.aspose.com/temporary-license/) للحصول على ترخيص تقييم لمدة 30 يومًا.

**س: أين يمكنني شراء ترخيص دائم؟**  
ج: اشترِ الترخيص مباشرة من [صفحة شراء Aspose.TeX](https://purchase.aspose.com/buy).

---

**آخر تحديث:** 2026-02-12  
**تم الاختبار مع:** Aspose.TeX 24.11 for Java  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}