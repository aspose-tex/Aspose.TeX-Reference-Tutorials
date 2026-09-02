---
date: 2026-08-18
description: Aspose.TeX का उपयोग करके Java में console output को redirect करना, terminal
  output को file में लिखना, और बेहतर logging के लिए job name को override करना सीखें।
keywords:
- redirect console output java
- Aspose.TeX Java
- Java logging
- override job name
lastmod: 2026-08-18
linktitle: Java में Terminal Output को File में लिखें और Job Name को Override करें
og_description: Aspose.TeX के साथ Java में console output को redirect करें और अलग-अलग
  log files बनाने के लिए job name को override करें। विश्वसनीय logging के लिए इस step‑by‑step
  ट्यूटोरियल का पालन करें।
og_image_alt: Screenshot of Java console output redirection using Aspose.TeX
og_title: Java में console output को redirect करें और job name को override करें –
  Aspose.TeX गाइड
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Learn how to redirect console output in Java using Aspose.TeX, write
    terminal output to a file, and override the job name for better logging.
  headline: How to redirect console output in Java and override job name
  type: TechArticle
- description: Learn how to redirect console output in Java using Aspose.TeX, write
    terminal output to a file, and override the job name for better logging.
  name: How to redirect console output in Java and override job name
  steps:
  - name: create conversion options
    text: '`TeXOptions` is the configuration object that controls how Aspose.TeX processes
      a TeX job. It holds settings such as output format, font handling, and terminal
      redirection.'
  - name: specify job name and working directories
    text: '`TeXJob` represents a single conversion task, linking input, output, and
      options together. Setting a custom job name ensures the generated log file is
      uniquely named. > **Why override the job name?** > Overriding the job name makes
      log files and generated artifacts easier to identify, especially whe'
  - name: write terminal output to file system
    text: '`setTerminalOut` tells Aspose.TeX where to write the console log file.
      The file will be named `<job_name>.trm` and placed in the output working directory
      you defined above. Configure the terminal output redirection:'
  - name: run the job
    text: '`run()` executes the conversion based on the supplied options and writes
      output files (including the `.trm` log) to the designated folder. Create a `TeXJob`
      with the desired input file (here we use a simple “hello‑world” example) and
      the XPS rendering device, then call `run()`: When the job finishes'
  type: HowTo
