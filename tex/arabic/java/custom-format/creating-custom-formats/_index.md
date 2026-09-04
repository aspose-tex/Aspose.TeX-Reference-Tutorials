---
date: 2026-09-04
description: تعلم كيفية إنشاء PDF من TeX في Java باستخدام Aspose.TeX، ضبط مجلدات العمل،
  وإنشاء ملفات صيغ TeX مخصصة لضمان تنسيق ثابت.
keywords:
- generate pdf from tex
- set working directories
- create custom tex format
- set tex input directory
- set tex output directory
lastmod: 2026-09-04
linktitle: إنشاء صيغ TeX مخصصة لضمان تنسيق ثابت في Java
og_description: إنشاء PDF من TeX في Java باستخدام Aspose.TeX. تعلم كيفية ضبط مجلدات
  العمل، إنشاء صيغ TeX مخصصة، وضمان تنسيق ثابت.
og_image_alt: Screenshot of Java code generating PDF from TeX using Aspose.TeX
og_title: إنشاء PDF من TeX وإنشاء صيغ مخصصة في Java
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to generate PDF from TeX in Java using Aspose.TeX, set working
    directories, and create custom TeX format files for consistent typesetting.
  headline: How to generate PDF from TeX and create formats in Java
  type: TechArticle
- description: Learn how to generate PDF from TeX in Java using Aspose.TeX, set working
    directories, and create custom TeX format files for consistent typesetting.
  name: How to generate PDF from TeX and create formats in Java
  steps:
  - name: Initialize TeX options (create a “no‑format” engine)
    text: The `TeXOptions` class lets you configure the TeX engine before any format
      is loaded.
  - name: Set the TeX input directory
    text: '`setInputWorkingDirectory` points the engine at the folder that contains
      your source `.tex` files, style packages, and any custom fonts. Using an absolute
      path during development avoids confusion with the IDE’s default working directory.
      > **Pro tip:** Keep your input folder read‑only in production '
  - name: Set the TeX output directory
    text: '`setOutputWorkingDirectory` defines where the engine writes compiled PDFs,
      log files, and auxiliary data. Separating output from source makes cleanup easier
      and enables you to archive results automatically.'
  - name: Run the format creation command
    text: Calling `createFormat("customtex", options)` tells Aspose.TeX to compile
      all packages referenced in the input directory into a binary format file named
      `customtex.fmt`. This step typically finishes within seconds, even for large
      collections of packages, because the engine only parses each macro once
  - name: Clean up the terminal output (optional)
    text: A simple `System.out.println()` adds a newline after the process finishes,
      keeping the console output tidy when you chain multiple conversions in a batch
      job.
  type: HowTo
