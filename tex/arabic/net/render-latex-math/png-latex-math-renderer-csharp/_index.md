---
date: 2025-12-28
description: تعلم كيفية تحويل LaTeX إلى PNG في C# باستخدام Aspose.TeX. اتبع دليلنا
  خطوة بخطوة لتصدير LaTeX كصورة PNG وإنشاء PNG من LaTeX بسهولة.
linktitle: How to Convert LaTeX to PNG with Aspose.TeX (C#)
second_title: Aspose.TeX .NET API
title: كيفية تحويل LaTeX إلى PNG باستخدام Aspose.TeX (C#)
url: /ar/net/render-latex-math/png-latex-math-renderer-csharp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحويل LaTeX إلى PNG باستخدام Aspose.TeX (C#)

## المقدمة

في هذا الدرس الشامل ستتعلم **كيفية تحويل LaTeX إلى PNG** باستخدام مكتبة Aspose.TeX لـ .NET. سواءً كنت تبني مولد تقارير علمية، أو منصة تعليم إلكتروني، أو خدمة مخصصة لعرض المعادلات، فإن تحويل رياضيات LaTeX إلى صور PNG عالية الجودة هو طلب شائع. سنستعرض العملية بالكامل—من إعداد خيارات العرض إلى حفظ الصورة النهائية—حتى تتمكن من تصدير LaTeX كـ PNG بثقة.

## إجابات سريعة
- **ما المكتبة التي يمكنني استخدامها؟** Aspose.TeX for .NET
- **هل يمكنني إنشاء PNG من LaTeX باستخدام C#؟** نعم، ببضع أسطر من الشيفرة
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية مجانية؛ الترخيص مطلوب للإنتاج
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6
- **هل يمكن تغيير الألوان؟** بالطبع – استخدم `TextColor` و `BackgroundColor`

## ما هو “تحويل latex إلى png”؟

تحويل LaTeX إلى PNG يعني أخذ تعبير رياضي مكتوب بـ LaTeX (أو جزء كامل من مستند) وعرضه كصورة نقطية. PNG مثالي لصفحات الويب، التطبيقات المحمولة، أو أي سيناريو تحتاج فيه إلى صورة خفيفة الوزن، غير مضغوطة وتحتفظ بجودتها عند التكبير أو التصغير.

## لماذا استخدام Aspose.TeX لتصدير latex كـ png؟

- **دعم كامل لـ LaTeX** – جميع الحزم القياسية (`amsmath`، `amssymb`، إلخ) تعمل مباشرة.  
- **تحكم دقيق** – الدقة، التكبير، الألوان، وتسجيل الأخطاء كلها قابلة للتكوين.  
- **لا حاجة لتثبيت LaTeX خارجي** – المكتبة تتعامل مع التجميع داخليًا، مما يبسط النشر.  

## المتطلبات المسبقة

- فهم أساسي لبرمجة C#.
- تثبيت Aspose.TeX لـ .NET. يمكنك تحميله من [هنا](https://releases.aspose.com/tex/net/).
- بيئة تطوير (Visual Studio، Rider، أو VS Code) جاهزة لمشاريع C#.

## استيراد المساحات الاسمية

في ملف C# الخاص بك، استورد مساحة الأسماء Aspose.TeX التي تحتوي على فئات العرض:

```csharp
using Aspose.TeX.Features;
```

الآن دعنا نقسم المثال إلى خطوات واضحة مرقمة.

## الخطوة 1: إعداد خيارات العرض

```csharp
MathRendererOptions options = new PngMathRendererOptions() { Resolution = 150 };
```

هنا نقوم بإنشاء كائن `PngMathRendererOptions` ونحدد دقة الصورة إلى **150 dpi**. اضبط الـ DPI وفقًا لمتطلبات الجودة الخاصة بك.

## الخطوة 2: تحديد المقدمة

```csharp
options.Preamble = @"\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
\usepackage{color}";
```

المقدمة تقوم بتحميل حزم LaTeX التي تحتاجها للرموز الرياضية المتقدمة ومعالجة الألوان.

## الخطوة 3: تعريف عامل التكبير

```csharp
options.Scale = 3000;
```

عامل التكبير **3000 %** يكبر المعادلة المعروضة، مما يمنحك صورة PNG واضحة حتى بعد تصغيرها.

## الخطوة 4: اختيار ألوان النص والخلفية

```csharp
options.TextColor = System.Drawing.Color.Black;
options.BackgroundColor = System.Drawing.Color.White;
```

يمكنك تعيين أي `System.Drawing.Color` للنص والخلفية لتتناسب مع سمة واجهة المستخدم الخاصة بك.

## الخطوة 5: إعداد التسجيل (اختياري لكن مفيد)

```csharp
options.LogStream = new System.IO.MemoryStream();
options.ShowTerminal = true;
```

تدفق السجل يلتقط رسائل تجميع LaTeX، وهو مفيد لاستكشاف الأخطاء.

## الخطوة 6: إنشاء تدفق الإخراج للـ PNG

```csharp
using (System.IO.Stream stream = System.IO.File.Open(
    System.IO.Path.Combine("Your Output Directory", "math-formula.png"), System.IO.FileMode.Create))
```

هذا الكتلة `using` تفتح تدفق ملف حيث سيتم حفظ PNG المعروض. استبدل `"Your Output Directory"` بالمسار الفعلي الذي تريده.

## الخطوة 7: عرض معادلة LaTeX

```csharp
new PngMathRenderer().Render(@"\begin{equation*}
e^x = x^{\color{red}0} + x^{\color{red}1} + \frac{x^{\color{red}2}}{2} + \frac{x^{\color{red}3}}{6} + \cdots = \sum_{n\geq 0} \frac{x^{\color{red}n}}{n!}
\end{equation*}", stream, options, out size);
```

طريقة `Render` تأخذ مصدر LaTeX، وتدفق الإخراج، والخيارات التي قمنا بتكوينها، وتعيد حجم الصورة النهائي.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل السريع |
|---------|-------|-------------|
| **صورة فارغة** | حزم مطلوبة مفقودة في المقدمة | أضف أسطر `\usepackage{...}` المفقودة |
| **دقة منخفضة** | تم ضبط `Resolution` منخفضًا جدًا | زيادة `Resolution` (مثلاً 300 dpi) |
| **ألوان غير متوقعة** | `TextColor` أو `BackgroundColor` غير محدد | حدد كلا اللونين صراحةً كما هو موضح في الخطوة 4 |
| **أخطاء تجميع** | خطأ في بناء جملة سلسلة LaTeX | تحقق من كود LaTeX؛ استخدم تدفق السجل للحصول على التفاصيل |

## الأسئلة المتكررة

**س: هل يمكنني تخصيص ألوان المعادلات المعروضة؟**  
ج: نعم، يمكنك تحديد كل من لون النص (`TextColor`) ولون الخلفية (`BackgroundColor`) في خيارات العرض.

**س: هل هناك حد لتعقيد معادلات LaTeX التي يمكن عرضها؟**  
ج: Aspose.TeX يتعامل مع معظم المعادلات المعقدة، لكن الصيغ الكبيرة جدًا قد تحتاج إلى مزيد من الذاكرة أو إعدادات أعلى للـ `Resolution`/`Scale`.

**س: كيف يمكنني استكشاف مشاكل العرض؟**  
ج: افحص `LogStream` للحصول على رسائل الأخطاء وتأكد من تضمين جميع حزم LaTeX المطلوبة في المقدمة.

**س: هل يمكنني عرض المعادلات بصيغ غير PNG؟**  
ج: بالطبع. Aspose.TeX يدعم أيضًا SVG، PDF، وصيغ نقطية/متجهة أخرى.

**س: أين يمكنني طلب الدعم من المجتمع؟**  
ج: زر [منتدى Aspose.TeX](https://forum.aspose.com/c/tex/47) للحصول على مساعدة من المطورين الآخرين وفريق Aspose.

**آخر تحديث:** 2025-12-28  
**تم الاختبار مع:** Aspose.TeX 24.11 for .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}