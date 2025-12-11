---
date: 2025-12-05
description: تعرّف على كيفية كتابة مخرجات الطرفية إلى ملف وتجاوز اسم المهمة باستخدام
  Aspose.TeX للغة Java. اتبع هذا الدليل خطوة بخطوة مع أمثلة شفرة كاملة.
linktitle: Write Terminal Output to File and Override Job Name in Java
second_title: Aspose.TeX Java API
title: كتابة مخرجات الطرفية إلى ملف وتجاوز اسم المهمة في جافا
url: /ar/java/customizing-output/override-job-name-disk/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كتابة مخرجات الطرفية إلى ملف وتجاوز اسم المهمة في جافا

## مقدمة

توفر Aspose.TeX for Java ميزات قوية للعمل مع ملفات TeX، مما يتيح للمطورين تعديل وتخصيص خط أنابيب معالجة مستندات TeX. في هذا البرنامج التعليمي ستتعلم **كيفية كتابة مخرجات الطرفية إلى ملف** مع تجاوز اسم المهمة الافتراضي — ميزتان تمنحانك تحكمًا دقيقًا في المعالجة الدفعية والتسجيل.

## إجابات سريعة
- **هل يمكنني تغيير اسم المهمة؟** نعم، استخدم `options.setJobName(...)` قبل تشغيل المهمة.  
- **أين تذهب مخرجات الطرفية؟** يتم حفظها كـ `<job_name>.trm` في دليل العمل الخاص بالمخرجات.  
- **هل أحتاج إلى ترخيص لهذه الميزة؟** تعمل هذه الوظيفة مع أي ترخيص صالح لـ Aspose.TeX؛ كما يتوفر نسخة تجريبية مجانية.  
- **ما هو تنسيق ملف المخرجات؟** سجل نصي عادي للطرفية يعكس مخرجات وحدة التحكم.  
- **هل هذا متوافق مع أجهزة إخراج أخرى؟** بالطبع—بمجرد كتابة السجل يمكنك معالجته بأي أداة تقرأ ملفات النص.

## المتطلبات المسبقة

قبل الغوص في الشيفرة، تأكد من أن لديك ما يلي:

