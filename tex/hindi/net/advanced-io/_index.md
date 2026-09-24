---
date: 2026-09-24
description: Aspose.TeX for .NET को C# में उपयोग करके TeX इनपुट डायरेक्टरी, स्ट्रीम,
  इमेजेज, और टर्मिनल इनपुट को कैसे कॉन्फ़िगर करें, सीखें।
keywords:
- configure tex input directory
- add image stream tex
- add images from stream
lastmod: 2026-09-24
linktitle: उन्नत Aspose.TeX इनपुट और आउटपुट
og_description: Aspose.TeX for .NET को C# में उपयोग करके TeX इनपुट डायरेक्टरी कॉन्फ़िगर
  करें, इमेज स्ट्रीम जोड़ें, और टर्मिनल इनपुट को संभालें। चरण‑दर‑चरण सीखें।
og_image_alt: Guide showing how to configure TeX input directory and streams in Aspose.TeX
  for .NET
og_title: TeX इनपुट डायरेक्टरी कॉन्फ़िगर करें – उन्नत Aspose.TeX गाइड
schemas:
- author: Aspose
  dateModified: '2026-09-24'
  description: Learn how to configure TeX input directory, streams, images, and terminal
    input using Aspose.TeX for .NET in C#.
  headline: Configure TeX input directory – Advanced Aspose.TeX Input and Output
  type: TechArticle
- description: Learn how to configure TeX input directory, streams, images, and terminal
    input using Aspose.TeX for .NET in C#.
  name: Configure TeX input directory – Advanced Aspose.TeX Input and Output
  steps:
  - name: instantiate TeXInputOptions
    text: Assign the base folder that holds the primary TeX source.
  - name: add extra search paths
    text: If your project stores figures in a separate folder (e.g., *Images*), call
      `AddSearchPath` to include it.
  - name: hand the options to the processor
    text: Create a `TeXProcessor`, provide the configured options, and invoke `Process`
      or `Render`.
  type: HowTo
- questions:
  - answer: Yes—you can create a new `TeXInputOptions` instance with a different `BaseFolder`
      and pass it to a fresh `TeXProcessor` whenever you need to reconfigure.
    question: Can I change the input directory at runtime?
  - answer: Retrieve the image as a `byte[]`, wrap it in a `MemoryStream`, and call
      `TeXInputOptions.AddImage("image.png", stream)`. The name must match the reference
      in your `.tex` file.
    question: How do I add images that are stored in a database?
  - answer: Absolutely. Convert the incoming string to a `MemoryStream`, set it as
      the source for `TeXProcessor`, and render directly to your desired output format.
    question: Is it possible to process LaTeX code received from a web API without
      saving a file?
  - answer: Dispose of any streams you create, and for large workloads invoke `TeXProcessor.Cleanup()`
      to free native resources.
    question: Do I need to call any cleanup methods after processing?
  - answer: The two tutorial links above contain full code samples that demonstrate
      each scenario in detail, including error handling and performance tips.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.TeX .NET API
tags:
- Aspose.TeX
- input directory
- C# document processing
title: TeX इनपुट डायरेक्टरी कॉन्फ़िगर करें – उन्नत Aspose.TeX इनपुट और आउटपुट
url: /hi/net/advanced-io/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.TeX for .NET में TeX इनपुट डायरेक्टरी कॉन्फ़िगर करें

Aspose.TeX for .NET आपको अपने C# एप्लिकेशन में सीधे पूर्ण‑विशेषताओं वाला TeX प्रोसेसिंग एम्बेड करने देता है। इस ट्यूटोरियल में आप सीखेंगे कि **TeX इनपुट डायरेक्टरी कॉन्फ़िगर करें**, स्ट्रीम से LaTeX कंटेंट कैसे फीड करें, और फ़ाइल सिस्टम को छुए बिना इमेजेज़ कैसे जोड़ें। यदि आपको यह सटीक नियंत्रण चाहिए कि इंजन `.tex` फ़ाइलों और रिसोर्सेज़ को कहाँ देखे, तो आप सही जगह पर हैं।

