---
date: 2025-12-18
description: تعلم كيفية استخدام تنسيق Aspose TeX المخصص لتنسيق النصوص باستخدام TeX
  مخصص في .NET وإنشاء مستندات عالية الجودة.
linktitle: Creating Custom TeX Formats in .NET
second_title: Aspose.TeX .NET API
title: تنسيق TeX مخصص من Aspose – إنشاء تنسيقات TeX مخصصة في .NET
url: /ar/net/custom-tex-formats/create-custom-tex-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose TeX Custom Format: إنشاء صيغ TeX مخصصة في .NET

## المقدمة

في بيئة .NET سريعة التطور، يمكن للتحكم الدقيق في تنسيق المستندات أن يحسن بشكل كبير مظهر وجودة ملفات PDF و XPS أو أي مخرجات أخرى يتم إنشاؤها. **Aspose TeX custom format** يتيح لك تعريف واستخدام ملفات صيغة TeX الخاصة بك، مما يمنحك القدرة على *تنسيق النص باستخدام صيغة مخصصة* تمامًا كما تحتاج. يوجهك هذا الدليل خطوة بخطوة—من إعداد البيئة إلى تشغيل مهمة TeX كاملة باستخدام الصيغة المخصصة الخاصة بك.

## إجابات سريعة
- **ما الذي يتيح “Aspose TeX custom format”؟** يتيح لك إنشاء واستخدام ملف صيغة TeX مخصص لتنسيق مخصص.  
- **هل أحتاج إلى ترخيص لتجربته؟** يتوفر إصدار تجريبي مجاني؛ يلزم وجود ترخيص تجاري للإنتاج.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6/7+.  
- **هل يمكنني الإخراج إلى XPS أو PDF أو أجهزة أخرى؟** نعم—أي جهاز مدعوم من Aspose.TeX (مثل XpsDevice، PdfDevice).  
- **كم يستغرق الإعداد من وقت؟** عادةً أقل من 10 دقائق بمجرد تثبيت المكتبة.

## ما هو Aspose TeX Custom Format؟

صيغة TeX مخصصة هي تكوين محرك TeX مُجمّع يحتوي على ماكروهات، حزم وإعدادات محمّلة مسبقًا. من خلال توفير ملف الصيغة الخاص بك، يمكنك تسريع عملية التجميع وتطبيق قواعد تنسيق خاصة بالمشروع، كل ذلك من داخل تطبيق .NET.

## لماذا تستخدم صيغة TeX مخصصة؟

- **الأداء:** الصيغ المُجمّعة مسبقًا تقلل من وقت بدء تشغيل المستندات الكبيرة.  
- **الاتساق:** فرض معايير الطباعة على مستوى الشركة دون الحاجة لإعادة كتابة الماكروهات في كل تشغيل.  
- **المرونة:** إضافة أوامر مملوكة أو تعديل الإعدادات الافتراضية لتتناسب مع هوية علامتك التجارية.

## المتطلبات المسبقة

قبل الغوص في الكود، تأكد من وجود ما يلي:

