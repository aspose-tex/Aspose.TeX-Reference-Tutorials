---
date: 2025-12-30
description: تعلم كيفية تحويل TeX إلى XPS في .NET باستخدام Aspose.TeX. اتبع هذا الدليل
  خطوة بخطوة للحصول على تكامل سلس وإخراج موثوق.
linktitle: How to Convert TeX to XPS in .NET
second_title: Aspose.TeX .NET API
title: كيفية تحويل TeX إلى XPS في .NET
url: /ar/net/xps-output/typeset-tex-to-xps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تحويل TeX إلى XPS في .NET

## كيفية تحويل TeX إلى XPS – المقدمة

مرحبًا بكم في دليلنا الشامل خطوة‑بخطوة حول **كيفية تحويل TeX** إلى صيغة XPS داخل بيئة .NET. باستخدام مكتبة Aspose.TeX القوية، ستتمكن من دمج تحويل TeX‑إلى‑XPS في أي تطبيق .NET—سواء كان أداة سطح مكتب، خدمة ويب، أو خط أنابيب تقارير مؤتمت. في الأقسام التالية سنستعرض كل الإعدادات المطلوبة، نعرض لك الشيفرة الدقيقة التي تحتاجها، ونشرح لماذا كل جزء مهم، لتتمكن من تنفيذ الحل بثقة.

## إجابات سريعة
- **ما الذي يغطيه هذا البرنامج التعليمي؟** تحويل ملفات TeX إلى XPS باستخدام Aspose.TeX لـ .NET.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **هل أحتاج إلى ترخيص؟** نسخة تجريبية مجانية تعمل للاختبار؛ يلزم الحصول على ترخيص تجاري للإنتاج.  
- **كم يستغرق التنفيذ؟** عادةً أقل من 15 دقيقة للتحويل الأساسي.  
- **أين يمكنني الحصول على المكتبة؟** يمكنك التحميل من صفحة الإصدار الرسمية لـ Aspose.TeX.

## المتطلبات المسبقة

قبل أن نغوص في البرنامج التعليمي، تأكد من توفر المتطلبات التالية:

- Aspose.TeX لـ .NET: تأكد من تثبيت مكتبة Aspose.TeX. يمكنك تحميلها [هنا](https://releases.aspose.com/tex/net/).

- الوثائق: تعرّف على المكتبة بالرجوع إلى الوثائق [هنا](https://reference.aspose.com/tex/net/).

- مجلدات الإدخال والإخراج: قم بإعداد مجلدات الإدخال والإخراج كما هو موضح في مثال الشيفرة.

الآن بعد أن أعددت كل شيء، دعنا نتابع دليل الخطوة‑بـ‑الخطوة.

## استيراد مساحات الأسماء

في تطبيق .NET الخاص بك، ابدأ باستيراد مساحات الأسماء الضرورية. يضمن ذلك حصولك على وظائف Aspose.TeX المطلوبة لتنسيق TeX إلى XPS.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
```

## الخطوة 1: ضبط خيارات التحويل

حدد خيارات التحويل، مع تحديد صيغة ObjectTeX على امتداد محرك ObjectTeX. كذلك، عيّن اسم المهمة، ومجلدات الإدخال والإخراج، وتفاصيل مخرجات الطرفية.

```csharp
// Create conversion options for default ObjectTeX format upon ObjectTeX engine extension.
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
// Specify a job name.
options.JobName = "external-file-stream";
// Specify a file system working directory for input.
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
// Specify a file system working directory for output.
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
// Specify that the terminal output must be written to a file in the output working directory.
// The file name is <job_name>.trm.
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## الخطوة 2: إنشاء تدفق مستند XPS

افتح تدفقًا لكتابة مستند XPS المنسق. اسم الملف ليس بالضرورة هو نفسه اسم المهمة.

```csharp
using (Stream stream = File.Open(Path.Combine("Your Output Directory", options.JobName + ".xps"), FileMode.Create))
```

## الخطوة 3: تشغيل مهمة TeX

ابدأ وشغّل مهمة TeX، مع تحديد اسم المستند، وXpsDevice، وخيارات التحويل.

```csharp
new TeXJob("hello-world", new XpsDevice(stream), options).Run();
```

تهانينا! لقد نجحت في تنسيق TeX إلى XPS في .NET باستخدام Aspose.TeX. لا تتردد في استكشاف المزيد من الميزات والخيارات بناءً على متطلباتك الخاصة.

## الخاتمة

في هذا البرنامج التعليمي، غطينا الخطوات الأساسية لتحويل مستندات TeX إلى صيغة XPS بسلاسة في .NET باستخدام Aspose.TeX. باتباعك لهذا الدليل، اكتسبت رؤى قيمة حول قدرات المكتبة وكيفية الاستفادة منها في مشاريعك.

## الأسئلة المتكررة

### س1: هل Aspose.TeX متوافق مع .NET Core؟
A1: نعم، Aspose.TeX متوافق تمامًا مع .NET Core.

### س2: هل يمكنني استخدام Aspose.TeX في المشاريع التجارية؟
A2: بالطبع! Aspose.TeX متاح للاستخدام التجاري والشخصي.

### س3: أين يمكنني العثور على أمثلة وموارد إضافية؟
A3: استكشف وثائق Aspose.TeX [هنا](https://reference.aspose.com/tex/net/) للحصول على المزيد من الأمثلة والموارد التفصيلية.

### س4: كيف يمكنني الحصول على دعم لـ Aspose.TeX؟
A4: قم بزيارة منتدى دعم Aspose.TeX [هنا](https://forum.aspose.com/c/tex/47) للحصول على مساعدة من المجتمع.

### س5: هل تتوفر نسخة تجريبية مجانية؟
A5: نعم، يمكنك الوصول إلى نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).

## أسئلة شائعة

**س: هل يمكنني تخصيص مخرجات XPS (مثل حجم الصفحة أو الهوامش)؟**  
ج: نعم. يمكنك تعديل إعدادات XpsDevice أو تعديل مصدر TeX للتحكم في تخطيط الصفحة قبل التحويل.

**س: ماذا يحدث إذا كان ملف TeX المدخل يحتوي على أخطاء؟**  
ج: عملية التحويل تكتب تفاصيل الأخطاء إلى ملف مخرجات الطرفية (`*.trm`). راجع هذا الملف لتشخيص وإصلاح المشكلات.

**س: هل من الممكن تحويل عدة ملفات TeX في تشغيل واحد؟**  
ج: يمكنك تكرار العملية على مجموعة من ملفات مصدر TeX، بإنشاء TeXJob منفصل لكل منها مع إعادة استخدام نفس كائن `TeXOptions`.

**س: هل يدعم Aspose.TeX حزم LaTeX مثل `amsmath` أو `graphicx`؟**  
ج: معظم حزم LaTeX القياسية مدعومة. راجع الوثائق الرسمية للحصول على القائمة الكاملة للحزم المتوافقة.

**س: كيف يمكنني تضمين الخطوط في ملف XPS المُولد؟**  
ج: Aspose.TeX يدمج الخطوط المستخدمة تلقائيًا من محرك TeX. تأكد من تثبيت الخطوط المطلوبة على الجهاز الذي يجري التحويل.

---

**آخر تحديث:** 2025-12-30  
**تم الاختبار مع:** Aspose.TeX لـ .NET 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}