## त्वरित उत्तर
- **“configure tex input directory” क्या मतलब है?**  
  यह Aspose.TeX को बताता है कि मुख्य `.tex` फ़ाइल, सहायक फ़ाइलें, और ग्राफ़िक्स कहाँ मिलें।
- **इनपुट पाथ्स को परिभाषित करने वाला क्लास कौन सा है?**  
  `TeXInputOptions` बेस फ़ोल्डर और अतिरिक्त सर्च लोकेशन को स्टोर करता है।
- **क्या मैं मेमोरी स्ट्रीम से इमेज लोड कर सकता हूँ?**  
  हाँ—`TeXInputOptions.AddImage` को `Stream` इंस्टेंस के साथ उपयोग करें।
- **क्या रनटाइम पर प्रदान किए गए LaTeX कोड को कंपाइल करना संभव है?**  
  बिल्कुल—सोर्स टेक्स्ट वाले `MemoryStream` को प्रोसेसर को पास करें।
- **क्या प्रोडक्शन उपयोग के लिए लाइसेंस चाहिए?**  
  गैर‑इवैल्यूएशन डिप्लॉयमेंट्स के लिए एक वैध Aspose.TeX लाइसेंस आवश्यक है।

## TeXInputOptions क्या है?
`TeXInputOptions` वह कॉन्फ़िगरेशन ऑब्जेक्ट है जो TeX रिसोर्सेज़ के लिए बेस फ़ोल्डर और अतिरिक्त सर्च पाथ्स को परिभाषित करता है। इसे सही ढंग से सेट करने से “file not found” त्रुटियों से बचा जा सकता है और एसेट्स को व्यवस्थित रखा जा सकता है।

## tex इनपुट डायरेक्टरी कैसे कॉन्फ़िगर करें?
`TeXInputOptions` एक कॉन्फ़िगरेशन ऑब्जेक्ट है जो TeX रिसोर्सेज़ के लिए बेस फ़ोल्डर और अतिरिक्त सर्च पाथ्स निर्दिष्ट करता है। अपना मुख्य दस्तावेज़ लोड करें और प्रोसेसर को कुछ ही लाइनों में बताएं कि सब कुछ कहाँ देखना है। यह सीधा उत्तर अतिरिक्त विवरण से पहले आवश्यक कदमों को समझाता है।

एक `TeXInputOptions` इंस्टेंस बनाएं, `BaseFolder` को उस फ़ोल्डर पर सेट करें जिसमें आपकी प्राथमिक `.tex` फ़ाइल है, इमेजेज़ या सहायक फ़ाइलों वाले किसी भी सब‑फ़ोल्डर को जोड़ें, और विकल्पों को `TeXProcessor` को पास करें। फिर इंजन सभी रिलेटिव रेफ़रेंसेज़ को स्वचालित रूप से हल कर देगा।

### चरण 1: TeXInputOptions को इंस्टैंशिएट करें
प्राथमिक TeX स्रोत को रखने वाले बेस फ़ोल्डर को असाइन करें।

### चरण 2: अतिरिक्त सर्च पाथ्स जोड़ें
यदि आपका प्रोजेक्ट फ़िगर्स को अलग फ़ोल्डर (जैसे, *Images*) में स्टोर करता है, तो इसे शामिल करने के लिए `AddSearchPath` को कॉल करें।

### चरण 3: विकल्पों को प्रोसेसर को दें
एक `TeXProcessor` बनाएं, कॉन्फ़िगर किए गए विकल्प प्रदान करें, और `Process` या `Render` को इनवोक करें।

