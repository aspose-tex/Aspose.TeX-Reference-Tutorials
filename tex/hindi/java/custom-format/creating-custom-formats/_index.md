---
date: 2026-09-04
description: Aspose.TeX का उपयोग करके Java में TeX से PDF उत्पन्न करना, कार्य निर्देशिकाएँ
  सेट करना, और सुसंगत टाइपसेटिंग के लिए कस्टम TeX फ़ॉर्मेट फ़ाइलें बनाना सीखें।
keywords:
- generate pdf from tex
- set working directories
- create custom tex format
- set tex input directory
- set tex output directory
lastmod: 2026-09-04
linktitle: Java में सुसंगत टाइपसेटिंग के लिए कस्टम TeX फ़ॉर्मेट बनाएं
og_description: Aspose.TeX के साथ Java में TeX से PDF उत्पन्न करें। कार्य निर्देशिकाएँ
  सेट करना, कस्टम TeX फ़ॉर्मेट बनाना, और सुसंगत टाइपसेटिंग सुनिश्चित करना सीखें।
og_image_alt: Screenshot of Java code generating PDF from TeX using Aspose.TeX
og_title: Java में TeX से PDF उत्पन्न करें और कस्टम फ़ॉर्मेट बनाएं
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to generate PDF from TeX in Java using Aspose.TeX, set working
    directories, and create custom TeX format files for consistent typesetting.
  headline: How to generate PDF from TeX and create formats in Java
  type: TechArticle
- description: Learn how to generate PDF from TeX in Java using Aspose.TeX, set working
    directories, and create custom TeX format files for consistent typesetting.
  name: How to generate PDF from TeX and create formats in Java
  steps:
  - name: Initialize TeX options (create a “no‑format” engine)
    text: The `TeXOptions` class lets you configure the TeX engine before any format
      is loaded.
  - name: Set the TeX input directory
    text: '`setInputWorkingDirectory` points the engine at the folder that contains
      your source `.tex` files, style packages, and any custom fonts. Using an absolute
      path during development avoids confusion with the IDE’s default working directory.
      > **Pro tip:** Keep your input folder read‑only in production '
  - name: Set the TeX output directory
    text: '`setOutputWorkingDirectory` defines where the engine writes compiled PDFs,
      log files, and auxiliary data. Separating output from source makes cleanup easier
      and enables you to archive results automatically.'
  - name: Run the format creation command
    text: Calling `createFormat("customtex", options)` tells Aspose.TeX to compile
      all packages referenced in the input directory into a binary format file named
      `customtex.fmt`. This step typically finishes within seconds, even for large
      collections of packages, because the engine only parses each macro once
  - name: Clean up the terminal output (optional)
    text: A simple `System.out.println()` adds a newline after the process finishes,
      keeping the console output tidy when you chain multiple conversions in a batch
      job.
  type: HowTo
