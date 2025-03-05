---
title: التنضيد TeX إلى XPS في .NET
linktitle: التنضيد TeX إلى XPS في .NET
second_title: Aspose.TeX .NET API
description: قم بتحويل مستندات TeX بسهولة إلى XPS في .NET باستخدام Aspose.TeX. استكشف دليلنا المفصّل خطوة بخطوة للحصول على تجربة تكامل سلسة.
type: docs
weight: 10
url: /ar/net/xps-output/typeset-tex-to-xps/
---
## مقدمة

مرحبًا بك في دليلنا خطوة بخطوة حول التنضيد TeX إلى XPS في .NET باستخدام مكتبة Aspose.TeX القوية. إذا كنت تتطلع إلى تحويل مستندات TeX إلى تنسيق XPS بسلاسة في تطبيقات .NET الخاصة بك، فقد وصلت إلى المكان الصحيح. في هذا البرنامج التعليمي، سنرشدك خلال العملية بأكملها، مع تفصيل كل خطوة لضمان التنفيذ السلس.

## المتطلبات الأساسية

قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

-  Aspose.TeX لـ .NET: تأكد من تثبيت مكتبة Aspose.TeX. يمكنك تنزيله[هنا](https://releases.aspose.com/tex/net/).

- التوثيق: تعرف على المكتبة من خلال الرجوع إلى الوثائق[هنا](https://reference.aspose.com/tex/net/).

- أدلة الإدخال والإخراج: قم بإعداد أدلة الإدخال والإخراج كما هو محدد في رمز المثال.

الآن بعد أن قمت بإعداد كل شيء، دعنا ننتقل إلى الدليل خطوة بخطوة.

## استيراد مساحات الأسماء

في تطبيق .NET الخاص بك، ابدأ باستيراد مساحات الأسماء الضرورية. وهذا يضمن أن لديك إمكانية الوصول إلى وظائف Aspose.TeX المطلوبة لتنضيد TeX إلى XPS.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
```

## الخطوة 1: ضبط خيارات التحويل

حدد خيارات التحويل، مع تحديد تنسيق ObjectTeX على امتداد محرك ObjectTeX. قم أيضًا بتعيين اسم الوظيفة وأدلة الإدخال والإخراج وتفاصيل الإخراج الطرفي.

```csharp
// قم بإنشاء خيارات تحويل لتنسيق ObjectTeX الافتراضي عند امتداد محرك ObjectTeX.
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
// حدد اسم الوظيفة.
options.JobName = "external-file-stream";
// تحديد دليل عمل نظام الملفات للإدخال.
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
// تحديد دليل عمل نظام الملفات للإخراج.
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
// حدد أنه يجب كتابة الإخراج الطرفي إلى ملف في دليل عمل الإخراج.
// اسم الملف هو <job_name>.trm.
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## الخطوة 2: إنشاء دفق مستند XPS

افتح دفقًا لكتابة مستند XPS المنضدي. اسم الملف ليس بالضرورة هو نفس اسم المهمة.

```csharp
using (Stream stream = File.Open(Path.Combine("Your Output Directory", options.JobName + ".xps"), FileMode.Create))
```

## الخطوة 3: قم بتشغيل وظيفة TeX

ابدأ مهمة TeX وقم بتشغيلها، مع تحديد اسم المستند وXpsDevice وخيارات التحويل.

```csharp
new TeXJob("hello-world", new XpsDevice(stream), options).Run();
```

تهانينا! لقد نجحت في كتابة TeX على XPS في .NET باستخدام Aspose.TeX. لا تتردد في استكشاف المزيد من الميزات والخيارات بناءً على متطلباتك المحددة.

## خاتمة

في هذا البرنامج التعليمي، قمنا بتغطية الخطوات الأساسية لتحويل مستندات TeX بسلاسة إلى تنسيق XPS في .NET باستخدام Aspose.TeX. باتباع هذا الدليل، اكتسبت رؤى قيمة حول إمكانيات المكتبة وكيفية الاستفادة منها في مشاريعك.

## الأسئلة الشائعة

### س1: هل Aspose.TeX متوافق مع .NET Core؟

ج1: نعم، Aspose.TeX متوافق تمامًا مع .NET Core.

### س2: هل يمكنني استخدام Aspose.TeX للمشاريع التجارية؟

ج2: بالتأكيد! Aspose.TeX متاح للاستخدام التجاري والشخصي.

### س3: أين يمكنني العثور على أمثلة وموارد إضافية؟

 ج3: استكشف وثائق Aspose.TeX[هنا](https://reference.aspose.com/tex/net/)لمزيد من الأمثلة والموارد التفصيلية.

### س4: كيف يمكنني الحصول على الدعم لـ Aspose.TeX؟

 ج4: قم بزيارة منتدى دعم Aspose.TeX[هنا](https://forum.aspose.com/c/tex/47) للحصول على المساعدة من المجتمع.

### س5: هل هناك نسخة تجريبية مجانية متاحة؟

 ج5: نعم، يمكنك الوصول إلى النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).