## Aspose.TeX के साथ इमेजेज़ कैसे जोड़ें
TeX फ़ाइल में रेफ़रेंस की गई इमेजेज़ को फ़ोल्डर के माध्यम से या सीधे स्ट्रीम से सप्लाई किया जा सकता है। स्ट्रीम सप्लाई करना तब उपयोगी होता है जब इमेजेज़ डेटाबेस में स्टोर हों या ऑन‑द‑फ्लाई जेनरेट हों। `AddImage(string name, Stream data)` दिए गए फ़ाइलनाम के साथ इमेज स्ट्रीम को TeX दस्तावेज़ में उपयोग के लिए रजिस्टर करता है। यह मेथड आपको टेम्पररी फ़ाइलों से बचाता है और प्रोसेसिंग को तेज़ बनाता है।

## Aspose.TeX में स्ट्रीम्स को कैसे प्रोसेस करें
जब आपका LaTeX स्रोत डायनामिक रूप से जेनरेट होता है—शायद यूज़र इनपुट या वेब सर्विस से—तो आप इसे फ़ाइल लिखे बिना सीधे प्रोसेसर को फीड कर सकते हैं। `TeXProcessor` TeX कंटेंट को प्रोसेस करता है और स्रोत LaTeX कोड वाले `MemoryStream` को स्वीकार कर सकता है। LaTeX स्ट्रिंग को `MemoryStream` में रैप करें, इसे `TeXProcessor` में स्रोत स्ट्रीम के रूप में सेट करें, और कन्वर्ज़न चलाएँ। यह तकनीक क्लाउड‑नेटीव सर्विसेज़ के लिए भी समान रूप से काम करती है जहाँ डिस्क I/O महँगा होता है।

## उन्नत I/O के लिए Aspose.TeX क्यों उपयोग करें?
Aspose.TeX **30+ इनपुट और आउटपुट फॉर्मैट्स** (PDF, PNG, SVG सहित) को सपोर्ट करता है और पूरी फ़ाइल को मेमोरी में लोड किए बिना कई‑सौ पेज़ दस्तावेज़ रेंडर कर सकता है। इसका स्ट्रीम‑फ़र्स्ट डिज़ाइन फ़ाइल‑आधारित वर्कफ़्लोज़ की तुलना में I/O ओवरहेड को 40 % तक कम करता है, जिससे यह हाई‑थ्रूपुट सर्वर एप्लिकेशन्स के लिए आदर्श बनता है।

## पूर्वापेक्षाएँ
- .NET 6.0 या बाद का (लाइब्रेरी .NET Core 3.1+ और .NET Framework 4.6.1+ के साथ भी काम करती है)
- Aspose.TeX for .NET NuGet पैकेज (वर्ज़न 24.11 या नया)
- प्रोडक्शन उपयोग के लिए एक वैध Aspose.TeX लाइसेंस