1. **Aspose.TeX for .NET Library** – قم بتنزيله وتثبيته من [موقع Aspose.TeX](https://releases.aspose.com/tex/net/).  
2. **بيئة تطوير .NET** – Visual Studio 2022، VS Code مع امتداد C#، أو أي بيئة تدعم .NET 6+.

## استيراد مساحات الأسماء

لبدء عملية التخصيص، استورد مساحات الأسماء الضرورية إلى مشروع .NET الخاص بك. يضمن ذلك الوصول إلى وظائف Aspose.TeX.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using Aspose.TeX.ResourceProviders;
using System.IO;
using System.Text;
```

## الخطوة 1: إنشاء موفر الصيغة

ابدأ بإنشاء موفر صيغة يشير إلى المجلد الذي يحتوي على ملف الصيغة المخصص الخاص بك. يحدد هذا الموفر للمحرك مكان العثور على ملف `.fmt` المُجمّع.

```csharp
using (FormatProvider formatProvider =
    new FormatProvider(new InputFileSystemDirectory("Your Output Directory"), "customtex"))
{
```

## الخطوة 2: تكوين خيارات التحويل

قم بإعداد خيارات التحويل للصيغة المخصصة. هنا نحدد اسم المهمة، ومجلدات العمل للمدخلات والمخرجات، وربط الصيغة المخصصة بمحرك ObjectTeX.

```csharp
    TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX(formatProvider));
    options.JobName = "typeset-with-custom-format";
    options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
    options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

## الخطوة 3: تشغيل المهمة

نفّذ مهمة TeX بتوفير النص المدخل، جهاز الإخراج (XpsDevice في هذا المثال)، والخيارات التي قمت بتكوينها.

```csharp
    new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
        "Congratulations! You have successfully typeset this text with your own TeX format!\\end")),
        new XpsDevice(), options).Run();
```

## الخطوة 4: ضمان إخراج نظيف

للحصول على مخرجات طرفية مصقولة، أضف سطرًا فارغًا بعد انتهاء المهمة. هذه اللمسة الصغيرة تجعل عرض وحدة التحكم أكثر نظافة.

```csharp
    options.TerminalOut.Writer.WriteLine();
}
// ExEnd:TypesetWithCustomTeXFormat
```

### المشكلات الشائعة والحلول

| العَرَض | السبب المحتمل | الحل |
|---------|--------------|-----|
| خطأ “format file not found” | مسار خاطئ في `FormatProvider` | تحقق من أن `"Your Output Directory"` يحتوي على `customtex.fmt` وأن المسار مطلق أو نسبي بشكل صحيح بالنسبة للملف التنفيذي. |
| لا يتم إنشاء أي مخرجات | دليل الإخراج يفتقر إلى صلاحية الكتابة | تأكد من أن التطبيق يملك صلاحية الكتابة إلى `"Your Output Directory"` أو اختر مجلدًا مثل `Path.GetTempPath()`. |
| نقص الماكروهات في المستند النهائي | الصيغة المخصصة لا تشمل الحزم المطلوبة | أعد تجميع ملف `.fmt` مع تضمين أوامر `\usepackage{...}` اللازمة، ثم استبدل ملف الصيغة القديم. |

## الخاتمة

في الختام، **Aspose TeX custom format** يوفر طريقة قوية وعالية الأداء لتخصيص تنسيق TeX مباشرة من .NET. باتباع الخطوات السابقة، يمكنك إنشاء، تكوين، وتشغيل صيغة مخصصة تلبي المتطلبات الطباعية الدقيقة لمشروعك. جرّب ماكروهات مختلفة، مخرجات أجهزة، وإعدادات الخيارات لاستكشاف كامل إمكانات توليد المستندات في تطبيقات .NET الخاصة بك.

## الأسئلة المتكررة

### س1: هل يمكنني استخدام Aspose.TeX لـ .NET مع مكتبات معالجة المستندات الأخرى؟

نعم، تم تصميم Aspose.TeX للتكامل بسلاسة مع مكتبات Aspose الأخرى لمعالجة المستندات بشكل شامل.

### س2: هل يتوفر إصدار تجريبي مجاني لـ Aspose.TeX لـ .NET؟

نعم، يمكنك الحصول على الإصدار التجريبي المجاني [من هنا](https://releases.aspose.com/).

### س3: كيف يمكنني الحصول على دعم لـ Aspose.TeX لـ .NET؟

توجه إلى [منتدى Aspose.TeX](https://forum.aspose.com/c/tex/47) للحصول على دعم المجتمع أو استكشف خيارات الدعم المتميزة [من هنا](https://purchase.aspose.com/buy).

### س4: هل تتوفر تراخيص مؤقتة لـ Aspose.TeX لـ .NET؟

نعم، يمكنك الحصول على ترخيص مؤقت [من هنا](https://purchase.aspose.com/temporary-license/).

### س5: أين يمكنني العثور على الوثائق الخاصة بـ Aspose.TeX لـ .NET؟

راجع الوثائق الشاملة [من هنا](https://reference.aspose.com/tex/net/).

## أسئلة متكررة إضافية

**س: هل تعمل الصيغة المخصصة مع إخراج PDF أيضًا؟**  
ج: بالتأكيد. استبدل `new XpsDevice()` بـ `new PdfDevice()` (أو أي جهاز مدعوم آخر) مع الحفاظ على نفس الخيارات.

**س: هل يمكنني تحميل الصيغة المخصصة من مورد مدمج؟**  
ج: نعم. استخدم `new FormatProvider(new InputEmbeddedResourceDirectory(typeof(Program).Assembly), "customtex")` للتحميل من الموارد المدمجة.

**س: كيف أقوم بتصحيح مهمة TeX فاشلة؟**  
ج: عيّن `options.TerminalOut.Writer` إلى `StringWriter` وتفحص السجل الملتقط بعد إكمال `Run()`.

---

**آخر تحديث:** 2025-12-18  
**تم الاختبار مع:** Aspose.TeX 24.11 for .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}