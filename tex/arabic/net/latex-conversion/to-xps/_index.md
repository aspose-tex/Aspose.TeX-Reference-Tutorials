---
title: LaTeX إلى XPS في .NET - تحويل سهل باستخدام Aspose.TeX
linktitle: LaTeX إلى XPS في .NET - تحويل سهل باستخدام Aspose.TeX
second_title: Aspose.TeX .NET API
description: يمكنك بسهولة تحويل LaTeX إلى XPS في .NET باستخدام Aspose.TeX. عالية الجودة وقابلة للتخصيص وفعالة.
type: docs
weight: 13
url: /ar/net/latex-conversion/to-xps/
---
## مقدمة

هل تبحث عن طريقة سلسة لتحويل مستندات LaTeX إلى تنسيق XPS في تطبيقات .NET الخاصة بك؟ يوفر Aspose.TeX for .NET حلاً قويًا لهذه المهمة، مما يجعل عملية التحويل بسيطة وفعالة. سيرشدك هذا الدليل التفصيلي خطوة بخطوة خلال عملية تحويل LaTeX إلى XPS باستخدام Aspose.TeX، مما يضمن تحقيق نتائج دقيقة وعالية الجودة.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

- معرفة عملية بتطوير C# و.NET.
-  تم تثبيت Aspose.TeX لمكتبة .NET. يمكنك تنزيله[هنا](https://releases.aspose.com/tex/net/).
- فهم بناء جملة LaTeX وبنيته.

## استيراد مساحات الأسماء

لنبدأ باستيراد مساحات الأسماء الضرورية لتطبيق .NET الخاص بنا. تعد مساحات الأسماء هذه ضرورية للتفاعل مع وظائف Aspose.TeX.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
using System.Text;
```

## الخطوة 1: إعداد خيارات التحويل

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectLaTeX);
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

هنا، نقوم بتهيئة خيارات التحويل وتعيين دليل عمل الإدخال لملفات LaTeX الخاصة بك.

## الخطوة 2: ضبط وضع التفاعل

```csharp
options.Interaction = Interaction.NonstopMode;
```

حدد وضع التفاعل، حيث قمنا بتعيينه على وضع عدم التوقف للتحويل دون انقطاع.

## الخطوة 3: تعيين اسم الوظيفة (اختياري)

```csharp
// options.JobName = "my-job-name";
```

يمكنك تعيين اسم مهمة مخصص إذا لزم الأمر.

## الخطوة 4: تعيين التاريخ في العنوان (اختياري)

```csharp
// options.DateTime = new System.DateTime(2022, 12, 18);
```

أجبر محرك TeX على إخراج تاريخ محدد في العنوان.

## الخطوة 5: تجاهل الحزم المفقودة

```csharp
options.IgnoreMissingPackages = true;
```

اضبط على "صحيح" إذا كنت تريد أن يتخطى المحرك الحزم المفقودة دون أخطاء.

## الخطوة 6: تعطيل الحروف المركبة

```csharp
options.NoLigatures = true;
```

اضبط على "صحيح" لمنع المحرك من إنشاء الحروف المركبة.

## الخطوة 7: كرر المهمة (اختياري)

```csharp
// options.Repeat = true;
```

اطلب من المحرك تكرار المهمة إذا لزم الأمر.

## الخطوة 8: تحديد دليل عمل الإخراج

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

قم بتعيين دليل عمل الإخراج لملفات XPS المحولة.

## الخطوة 9: تهيئة خيارات الحفظ لنظام XPS

```csharp
options.SaveOptions = new XpsSaveOptions(); // القيمة الافتراضية. التعيين التعسفي.
```

قم بتهيئة خيارات الحفظ بتنسيق XPS.

## الخطوة 10: تنقيط الصيغ (اختياري)

```csharp
options.SaveOptions.RasterizeFormulas = true;
```

اضبط على "صحيح" إذا كنت تريد تحويل الصيغ الرياضية إلى صور نقطية.

## الخطوة 11: تنقيط الرسومات المضمنة (اختياري)

```csharp
options.SaveOptions.RasterizeIncludedGraphics = true;
```

اضبط على "صحيح" إذا كنت تريد تحويل الرسومات المضمنة مع العناصر المتجهة إلى صور نقطية.

## الخطوة 12: الخطوط الفرعية

```csharp
options.SaveOptions.SubsetFonts = true;
```

اضبط على true لجعل خطوط المجموعة الفرعية للجهاز مستخدمة في المستند.

## الخطوة 13: تشغيل تحويل LaTeX إلى XPS

```csharp
new TeXJob(Path.Combine("Your Input Directory", "sample.ltx"), new XpsDevice(), options).Run();
```

ابدأ عملية تحويل LaTeX إلى XPS.

## الخطوة 14: تشغيل تحويل LaTeX إلى XPS باستخدام MemoryStream (البديل)

```csharp
// new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(@"\documentclass{article} \begin{document} مرحبًا أيها العالم! \end{document}"))،
// new XpsDevice(), options).Run();
```

يمكنك أيضًا تشغيل التحويل باستخدام MemoryStream لإدخال محتوى LaTeX.

## الخطوة 15: تشغيل تحويل LaTeX إلى XPS باستخدام محطة الإدخال الرئيسية (البديل)

```csharp
// new TeXJob(new XpsDevice(), options).Run();
```

قم بتشغيل التحويل مباشرة من محطة الإدخال الرئيسية.

## خاتمة

باتباع هذه الخطوات البسيطة، يمكنك بسهولة تحويل مستندات LaTeX إلى تنسيق XPS باستخدام Aspose.TeX for .NET. توفر هذه المكتبة القوية خيارات المرونة والتخصيص لتلبية متطلباتك المحددة.

## الأسئلة الشائعة

### س1: هل Aspose.TeX متوافق مع أحدث أطر عمل .NET؟

ج1: نعم، يتم تحديث Aspose.TeX بانتظام لضمان التوافق مع أحدث أطر عمل .NET.

### س٢: هل يمكنني تخصيص تنسيق الإخراج بخلاف XPS؟

 ج2: يدعم Aspose.TeX تنسيقات الإخراج المختلفة. الرجوع إلى الوثائق[هنا](https://reference.aspose.com/tex/net/) للتفاصيل.

### س3: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.TeX؟

 ج3: يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).

### س4: أين يمكنني طلب المساعدة أو مشاركة تجاربي مع Aspose.TeX؟

 ج4: قم بزيارة منتدى Aspose.TeX[هنا](https://forum.aspose.com/c/tex/47) لدعم المجتمع.

### س 5: هل هناك أي مستندات عينة متاحة للاختبار؟

 ج5: استكشف أمثلة Aspose.TeX[هنا](https://github.com/aspose-tex/Aspose.TeX-for-.NET).