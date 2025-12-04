---
date: 2025-12-04
description: تعلم كيفية إضافة فواصل أسطر في TeX أثناء إنشاء تنسيق TeX مخصص في Java
  باستخدام Aspose.TeX. دليل خطوة بخطوة للكتابة الفعّالة.
language: ar
linktitle: Add Line Breaks Tex – Typesetting Custom TeX Formats in Java
second_title: Aspose.TeX Java API
title: إضافة فواصل أسطر في TeX – تنسيق صيغ TeX مخصصة في Java
url: /java/custom-tex-formats/typesetting-custom-tex-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة فواصل سطرية في TeX – تنسيق صيغ TeX مخصصة في Java

## المقدمة

إذا كنت بحاجة إلى **إضافة فواصل سطرية في tex** أثناء العمل مع تعريفات TeX الخاصة بك، فإن Aspose.TeX for Java يجعل ذلك سهلًا. في هذا البرنامج التعليمي سنستعرض سير العمل بالكامل — من إعداد *صيغة TeX مخصصة* إلى عرض المستند النهائي — حتى تتمكن من رؤية **كيفية تنسيق tex java** بثقة. سواء كنت تبني خط أنابيب نشر علمي أو مولد تقارير مخصص، فإن الخطوات أدناه ستجعلك تبدأ بسرعة.

## إجابات سريعة
- **ماذا يفعل “add line breaks tex”؟**  
  يضيف أوامر فواصل سطرية صريحة إلى تدفق الإخراج، مما يضمن أن المستند المعروض يحترم التخطيط المطلوب.
- **هل أحتاج إلى ترخيص لتجربة ذلك؟**  
  تتوفر نسخة تجريبية مجانية من Aspose.TeX؛ يلزم وجود ترخيص للاستخدام في الإنتاج.
- **ما نسخة Java المدعومة؟**  
  أي JDK 8 أو أحدث يعمل مع أحدث مكتبة Aspose.TeX.
- **هل يمكنني استخدام ملف صيغة TeX الخاص بي؟**  
  نعم — ستتعلم كيفية **إنشاء صيغ tex مخصصة** وتوجيه الـ API إليها.
- **ما صيغ الإخراج الممكنة؟**  
  المثال أدناه يولد XPS، لكن يمكنك التبديل إلى PDF أو PNG، إلخ، عن طريق تغيير جهاز العرض.

## ما هو “add line breaks tex”؟
إضافة فواصل سطرية في TeX تخبر المحرك أين يبدأ سطر جديد في المستند الناتج. في Aspose.TeX API يتم التحكم بذلك عبر تدفق الإخراج الطرفي، ويمكنك كتابة سطر جديد صريح بعد انتهاء المهمة.

## لماذا إنشاء صيغة TeX مخصصة؟
تتيح لك الصيغة المخصصة تجميع الماكرو والحزم والإعدادات المستخدمة بشكل متكرر مسبقًا، مما يسرّع عملية التنسيق بشكل كبير. كما تمنحك سيطرة كاملة على سلوك محرك TeX — مثالية لسير عمل النشر المتخصص.

## المتطلبات المسبقة