## Aspose.TeX का अन्वेषण: उन्नत दस्तावेज़ प्रोसेसिंग का गेटवे
कॉन्फ़िगरेशन को कार्रवाई में देखने के लिए, हमारे चरण‑दर‑चरण गाइड **[Aspose.TeX (C#) के लिए आवश्यक इनपुट डायरेक्टरी निर्दिष्ट करें](./required-input-directory-csharp/)** का पालन करें। वह ट्यूटोरियल आपको `TeXInputOptions` ऑब्जेक्ट बनाने और PDF आउटपुट रेंडर करने के माध्यम से ले जाता है।  
**[Aspose.TeX (C#) के लिए आवश्यक इनपुट डायरेक्टरी निर्दिष्ट करें](./required-input-directory-csharp/)**

## Aspose.TeX for C# में स्ट्रीम्स, इमेजेज़, और टर्मिनल इनपुट में महारत
मेमोरी से LaTeX फीड करने, स्ट्रीम्स के माध्यम से इमेजेज़ जोड़ने, और टर्मिनल‑स्टाइल इनपुट उपयोग करने के बारे में गहराई से जानने के लिए, **[Aspose.TeX for C# में स्ट्रीम्स, इमेजेज़, और टर्मिनल इनपुट में महारत](./stream-input-image-output-terminal-input-csharp/)** देखें। यह दिखाता है कि Aspose.TeX को वेब APIs, बैकग्राउंड सर्विसेज़, और कंसोल टूल्स में कैसे इंटीग्रेट किया जाए।  
**[Aspose.TeX for C# में स्ट्रीम्स, इमेजेज़, और टर्मिनल इनपुट में महारत](./stream-input-image-output-terminal-input-csharp/)**

## सामान्य समस्याएँ और समाधान
- **“File not found” त्रुटियाँ** – सुनिश्चित करें कि `BaseFolder` सही डायरेक्टरी की ओर इशारा कर रहा है और रेंडरिंग से पहले सभी अतिरिक्त सर्च पाथ्स जोड़े गए हैं।
- **इमेजेज़ लोड नहीं हो रही हैं** – सुनिश्चित करें कि `AddImage` में इमेज का नाम TeX स्रोत में उपयोग किए गए नाम से बिल्कुल मेल खाता है, फ़ाइल एक्सटेंशन सहित।
- **मेमोरी उपयोग में स्पाइक** – बहुत बड़े दस्तावेज़ प्रोसेस करते समय, रेंडरिंग के बाद `TeXProcessor.Cleanup()` को कॉल करके अनमैनेज्ड रिसोर्सेज़ को रिलीज़ करें।

## अक्सर पूछे जाने वाले प्रश्न

**प्र: क्या मैं रनटाइम पर इनपुट डायरेक्टरी बदल सकता हूँ?**  
A: हाँ—आप एक नया `TeXInputOptions` इंस्टेंस अलग `BaseFolder` के साथ बना सकते हैं और जब भी री‑कन्फ़िगर करने की जरूरत हो, इसे एक नए `TeXProcessor` को पास कर सकते हैं।

**प्र: डेटाबेस में स्टोर की गई इमेजेज़ को कैसे जोड़ूँ?**  
A: इमेज को `byte[]` के रूप में प्राप्त करें, इसे `MemoryStream` में रैप करें, और `TeXInputOptions.AddImage("image.png", stream)` को कॉल करें। नाम आपके `.tex` फ़ाइल में रेफ़रेंस से मेल खाना चाहिए।

**प्र: क्या वेब API से प्राप्त LaTeX कोड को फ़ाइल सेव किए बिना प्रोसेस करना संभव है?**  
A: बिल्कुल। इनकमिंग स्ट्रिंग को `MemoryStream` में बदलें, इसे `TeXProcessor` के स्रोत के रूप में सेट करें, और सीधे अपनी इच्छित आउटपुट फॉर्मैट में रेंडर करें।

**प्र: प्रोसेसिंग के बाद क्या मुझे कोई क्लीनअप मेथड कॉल करना चाहिए?**  
A: आप द्वारा बनाए गए सभी स्ट्रीम्स को डिस्पोज़ करें, और बड़े वर्कलोड्स के लिए `TeXProcessor.Cleanup()` को इनवोक करके नेटीव रिसोर्सेज़ को फ्री करें।

**प्र: अधिक उन्नत उदाहरण कहाँ मिल सकते हैं?**  
A: ऊपर दिए गए दो ट्यूटोरियल लिंक में पूर्ण कोड सैंपल्स हैं जो प्रत्येक परिदृश्य को विस्तार से दिखाते हैं, जिसमें एरर हैंडलिंग और परफ़ॉर्मेंस टिप्स शामिल हैं।

---

**अंतिम अपडेट:** 2026-09-24  
**परीक्षित संस्करण:** Aspose.TeX 24.11 for .NET  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Aspose.TeX API का उपयोग करके TeX फ़ाइल स्ट्रीम प्राप्त करें (C#) – आवश्यक इनपुट डायरेक्टरी](/tex/net/advanced-io/required-input-directory-csharp/)
- [फ़ाइल सिस्टम के साथ TeX से XPS बनाएं – Aspose.TeX for .NET](/tex/net/file-input-output/filesystem-input-xps-output/)
- [Aspose.TeX for .NET का उपयोग करके LaTeX को PNG में कन्वर्ट करें – फ़ाइल सिस्टम और ZIP इनपुट प्रोसेस करें](/tex/net/file-input-output/required-inputs-from-filesystem-and-zip/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}