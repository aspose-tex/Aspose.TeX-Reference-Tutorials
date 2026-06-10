---
date: 2026-02-10
description: تعلم كيفية إنشاء تنسيق TeX مخصص وكيفية تنسيق TeX في Java باستخدام Aspose.TeX
  for Java، بما في ذلك الإعداد خطوة بخطوة، ومعالجة التنسيق المخصص، والحصول على ترخيص
  مؤقت.
linktitle: How to Typeset TeX with Custom Formats in Java
second_title: Aspose.TeX Java API
title: كيفية إنشاء تنسيق TeX مخصص وتنسيق TeX في Java
url: /ar/java/custom-tex-formats/typesetting-custom-tex-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء تنسيق TeX مخصص وتنسيق TeX في Java

## المقدمة

إذا كنت بحاجة إلى **إنشاء تنسيق tex مخصص** وتنسيق TeX داخل تطبيق Java، فإن Aspose.TeX توفر طريقة نظيفة وعالية الأداء للعمل مع ملفات تنسيق TeX المخصصة. في هذا الدرس سنستعرض كل ما تحتاجه — من إعداد البيئة إلى تشغيل مهمة TeX التي تستخدم تنسيقك الخاص. سواءً كنت تبني أداة نشر علمية أو مولد تقارير مخصص، فإن الخطوات أدناه ستجعلك جاهزًا بسرعة.

## إجابات سريعة
- **ما المكتبة التي أحتاجها؟** Aspose.TeX for Java  
- **هل يمكنني استخدام تنسيق TeX مخصص؟** نعم — ما عليك سوى توجيه `FormatProvider` إلى ملفك.  
- **هل أحتاج إلى ترخيص للتطوير؟** ترخيص مؤقت من Aspose للاختبار؛ الترخيص الكامل مطلوب للإنتاج.  
- **ما نسخة Java المدعومة؟** JDK 8 أو أعلى.  
- **ما تنسيق الإخراج الذي يولده المثال؟** XPS (يمكنك التبديل إلى PDF أو PNG، إلخ).

## ما هو تنسيق TeX المخصص؟
تنسيق TeX المخصص هو مجموعة مُجمَّعة مسبقًا من الماكروات والبدائيات التي تُخصِّص محرك TeX لأسلوب المستند الخاص بك. من خلال توفير ملف `.fmt` الخاص بك، يمكنك التحكم في الخطوط، قواعد التخطيط، وتعريفات الأوامر دون تعديل مصدر TeX في كل مرة.

## لماذا نستخدم Aspose.TeX for Java؟
- **Pure Java** – لا توجد ثنائيات أصلية، سهل الإدماج في أي مشروع يعتمد على JVM.  
- **دقة عالية** – يولد مخرجات تتطابق مع عرض LaTeX.  
- **قابلية التوسيع** – يدعم التنسيقات المخصصة، أجهزة إخراج متعددة، ومعالجة دفعات.  
- **مرونة الترخيص** – ابدأ بترخيص مؤقت من Aspose، ثم قم بالترقية عند الانتقال إلى الإنتاج.

## المتطلبات المسبقة

قبل أن تبدأ، تأكد من وجود ما يلي:

1. **مجموعة تطوير Java (JDK)** – JDK 8 أو أحدث مثبت. حمّله من [موقع Java الرسمي](https://www.oracle.com/java/technologies/javase-downloads.html) إذا لم تكن قد فعلت ذلك.  
2. **مكتبة Aspose.TeX للـ Java** – احصل على أحدث ملف JAR من [صفحة تنزيل Aspose.TeX for Java](https://releases.aspose.com/tex/java/).  
3. **ملف تنسيق TeX المخصص** – ضع ملف `.fmt` المُجمَّع (مثال: `customtex.fmt`) في مجلد سيعمل كدليل إخراج.  

> **نصيحة احترافية:** إذا كنت تقيم المنتج، اطلب *ترخيصًا مؤقتًا من Aspose* عبر بوابة Aspose؛ فهو يزيل علامة التقييم لفترة محدودة.

## استيراد الحزم

أولاً، أضف الاستيرادات المطلوبة إلى مشروع Java الخاص بك. هذه الفئات تمنحك الوصول إلى موفر التنسيق، تكوين المهمة، وجهاز العرض.

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

## دليل خطوة بخطوة

### الخطوة 1: إنشاء موفر تنسيق

`FormatProvider` يحدد الدليل الذي يحتوي على ملف تنسيق TeX المخصص. استبدل `"Your Output Directory"` بالمسار الفعلي حيث يتواجد `customtex.fmt`.

```java
final FormatProvider formatProvider = new FormatProvider(
        new InputFileSystemDirectory("Your Output Directory"), "customtex");
```

### الخطوة 2: ضبط خيارات التحويل

قم بتكوين المهمة لاستخدام محرك ObjectTeX (المحرك الذي يفهم التنسيقات المخصصة). هنا نحدد أيضًا اسم المهمة ونحدد دلائل العمل للمدخلات/المخرجات.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX(formatProvider));
options.setJobName("typeset-with-custom-format");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### الخطوة 3: تشغيل مهمة TeX

أنشئ كائن `TeXJob`، زوده بمقتطف TeX بسيط، واطلب منه عرض النتيجة باستخدام `XpsDevice`. ينتهي المقتطف بـ `\end` لإغلاق المستند.

```java
new TeXJob(new ByteArrayInputStream(
        "Congratulations! You have successfully typeset this text with your own TeX format!\\end".getBytes("ASCII")),
        new XpsDevice(), options).run();
```

### الخطوة 4: إنهاء الإخراج

بعد انتهاء المهمة، أضف سطرًا جديدًا إلى مخرجات الطرفية حتى يبقى سطر الأوامر منظمًا.

```java
options.getTerminalOut().getWriter().newLine();
```

### الخطوة 5: إغلاق موفر التنسيق

عند الانتهاء، أغلق الموفر لتحرير مقبض الملف وتحرير الموارد.

```java
formatProvider.close();
```

## حالات الاستخدام الشائعة

- **إنشاء أوراق علمية تلقائيًا** – استخدم تنسيقًا مُجمَّعًا يضم ماكروات خاصة بالمجلة.  
- **إنشاء تقارير ديناميكية** – توليد فواتير أو شهادات في الوقت الفعلي دون إعادة بناء مصادر LaTeX في كل مرة.  
- **معالجة دفعات من مجموعات مستندات كبيرة** – حمّل تنسيقًا مخصصًا مرة واحدة وأعد استخدامه لمئات الملفات، مما يقلل وقت المعالجة بشكل كبير.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|-------|-----|
| **“Format file not found”** | مسار غير صحيح في `FormatProvider` | تحقق من أن الدليل واسم الملف (`customtex.fmt`) صحيحان ومتاحان. |
| **أخطاء الترميز** | أحرف غير ASCII في سلسلة TeX | استخدم ترميز UTF‑8 (`"UTF-8"` بدلاً من `"ASCII"`). |
| **عدم إنشاء الإخراج** | دليل الإخراج يفتقر إلى صلاحية الكتابة | تأكد من أن عملية Java لديها صلاحية كتابة على `"Your Output Directory"`. |
| **علامة ترخيص مائية** | استخدام ترخيص التقييم فقط | طبّق *ترخيصًا مؤقتًا من Aspose* للاختبار أو اشترِ ترخيصًا كاملاً للإنتاج. |

**الموارد ذات الصلة:** [Aspose.TeX API Reference](https://docs.aspose.com/tex/java/) | [Download Free Trial](https://releases.aspose.com/tex/java/)

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.TeX مع مكتبات Java أخرى؟**  
ج: بالتأكيد. الـ API مكتبة Java صافية وتعمل جنبًا إلى جنب مع مكتبات مثل Apache PDFBox أو iText أو Spring Boot.

**س: أين يمكنني الحصول على ترخيص مؤقت من Aspose للتقييم؟**  
ج: اطلبه من [صفحة الترخيص المؤقت لـ Aspose](https://purchase.aspose.com/temporary-license/). يزيل علامة التقييم لمدة تصل إلى 30 يومًا.

**س: هل يدعم Aspose.TeX تنسيقات إخراج غير XPS؟**  
ج: نعم. يمكنك استبدال `new XpsDevice()` بـ `new PdfDevice()` أو `new PngDevice()` حسب الحاجة.

**س: كيف يمكنني تتبع مهمة TeX فاشلة؟**  
ج: فعّل التسجيل التفصيلي عبر استدعاء `options.setLogLevel(LogLevel.DEBUG);` وتفحص مخرجات الطرفية للحصول على رسائل الأخطاء المفصلة.

**س: هل هناك نسخة تجريبية مجانية متاحة؟**  
ج: نعم – حمّل النسخة التجريبية من [صفحة تنزيل Aspose.TeX](https://releases.aspose.com/tex/java/).

**س: هل يمكنني إنشاء تنسيقات مخصصة متعددة في نفس التطبيق؟**  
ج: نعم. أنشئ `FormatProvider` منفصل لكل ملف `.fmt` ومرّر الموفر المناسب إلى `TeXConfig.objectTeX()`.

## الخاتمة

أنت الآن تعرف **كيفية إنشاء تنسيق tex مخصص** و**كيفية تنسيق tex في Java** باستخدام Aspose.TeX. باتباع الخطوات أعلاه، يمكنك دمج تنضيد عالي الجودة في أي سير عمل مبني على Java، تجربة ملفات التنسيق الخاصة بك، والانتقال من النموذج الأولي إلى الإنتاج مع ترخيص مناسب.

---

**آخر تحديث:** 2026-02-10  
**تم الاختبار مع:** Aspose.TeX for Java 24.10  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}