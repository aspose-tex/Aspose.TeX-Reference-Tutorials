---
date: 2025-12-05
description: تعلم كيفية تنسيق TeX باستخدام Aspose.TeX للغة Java، بما في ذلك خطوات
  التنسيقات المخصصة وكيفية الحصول على ترخيص مؤقت من Aspose.
linktitle: How to Typeset TeX with Custom Formats in Java
second_title: Aspose.TeX Java API
title: كيفية تنضيد TeX باستخدام صيغ مخصصة في Java
url: /ar/java/custom-tex-formats/typesetting-custom-tex-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تنسيق TeX باستخدام تنسيقات مخصصة في Java

## مقدمة

إذا كنت بحاجة إلى **how to typeset tex** داخل تطبيق Java، توفر Aspose.TeX طريقة نظيفة وعالية الأداء للعمل مع ملفات تنسيق TeX المخصصة. في هذا الدليل سنستعرض كل ما تحتاجه — من إعداد البيئة إلى تشغيل مهمة TeX تستخدم تنسيقك الخاص. سواء كنت تبني أداة نشر علمية أو مولد تقارير مخصص، فإن الخطوات أدناه ستجعلك تبدأ بسرعة.

## إجابات سريعة
- **ما المكتبة التي أحتاجها؟** Aspose.TeX for Java  
- **هل يمكنني استخدام تنسيق TeX مخصص؟** نعم – فقط وجه `FormatProvider` إلى ملفك.  
- **هل أحتاج إلى ترخيص للتطوير؟** ترخيص مؤقت aspose يعمل للاختبار؛ الترخيص الكامل مطلوب للإنتاج.  
- **ما نسخة Java المدعومة؟** JDK 8 أو أعلى.  
- **ما تنسيق الإخراج الذي يولده المثال؟** XPS (يمكنك التبديل إلى PDF، PNG، إلخ).

## ما هو تنسيق TeX مخصص؟

تنسيق TeX مخصص هو مجموعة مُجمّعة مسبقًا من الماكرو والبدائيات التي تُخصّص محرك TeX لأسلوب المستند الخاص بك. من خلال توفير ملف `.fmt` الخاص بك، يمكنك التحكم في الخطوط، قواعد التخطيط، وتعريفات الأوامر دون تعديل مصدر TeX في كل مرة.

## لماذا تستخدم Aspose.TeX لـ Java؟

- **Pure Java** – لا توجد ملفات تنفيذية أصلية، سهل الإدماج في أي مشروع يعتمد على JVM.  
- **High fidelity** – يولد مخرجات تتطابق مع عرض LaTeX.  
- **Extensible** – يدعم التنسيقات المخصصة، أجهزة إخراج متعددة، ومعالجة دفعات.  
- **License flexibility** – ابدأ بترخيص مؤقت aspose، ثم قم بالترقية عند الانتقال إلى الإنتاج.

## المتطلبات المسبقة

قبل أن تبدأ، تأكد من أن لديك:

1. **Java Development Kit (JDK)** – JDK 8 أو أحدث مثبت. قم بتنزيله من [Java website](https://www.oracle.com/java/technologies/javase-downloads.html) الرسمي إذا لم تقم بذلك بعد.  
2. **Aspose.TeX library for Java** – احصل على أحدث ملف JAR من [Aspose.TeX for Java download page](https://releases.aspose.com/tex/java/).  
3. **Your custom TeX format file** – ضع ملف `.fmt` المُجمّع (مثال: `customtex.fmt`) في مجلد سيعمل كدليل الإخراج.  

> **نصيحة احترافية:** إذا كنت تقيم المنتج، اطلب *ترخيصًا مؤقتًا aspose* من بوابة Aspose؛ فهو يزيل علامة التقييم المائية لفترة محدودة.

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

`FormatProvider` يشير إلى الدليل الذي يحتوي على ملف تنسيق TeX المخصص الخاص بك. استبدل `"Your Output Directory"` بالمسار الفعلي حيث يوجد `customtex.fmt`.

```java
final FormatProvider formatProvider = new FormatProvider(
        new InputFileSystemDirectory("Your Output Directory"), "customtex");
```

### الخطوة 2: ضبط خيارات التحويل

قم بتهيئة المهمة لاستخدام محرك ObjectTeX (المحرك الذي يفهم التنسيقات المخصصة). هنا نحدد أيضًا اسم المهمة ونحدد أدلة العمل للإدخال/الإخراج.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX(formatProvider));
options.setJobName("typeset-with-custom-format");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### الخطوة 3: تشغيل مهمة TeX

أنشئ كائن `TeXJob`، وزوده بمقتطف TeX بسيط، واطلب منه عرض النتيجة باستخدام `XpsDevice`. ينتهي المقتطف بـ `\end` لإغلاق المستند.

```java
new TeXJob(new ByteArrayInputStream(
        "Congratulations! You have successfully typeset this text with your own TeX format!\\end".getBytes("ASCII")),
        new XpsDevice(), options).run();
```

### الخطوة 4: إنهاء الإخراج

بعد انتهاء المهمة، أضف فاصل سطر إلى مخرجات الطرفية حتى يبقى سطر الأوامر منظمًا.

```java
options.getTerminalOut().getWriter().newLine();
```

### الخطوة 5: إغلاق موفر التنسيق

عند الانتهاء، أغلق الموفر لتحرير مقابض الملفات وتحرير الموارد.

```java
formatProvider.close();
```

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|-------|-----|
| **“Format file not found”** | مسار غير صحيح في `FormatProvider` | تحقق من أن الدليل واسم الملف (`customtex.fmt`) صحيحان ومتاحان. |
| **Encoding errors** | أحرف غير ASCII في سلسلة TeX | استخدم ترميز UTF‑8 (`"UTF-8"` بدلاً من `"ASCII"`). |
| **Output not generated** | دليل الإخراج يفتقر إلى صلاحية الكتابة | تأكد من أن عملية Java لديها صلاحية كتابة على `"Your Output Directory"`. |
| **License watermark** | استخدام ترخيص التقييم فقط | طبق *ترخيصًا مؤقتًا aspose* للاختبار أو اشترِ ترخيصًا كاملاً للإنتاج. |


**الموارد ذات الصلة:** [Aspose.TeX API Reference](https://docs.aspose.com/tex/java/) | [Download Free Trial](https://releases.aspose.com/tex/java/)

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.TeX مع مكتبات Java أخرى؟**  
ج: بالتأكيد. الـ API هو Pure Java ويعمل جنبًا إلى جنب مع مكتبات مثل Apache PDFBox أو iText أو Spring Boot.

**س: من أين يمكنني الحصول على ترخيص مؤقت aspose للتقييم؟**  
ج: اطلب واحدًا من [Aspose temporary license page](https://purchase.aspose.com/temporary-license/). يزيل علامة التقييم المائية لمدة تصل إلى 30 يومًا.

**س: هل يدعم Aspose.TeX تنسيقات إخراج غير XPS؟**  
ج: نعم. يمكنك استبدال `new XpsDevice()` بـ `new PdfDevice()` أو `new PngDevice()` وغيرها حسب احتياجاتك.

**س: كيف يمكنني تتبع مهمة TeX فاشلة؟**  
ج: فعّل التسجيل التفصيلي عبر استدعاء `options.setLogLevel(LogLevel.DEBUG);` وتفحص مخرجات وحدة التحكم للحصول على رسائل خطأ مفصلة.

**س: هل هناك نسخة تجريبية مجانية متاحة؟**  
ج: نعم – قم بتنزيل الملفات التجريبية من [Aspose.TeX download page](https://releases.aspose.com/tex/java/).

## الخلاصة

أنت الآن تعرف **how to typeset tex** في تطبيق Java باستخدام تنسيق TeX مخصص مع Aspose.TeX. باتباع الخطوات أعلاه، يمكنك دمج تنسيق عالي الجودة في أي سير عمل مبني على Java، تجربة ملفات التنسيق الخاصة بك، والانتقال من النموذج الأولي إلى الإنتاج باستخدام ترخيص مناسب.

---

**آخر تحديث:** 2025-12-05  
**تم الاختبار مع:** Aspose.TeX for Java 24.10  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}