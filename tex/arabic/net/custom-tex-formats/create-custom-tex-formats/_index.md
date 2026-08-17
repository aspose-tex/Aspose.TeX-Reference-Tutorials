---
date: 2026-03-26
description: تعلم كيفية إنشاء تنسيق tex مخصص في .NET باستخدام Aspose.TeX وتعيين دليل
  إدخال tex لتوليد مستندات مرنة. يوضح لك هذا الدليل خطوةً بخطوة كيفية تكوين موفر التنسيق،
  وتعيين دليل إدخال tex، وإنشاء مخرجات XPS.
linktitle: Creating Custom TeX Formats in .NET
second_title: Aspose.TeX .NET API
title: كيفية إنشاء تنسيق TeX مخصص في .NET باستخدام Aspose.TeX
url: /ar/net/custom-tex-formats/create-custom-tex-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء تنسيق tex مخصص في .NET باستخدام Aspose.TeX

في عالم .NET الديناميكي، **إنشاء تنسيق tex مخصص** يمنحك تحكمًا دقيقًا في كيفية تنسيق المستندات. باستخدام Aspose.TeX لـ .NET يمكنك تخصيص محرك TeX، وتوجيهه إلى مجلد إدخال محدد، وإنتاج مخرجات XPS ذات مظهر احترافي—كل ذلك من بضع أسطر من كود C#.

## إجابات سريعة
- **ماذا يعني “create custom tex format”?** يعني ذلك تعريف تكوين محرك TeX الخاص بك وملفات التنسيق للتحكم في عملية التنضيد.  
- **أي مكتبة أحتاجها؟** Aspose.TeX for .NET.  
- **هل يجب عليّ تعيين دليل إدخال tex؟** نعم – تقوم بتحديده باستخدام `InputFileSystemDirectory`.  
- **ما المخرجات التي يمكنني إنشاؤها؟** أي جهاز مدعوم من قبل Aspose.TeX، مثل XPS أو PDF أو PNG.  
- **هل يلزم وجود ترخيص للاستخدام في الإنتاج؟** يتطلب ترخيص Aspose.TeX صالح للاستخدام التجاري.

## ما هو تنسيق TeX مخصص؟
تنسيق TeX مخصص هو مجموعة مسبقة التجميع من الماكرو وإعدادات المحرك التي يستخدمها معالج TeX لتفسير ملفات المصدر الخاصة بك. من خلال إنشاء واحد، يمكنك دمج هوية الشركة، فرض معايير المستندات، أو تسريع عملية التجميع للمهام المتكررة.

## لماذا تعيين دليل إدخال tex؟
تعيين **دليل إدخال tex** يخبر المحرك أين يبحث عن الملفات المساعدة، الخطوط المخصصة، أو ملفات الأنماط الإضافية. هذا يحافظ على تنظيم مشروعك ويمنع أخطاء “الملف غير موجود” أثناء التجميع.

## المتطلبات المسبقة

قبل الغوص في رحلة التخصيص، تأكد من أن لديك:

