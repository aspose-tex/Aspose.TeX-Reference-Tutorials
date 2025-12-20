---
date: 2025-12-20
description: تعلم كيفية تحويل TeX إلى PNG باستخدام Aspose.TeX للغة C#. يوضح لك هذا
  الدليل كيفية إنشاء صورة من TeX، ومعالجة التدفقات، والتقاط إدخال الطرفية.
linktitle: Convert TeX to PNG – Master Streams, Images, & Terminal Input in Aspose.TeX
  for C#
second_title: Aspose.TeX .NET API
title: تحويل TeX إلى PNG – إتقان التدفقات، الصور، وإدخال الطرفية في Aspose.TeX للغة
  C#
url: /ar/net/advanced-io/stream-input-image-output-terminal-input-csharp/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحويل TeX إلى PNG – التحكم في التدفقات، الصور، وإدخال الطرفية في Aspose.TeX للغة C#

## المقدمة

في هذا الدرس الشامل ستتعلم **كيفية تحويل TeX إلى PNG** باستخدام Aspose.TeX للغة C#. سواء كنت بحاجة إلى **إنشاء صورة من TeX** للتقارير، أو معاينات الويب، أو خطوط أنابيب المستندات الآلية، فإن هذا الدليل يشرح لك التعامل مع التدفقات، وإدارة الصور، والتقاط إدخال الطرفية—كل ذلك في مثال واحد سهل المتابعة.

## إجابات سريعة
- **ماذا يفعل Aspose.TeX؟** يقوم بتحليل مصدر TeX وتحويله إلى صيغ متعددة، بما في ذلك PNG.  
- **هل يمكنني تحويل TeX إلى PNG دون كتابة ملفات على القرص؟** نعم – يمكنك تمرير TeX عبر `MemoryStream` والحصول على بايتات PNG مباشرة.  
- **ما إصدارات .NET المدعومة؟** جميع إصدارات .NET الحديثة (Framework 4.6+، .NET Core 3.1+، .NET 5/6).  
- **هل أحتاج إلى ترخيص للاستخدام في الإنتاج؟** الترخيص التجاري مطلوب للإنتاج؛ يتوفر نسخة تجريبية مجانية.  
- **ما الدقة التي يمكنني ضبطها للصورة؟** خاصية `PngSaveOptions.Resolution` تسمح لك بتحديد DPI (مثال: 300 dpi).

## ما هو “convert tex to png”؟

تحويل TeX إلى PNG يعني أخذ سلسلة ترميز TeX (اللغة المستخدمة في المستندات العلمية) وتحويلها إلى صورة نقطية. هذا مفيد عندما تريد تضمين صيغ رياضية أو صفحات TeX كاملة في صفحات الويب، أو التطبيقات المحمولة، أو أي بيئة لا تدعم عرض TeX أصلاً.

## لماذا نولد صورة من TeX باستخدام Aspose.TeX؟

- **بدون تبعيات خارجية** – Aspose.TeX مكتبة .NET نقية، لذا لا تحتاج إلى توزيع TeX على الخادم.  
- **واجهة برمجة تطبيقات صديقة للتدفقات** – تعمل مباشرة مع `MemoryStream`، مما يجعلها مثالية للخدمات السحابية والمايكرو‑سيرفيسز.  
- **تحكم دقيق** – يمكنك ضبط دقة الصورة، ومسارات الإخراج، وحتى التقاط إدخال الطرفية التفاعلية.  

## المتطلبات المسبقة

قبل الغوص في الكود، تأكد من وجود ما يلي:

- معرفة أساسية بلغة C#.  
- تثبيت Aspose.TeX للـ .NET – يمكنك تحميله **[من هنا](https://releases.aspose.com/tex/net/)**.  
- بيئة تطوير C# (Visual Studio، VS Code، Rider، إلخ).  

## استيراد المساحات الاسمية

أضف عبارات `using` المطلوبة في أعلى ملف C# الخاص بك لتتمكن من الوصول إلى فئات Aspose.TeX:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Image;
using System.IO;
using System.Text;
```

## الخطوة 1: إعداد خيارات التحويل

قم بتهيئة خط أنابيب التحويل. هنا نخبر Aspose.TeX بأن التطبيق يعمل كبرنامج طرفية، نحدد مجلدات الإدخال/الإخراج، نوجه إدخال/إخراج الطرفية، ونطلب إخراج PNG بدقة 300 dpi.

```csharp
// ExStart:TakeMainInputFromStream-AuxFromFileSystem-TakeTerminalInputFromConsole-AlternativeImagesStorage
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
options.JobName = "stream-in-image-out";
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
options.TerminalIn = new InputConsoleTerminal();
options.TerminalOut = new OutputConsoleTerminal();
options.SaveOptions = new PngSaveOptions() { Resolution = 300 };
```

## الخطوة 2: إنشاء جهاز الصورة وتشغيل المهمة

`ImageDevice` يلتقط بيانات PNG المرسومة. نقوم بتمرير مقطع TeX بسيط عبر `MemoryStream`، نشغل المهمة، وتترك Aspose.TeX تتولى الجزء الصعب.

```csharp
ImageDevice device = new ImageDevice();
TeXJob job = new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
    "\\hrule height 10pt width 95pt\\vskip10pt\\hrule height 5pt")),
    device, options);