- questions:
  - answer: You can refer to the [Aspose.TeX for Java documentation](https://reference.aspose.com/tex/java/)
      for comprehensive API details and usage examples.
    question: Where can I find the documentation for Aspose.TeX for Java?
  - answer: You can download the library from the [Aspose.TeX download page](https://releases.aspose.com/tex/java/).
    question: How can I download Aspose.TeX for Java?
  - answer: You can buy Aspose.TeX for Java from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.TeX for Java?
  - answer: Yes, you can access the free trial version on the [Aspose.TeX free trial
      download page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.TeX for Java?
  - answer: You can seek support on the [Aspose.TeX forum](https://forum.aspose.com/c/tex/47).
    question: How can I get support for Aspose.TeX for Java?
  type: FAQPage
second_title: Aspose.TeX Java API
tags:
- generate pdf
- Aspose.TeX
- Java typesetting
- custom tex format
title: Java में TeX से PDF उत्पन्न करने और फ़ॉर्मेट बनाने की विधि
url: /hi/java/custom-format/creating-custom-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# TeX से PDF कैसे जनरेट करें और Java में फॉर्मेट बनाएं

TeX से PDF जनरेट करना एक सामान्य आवश्यकता है जब आपको Java‑आधारित पाइपलाइन में उच्च‑गुणवत्ता वाले वैज्ञानिक या गणितीय दस्तावेज़ों की आवश्यकता होती है। इस ट्यूटोरियल में आप सीखेंगे कि Aspose.TeX के साथ **कस्टम TeX फॉर्मेट बनाएं**, **TeX इनपुट और आउटपुट डायरेक्टरी सेट करें**, और अंत में **TeX से PDF जनरेट करें** एक दोहराने योग्य, प्रदर्शनकारी तरीके से। अंत तक आपके पास एक पुन: उपयोग योग्य `.fmt` फ़ाइल होगी जो प्रत्येक दस्तावेज़ के लिए समान शैली की गारंटी देती है।

## त्वरित उत्तर
- **“create custom TeX format” का क्या मतलब है?** यह मैक्रोज़, फ़ॉन्ट्स, और लेआउट नियमों का एक सेट बाइनरी में संकलित करता है जिसे इंजन तुरंत लोड करता है।  
- **क्या मुझे लाइसेंस चाहिए?** विकास के लिए एक मुफ्त ट्रायल पर्याप्त है; उत्पादन तैनाती के लिए एक व्यावसायिक लाइसेंस आवश्यक है।  
- **कौन सा JDK संस्करण आवश्यक है?** Java 8 या उससे ऊपर (Java 17 LTS की सिफारिश की जाती है)।  
- **क्या मैं रनटाइम पर इनपुट फ़ोल्डर बदल सकता हूँ?** हाँ—ऑप्शन ऑब्जेक्ट पर `setInputWorkingDirectory` कॉल करें।  
- **क्या आउटपुट फ़ोल्डर कॉन्फ़िगर किया जा सकता है?** बिल्कुल—`setOutputWorkingDirectory` का उपयोग करके निर्धारित करें कि PDFs और लॉग्स कहाँ लिखे जाएँ।

## Java में TeX के लिए फॉर्मेट कैसे बनाएं?

`TeXOptions` एक कॉन्फ़िगरेशन ऑब्जेक्ट है जो Aspose.TeX इंजन की सेटिंग्स को नियंत्रित करता है। पहले, एक `TeXOptions` ऑब्जेक्ट बनाएं, इसे अपने स्रोत फ़ोल्डर की ओर इंगित करें, परिणाम लिखने की जगह बताएं, और अंत में `createFormat("customtex", options)` कॉल करें। `createFormat` मेथड स्रोत फ़ाइलों को एक पुन: उपयोग योग्य `.fmt` बाइनरी में संकलित करता है, जिसे आप बाद में PDF जनरेशन के लिए लोड कर सकते हैं। यह तरीका कंपाइल समय को 70 % तक कम करता है और सभी दस्तावेज़ों में सुसंगत लेआउट की गारंटी देता है।

## क्यों सेट करें TeX इनपुट और आउटपुट डायरेक्टरी?

इनपुट डायरेक्टरी सेट करने से इंजन को पता चलता है कि `.tex` स्रोत, फ़ॉन्ट फ़ाइलें, और सहायक पैकेज कहाँ स्थित हैं, जबकि आउटपुट डायरेक्टरी निर्धारित करती है कि संकलित PDFs, लॉग फ़ाइलें, और अस्थायी आर्टिफैक्ट्स कहाँ संग्रहीत हों। उचित डायरेक्टरी कॉन्फ़िगरेशन “फ़ाइल नहीं मिली” त्रुटियों को समाप्त करता है, आपके प्रोजेक्ट संरचना को साफ रखता है, और आपको कई रूपांतरणों को समानांतर में बिना टकराव के चलाने की अनुमति देता है।

## पूर्वापेक्षाएँ
- **Aspose.TeX for Java** – [Aspose.TeX डाउनलोड पेज](https://releases.aspose.com/tex/java/) से डाउनलोड करें।  
- **वर्किंग डायरेक्टरीज़** – एक *इनपुट* फ़ोल्डर (जहाँ आपके `.tex` फ़ाइलें स्थित हैं) और एक *आउटपुट* फ़ोल्डर (जहाँ जनरेट किए गए PDFs सहेजे जाएंगे) तय करें। स्निपेट्स में `"Your Input Directory"` और `"Your Output Directory"` को अपने वास्तविक पाथ से बदलें।  
- **Java Development Kit (JDK)** – संस्करण 8 या उससे नया स्थापित और आपके IDE या बिल्ड सिस्टम में कॉन्फ़िगर किया हुआ।

## पैकेज इम्पोर्ट करें
`TeXOptions` क्लास Aspose.TeX इंजन को कॉन्फ़िगर करती है, और यूटिलिटी `FileHelper` सैंपल प्रोजेक्ट में उपयोग किए गए सरल फ़ाइल‑सिस्टम हेल्पर प्रदान करती है।

```java
package com.aspose.tex.CustomTeXFormatFileCreation;

import java.io.IOException;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;

import util.Utils;
```

## कस्टम TeX फॉर्मेट बनाने के लिए चरण‑दर‑चरण गाइड

### चरण 1: TeX विकल्प प्रारंभ करें (एक “no‑format” इंजन बनाएं)

`TeXOptions` क्लास आपको TeX इंजन को किसी भी फॉर्मेट को लोड करने से पहले कॉन्फ़िगर करने देती है।

```java
// Create TeX engine options for no format upon ObjectTeX engine extension.
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectIniTeX());
```

### चरण 2: TeX इनपुट डायरेक्टरी सेट करें

`setInputWorkingDirectory` इंजन को उस फ़ोल्डर की ओर इंगित करता है जिसमें आपके स्रोत `.tex` फ़ाइलें, स्टाइल पैकेज, और कोई भी कस्टम फ़ॉन्ट्स होते हैं। विकास के दौरान एक एब्सोल्यूट पाथ उपयोग करने से IDE की डिफ़ॉल्ट वर्किंग डायरेक्टरी से भ्रम बचता है।

```java
// Specify a file system working directory for the input.
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
```

> **प्रो टिप:** उत्पादन में अपने इनपुट फ़ोल्डर को केवल‑पढ़ने योग्य रखें ताकि स्रोत TeX फ़ाइलों में आकस्मिक संशोधन से बचा जा सके।

### चरण 3: TeX आउटपुट डायरेक्टरी सेट करें

`setOutputWorkingDirectory` निर्धारित करता है कि इंजन संकलित PDFs, लॉग फ़ाइलें, और सहायक डेटा कहाँ लिखे। आउटपुट को स्रोत से अलग रखने से सफ़ाई आसान होती है और आप परिणामों को स्वचालित रूप से आर्काइव कर सकते हैं।

```java
// Specify a file system working directory for the output.
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### चरण 4: फॉर्मेट निर्माण कमांड चलाएँ

`createFormat("customtex", options)` कॉल करने से Aspose.TeX को इनपुट डायरेक्टरी में संदर्भित सभी पैकेजों को `customtex.fmt` नामक बाइनरी फॉर्मेट फ़ाइल में संकलित करने को कहा जाता है। यह चरण आमतौर पर कुछ सेकंड में समाप्त हो जाता है, यहाँ तक कि बड़े पैकेज संग्रह के लिए भी, क्योंकि इंजन प्रत्येक मैक्रो को केवल एक बार पार्स करता है।

```java
// Run format creation.
TeXJob.createFormat("customtex", options);
```

कॉल पूर्ण होने के बाद, आप `customtex.fmt` को आउटपुट फ़ोल्डर में पाएँगे। बाद में इस फ़ाइल को लोड करने से प्रत्येक दस्तावेज़ के कंपाइल समय को **70 %** तक कम किया जा सकता है, जैसा कि Aspose बेंचमार्क्स में दिखाया गया है।

### चरण 5: टर्मिनल आउटपुट साफ़ करें (वैकल्पिक)

एक साधारण `System.out.println()` प्रक्रिया समाप्त होने के बाद एक नई पंक्ति जोड़ता है, जिससे जब आप बैच जॉब में कई रूपांतरणों को श्रृंखला में चलाते हैं तो कंसोल आउटपुट साफ़ रहता है।

```java
// For further output to look fine.
options.getTerminalOut().getWriter().newLine();
// ExEnd:CreateCustomTeXFormatFile
```

## सामान्य समस्याएँ और समाधान
| समस्या | कारण | समाधान |
|-------|-------|-----|
| **“.tex स्रोत के लिए “फ़ाइल नहीं मिली”** | इनपुट डायरेक्टरी पाथ गलत | यह सुनिश्चित करें कि `setInputWorkingDirectory` को दिया गया पाथ आपके `.tex` फ़ाइलों वाले फ़ोल्डर से मेल खाता है। |
| **आउटपुट फ़ोल्डर पर अनुमति अस्वीकृत** | लिखने की अधिकार नहीं | यह सुनिश्चित करें कि Java प्रक्रिया के पास `setOutputWorkingDirectory` द्वारा सेट की गई डायरेक्टरी पर लिखने की अनुमति है। |
| **फ़ॉर्मेट निर्माण अटक रहा है** | बहुत अधिक पैकेज लोड हो रहे हैं | केवल आवश्यक पैकेजों को प्री‑कम्पाइल करें; Aspose.TeX **60+** इनपुट फॉर्मेट को पूरी TeX वितरण लोड किए बिना संभाल सकता है। |

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: Aspose.TeX for Java की दस्तावेज़ीकरण कहाँ मिल सकती है?**  
उत्तर: आप व्यापक API विवरण और उपयोग उदाहरणों के लिए [Aspose.TeX for Java दस्तावेज़ीकरण](https://reference.aspose.com/tex/java/) देख सकते हैं।

**प्रश्न: Aspose.TeX for Java को कैसे डाउनलोड करूँ?**  
उत्तर: आप लाइब्रेरी को [Aspose.TeX डाउनलोड पेज](https://releases.aspose.com/tex/java/) से डाउनलोड कर सकते हैं।

**प्रश्न: Aspose.TeX for Java को कहाँ खरीद सकते हैं?**  
उत्तर: आप [खरीद पेज](https://purchase.aspose.com/buy) से Aspose.TeX for Java खरीद सकते हैं।

**प्रश्न: क्या Aspose.TeX for Java के लिए मुफ्त ट्रायल उपलब्ध है?**  
उत्तर: हाँ, आप [Aspose.TeX मुफ्त ट्रायल डाउनलोड पेज](https://releases.aspose.com/) पर मुफ्त ट्रायल संस्करण प्राप्त कर सकते हैं।

**प्रश्न: Aspose.TeX for Java के लिए समर्थन कैसे प्राप्त करूँ?**  
उत्तर: आप [Aspose.TeX फ़ोरम](https://forum.aspose.com/c/tex/47) पर समर्थन प्राप्त कर सकते हैं।

## निष्कर्ष
अब आपके पास Aspose.TeX for Java के साथ **TeX से PDF जनरेट करने** के लिए एक पूर्ण, उत्पादन‑तैयार रेसिपी है। **TeX इनपुट डायरेक्टरी सेट करके** और **TeX आउटपुट डायरेक्टरी सेट करके**, आप यह नियंत्रित कर सकते हैं कि स्रोत फ़ाइलें कहाँ पढ़ी जाएँ और परिणाम कहाँ लिखे जाएँ, जिससे आपके सभी Java प्रोजेक्ट्स में विश्वसनीय, दोहराने योग्य टाइपसेटिंग मिलती है। किसी भी बाद के रन में `customtex.fmt` फ़ाइल को पुन: उपयोग करें ताकि तेज़ कंपाइलेशन और सुसंगत लेआउट का आनंद ले सकें।

---

**अंतिम अपडेट:** 2026-09-04  
**परीक्षित संस्करण:** Aspose.TeX for Java 24.11  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [कस्टम Tex फॉर्मेट टाइपसेटिंग](/tex/java/custom-tex-formats/typesetting-custom-tex-formats/)
- [TeX पढ़ना – इनपुट डायरेक्टरी सेट करना Java गाइड Aspose.TeX for Java के साथ](/tex/java/advanced-io/required-input-directory/)
- [Java में TeX को XPS में बदलना – चरण‑दर‑चरण गाइड](/tex/java/typesetting-tex-to-xps/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}