1. **Aspose.TeX for .NET** – قم بتنزيله من [موقع Aspose.TeX](https://releases.aspose.com/tex/net/).  
2. بيئة تطوير **.NET** (Visual Studio أو VS Code أو .NET CLI).  
3. (اختياري) ترخيص **Aspose.TeX** صالح إذا كنت تخطط لتشغيل الكود في بيئة الإنتاج.

## استيراد المساحات الاسمية

أولاً، استورد المساحات الاسمية التي تمنحك الوصول إلى Aspose.TeX API. هذه الخطوة تضمن أن الفئات التي سنستخدمها يتم التعرف عليها من قبل المترجم.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using Aspose.TeX.ResourceProviders;
using System.IO;
using System.Text;
```

## الخطوة 1: إنشاء موفر التنسيق

`FormatProvider` يوجه المحرك إلى المجلد الذي يحتوي على ملف التنسيق المخصص الخاص بك (`customtex.fmt`). استبدل `"Your Output Directory"` بالمسار حيث حفظت التنسيق المجمّع.

```csharp
using (FormatProvider formatProvider =
    new FormatProvider(new InputFileSystemDirectory("Your Output Directory"), "customtex"))
{
```

## الخطوة 2: تكوين خيارات التحويل (وتعيين دليل إدخال tex)

هنا نقوم بإنشاء كائن `TeXOptions`. لاحظ `InputWorkingDirectory` – هذا هو المكان الذي **نعيّن فيه دليل إدخال tex** بحيث يمكن للمحرك العثور على أي ملفات داعمة.

```csharp
    TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX(formatProvider));
    options.JobName = "typeset-with-custom-format";
    options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
    options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

## الخطوة 3: تشغيل المهمة

الآن نقوم بتمرير سلسلة TeX بسيطة إلى المحرك، نختار جهاز إخراج (XPS في هذا المثال)، وننفّذ المهمة.

```csharp
    new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
        "Congratulations! You have successfully typeset this text with your own TeX format!\\end")),
        new XpsDevice(), options).Run();
```

## الخطوة 4: تحسين مخرجات الطرفية

إضافة سطر فارغ يجعل مخرجات وحدة التحكم أسهل للقراءة، خاصةً عندما تقوم بتشغيل مهام متعددة في دفعة.

```csharp
    options.TerminalOut.Writer.WriteLine();
}
// ExEnd:TypesetWithCustomTeXFormat
```

تهانينا! لقد **أنشأت الآن تنسيق tex مخصص** واستخدمته بنجاح لتنسيق مستند في .NET.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|--------|-----|
| *“Format file not found”* | مسار خاطئ في `FormatProvider` | تحقق من أن `"Your Output Directory"` يحتوي على `customtex.fmt` وأن المسار مطلق أو نسبياً صحيحاً بالنسبة للملف التنفيذي. |
| *“Cannot find input file”* | `InputWorkingDirectory` يشير إلى المجلد الخطأ | تأكد من أن `"Your Input Directory"` يحتوي على ملف مصدر TeX أو أنك تمرر المصدر كـ stream (كما في المثال). |
| *Terminal output garbled* | عدم توافق الترميز | استخدم `Encoding.UTF8` إذا كان مصدر TeX يحتوي على أحرف غير ASCII. |
| *XPS file is empty* | المهمة لم تُنفّذ بسبب استثناء سابق | تحقق من وحدة التحكم للحصول على رسائل الخطأ؛ غالباً ما تشير إلى حزم مفقودة أو أخطاء في بناء جملة TeX. |

## الأسئلة المتكررة

### س1: هل يمكنني استخدام Aspose.TeX لـ .NET مع مكتبات معالجة مستندات أخرى؟
نعم، تم تصميم Aspose.TeX للتكامل بسلاسة مع مكتبات معالجة المستندات الأخرى من Aspose لتوفير معالجة مستندات شاملة.

### س2: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.TeX لـ .NET؟
نعم، يمكنك الوصول إلى النسخة التجريبية المجانية [هنا](https://releases.aspose.com/).

### س3: كيف يمكنني الحصول على الدعم لـ Aspose.TeX لـ .NET؟
قم بزيارة [منتدى Aspose.TeX](https://forum.aspose.com/c/tex/47) للحصول على دعم المجتمع أو استكشف خيارات الدعم المتميزة [هنا](https://purchase.aspose.com/buy).

### س4: هل تتوفر تراخيص مؤقتة لـ Aspose.TeX لـ .NET؟
نعم، يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

### س5: أين يمكنني العثور على الوثائق الخاصة بـ Aspose.TeX لـ .NET؟
ارجع إلى الوثائق الشاملة [هنا](https://reference.aspose.com/tex/net/).

**أسئلة وإجابات إضافية**

**س: هل يمكنني إخراج PDF بدلاً من XPS؟**  
ج: بالتأكيد. استبدل `new XpsDevice()` بـ `new PdfDevice()` واضبط دليل الإخراج وفقًا لذلك.

**س: هل أحتاج إلى إعادة تجميع ملف التنسيق بعد كل تغيير؟**  
ج: نعم. أي تغيير في الماكرو أو إعدادات المحرك يتطلب تشغيل `tex -ini` مرة أخرى لإنشاء ملف `.fmt` جديد.

## الخلاصة

في الختام، يوفر Aspose.TeX لـ .NET حلاً قويًا لسيناريوهات **إنشاء تنسيق tex مخصص**، مما يمنح المطورين تحكمًا غير مسبوق في تنضيد المستندات. جرّب تكوينات مختلفة، عيّن دليل إدخال tex المناسب، ودمج سير العمل في تطبيقات .NET الأكبر الخاصة بك لتوليد مستندات تلقائية وعالية الجودة.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2026-03-26  
**تم الاختبار مع:** Aspose.TeX 24.11 for .NET  
**المؤلف:** Aspose