- questions:
  - answer: Yes, Aspose.TeX integrates seamlessly with other Java libraries, allowing
      you to combine PDF, image, or database utilities in the same workflow.
    question: Can I use Aspose.TeX for Java with other Java libraries?
  - answer: Visit the [Aspose.TeX forum](https://forum.aspose.com/c/tex/47) for community
      help, or open a support ticket through the Aspose support portal.
    question: Where can I find support for Aspose.TeX for Java?
  - answer: Absolutely. You can download a fully functional trial from the [Aspose.TeX
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.TeX for Java?
  - answer: Use the temporary‑license request form at [Aspose temporary license](https://purchase.aspose.com/temporary-license/)
      to get a 30‑day evaluation license.
    question: How can I obtain a temporary license for testing?
  - answer: Purchase a license directly from the [Aspose.TeX buying page](https://purchase.aspose.com/buy).
    question: Where can I purchase a permanent license?
  type: FAQPage
second_title: Aspose.TeX Java API
tags:
- redirect console output
- Aspose.TeX
- Java console logging
- job name override
title: Java में console output को redirect करने और job name को override करने का तरीका
url: /hi/java/customizing-output/override-job-name-disk/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# टर्मिनल आउटपुट को फ़ाइल में लिखें और जावा में जॉब नाम को ओवरराइड करें

## परिचय

इस ट्यूटोरियल में आप सीखेंगे कि **redirect console output in Java** कैसे किया जाता है जबकि Aspose.TeX के साथ TeX फ़ाइलों को प्रोसेस किया जाता है। हम आपको दिखाएंगे कि टर्मिनल लॉग को `.trm` फ़ाइल में कैसे लिखा जाए, डिफ़ॉल्ट जॉब नाम को ओवरराइड कैसे किया जाए, और बैच रूपांतरण या स्वचालित पाइपलाइन के लिए आपके लॉग को व्यवस्थित कैसे रखा जाए। Aspose.TeX **30+ input and output formats** को सपोर्ट करता है और **500 pages** तक के दस्तावेज़ों को पूरी फ़ाइल को मेमोरी में लोड किए बिना प्रोसेस कर सकता है, जिससे यह उच्च‑वॉल्यूम परिदृश्यों के लिए आदर्श बनता है।

## त्वरित उत्तर

`options.setJobName(String name)` एक कस्टम जॉब पहचानकर्ता सेट करता है जिसका उपयोग उत्पन्न लॉग और आउटपुट फ़ाइलों के लिए किया जाएगा।

- **क्या मैं जॉब नाम बदल सकता हूँ?** हाँ – `options.setJobName("my‑job")` को `TeXJob` बनाने से पहले कॉल करें।  
- **टर्मिनल आउटपुट कहाँ जाता है?** यह आपके द्वारा निर्दिष्ट आउटपुट वर्किंग डायरेक्टरी में `<job_name>.trm` के रूप में सहेजा जाता है।  
- **क्या इस फीचर के लिए लाइसेंस चाहिए?** यह कार्यक्षमता किसी भी वैध Aspose.TeX लाइसेंस के साथ काम करती है; एक मुफ्त ट्रायल भी उपलब्ध है।  
- **आउटपुट फ़ाइल का फ़ॉर्मेट क्या है?** एक प्लेन‑टेक्स्ट टर्मिनल लॉग जो कंसोल पर प्रिंट की गई सभी चीज़ों को प्रतिबिंबित करता है।  
- **क्या यह अन्य आउटपुट डिवाइसों के साथ संगत है?** बिल्कुल – एक बार लॉग लिख दिया जाए तो आप इसे किसी भी टेक्स्ट‑प्रोसेसिंग टूल में फीड कर सकते हैं।

## Aspose.TeX के संदर्भ में **how to capture console** क्या है?

कंसोल आउटपुट को कैप्चर करना मतलब है कि सभी चीज़ें जो सामान्यतः स्टैंडर्ड आउटपुट स्ट्रीम (टर्मिनल) पर दिखाई देती हैं, उन्हें डिस्क पर एक फ़ाइल में रीडायरेक्ट करना। Aspose.TeX के साथ आप इसे आसानी से `OutputFileTerminal` को कॉन्फ़िगर करके और इसे कन्वर्ज़न विकल्पों में असाइन करके कर सकते हैं।

## जॉब नाम को ओवरराइड क्यों करें?

जॉब नाम को ओवरराइड करने से प्रत्येक कन्वर्ज़न रन को एक अनूठा पहचानकर्ता मिलता है। इससे उत्पन्न लॉग फ़ाइलें (`*.trm`) और अन्य आर्टिफैक्ट्स को ट्रैक करना आसान हो जाता है, विशेष रूप से जब आप समानांतर में कई जॉब चलाते हैं या बैच प्रोसेस शेड्यूल करते हैं। एक विशिष्ट नाम प्रदान करके आप पिछले लॉग को ओवरराइट होने से बचते हैं और उन पोस्ट‑प्रोसेसिंग स्क्रिप्ट्स को सरल बनाते हैं जो पूर्वानुमेय फ़ाइलनामों पर निर्भर करती हैं।

## पूर्वापेक्षाएँ

- Java प्रोग्रामिंग में बुनियादी दक्षता।  
- Aspose.TeX for Java स्थापित है (आधिकारिक [Aspose.TeX Java documentation](https://reference.aspose.com/tex/java/) से डाउनलोड करें)।  
- एक Java IDE या बिल्ड टूल (Maven/Gradle) तैयार है सैंपल को कंपाइल और रन करने के लिए।

## पैकेज इम्पोर्ट करें

शुरू करने के लिए, आवश्यक पैकेजों को अपने Java प्रोजेक्ट में इम्पोर्ट करें। अपने Java फ़ाइल में, निम्नलिखित इम्पोर्ट्स शामिल करें:

```java
package com.aspose.tex.OverridenJobNameAndTerminalOutputWrittenToDisk;

import java.io.IOException;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

> **Pro tip:** `util.Utils` इम्पोर्ट केवल तभी रखें जब आपको Aspose सैंपल यूटिलिटीज़ के हेल्पर मेथड्स की आवश्यकता हो; अन्यथा आप इसे हटा सकते हैं ताकि कोड साफ़ रहे।

## जावा में कंसोल आउटपुट को कैसे कैप्चर करें

नीचे एक चरण‑दर‑चरण गाइड दिया गया है जो दिखाता है कि कन्वर्ज़न विकल्पों को कैसे कॉन्फ़िगर किया जाए, जॉब नाम को ओवरराइड किया जाए, और टर्मिनल आउटपुट को डिस्क पर फ़ाइल में कैसे निर्देशित किया जाए। निम्नलिखित चरण आवश्यक API कॉल्स को दर्शाते हैं और यह प्रदर्शित करते हैं कि पर्यावरण को कैसे सेट किया जाए ताकि सभी कंसोल संदेशों को कोर Aspose.TeX कोड को संशोधित किए बिना कैप्चर किया जा सके।

### चरण 1: कन्वर्ज़न विकल्प बनाएं

`TeXOptions` वह कॉन्फ़िगरेशन ऑब्जेक्ट है जो नियंत्रित करता है कि Aspose.TeX एक TeX जॉब को कैसे प्रोसेस करता है। यह आउटपुट फ़ॉर्मेट, फ़ॉन्ट हैंडलिंग, और टर्मिनल रीडायरेक्शन जैसी सेटिंग्स रखता है।

```java
// ExStart:OverrideJobName-WriteTerminalOutputToFileSystem
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
// ExEnd:OverrideJobName-WriteTerminalOutputToFileSystem
```

### चरण 2: जॉब नाम और वर्किंग डायरेक्टरी निर्दिष्ट करें

`TeXJob` एकल कन्वर्ज़न टास्क को दर्शाता है, जो इनपुट, आउटपुट और विकल्पों को आपस में जोड़ता है। कस्टम जॉब नाम सेट करने से उत्पन्न लॉग फ़ाइल का नाम अनूठा रहता है।

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

> **जॉब नाम को ओवरराइड क्यों करें?**  
> जॉब नाम को ओवरराइड करने से लॉग फ़ाइलें और उत्पन्न आर्टिफैक्ट्स को पहचानना आसान हो जाता है, विशेष रूप से जब आप समानांतर में कई जॉब चलाते हैं या बैच प्रोसेसिंग को स्वचालित करते हैं।

### चरण 3: टर्मिनल आउटपुट को फ़ाइल सिस्टम में लिखें

`setTerminalOut` Aspose.TeX को बताता है कि कंसोल लॉग फ़ाइल कहाँ लिखी जाए। फ़ाइल का नाम `<job_name>.trm` होगा और इसे ऊपर परिभाषित आउटपुट वर्किंग डायरेक्टरी में रखा जाएगा।

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### चरण 4: जॉब चलाएँ

`run()` प्रदान किए गए विकल्पों के आधार पर कन्वर्ज़न को निष्पादित करता है और आउटपुट फ़ाइलें (जिसमें `.trm` लॉग भी शामिल है) निर्दिष्ट फ़ोल्डर में लिखता है।

इच्छित इनपुट फ़ाइल (यहाँ हम एक सरल “hello‑world” उदाहरण का उपयोग करते हैं) और XPS रेंडरिंग डिवाइस के साथ एक `TeXJob` बनाएं, फिर `run()` को कॉल करें:

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
```

जब जॉब समाप्त हो जाएगा, तो आप **Your Output Directory** के अंदर `overridden-job-name.trm` नामक फ़ाइल पाएँगे जिसमें पूरा टर्मिनल लॉग होगा।

## सामान्य समस्याएँ और समस्या निवारण

| समस्या | कारण | समाधान |
|-------|-------|-----|
| **`.trm` फ़ाइल नहीं बनी** | `setTerminalOut` नहीं बुलाया गया या आउटपुट डायरेक्टरी गायब है | जाँचें कि आउटपुट डायरेक्टरी मौजूद है और `options.setTerminalOut(...)` `job.run()` से पहले निष्पादित हो रहा है। |
| **फ़ाइल नाम ओवरराइडेड नाम नहीं है** | जॉब नाम सही ढंग से सेट नहीं है | सुनिश्चित करें कि `options.setJobName("your‑desired‑name")` `TeXJob` बनाने से **पहले** कॉल किया गया है। |
| **खाली लॉग फ़ाइल** | लॉगिंग शुरू होने से पहले अपवाद फेंके गए | `job.run()` को try‑catch ब्लॉक में रखें और गायब फ़ॉन्ट्स या खराब TeX स्रोत के लिए अपवाद स्टैक ट्रेस देखें। |

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं Aspose.TeX for Java को अन्य Java लाइब्रेरीज़ के साथ उपयोग कर सकता हूँ?**  
A: हाँ, Aspose.TeX अन्य Java लाइब्रेरीज़ के साथ सहजता से एकीकृत होता है, जिससे आप एक ही वर्कफ़्लो में PDF, इमेज, या डेटाबेस यूटिलिटीज़ को संयोजित कर सकते हैं।

**Q: Aspose.TeX for Java के लिए समर्थन कहाँ मिल सकता है?**  
A: समुदाय सहायता के लिए [Aspose.TeX forum](https://forum.aspose.com/c/tex/47) पर जाएँ, या Aspose सपोर्ट पोर्टल के माध्यम से एक सपोर्ट टिकट खोलें।

**Q: क्या Aspose.TeX for Java के लिए मुफ्त ट्रायल उपलब्ध है?**  
A: बिल्कुल। आप पूरी तरह कार्यात्मक ट्रायल को [Aspose.TeX free trial page](https://releases.aspose.com/) से डाउनलोड कर सकते हैं।

**Q: परीक्षण के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?**  
A: 30‑दिन के मूल्यांकन लाइसेंस के लिए [Aspose temporary license](https://purchase.aspose.com/temporary-license/) पर अस्थायी‑लाइसेंस अनुरोध फ़ॉर्म का उपयोग करें।

**Q: स्थायी लाइसेंस कहाँ खरीद सकता हूँ?**  
A: सीधे [Aspose.TeX buying page](https://purchase.aspose.com/buy) से लाइसेंस खरीदें।

---

**अंतिम अपडेट:** 2026-08-18  
**परीक्षित संस्करण:** Aspose.TeX 24.11 for Java  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [जावा में TeX को PDF में बदलें, जॉब नाम ओवरराइड करें और टर्मिनल आउटपुट को ZIP में लिखें](/tex/java/customizing-output/override-job-name-zip/)
- [Aspose.TeX Java में इनपुट और आउटपुट के लिए ZIP आर्काइव्स का उपयोग कैसे करें](/tex/java/zip-archives/zip-archives-input-output/)
- [जावा में स्ट्रीम इनपुट और टर्मिनल हैंडलिंग के साथ TeX को PNG में कैसे बदलें](/tex/java/advanced-io/stream-input-image-output/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}