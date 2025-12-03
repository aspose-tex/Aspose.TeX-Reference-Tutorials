---
date: 2025-12-03
description: تعلم كيفية إنشاء صيغ TeX في Java باستخدام Aspose.TeX، وتعيين مجلدات الإدخال
  والإخراج لـ TeX، وإنشاء صيغ TeX مخصصة لضمان تنسيق ثابت.
language: ar
linktitle: Create Custom TeX Formats for Consistent Typesetting in Java
second_title: Aspose.TeX Java API
title: كيفية إنشاء صيغ TeX لتنسيق ثابت في جافا
url: /java/custom-format/creating-custom-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء صيغ TeX لتنسيق ثابت في Java

يمكن أن يكون تنسيق المستندات المتسق عبر العديد من الوثائق مصدر صداع — خاصة عندما تحتاج إلى نفس قواعد التخطيط مرارًا وتكرارًا. **في هذا البرنامج التعليمي ستتعلم كيفية إنشاء صيغ TeX** باستخدام Aspose.TeX for Java، وسترى بالضبط كيفية **تحديد مجلدات الإدخال والإخراج لـ TeX** حتى يعرف المحرك أين يقرأ ملفات المصدر وأين يكتب النتائج المولدة. في النهاية، ستكون قادرًا على إنشاء صيغة TeX مخصصة تضمن تنسيقًا موحدًا لجميع خطوط أنابيب المستندات المعتمدة على Java.

## إجابات سريعة
- **ماذا يعني “إنشاء صيغة TeX مخصصة”?** يخبر ذلك محرك Aspose.TeX بإنشاء مجموعة قابلة لإعادة الاستخدام من الماكروهات، الخطوط، وقواعد التخطيط.
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تعمل للتطوير؛ يلزم ترخيص تجاري للإنتاج.
- **ما نسخة JDK المطلوبة؟** Java 8 أو أعلى.
- **هل يمكنني تغيير مجلد الإدخال أثناء التشغيل؟** نعم — استخدم `setInputWorkingDirectory`.
- **هل يمكن تكوين مجلد الإخراج؟** بالطبع — استخدم `setOutputWorkingDirectory`.

## ما هي صيغة TeX المخصصة؟
صيغة TeX المخصصة هي مجموعة مُجمّعة مسبقًا من ماكروهات TeX، الحزم، وإعدادات التكوين التي يقوم المحرك بتحميلها وقت التشغيل. بدلاً من تحليل ملفات النمط نفسها لكل مستند، تقوم بدمجها مرة واحدة في صيغة (مثل `customtex.fmt`) وتعيد استخدامها، مما يحسن الأداء بشكل كبير ويضمن عرضًا متطابقًا.

## لماذا يتم تحديد مجلدات الإدخال والإخراج لـ TeX؟
تحديد **مجلد إدخال TeX** يخبر المحرك أين يجد ملفات المصدر `.tex`، الخطوط، والموارد المساعدة. **مجلد إخراج TeX** يحدد أين تُكتب ملفات PDF المجمّعة، السجلات، والملفات المساعدة. تكوين هذه المسارات بشكل صحيح يمنع أخطاء “الملف غير موجود” ويحافظ على تنظيم مجلد المشروع.

