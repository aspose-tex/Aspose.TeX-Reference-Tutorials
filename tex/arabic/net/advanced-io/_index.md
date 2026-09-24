---
date: 2026-09-24
description: تعلم كيفية تكوين دليل إدخال TeX، وتدفقات البيانات، والصور، وإدخال الطرفية
  باستخدام Aspose.TeX لـ .NET في C#.
keywords:
- configure tex input directory
- add image stream tex
- add images from stream
lastmod: 2026-09-24
linktitle: Aspose.TeX المتقدم للإدخال والإخراج
og_description: قم بتكوين دليل إدخال TeX، وإضافة تدفقات الصور، ومعالجة إدخال الطرفية
  باستخدام Aspose.TeX لـ .NET في C#. تعلم خطوة بخطوة.
og_image_alt: Guide showing how to configure TeX input directory and streams in Aspose.TeX
  for .NET
og_title: تكوين دليل إدخال TeX – دليل Aspose.TeX المتقدم
schemas:
- author: Aspose
  dateModified: '2026-09-24'
  description: Learn how to configure TeX input directory, streams, images, and terminal
    input using Aspose.TeX for .NET in C#.
  headline: Configure TeX input directory – Advanced Aspose.TeX Input and Output
  type: TechArticle
- description: Learn how to configure TeX input directory, streams, images, and terminal
    input using Aspose.TeX for .NET in C#.
  name: Configure TeX input directory – Advanced Aspose.TeX Input and Output
  steps:
  - name: instantiate TeXInputOptions
    text: Assign the base folder that holds the primary TeX source.
  - name: add extra search paths
    text: If your project stores figures in a separate folder (e.g., *Images*), call
      `AddSearchPath` to include it.
  - name: hand the options to the processor
    text: Create a `TeXProcessor`, provide the configured options, and invoke `Process`
      or `Render`.
  type: HowTo
- questions:
  - answer: Yes—you can create a new `TeXInputOptions` instance with a different `BaseFolder`
      and pass it to a fresh `TeXProcessor` whenever you need to reconfigure.
    question: Can I change the input directory at runtime?
  - answer: Retrieve the image as a `byte[]`, wrap it in a `MemoryStream`, and call
      `TeXInputOptions.AddImage("image.png", stream)`. The name must match the reference
      in your `.tex` file.
    question: How do I add images that are stored in a database?
  - answer: Absolutely. Convert the incoming string to a `MemoryStream`, set it as
      the source for `TeXProcessor`, and render directly to your desired output format.
    question: Is it possible to process LaTeX code received from a web API without
      saving a file?
  - answer: Dispose of any streams you create, and for large workloads invoke `TeXProcessor.Cleanup()`
      to free native resources.
    question: Do I need to call any cleanup methods after processing?
  - answer: The two tutorial links above contain full code samples that demonstrate
      each scenario in detail, including error handling and performance tips.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.TeX .NET API
tags:
- Aspose.TeX
- input directory
- C# document processing
title: تكوين دليل إدخال TeX – إدخال وإخراج Aspose.TeX المتقدم
url: /ar/net/advanced-io/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تكوين دليل إدخال TeX في Aspose.TeX لـ .NET

Aspose.TeX لـ .NET يتيح لك تضمين معالجة TeX المتكاملة مباشرةً في تطبيقات C# الخاصة بك. في هذا البرنامج التعليمي ستتعلم كيفية **تكوين دليل إدخال TeX**، وتغذية محتوى LaTeX من التدفقات، وإضافة الصور دون لمس نظام الملفات. إذا كنت بحاجة إلى تحكم دقيق في المكان الذي يبحث فيه المحرك عن ملفات `.tex` والموارد، فأنت في المكان المناسب.

## إجابات سريعة
- **ماذا يعني “configure tex input directory”؟**  
  يخبر Aspose.TeX بمكان العثور على ملف `.tex` الرئيسي، والملفات المساعدة، والرسومات.
- **أي فئة تحدد مسارات الإدخال؟**  
  `TeXInputOptions` يخزن المجلد الأساسي وأي مواقع بحث إضافية.
- **هل يمكنني تحميل صورة من تدفق الذاكرة؟**  
  نعم—استخدم `TeXInputOptions.AddImage` مع كائن `Stream`.