job.Run();
```

## الخطوة 3: توفير الإدخال في الطرفية

عند ظهور مطالبة الطرفية، اكتب **ABC**، اضغط **Enter**، ثم اكتب **\end** واضغط **Enter** مرة أخرى. هذا يوضح كيفية التقاط إدخال الطرفية أثناء تشغيل محرك TeX.

## الخطوة 4: ضبط الإخراج بدقة

بعد انتهاء المهمة، يمكنك كتابة سطر فارغ إلى الطرفية واسترجاع بايتات PNG الخام من الجهاز. مصفوفة `result` تحتوي على صورة PNG واحدة لكل صفحة.

```csharp
options.TerminalOut.Writer.WriteLine();
byte[][] result = device.Result;
// ExEnd:TakeMainInputFromStream-AuxFromFileSystem-TakeTerminalInputFromConsole-AlternativeImagesStorage
```

الآن يمكنك حفظ `result[0]` إلى ملف، إرساله عبر الشبكة، أو تضمينه مباشرةً في مكوّن واجهة المستخدم.

## المشكلات الشائعة والحلول

| المشكلة | لماذا يحدث | الحل |
|-------|----------------|-----|
| **لا يوجد إخراج PNG** | لم يتم تعيين `SaveOptions` أو الدقة صفر. | تأكد من `options.SaveOptions = new PngSaveOptions() { Resolution = 300 };` |
| **توقف الطرفية** | لا يتلقى إدخال TeX `\end`. | احرص دائمًا على إنهاء تدفق TeX بـ `\end` (أو `\stop`). |
| **حجم الصورة غير صحيح** | DPI الافتراضي هو 96. | زد `Resolution` في `PngSaveOptions`. |
| **مسارات نظام الملفات غير موجودة** | سلاسل دليل العمل غير صحيحة. | استخدم مسارات مطلقة أو تحقق من وجود الأدلة قبل التشغيل. |

## الأسئلة المتكررة

### س1: هل يمكنني استخدام Aspose.TeX للـ .NET في تطبيق غير طرفية؟

ج1: بالتأكيد! Aspose.TeX يعمل في تطبيقات سطح المكتب، الويب، وتطبيقات الخدمات. ما عليك سوى استبدال طرفيات الكونسول بتدفقات مخصصة أو عناصر تحكم واجهة المستخدم.

### س2: كيف يمكنني تخصيص دقة صورة الإخراج؟

ج2: في المثال، يتم ضبط الدقة عبر `PngSaveOptions.Resolution`. غيّر القيمة العددية (مثال: `Resolution = 600`) للحصول على PNG بجودة أعلى.

### س3: هل تتوفر نسخة تجريبية؟

ج3: نعم، يمكنك تجربة Aspose.TeX عبر نسخة تجريبية مجانية **[من هنا](https://releases.aspose.com/)**.

### س4: أين يمكنني العثور على دعم إضافي ومساعدة؟

ج4: زر منتدى Aspose.TeX **[من هنا](https://forum.aspose.com/c/tex/47)** للحصول على دعم المجتمع والنقاشات.

### س5: كيف أحصل على ترخيص مؤقت لـ Aspose.TeX؟

ج5: يمكنك الحصول على ترخيص مؤقت **[من هنا](https://purchase.aspose.com/temporary-license/)**.

## الخاتمة

لقد رأيت الآن كيف **تحول TeX إلى PNG** باستخدام Aspose.TeX للغة C#. من خلال تكوين التدفقات، إعداد `ImageDevice`، ومعالجة إدخال الطرفية، يمكنك إنشاء صور عالية الدقة من أي مصدر TeX—مثالية للتقارير، معاينات الويب، أو خطوط الأنابيب الآلية. استكشف المزيد بتجربة مقاطع TeX مختلفة، تعديل DPI، أو دمج مصفوفة البايتات في واجهة المستخدم الخاصة بك.

---

**آخر تحديث:** 2025-12-20  
**تم الاختبار مع:** Aspose.TeX 24.11 للـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}