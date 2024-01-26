---
title: تجاوز اسم المهمة وكتابة المخرجات الطرفية على القرص (C#)
linktitle: تجاوز اسم المهمة وكتابة المخرجات الطرفية على القرص (C#)
second_title: Aspose.TeX .NET API
description: اكتشف كيفية استخدام Aspose.TeX لـ .NET لتجاوز أسماء الوظائف والتقاط مخرجات المحطة الطرفية. اتبع دليلنا الشامل لإدارة ملفات TeX بسلاسة.
type: docs
weight: 10
url: /ar/net/job-output/override-job-name-disk-output-csharp/
---
## مقدمة

مرحبًا بك في هذا الدليل التفصيلي حول استخدام Aspose.TeX لـ .NET لتجاوز أسماء المهام وكتابة المخرجات الطرفية على القرص بلغة البرمجة C#. Aspose.TeX for .NET هي مكتبة قوية تتيح لك العمل بسلاسة مع ملفات TeX، وفي هذا البرنامج التعليمي، سنركز على مهمة محددة: تجاوز أسماء الوظائف والتقاط مخرجات المحطة الطرفية.

## المتطلبات الأساسية

قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

-  Aspose.TeX لمكتبة .NET: تأكد من تثبيت مكتبة Aspose.TeX لـ .NET. يمكنك تنزيله من[موقع Aspose.TeX](https://releases.aspose.com/tex/net/).

- بيئة تطوير .NET: تمتع ببيئة تطوير .NET عاملة، بما في ذلك بيئة تطوير متكاملة (IDE) مثل Visual Studio.

- المعرفة الأساسية لـ C#: تعرف على أساسيات لغة البرمجة C#.

- أدلة الإدخال والإخراج: قم بإعداد أدلة الإدخال والإخراج لملفات TeX الخاصة بك.

## استيراد مساحات الأسماء

في كود C# الخاص بك، تأكد من تضمين مساحات الأسماء الضرورية للوصول إلى وظائف Aspose.TeX:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

## الخطوة 1: إنشاء خيارات التحويل

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

أنشئ TeXOptions باستخدام ConsoleAppOptions، مع تحديد ObjectTeX باعتباره TeXConfig.

## الخطوة 2: تحديد اسم الوظيفة

```csharp
options.JobName = "overridden-job-name";
```

حدد اسم المهمة لتجاوز الاسم الافتراضي.

## الخطوة 3: تحديد دليل عمل الإدخال

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

قم بتعيين دليل عمل الإدخال لملفات TeX الخاصة بك.

## الخطوة 4: تحديد دليل عمل الإخراج

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

حدد دليل عمل الإخراج لحفظ ملفات TeX المعالجة.

## الخطوة 5: كتابة المخرجات الطرفية على القرص

```csharp
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

قم بتكوين الإخراج الطرفي ليتم كتابته إلى ملف في دليل الإخراج.

## الخطوة 6: تشغيل المهمة

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

قم بإنشاء TeXJob، مع تحديد اسم المهمة وجهاز الإخراج (XpsDevice) والخيارات. وأخيرا، قم بتشغيل المهمة.

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية تجاوز أسماء المهام وكتابة المخرجات الطرفية على القرص باستخدام Aspose.TeX لـ .NET في C#. تعتبر هذه الإمكانية ذات قيمة لإدارة مهام معالجة TeX الخاصة بك بكفاءة.

## الأسئلة الشائعة

### س1: هل يمكنني استخدام Aspose.TeX لـ .NET مع مكتبات .NET الأخرى؟

ج1: نعم، يمكن دمج Aspose.TeX for .NET مع مكتبات .NET الأخرى بسلاسة.

### س2: هل تتوفر نسخة تجريبية مجانية من Aspose.TeX لـ .NET؟

 ج2: نعم، يمكنك تنزيل نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).

### س3: كيف يمكنني الحصول على دعم Aspose.TeX لـ .NET؟

 ج3: قم بزيارة[منتدى Aspose.TeX](https://forum.aspose.com/c/tex/47) للحصول على المجتمع والدعم.

### س4: هل التراخيص المؤقتة متاحة لـ Aspose.TeX لـ .NET؟

 ج4: نعم، يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).

### س5: أين يمكنني العثور على الوثائق الخاصة بـ Aspose.TeX لـ .NET؟

 ج5: الوثائق متاحة[هنا](https://reference.aspose.com/tex/net/).