- فهم قوي لأساسيات برمجة جافا.  
- Aspose.TeX for Java مثبت (حمّل من [توثيق Aspose.TeX Java الرسمي](https://reference.aspose.com/tex/java/)).  
- بيئة تطوير جافا IDE أو أداة بناء (Maven/Gradle) جاهزة لتجميع وتشغيل العينة.

## استيراد الحزم

للبدء، استورد الحزم اللازمة إلى مشروع جافا الخاص بك. في ملف جافا الخاص بك، أدرج الاستيرادات التالية:

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

> **نصيحة احترافية:** احتفظ باستيراد `util.Utils` فقط إذا كنت بحاجة إلى طرق مساعدة من أدوات Aspose العينية؛ وإلا يمكنك إزالته للحفاظ على نظافة الشيفرة.

## كيفية كتابة مخرجات الطرفية إلى ملف في جافا

فيما يلي دليل خطوة بخطوة يوضح بالضبط كيفية تكوين خيارات التحويل، تجاوز اسم المهمة، وتوجيه مخرجات الطرفية إلى ملف على القرص.

### الخطوة 1: إنشاء خيارات التحويل

أولاً، أنشئ كائن `TeXOptions` يستخدم تكوين ObjectTeX الافتراضي. سيحتفظ هذا الكائن بجميع الإعدادات لعملية التحويل.

```java
// ExStart:OverrideJobName-WriteTerminalOutputToFileSystem
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
// ExEnd:OverrideJobName-WriteTerminalOutputToFileSystem
```

### الخطوة 2: تحديد اسم المهمة ودلائل العمل

بعد ذلك، عيّن اسم مهمة مخصص وحدد مكان وجود ملفات الإدخال والإخراج. إذا لم تقم بتعيين اسم مهمة، يصبح أول معامل في مُنشئ `TeXJob` هو اسم المهمة تلقائيًا.

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

> **لماذا تجاوز اسم المهمة؟**  
> تجاوز اسم المهمة يجعل ملفات السجل والملفات الناتجة أسهل في التعرف عليها، خاصةً عندما تقوم بتشغيل مهام متعددة بالتوازي أو أتمتة المعالجة الدفعية.

### الخطوة 3: كتابة مخرجات الطرفية إلى نظام الملفات

أخبر Aspose.TeX بالتقاط كل ما يظهر عادةً على وحدة التحكم وكتابته إلى ملف. سيكون اسم الملف `<job_name>.trm` وسيُوضع في دليل العمل الخاص بالمخرجات الذي حددته أعلاه.

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### الخطوة 4: تشغيل المهمة

أخيرًا، أنشئ `TeXJob` مع ملف الإدخال المطلوب (هنا نستخدم مثالًا بسيطًا “hello‑world”) وجهاز عرض XPS. ثم استدعِ `run()` لتنفيذ التحويل.

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
```

عند انتهاء المهمة، ستجد ملفًا باسم `overridden-job-name.trm` داخل **دليل المخرجات الخاص بك** يحتوي على سجل الطرفية الكامل.

## المشكلات الشائعة & استكشاف الأخطاء وإصلاحها

| المشكلة | السبب | الحل |
|-------|-------|-----|
| **لم يتم إنشاء ملف `.trm`** | `setTerminalOut` لم يُستدعَ أو دليل الإخراج مفقود | تحقق من وجود دليل الإخراج وأن `options.setTerminalOut(...)` تم تنفيذه قبل `job.run()`. |
| **اسم الملف ليس الاسم المتجاوز** | اسم المهمة لم يُضبط بشكل صحيح | تأكد من استدعاء `options.setJobName("your‑desired‑name")` **قبل** إنشاء `TeXJob`. |
| **ملف سجل فارغ** | استثناءات تم رميها قبل بدء التسجيل | ضع `job.run()` داخل كتلة try‑catch وتفحص تتبع الاستثناء للخطوط المفقودة أو مصدر TeX غير صالح. |

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.TeX for Java مع مكتبات جافا أخرى؟**  
**ج:** نعم، تم تصميم Aspose.TeX للتكامل بسلاسة مع مكتبات جافا الأخرى، مما يتيح لك دمج أدوات PDF أو الصور أو قواعد البيانات في نفس سير العمل.

**س: أين يمكنني العثور على دعم Aspose.TeX for Java؟**  
**ج:** زر [منتدى Aspose.TeX](https://forum.aspose.com/c/tex/47) للحصول على مساعدة المجتمع، أو افتح تذكرة دعم عبر بوابة دعم Aspose.

**س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.TeX for Java؟**  
**ج:** بالتأكيد. يمكنك تنزيل نسخة تجريبية كاملة الوظائف من [صفحة التجربة المجانية لـ Aspose.TeX](https://releases.aspose.com/).

**س: كيف يمكنني الحصول على ترخيص مؤقت للاختبار؟**  
**ج:** استخدم نموذج طلب الترخيص المؤقت على [ترخيص Aspose المؤقت](https://purchase.aspose.com/temporary-license/) للحصول على ترخيص تقييم لمدة 30 يومًا.

**س: أين يمكنني شراء ترخيص دائم؟**  
**ج:** اشترِ الترخيص مباشرةً من [صفحة شراء Aspose.TeX](https://purchase.aspose.com/buy).

## الخاتمة

في هذا الدليل، أظهرنا كيفية **كتابة مخرجات الطرفية إلى ملف** وتجاوز اسم المهمة الافتراضي باستخدام Aspose.TeX for Java. تتيح لك هذه القدرات الاحتفاظ بسجلات مفصلة لتصحيح الأخطاء، أتمتة المعالجة الدفعية، والحفاظ على هيكل مخرجات نظيف ومنظم—وهو أمر أساسي لأنابيب تحويل المستندات على مستوى الإنتاج.

---

**آخر تحديث:** 2025-12-05  
**تم الاختبار مع:** Aspose.TeX 24.11 for Java  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}