## المتطلبات المسبقة
- **Aspose.TeX for Java** – قم بالتنزيل من [صفحة تنزيل Aspose.TeX](https://releases.aspose.com/tex/java/).
- **مجلدات العمل** – قرّر مجلد *الإدخال* (حيث توجد ملفات `.tex` الخاصة بك) ومجلد *الإخراج* (حيث سيتم حفظ ملفات PDF المولدة). استبدل `"Your Input Directory"` و `"Your Output Directory"` في الشفرات بالمسارات الفعلية.
- **مجموعة تطوير Java (JDK)** – نسخة 8 أو أحدث مثبتة ومُكوّنة في بيئة التطوير المتكاملة (IDE) أو نظام البناء الخاص بك.

## استيراد الحزم
أولاً، استورد الفئات التي سنحتاجها. احتفظ بهذا الجزء تمامًا كما هو موضح؛ فهو يجلب واجهة برمجة التطبيقات الأساسية لـ Aspose.TeX وفئة مساعدة تُستخدم في مشروع العينة.

```java
package com.aspose.tex.CustomTeXFormatFileCreation;

import java.io.IOException;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;

import util.Utils;
```

## دليل خطوة بخطوة لإنشاء صيغة TeX مخصصة

### الخطوة 1: تهيئة خيارات TeX (إنشاء محرك “بدون صيغة”)
نبدأ بإنشاء كائن `TeXOptions` الذي يخبر المحرك أننا لا نريد تحميل أي صيغة موجودة مسبقًا بعد. هذا هو الأساس لـ **إنشاء صيغة TeX مخصصة**.

```java
// Create TeX engine options for no format upon ObjectTeX engine extension.
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectIniTeX());
```

### الخطوة 2: تحديد مجلد إدخال TeX
أخبر Aspose.TeX بمكان العثور على ملفات المصدر، حزم الأنماط، وأي موارد مساعدة. استبدل `"Your Input Directory"` بالمسار المطلق أو النسبي لمجلد الإدخال في مشروعك.

```java
// Specify a file system working directory for the input.
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
```

> **نصيحة احترافية:** استخدم المسارات المطلقة أثناء التطوير لتجنب الالتباس مع مجلد العمل في IDE.

### الخطوة 3: تحديد مجلد إخراج TeX
الآن نحدد أين تُكتب ملفات PDF المجمّعة وملفات السجل. هذه هي خطوة **تحديد مجلد إخراج TeX**.

```java
// Specify a file system working directory for the output.
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### الخطوة 4: تشغيل أمر إنشاء الصيغة
بعد تكوين الخيارات، نطلب من Aspose.TeX تجميع الصيغة. الوسيط الأول هو اسم الصيغة الجديدة (`"customtex"`)، والوسيط الثاني يمرر الخيارات التي أعددناها للتو.

```java
// Run format creation.
TeXJob.createFormat("customtex", options);
```

بعد انتهاء هذا الاستدعاء، ستجد ملفًا باسم `customtex.fmt` (أو ملفًا ثنائيًا باسم مشابه) داخل مجلد الإخراج. يمكن تحميل هذا الملف في عمليات لاحقة لتسريع المعالجة.

### الخطوة 5: تنظيف مخرجات الطرفية (اختياري)
القطعة النهائية تضيف سطرًا جديدًا إلى وحدة التحكم لجعل عرض الطرفية يبدو مرتبًا بعد إكمال المهمة.

```java
// For further output to look fine.
options.getTerminalOut().getWriter().newLine();
// ExEnd:CreateCustomTeXFormatFile
```

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|-------|-----|
| **“الملف غير موجود” لملف مصدر .tex** | مسار مجلد الإدخال غير صحيح | تحقق من أن المسار الممرّر إلى `setInputWorkingDirectory` يطابق المجلد الذي يحتوي على ملفات `.tex`. |
| **رفض الإذن على مجلد الإخراج** | نقص في صلاحيات الكتابة | تأكد من أن عملية Java لديها صلاحيات كتابة للمجلد المحدد عبر `setOutputWorkingDirectory`. |
| **توقف إنشاء الصيغة** | تحميل عدد كبير من الحزم | قم بدمج مسبقًا فقط الحزم التي تحتاجها؛ تجنّب تحميل توزيع TeX الكامل إذا لم يكن ضروريًا. |

## الأسئلة المتكررة

**س: هل يمكنني إعادة استخدام نفس الصيغة المخصصة عبر تطبيقات Java متعددة؟**  
ج: نعم. ملف `.fmt` المولد مستقل عن النظام الأساسي ويمكن تحميله بواسطة أي نسخة من محرك Aspose.TeX.

**س: هل أحتاج إلى إعادة إنشاء الصيغة بعد إضافة ماكرو جديد؟**  
ج: يجب عليك تشغيل `TeXJob.createFormat` مرة أخرى كلما غيرت تعريفات الماكرو أو قائمة الحزم التي تعتمد عليها الصيغة.

**س: هل يمكن تعيين مجلدات الإدخال والإخراج برمجيًا أثناء التشغيل؟**  
ج: بالتأكيد — فقط استدعِ `options.setInputWorkingDirectory(...)` و `options.setOutputWorkingDirectory(...)` قبل استدعاء `TeXJob.createFormat` أو `TeXJob.process`.

**س: كيف يختلف هذا عن استخدام الصيغة الافتراضية `plain`؟**  
ج: الصيغة الافتراضية تحمل مجموعة عامة من الماكروهات في كل مرة، مما يضيف عبئًا. الصيغة المخصصة مُجمّعة مسبقًا، أسرع، وتضمن التخطيط الدقيق الذي حددته.

**س: هل سيعمل هذا على أنظمة تشغيل غير Windows؟**  
ج: نعم. Aspose.TeX for Java متعدد المنصات؛ فقط تأكد من أن مسارات الملفات تستخدم الفاصل الصحيح لنظام التشغيل الخاص بك.

## الخلاصة
أصبحت الآن تمتلك وصفة كاملة وجاهزة للإنتاج **لإنشاء صيغ TeX مخصصة** باستخدام Aspose.TeX for Java. من خلال **تحديد مجلد إدخال TeX** و **تحديد مجلد إخراج TeX**، تحصل على تحكم كامل في مكان قراءة ملفات المصدر ومكان كتابة النتائج، مما يؤدي إلى تنسيق موثوق وقابل للتكرار عبر جميع مشاريع Java الخاصة بك.

## الأسئلة الشائعة

### س1: أين يمكنني العثور على وثائق Aspose.TeX for Java؟
ج1: يمكنك الرجوع إلى [وثائق Aspose.TeX for Java](https://reference.aspose.com/tex/java/) للحصول على معلومات شاملة.

### س2: كيف يمكنني تنزيل Aspose.TeX for Java؟
ج2: يمكنك تنزيل المكتبة من [صفحة تنزيل Aspose.TeX for Java](https://releases.aspose.com/tex/java/).

### س3: أين يمكنني شراء Aspose.TeX for Java؟
ج3: يمكنك شراء Aspose.TeX for Java من [صفحة الشراء](https://purchase.aspose.com/buy).

### س4: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.TeX for Java؟
ج4: نعم، يمكنك الوصول إلى النسخة التجريبية المجانية [هنا](https://releases.aspose.com/).

### س5: كيف يمكنني الحصول على الدعم لـ Aspose.TeX for Java؟
ج5: يمكنك طلب الدعم في [منتدى Aspose.TeX](https://forum.aspose.com/c/tex/47).

---

**Last Updated:** 2025-12-03  
**Tested With:** Aspose.TeX for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
