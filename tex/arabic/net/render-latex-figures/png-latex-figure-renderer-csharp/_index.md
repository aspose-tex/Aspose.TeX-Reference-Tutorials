---
title: تقديم أشكال LaTeX إلى PNG باستخدام Aspose.TeX (C#)
linktitle: تقديم أشكال LaTeX إلى PNG باستخدام Aspose.TeX (C#)
second_title: Aspose.TeX .NET API
description: استكشف دليلاً شاملاً حول عرض أشكال LaTeX إلى PNG باستخدام Aspose.TeX في C#. تعلم خطوة بخطوة مع أمثلة التعليمات البرمجية.
weight: 10
url: /ar/net/render-latex-figures/png-latex-figure-renderer-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تقديم أشكال LaTeX إلى PNG باستخدام Aspose.TeX (C#)

## مقدمة

إذا كنت تتعمق في عالم التنضيد وإنشاء المستندات في .NET، فمن المحتمل أنك على دراية بتحديات عرض أرقام LaTeX. في هذا الدليل التفصيلي، سنستكشف كيفية استخدام Aspose.TeX لـ .NET لعرض أشكال LaTeX إلى تنسيق PNG باستخدام C#. يوفر Aspose.TeX حلاً قويًا ومرنًا للتعامل مع مستندات LaTeX، مما يجعله أداة لا تقدر بثمن للمطورين الذين يعملون في إنشاء المستندات وتنسيقها.

## المتطلبات الأساسية

قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

-  Aspose.TeX لمكتبة .NET: تأكد من تثبيت مكتبة Aspose.TeX لـ .NET. يمكنك تنزيله[هنا](https://releases.aspose.com/tex/net/).

## استيراد مساحات الأسماء

في كود C# الخاص بك، ابدأ باستيراد مساحات الأسماء الضرورية. تضمن هذه الخطوة أن لديك إمكانية الوصول إلى الفئات والوظائف المطلوبة.

```csharp
using Aspose.TeX.Features;
```

## تقديم أرقام LaTeX إلى PNG

### الخطوة 1: إعداد خيارات العرض

ابدأ بإنشاء خيارات العرض وتعيين المعلمات مثل دقة الصورة والتمهيد وعامل القياس ولون الخلفية والمزيد.

```csharp
FigureRendererOptions options = new PngFigureRendererOptions() { Resolution = 150 };
options.Preamble = "\\usepackage{pict2e}";
options.Scale = 3000;
options.BackgroundColor = System.Drawing.Color.White;
options.LogStream = new System.IO.MemoryStream();
options.ShowTerminal = true;
```

### الخطوة 2: تحديد دفق الإخراج والأبعاد

قم بإنشاء دفق إخراج لصورة PNG ومتغيرات لتخزين أبعاد الصورة الناتجة.

```csharp
System.Drawing.SizeF size = new System.Drawing.SizeF();
using (System.IO.Stream stream = System.IO.File.Open(
   System.IO.Path.Combine("Your Output Directory", "text-and-formula.png"), System.IO.FileMode.Create))
{
    // رمز التقديم يذهب هنا
}
```

### الخطوة 3: تشغيل العرض

قم بتنفيذ عملية العرض باستخدام مكتبة Aspose.TeX. قم بتوفير رمز LaTeX ودفق الإخراج وخيارات العرض ومتغير الحجم.

```csharp
new PngFigureRenderer().Render(@"\setlength{\unitlength}{0.8cm}
\begin{picture}(6,5)
    % LaTeX figure code goes here
\end{picture}", stream, options, out size);
```

### الخطوة 4: عرض النتائج

وأخيرًا، قم بعرض النتائج، بما في ذلك أي تقارير أخطاء وحجم الصورة المقدمة.

```csharp
System.Console.Out.WriteLine(options.ErrorReport);
System.Console.Out.WriteLine();
System.Console.Out.WriteLine("Size: " + size);
```

## خاتمة

مع Aspose.TeX for .NET، يصبح عرض أشكال LaTeX إلى تنسيق PNG عملية سلسة. يرشدك هذا البرنامج التعليمي عبر الخطوات الأساسية، بدءًا من إعداد خيارات العرض وحتى عرض النتائج النهائية.

## الأسئلة الشائعة

### س1: هل Aspose.TeX متوافق مع جميع أوامر LaTeX؟

 ج1: يدعم Aspose.TeX نطاقًا واسعًا من أوامر LaTeX، ولكن يوصى بالرجوع إلى[توثيق](https://reference.aspose.com/tex/net/) للحصول على معلومات مفصلة.

### س2: هل يمكنني تجربة Aspose.TeX قبل الشراء؟

 ج2: نعم، يمكنك استكشاف نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).

### س3: كيف يمكنني الحصول على الدعم لـ Aspose.TeX؟

 ج3: قم بزيارة[منتدى Aspose.TeX](https://forum.aspose.com/c/tex/47)لدعم المجتمع والمناقشات.

### س4: أين يمكنني العثور على تراخيص مؤقتة لـ Aspose.TeX؟

 ج4: التراخيص المؤقتة متاحة[هنا](https://purchase.aspose.com/temporary-license/).

### س5: ما هو هيكل التسعير لـ Aspose.TeX؟

ج5: استكشف تفاصيل الأسعار وقم بإجراء عملية شراء[هنا](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