- **هل من الممكن تجميع شفرة LaTeX المقدمة في وقت التشغيل؟**  
  بالطبع—مرّر `MemoryStream` يحتوي على النص المصدر إلى المعالج.
- **هل أحتاج إلى ترخيص للاستخدام في الإنتاج؟**  
  يتطلب ترخيص Aspose.TeX صالح للنشر غير التجريبي.

## ما هو TeXInputOptions؟
`TeXInputOptions` هو كائن التكوين الذي يحدد المجلد الأساسي ومسارات البحث الإضافية لموارد TeX. إعدادها بشكل صحيح يزيل أخطاء “الملف غير موجود” ويسمح لك بتنظيم الأصول.

## كيفية تكوين دليل إدخال tex؟
`TeXInputOptions` هو كائن تكوين يحدد المجلد الأساسي ومسارات البحث الإضافية لموارد TeX. حمّل المستند الرئيسي وأخبر المعالج بمكان البحث عن كل شيء في بضع أسطر فقط. يشرح هذا الجواب المباشر الخطوات الأساسية قبل أي تفاصيل إضافية.

أنشئ مثيلًا من `TeXInputOptions`، عيّن `BaseFolder` إلى المجلد الذي يحتوي على ملف `.tex` الأساسي الخاص بك، أضف أي مجلدات فرعية تحتوي على صور أو ملفات مساعدة، ومرّر الخيارات إلى `TeXProcessor`. سيقوم المحرك بعد ذلك بحل جميع المراجع النسبية تلقائيًا.

### الخطوة 1: إنشاء مثيل TeXInputOptions
عيّن المجلد الأساسي الذي يحتوي على مصدر TeX الرئيسي.

### الخطوة 2: إضافة مسارات بحث إضافية
إذا كان مشروعك يخزن الرسوم في مجلد منفصل (مثال: *Images*)، استدعِ `AddSearchPath` لتضمينه.

### الخطوة 3: تمرير الخيارات إلى المعالج
أنشئ `TeXProcessor`، قدّم الخيارات المكوّنة، واستدعِ `Process` أو `Render`.

## كيفية إضافة الصور باستخدام Aspose.TeX
يمكن توفير الصور المشار إليها في ملف TeX إما عبر مجلد أو مباشرةً من تدفق. توفير تدفق يكون مفيدًا عندما تُخزن الصور في قاعدة بيانات أو تُنشأ في الوقت الفعلي. `AddImage(string name, Stream data)` يسجل تدفق صورة بالاسم المحدد لاستخدامه في مستند TeX. هذه الطريقة تتيح لك تجنب الملفات المؤقتة وتسرّع المعالجة.

## كيفية معالجة التدفقات في Aspose.TeX
عندما يتم إنشاء مصدر LaTeX الخاص بك ديناميكيًا—ربما من مدخلات المستخدم أو خدمة ويب—يمكنك تغذيته مباشرةً إلى المعالج دون كتابة ملف. `TeXProcessor` يعالج محتوى TeX ويمكنه قبول `MemoryStream` يحتوي على شفرة LaTeX المصدرية. غلف سلسلة LaTeX في `MemoryStream`، عيّنها كتدفق مصدر في `TeXProcessor`، وشغّل التحويل. تعمل هذه التقنية بنفس الفاعلية لخدمات السحابة حيث تكون عمليات الإدخال/الإخراج على القرص مكلفة.

## لماذا تستخدم Aspose.TeX لإدخال/إخراج متقدم؟
Aspose.TeX يدعم **أكثر من 30 تنسيقًا للإدخال والإخراج** (بما في ذلك PDF، PNG، SVG) ويمكنه عرض مستندات مئات الصفحات دون تحميل الملف بالكامل في الذاكرة. تصميمه القائم على التدفق يقلل من عبء الإدخال/الإخراج بنسبة تصل إلى 40 % مقارنةً بسير العمل القائم على الملفات، مما يجعله مثاليًا لتطبيقات الخوادم عالية الإنتاجية.

## المتطلبات المسبقة
- .NET 6.0 أو أحدث (المكتبة تعمل أيضًا مع .NET Core 3.1+ و .NET Framework 4.6.1+)
- حزمة NuGet الخاصة بـ Aspose.TeX لـ .NET (الإصدار 24.11 أو أحدث)
- ترخيص Aspose.TeX صالح للاستخدام في الإنتاج