1. **مجموعة تطوير Java (JDK)** – JDK 8 أو أحدث. حمّلها من [موقع Java الرسمي](https://www.oracle.com/java/technologies/javase-downloads.html) إذا لم تكن قد فعلت ذلك.  
2. **Aspose.TeX for Java** – احصل على أحدث مكتبة من [صفحة تنزيل Aspose.TeX for Java](https://releases.aspose.com/tex/java/).  
3. **ملف صيغة TeX مخصص** – حضّر ملف `.fmt` (مثال: `customtex.fmt`) وضعه في الدليل الذي ستشير إليه لاحقًا كـ *دليل الإخراج*.

## استيراد الحزم

أولاً، استورد الفئات المطلوبة إلى مشروعك. استيراد `util.Utils` اختياري ويُستخدم فقط للمساعدات التجريبية.

```java
package com.aspose.tex.TypesetWithCustomTeXFormat;

import java.io.ByteArrayInputStream;
import java.io.IOException;

import com.aspose.tex.FormatProvider;
import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

### الخطوة 1: إنشاء موفر الصيغة  

`FormatProvider` يشير إلى المجلد الذي يحتوي على صيغة TeX المخصصة الخاصة بك (`customtex.fmt`). استبدل **Your Output Directory** بالمسار الفعلي على جهازك.

```java
final FormatProvider formatProvider = new FormatProvider(
		new InputFileSystemDirectory("Your Output Directory"), "customtex");
```

### الخطوة 2: ضبط خيارات التحويل  

قم بتكوين المهمة لاستخدام محرك ObjectTeX (المحرك الذي يعمل مع الصيغ المخصصة). هنا نحدد أيضًا اسم المهمة، دليل الإدخال، ودليل الإخراج.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX(formatProvider));
options.setJobName("typeset-with-custom-format");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### الخطوة 3: تشغيل مهمة TeX  

مرّر سلسلة TeX بسيطة إلى `TeXJob`. تنتهي السلسلة بـ `\\end` للإشارة إلى نهاية المستند. هنا ستظهر عملية **add line breaks tex** في مستند XPS المعروض.

```java
new TeXJob(new ByteArrayInputStream(
        "Congratulations! You have successfully typeset this text with your own TeX format!\\end".getBytes("ASCII")),
        new XpsDevice(), options).run();
```

### الخطوة 4: إضافة فواصل سطرية صريحة  

بعد انتهاء المهمة، اكتب سطرًا جديدًا إلى تدفق الإخراج الطرفي. تُظهر هذه الخطوة تقنية “add line breaks tex”.

```java
options.getTerminalOut().getWriter().newLine();
```

### الخطوة 5: إغلاق موفر الصيغة  

دائمًا حرّر الموارد عند الانتهاء.

```java
formatProvider.close();
```

## المشكلات الشائعة وكيفية حلها

| المشكلة | السبب | الحل |
|-------|----------------|-----|
| **`FormatProvider` لا يمكنه العثور على ملف `.fmt`** | مسار الدليل غير صحيح أو امتداد الملف مفقود. | تحقق من أن المسار في `InputFileSystemDirectory` يشير إلى المجلد الذي يحتوي على `customtex.fmt`. |
| **ملف الإخراج فارغ** | قد لا تحتوي سلسلة TeX على أمر `\end` صحيح. | تأكد من أن السلسلة تنتهي بـ `\\end` (شرطة مائلة مزدوجة في Java). |
| **جهاز عرض غير مدعوم** | محاولة العرض إلى صيغة غير مرتبطة بالمكتبة. | استبدل `new XpsDevice()` بـ `new PdfDevice()` أو أي جهاز مدعوم آخر. |

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.TeX مع مكتبات Java أخرى؟**  
ج: نعم، يتكامل Aspose.TeX بسلاسة مع مكتبات مثل Apache Commons IO، Log4j، أو أي أداة بناء مثل Maven/Gradle.

**س: أين يمكنني العثور على مزيد من المساعدة والدعم؟**  
ج: استكشف [منتدى Aspose.TeX](https://forum.aspose.com/c/tex/47) للحصول على دعم المجتمع والنقاشات.

**س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.TeX؟**  
ج: نعم، يمكنك الوصول إلى النسخة التجريبية [هنا](https://releases.aspose.com/).

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.TeX؟**  
ج: زر صفحة [الترخيص المؤقت](https://purchase.aspose.com/temporary-license/) للحصول على خيارات الترخيص المؤقت.

**س: أين يمكنني شراء مكتبة Aspose.TeX؟**  
ج: احصل على نسختك بزيارة [صفحة الشراء](https://purchase.aspose.com/buy).

**أسئلة وإجابات إضافية**

**س: كيف أغيّر صيغة الإخراج من XPS إلى PDF؟**  
ج: استبدل `new XpsDevice()` بـ `new PdfDevice()` وعدّل أي خيارات خاصة بالصِيغة في `TeXOptions`.

**س: هل يمكنني تضمين خطوط مخصصة في المستند المُولد؟**  
ج: نعم — استخدم `options.getFontResolver().addFont("path/to/font.ttf")` قبل تشغيل المهمة.

## الخاتمة

لقد تعلمت الآن كيفية **إضافة فواصل سطرية في tex**، إنشاء **صيغة tex مخصصة**، وتنفيذ سير عمل تنسيق كامل باستخدام Aspose.TeX for Java. باستخدام هذه اللبنات الأساسية يمكنك توسيع الحل لتوليد PDFs أو PNGs أو أي صيغة مدعومة أخرى — مثالي لأتمتة الأوراق العلمية، الفواتير، أو التقارير المخصصة.

---

**آخر تحديث:** 2025-12-04  
**تم الاختبار مع:** Aspose.TeX 24.11 for Java  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}