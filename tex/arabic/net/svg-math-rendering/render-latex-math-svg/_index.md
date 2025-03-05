---
title: عرض LaTeX Math كـ SVG في .NET
linktitle: عرض LaTeX Math كـ SVG في .NET
second_title: Aspose.TeX .NET API
description: تعرف على كيفية عرض معادلات LaTeX الرياضية بتنسيق SVG في .NET باستخدام Aspose.TeX. دليل خطوة بخطوة مع خيارات قابلة للتخصيص للتمثيل الرياضي الدقيق.
type: docs
weight: 10
url: /ar/net/svg-math-rendering/render-latex-math-svg/
---
## مقدمة

في عالم التطوير المستمر لـ .NET، يعد عرض معادلات LaTeX الرياضية جانبًا حاسمًا، خاصة عند التعامل مع التطبيقات العلمية أو الرياضية. يوفر Aspose.TeX for .NET حلاً قويًا لهذا المطلب، مما يسمح لك بعرض معادلات LaTeX الرياضية بسلاسة في رسومات متجهة قابلة للتطوير (SVG). في هذا البرنامج التعليمي، سنرشدك خلال عملية عرض معادلات LaTeX الرياضية باستخدام مكتبة Aspose.TeX في بيئة .NET.

## المتطلبات الأساسية

قبل أن نتعمق في الدليل التفصيلي، تأكد من توفر المتطلبات الأساسية التالية:

-  Aspose.TeX for .NET Library: قم بتنزيل المكتبة وتثبيتها من ملف[صفحة الإصدار](https://releases.aspose.com/tex/net/).
- الفهم الأساسي لـ LaTeX: تعرف على بناء جملة LaTeX، لأنه يشكل أساس المعادلات الرياضية التي سنعرضها.
- بيئة تطوير .NET: قم بإعداد بيئة تطوير .NET عاملة على جهازك.

## استيراد مساحات الأسماء

في تطبيق .NET الخاص بك، ابدأ باستيراد مساحات الأسماء الضرورية للاستفادة من وظيفة Aspose.TeX:

```csharp
using Aspose.TeX.Features;
```

الآن، دعونا نقسم العملية إلى خطوات متعددة:

## الخطوة 1: إنشاء خيارات العرض

```csharp
// إنشاء خيارات العرض.
MathRendererOptions options = new SvgMathRendererOptions();
```

## الخطوة 2: تحديد الديباجة

```csharp
// تحديد الديباجة.
options.Preamble = @"\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
\usepackage{color}";
```

## الخطوة 3: تحديد عامل القياس والألوان

```csharp
// حدد عامل القياس (على سبيل المثال، 300%).
options.Scale = 3000;

// تحديد اللون الأمامي.
options.TextColor = System.Drawing.Color.Black;

// تحديد لون الخلفية.
options.BackgroundColor = System.Drawing.Color.White;
```

## الخطوة 4: تكوين خيارات الإخراج

```csharp
// حدد دفق الإخراج لملف السجل.
options.LogStream = new System.IO.MemoryStream();

// حدد ما إذا كنت تريد إظهار مخرجات الوحدة الطرفية على وحدة التحكم أم لا.
options.ShowTerminal = true;
```

## الخطوة 5: تقديم معادلة LaTeX Math

```csharp
// قم بإنشاء دفق الإخراج لصورة الصيغة.
using (System.IO.Stream stream = System.IO.File.Open(
    System.IO.Path.Combine("Your Output Directory", "math-formula.svg"), System.IO.FileMode.Create))
{
    // تشغيل العرض.
    new SvgMathRenderer().Render(@"\begin{equation*}
    e^x = x^{\color{red}0} + x^{\color{red}1} + \frac{x^{\color{red}2}}{2} + \frac{x^{\color{red}3}}{6} + \cdots = \sum_{n\geq 0} \frac{x^{\color{red}n}}{n!}
\end{equation*}", stream, options, out size);
}
```

## الخطوة 6: عرض النتائج

```csharp
// عرض نتائج أخرى.
System.Console.Out.WriteLine(options.ErrorReport);
System.Console.Out.WriteLine();
System.Console.Out.WriteLine("Size: " + size);
```

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية استخدام Aspose.TeX لـ .NET لعرض معادلات LaTeX الرياضية بصيغة SVG. هذه القدرة لا تقدر بثمن بالنسبة للتطبيقات التي يكون فيها التمثيل الرياضي الدقيق أمرًا ضروريًا.

## الأسئلة الشائعة

### س1: هل يمكنني تخصيص ألوان المعادلات المقدمة؟

 A1: نعم، يمكنك بسهولة تخصيص الألوان الأمامية والخلفية باستخدام`TextColor` و`BackgroundColor` الخصائص في خيارات العرض.

### س2: هل يلزم الحصول على ترخيص لاستخدام Aspose.TeX لـ .NET؟

 ج٢: نعم، أنت بحاجة إلى ترخيص صالح. يمكنك الحصول على واحدة من[صفحة شراء Aspose](https://purchase.aspose.com/buy).

### س3: أين يمكنني العثور على دعم إضافي أو طلب المساعدة؟

 ج3: قم بزيارة[منتدى Aspose.TeX](https://forum.aspose.com/c/tex/47)لدعم المجتمع والمناقشات.

### س4: كيف يمكنني الحصول على ترخيص مؤقت لأغراض الاختبار؟

 ج4: الحصول على ترخيص مؤقت من[هنا](https://purchase.aspose.com/temporary-license/).

### س5: هل هناك أي أمثلة للدروس المتاحة في الوثائق؟

 ج5: نعم، يمكنك استكشاف المزيد من الأمثلة في[وثائق Aspose.TeX](https://reference.aspose.com/tex/net/).