## استكشاف Aspose.TeX: بوابة لمعالجة المستندات المتقدمة
لمشاهدة التكوين عمليًا، اتبع دليلنا خطوة بخطوة **[Specify Required Input Directory for Aspose.TeX (C#)](./required-input-directory-csharp/)**. يشرح هذا البرنامج التعليمي كيفية إنشاء كائن `TeXInputOptions` وعرض مخرجات PDF.  
**[Specify Required Input Directory for Aspose.TeX (C#)](./required-input-directory-csharp/)**

## إتقان التدفقات، الصور، وإدخال الطرفية في Aspose.TeX لـ C#
للتعمق أكثر في تغذية LaTeX من الذاكرة، وإضافة الصور عبر التدفقات، واستخدام إدخال على نمط الطرفية، اطلع على **[Master Streams, Images, & Terminal Input in Aspose.TeX for C#](./stream-input-image-output-terminal-input-csharp/)**. يوضح كيفية دمج Aspose.TeX في واجهات برمجة تطبيقات الويب، والخدمات الخلفية، وأدوات سطر الأوامر.  
**[Master Streams, Images, & Terminal Input in Aspose.TeX for C#](./stream-input-image-output-terminal-input-csharp/)**

## المشكلات الشائعة والحلول
- **أخطاء “File not found”** – تحقق من أن `BaseFolder` يشير إلى الدليل الصحيح وأن أي مسارات بحث إضافية تم إضافتها قبل العرض.
- **عدم تحميل الصور** – تأكد من أن اسم الصورة في `AddImage` يطابق تمامًا الاسم المستخدم في مصدر TeX، بما في ذلك امتداد الملف.
- **ارتفاع استهلاك الذاكرة** – عند معالجة مستندات كبيرة جدًا، استدعِ `TeXProcessor.Cleanup()` بعد العرض لتحرير الموارد غير المدارة.

## الأسئلة المتكررة

**س: هل يمكنني تغيير دليل الإدخال في وقت التشغيل؟**  
ج: نعم—يمكنك إنشاء مثيل جديد من `TeXInputOptions` بمجلد `BaseFolder` مختلف وتمريره إلى `TeXProcessor` جديد كلما احتجت إلى إعادة التكوين.

**س: كيف يمكنني إضافة الصور المخزنة في قاعدة بيانات؟**  
ج: استرجع الصورة كـ `byte[]`، غلفها في `MemoryStream`، واستدعِ `TeXInputOptions.AddImage("image.png", stream)`. يجب أن يتطابق الاسم مع المرجع في ملف `.tex` الخاص بك.

**س: هل من الممكن معالجة شفرة LaTeX المستلمة من واجهة برمجة تطبيقات ويب دون حفظ ملف؟**  
ج: بالتأكيد. حوّل السلسلة الواردة إلى `MemoryStream`، عيّنها كمصدر لـ `TeXProcessor`، واعرض مباشرةً إلى تنسيق الإخراج المطلوب.

**س: هل يجب استدعاء أي طرق تنظيف بعد المعالجة؟**  
ج: قم بتحرير أي تدفقات تنشئها، وللأحمال الكبيرة استدعِ `TeXProcessor.Cleanup()` لتحرير الموارد الأصلية.

**س: أين يمكنني العثور على أمثلة أكثر تقدمًا؟**  
ج: الروابط التعليمية المذكورة أعلاه تحتوي على عينات كود كاملة توضح كل سيناريو بالتفصيل، بما في ذلك معالجة الأخطاء ونصائح الأداء.

**آخر تحديث:** 2026-09-24  
**تم الاختبار مع:** Aspose.TeX 24.11 لـ .NET  
**المؤلف:** Aspose

## دروس ذات صلة

- [الحصول على تدفق ملف TeX (C#) باستخدام Aspose.TeX API دليل الإدخال المطلوب](/tex/net/advanced-io/required-input-directory-csharp/)
- [إنشاء XPS من TeX باستخدام أنظمة الملفات – Aspose.TeX لـ .NET](/tex/net/file-input-output/filesystem-input-xps-output/)
- [تحويل LaTeX إلى PNG باستخدام Aspose.TeX لـ .NET – معالجة مدخلات نظام الملفات وZIP](/tex/net/file-input-output/required-inputs-from-filesystem-and-zip/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}