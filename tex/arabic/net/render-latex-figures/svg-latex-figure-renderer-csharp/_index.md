---
title: عرض أشكال LaTeX إلى SVG باستخدام Aspose.TeX (C#)
linktitle: عرض أشكال LaTeX إلى SVG باستخدام Aspose.TeX (C#)
second_title: Aspose.TeX .NET API
description: تحسين عرض المستندات في .NET باستخدام Aspose.TeX. تعرف على كيفية عرض أشكال LaTeX إلى SVG في لغة C# لتحقيق التكامل السلس للتعبيرات الرياضية.
weight: 11
url: /ar/net/render-latex-figures/svg-latex-figure-renderer-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# عرض أشكال LaTeX إلى SVG باستخدام Aspose.TeX (C#)

## مقدمة

إذا كنت تتطلع إلى تحسين إمكانات عرض المستندات لديك في .NET باستخدام أشكال LaTeX، فإن Aspose.TeX هو الحل الأمثل لك. في هذا الدليل خطوة بخطوة، سنرشدك خلال عملية عرض أشكال LaTeX إلى SVG باستخدام Aspose.TeX في C#. بحلول نهاية هذا البرنامج التعليمي، سيكون لديك فهم واضح للعملية، مما يمكّنك من دمج التعبيرات والأشكال الرياضية عالية الجودة بسلاسة في مستنداتك.

## المتطلبات الأساسية

قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

- المعرفة الأساسية بلغة البرمجة C#.
-  تم تثبيت Aspose.TeX لمكتبة .NET. يمكنك تنزيله[هنا](https://releases.aspose.com/tex/net/).

## استيراد مساحات الأسماء

في كود C# الخاص بك، تأكد من استيراد مساحات الأسماء الضرورية:

```csharp
using Aspose.TeX.Features;
```

الآن، دعونا نقسم البرنامج التعليمي إلى خطوات متعددة:

## الخطوة 1: إنشاء خيارات العرض

```csharp
FigureRendererOptions options = new SvgFigureRendererOptions();
options.Preamble = "\\usepackage{pict2e}";
options.Scale = 3000;
options.BackgroundColor = Color.White;
options.LogStream = new System.IO.MemoryStream();
options.ShowTerminal = true;
```

هنا، قمنا بإعداد خيارات العرض، وتحديد الديباجة، وعامل القياس، ولون الخلفية، ودفق السجل، وما إذا كان سيتم إظهار مخرجات المحطة الطرفية.

## الخطوة 2: تحديد الأبعاد ودفق الإخراج

```csharp
SizeF size = new SizeF();
using (Stream stream = File.Open(Path.Combine("Your Output Directory", "text-and-formula.svg"), FileMode.Create))
{
    // تشغيل العرض.
    new SvgFigureRenderer().Render("Your LaTeX Code", stream, options, out size);
}
```

استبدل "دليل المخرجات الخاص بك" بالدليل المطلوب وقم بتوفير رمز LaTeX الخاص بك كسلسلة.

## الخطوة 3: عرض النتائج

```csharp
Console.Out.WriteLine(options.ErrorReport);
Console.Out.WriteLine();
Console.Out.WriteLine("Size: " + size);
```

تعرض هذه الخطوة أي تقارير أخطاء وحجم الصورة الناتجة.

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية عرض أشكال LaTeX إلى SVG باستخدام Aspose.TeX في C#. الآن، يمكنك دمج التعبيرات والأشكال الرياضية بسلاسة في تطبيقات .NET الخاصة بك.

## الأسئلة الشائعة

### س1: هل Aspose.TeX مجاني للاستخدام؟

 ج1: يقدم Aspose.TeX نسخة تجريبية مجانية. يمكنك الوصول إليه[هنا](https://releases.aspose.com/).

### س2: أين يمكنني العثور على وثائق Aspose.TeX؟

 ج2: راجع الوثائق[هنا](https://reference.aspose.com/tex/net/).

### س3: كيف يمكنني الحصول على الدعم لـ Aspose.TeX؟

 ج3: قم بزيارة منتدى الدعم[هنا](https://forum.aspose.com/c/tex/47).

### س4: هل يمكنني شراء Aspose.TeX؟

 ج4: نعم، يمكنك شراء Aspose.TeX[هنا](https://purchase.aspose.com/buy).

### س5: هل أحتاج إلى ترخيص مؤقت؟

 ج5: إذا لزم الأمر، يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