- questions:
  - answer: You can refer to the [Aspose.TeX for Java documentation](https://reference.aspose.com/tex/java/)
      for comprehensive API details and usage examples.
    question: Where can I find the documentation for Aspose.TeX for Java?
  - answer: You can download the library from the [Aspose.TeX download page](https://releases.aspose.com/tex/java/).
    question: How can I download Aspose.TeX for Java?
  - answer: You can buy Aspose.TeX for Java from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.TeX for Java?
  - answer: Yes, you can access the free trial version on the [Aspose.TeX free trial
      download page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.TeX for Java?
  - answer: You can seek support on the [Aspose.TeX forum](https://forum.aspose.com/c/tex/47).
    question: How can I get support for Aspose.TeX for Java?
  type: FAQPage
second_title: Aspose.TeX Java API
tags:
- generate pdf
- Aspose.TeX
- Java typesetting
- custom tex format
title: كيفية إنشاء PDF من TeX وإنشاء صيغ في Java
url: /ar/java/custom-format/creating-custom-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء PDF من TeX وإنشاء صيغ في Java

إنشاء PDF من TeX هو طلب شائع عندما تحتاج إلى مستندات علمية أو رياضية عالية الجودة في خط أنابيب مبني على Java. في هذا الدرس ستتعرف على كيفية **إنشاء صيغة TeX مخصصة** باستخدام Aspose.TeX، **تحديد مجلدات إدخال وإخراج TeX**، وأخيرًا **إنشاء PDF من TeX** بطريقة قابلة للتكرار وعالية الأداء. في النهاية ستحصل على ملف `.fmt` قابل لإعادة الاستخدام يضمن تنسيقًا موحدًا لكل مستند تقوم بمعالجته.

## إجابات سريعة
- **ماذا يعني “إنشاء صيغة TeX مخصصة”؟** يعني أنه يتم تجميع مجموعة من الماكروهات، الخطوط، وقواعد التخطيط في ملف ثنائي يحملها المحرك فورًا.  
- **هل أحتاج إلى ترخيص؟** نسخة التجربة المجانية كافية للتطوير؛ الترخيص التجاري مطلوب للنشر في بيئات الإنتاج.  
- **ما إصدار JDK المطلوب؟** Java 8 أو أعلى (يوصى بـ Java 17 LTS).  
- **هل يمكن تغيير مجلد الإدخال أثناء التشغيل؟** نعم—استدعِ `setInputWorkingDirectory` على كائن الخيارات.  
- **هل مجلد الإخراج قابل للتكوين؟** بالتأكيد—استخدم `setOutputWorkingDirectory` لتحديد أين تُكتب ملفات PDF والسجلات.

## كيفية إنشاء صيغة TeX في Java؟

`TeXOptions` هو كائن تكوين يتحكم في إعدادات محرك Aspose.TeX. أولاً، أنشئ كائن `TeXOptions`، وحدده إلى مجلد المصدر الخاص بك، وعرّف مكان كتابة النتائج، ثم استدعِ `createFormat("customtex", options)`. تقوم طريقة `createFormat` بتجميع ملفات المصدر في ملف ثنائي `.fmt` قابل لإعادة الاستخدام، يمكنك تحميله لتوليد PDF لاحقًا. يقلل هذا النهج من وقت التجميع حتى 70 % ويضمن تخطيطًا ثابتًا عبر جميع المستندات.

## لماذا نحدد مجلدات إدخال وإخراج TeX؟

تحديد مجلد الإدخال يخبر المحرك أين يجد ملفات `.tex`، ملفات الخطوط، والحزم المساعدة، بينما يحدد مجلد الإخراج أين تُحفظ ملفات PDF المجمعة، ملفات السجل، والملفات المؤقتة. يزيل تكوين المجلدات الصحيح أخطاء “الملف غير موجود”، ويحافظ على بنية المشروع نظيفة، ويسمح بتشغيل تحويلات متعددة بالتوازي دون تصادم.

## المتطلبات المسبقة
قبل الغوص في الشيفرة، تأكد من وجود ما يلي:

- **Aspose.TeX for Java** – حمّله من [صفحة تنزيل Aspose.TeX](https://releases.aspose.com/tex/java/).
- **مجلدات العمل** – حدد مجلد *الإدخال* (حيث توجد ملفات `.tex`) ومجلد *الإخراج* (حيث سُتحفظ ملفات PDF المُولدة). استبدل `"Your Input Directory"` و `"Your Output Directory"` في المقاطع بالمسارات الفعلية لديك.
- **مجموعة تطوير Java (JDK)** – الإصدار 8 أو أحدث مثبت ومُعد في بيئتك التطويرية أو نظام البناء.

## استيراد الحزم
فئة `TeXOptions` تُكوّن محرك Aspose.TeX، وتوفر الأداة `FileHelper` مساعدات بسيطة لنظام الملفات تُستخدم في مشروع العينة.

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

تتيح لك فئة `TeXOptions` تكوين محرك TeX قبل تحميل أي صيغة.

```java
// Create TeX engine options for no format upon ObjectTeX engine extension.
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectIniTeX());
```

### الخطوة 2: تحديد مجلد إدخال TeX

`setInputWorkingDirectory` يوجه المحرك إلى المجلد الذي يحتوي على ملفات `.tex` المصدر، حزم الأنماط، وأي خطوط مخصصة. استخدام مسار مطلق أثناء التطوير يجنب الالتباس مع مجلد العمل الافتراضي للـ IDE.

```java
// Specify a file system working directory for the input.
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
```

> **نصيحة احترافية:** اجعل مجلد الإدخال للقراءة فقط في بيئة الإنتاج لتفادي تعديل ملفات TeX المصدرية عن طريق الخطأ.

### الخطوة 3: تحديد مجلد إخراج TeX

`setOutputWorkingDirectory` يحدد أين يكتب المحرك ملفات PDF المجمعة، ملفات السجل، والبيانات المساعدة. فصل الإخراج عن المصدر يسهل عملية التنظيف ويسمح بأرشفة النتائج تلقائيًا.

```java
// Specify a file system working directory for the output.
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### الخطوة 4: تشغيل أمر إنشاء الصيغة

استدعاء `createFormat("customtex", options)` يُخبر Aspose.TeX بتجميع جميع الحزم المشار إليها في مجلد الإدخال إلى ملف صيغة ثنائي يُسمى `customtex.fmt`. عادةً ما يكتمل هذا الخطوة خلال ثوانٍ، حتى مع مجموعات كبيرة من الحزم، لأن المحرك يقرأ كل ماكرو مرة واحدة فقط.

```java
// Run format creation.
TeXJob.createFormat("customtex", options);
```

بعد انتهاء الاستدعاء، ستجد `customtex.fmt` داخل مجلد الإخراج. تحميل هذا الملف في عمليات لاحقة يقلل وقت التجميع لكل مستند حتى **70 %**، وفقًا لمقاييس Aspose.

### الخطوة 5: تنظيف مخرجات الطرفية (اختياري)

إضافة سطر `System.out.println()` بسيط يضيف سطرًا جديدًا بعد انتهاء العملية، مما يحافظ على نظافة مخرجات الكونسول عند ربط تحويلات متعددة في مهمة دفعة.

```java
// For further output to look fine.
options.getTerminalOut().getWriter().newLine();
// ExEnd:CreateCustomTeXFormatFile
```

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|-------|-----|
| **“الملف غير موجود” لملف .tex المصدر** | مسار مجلد الإدخال غير صحيح | تحقق من أن المسار الممرّر إلى `setInputWorkingDirectory` يطابق المجلد الذي يحتوي على ملفات `.tex`. |
| **رفض الإذن على مجلد الإخراج** | نقص صلاحيات الكتابة | تأكد من أن عملية Java لديها صلاحيات كتابة للمجلد المحدد عبر `setOutputWorkingDirectory`. |
| **توقف إنشاء الصيغة** | تحميل عدد كبير من الحزم | قم بتجميع الحزم التي تحتاجها فقط؛ يمكن لـ Aspose.TeX التعامل مع **60+** صيغة إدخال دون تحميل توزيع TeX الكامل. |

## الأسئلة المتكررة

**س: أين يمكنني العثور على وثائق Aspose.TeX for Java؟**  
ج: يمكنك الرجوع إلى [وثائق Aspose.TeX for Java](https://reference.aspose.com/tex/java/) للحصول على تفاصيل شاملة عن الـ API وأمثلة الاستخدام.

**س: كيف يمكنني تنزيل Aspose.TeX for Java؟**  
ج: يمكنك تنزيل المكتبة من [صفحة تنزيل Aspose.TeX](https://releases.aspose.com/tex/java/).

**س: أين يمكنني شراء Aspose.TeX for Java؟**  
ج: يمكنك شراء Aspose.TeX for Java من [صفحة الشراء](https://purchase.aspose.com/buy).

**س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.TeX for Java؟**  
ج: نعم، يمكنك الوصول إلى نسخة التجربة المجانية عبر [صفحة تنزيل نسخة التجربة المجانية لـ Aspose.TeX](https://releases.aspose.com/).

**س: كيف يمكنني الحصول على دعم لـ Aspose.TeX for Java؟**  
ج: يمكنك طلب الدعم عبر [منتدى Aspose.TeX](https://forum.aspose.com/c/tex/47).

## الخلاصة
أصبح لديك الآن وصفة كاملة وجاهزة للإنتاج **لإنشاء PDF من TeX** باستخدام Aspose.TeX for Java. من خلال **تحديد مجلد إدخال TeX** و**تحديد مجلد إخراج TeX**، تحصل على تحكم كامل في مكان قراءة الملفات المصدرية ومكان كتابة النتائج، مما يضمن عملية تنضيد موثوقة وقابلة للتكرار عبر جميع مشاريع Java الخاصة بك. أعد استخدام ملف `customtex.fmt` في أي تشغيل لاحق لتستمتع بتجميع أسرع وتخطيط ثابت.

---

**آخر تحديث:** 2026-09-04  
**تم الاختبار مع:** Aspose.TeX for Java 24.11  
**المؤلف:** Aspose

## دروس ذات صلة

- [Typesetting Custom Tex Formats](/tex/java/custom-tex-formats/typesetting-custom-tex-formats/)
- [How to Read TeX – Set Input Directory Java Guide with Aspose.TeX for Java](/tex/java/advanced-io/required-input-directory/)
- [How to Convert TeX to XPS in Java – Step by Step Guide](/tex/java/typesetting-tex-to-xps/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}