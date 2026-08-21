---
date: 2026-07-05
description: जानिए कैसे TeX को PNG में बदलें, Java में console input को हैंडल करें,
  और Aspose.TeX का उपयोग करके TeX को PNG के रूप में सहेजें। Java डेवलपर्स के लिए पूर्ण
  चरण‑दर‑चरण गाइड।
keywords:
- convert tex to png
- high resolution png tex
- save tex as png
- handle console input java
- java stream input tex
linktitle: Java में Stream Input & Terminal के साथ TeX को PNG में बदलें
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to convert TeX to PNG, handle console input Java, and save
    TeX as PNG using Aspose.TeX. Complete step‑by‑step guide for Java developers.
  headline: Convert TeX to PNG with Stream Input and Terminal Handling in Java
  type: TechArticle
- description: Learn how to convert TeX to PNG, handle console input Java, and save
    TeX as PNG using Aspose.TeX. Complete step‑by‑step guide for Java developers.
  name: Convert TeX to PNG with Stream Input and Terminal Handling in Java
  steps:
  - name: Set Up Conversion Options
    text: The `TeXOptions` class defines how Aspose.TeX processes the document. **Definition:**
      `TeXOptions` is the central configuration object that controls engine selection,
      terminal handling, and output paths. Create an instance, enable console mode,
      and point the engine to the ObjectTeX implementation.
  - name: Specify Input and Output Terminals
    text: Binding the console to both input and output terminals enables interactive
      prompts. **Definition:** `InputConsoleTerminal` represents a standard input
      stream that reads user keystrokes from the console. Attach it to the options
      so the TeX job can request data during execution.
  - name: Define Saving Options (Save TeX as PNG)
    text: Configure PNG‑specific settings such as DPI and color depth. **Definition:**
      `PngSaveOptions` encapsulates all raster‑output parameters for PNG files. Setting
      `setResolution(300)` yields a crisp **high resolution PNG tex** image suitable
      for print‑quality graphics.
  - name: Create an Image Device
    text: The `ImageDevice` collects rendered pages as byte arrays. **Definition:**
      `ImageDevice` is an Aspose.TeX output sink that stores each page’s raster data
      in memory. Instantiate it and associate it with the job to capture the PNG payload.
  - name: Run the TeX Job
    text: Feed the TeX markup via a `ByteArrayInputStream`. The sample source draws
      two horizontal rules and a vertical skip, but you can replace it with any valid
      TeX code. **Definition:** `TeXJob` orchestrates the entire compilation pipeline
      from source parsing to device rendering. Execute the job and let A
  - name: Handle Terminal Input
    text: When the console prompts, type `ABC`, press **Enter**, then type `\end`
      and press **Enter** again. This demonstrates interactive input handling and
      shows how the `InputConsoleTerminal` captures user responses.
  - name: Retrieve the PNG Image
    text: After the job finishes, the rendered PNG data is available as an array of
      byte arrays. You can write these bytes to files, stream them over a network,
      or embed them directly in a UI component. This eliminates the need for temporary
      disk storage and speeds up end‑to‑end processing.
  type: HowTo
- questions:
  - answer: Yes. Loop over your TeX strings, create a new `TeXJob` for each, and collect
      the resulting `byte[][]` arrays.
    question: Can I convert multiple TeX snippets in a single run?
  - answer: Absolutely. Replace `PngSaveOptions` with `PdfSaveOptions` and adjust
      the device accordingly.
    question: Is it possible to output PDF instead of PNG?
  - answer: Yes. Provide UTF‑8 encoded byte streams or set the appropriate charset
      on the input stream.
    question: Does Aspose.TeX support Unicode characters?
  - answer: You can get a temporary license from [here](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for Aspose.TeX?
  - answer: Explore the comprehensive [documentation](https://reference.aspose.com/tex/java/)
      for deeper insights and advanced scenarios.
    question: Where can I find more detailed API documentation?
  type: FAQPage
second_title: Aspose.TeX Java API
title: Java में Stream Input और Terminal Handling के साथ TeX को PNG में बदलें
url: /hi/java/advanced-io/stream-input-image-output/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# स्ट्रिम इनपुट और टर्मिनल हैंडलिंग के साथ जावा में TeX को PNG में परिवर्तित करें

## परिचय

यदि आपको कंसोल के साथ इंटरैक्ट करते हुए जावा स्ट्रिम से सीधे **TeX को PNG में बदलने** की आवश्यकता है, तो Aspose.TeX for Java इसे सरल बनाता है। इस ट्यूटोरियल में आप सीखेंगे कि कैसे TeX स्रोत को स्ट्रिम के रूप में फीड करें, **उच्च‑रिज़ॉल्यूशन PNG** इमेज जनरेट करें, और **कंसोल इनपुट जावा‑स्टाइल** को संभालें—बिना किसी मध्यवर्ती फ़ाइल को लिखे। अंत में आप केवल कुछ लाइनों के कोड से **TeX को PNG के रूप में सहेज** सकेंगे।

## त्वरित उत्तर
- **इस ट्यूटोरियल में क्या कवर किया गया है?** स्ट्रिम इनपुट का उपयोग करके TeX को PNG में बदलना, उच्च‑रिज़ॉल्यूशन इमेज आउटपुट को कॉन्फ़िगर करना, और कंसोल इंटरैक्शन को संभालना।  
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.TeX for Java (download [यहाँ](https://releases.aspose.com/tex/java/)).  
- **क्या मुझे लाइसेंस चाहिए?** प्रोडक्शन उपयोग के लिए एक अस्थायी या पूर्ण लाइसेंस आवश्यक है।  
- **कौन सा इमेज फ़ॉर्मेट उत्पन्न होता है?** PNG, जिसे रिज़ॉल्यूशन (जैसे 300 DPI) के साथ कॉन्फ़िगर किया जा सकता है।  
- **क्या मैं आउटपुट फ़ॉर्मेट बदल सकता हूँ?** हाँ – Aspose.TeX विभिन्न `SaveOptions` के माध्यम से अन्य फ़ॉर्मेट्स को सपोर्ट करता है।  

## convert tex to png क्या है?
**convert tex to png** वह प्रक्रिया है जिसमें TeX मार्कअप को रास्टर PNG इमेज में रेंडर किया जाता है। Aspose.TeX TeX स्रोत को पार्स करता है, ObjectTeX इंजन चलाता है, और एक पिक्सेल‑परफेक्ट PNG आउटपुट करता है जो गणितीय प्रतीकों और लेआउट को संरक्षित रखता है। यह रूपांतरण वेब पेजों में समीकरण एम्बेड करने, दस्तावेज़ ग्राफ़िक्स जनरेट करने, या पूर्ण PDF वर्कफ़्लो की आवश्यकता के बिना प्रिंटेबल एसेट्स बनाने के लिए उपयोगी है।

## इस कार्य के लिए Aspose.TeX क्यों उपयोग करें?
Aspose.TeX **50+ इनपुट और आउटपुट फ़ॉर्मेट्स** को सपोर्ट करता है, जिसमें PDF, JPEG, BMP, और SVG शामिल हैं, और यह **500 पृष्ठों** तक के दस्तावेज़ों को पूरी फ़ाइल को मेमोरी में लोड किए बिना रेंडर कर सकता है। इसका इन‑मेमोरी पाइपलाइन अस्थायी फ़ाइलों को समाप्त करता है, जिससे यह माइक्रो‑सर्विसेज़, वेब API, और बैच प्रोसेसिंग के लिए आदर्श बनता है जहाँ गति और संसाधन दक्षता महत्वपूर्ण होती है।

## आवश्यकताएँ
- Java Development Kit (JDK) 8 या उससे ऊपर स्थापित हो।  
- जावा और Aspose.TeX लाइब्रेरी की बुनियादी समझ।  
- Aspose.TeX for Java बाइनरी को अपने क्लासपाथ पर रखें (download [यहाँ](https://releases.aspose.com/tex/java/)).  

## जावा स्ट्रिम का उपयोग करके TeX को PNG में कैसे बदलें?
`ByteArrayInputStream` एक जावा क्लास है जो बाइट एरे को इनपुट स्ट्रिम के रूप में उपयोग करने की अनुमति देता है। `ByteArrayInputStream` से TeX स्रोत लोड करें, रूपांतरण विकल्प कॉन्फ़िगर करें, और रेंडरिंग जॉब को इनवोक करें – सब कुछ मेमोरी में। यह दो‑स्टेप पैटर्न (सेटअप + एक्ज़ीक्यूट) **java stream input tex** परिदृश्यों के लिए मानक दृष्टिकोण है और सुनिश्चित करता है कि डिस्क पर कोई मध्यवर्ती फ़ाइल नहीं लिखी जाए, जिससे प्रदर्शन और सुरक्षा में सुधार होता है।

### चरण 1: रूपांतरण विकल्प सेट करें  
`TeXOptions` क्लास यह निर्धारित करती है कि Aspose.TeX दस्तावेज़ को कैसे प्रोसेस करता है।  
**परिभाषा:** `TeXOptions` वह केंद्रीय कॉन्फ़िगरेशन ऑब्जेक्ट है जो इंजन चयन, टर्मिनल हैंडलिंग, और आउटपुट पाथ्स को नियंत्रित करता है।  

```java
package com.aspose.tex.StreamInputImageOutputAndTerminalInput;

import java.io.ByteArrayInputStream;
import java.io.IOException;

import com.aspose.tex.InputConsoleTerminal;
import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputConsoleTerminal;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.ImageDevice;
import com.aspose.tex.rendering.PngSaveOptions;
```

### चरण 2: इनपुट और आउटपुट टर्मिनल निर्दिष्ट करें  
कंसोल को इनपुट और आउटपुट दोनों टर्मिनल से बाइंड करने से इंटरैक्टिव प्रॉम्प्ट सक्षम होते हैं।  
**परिभाषा:** `InputConsoleTerminal` एक मानक इनपुट स्ट्रिम को दर्शाता है जो कंसोल से उपयोगकर्ता की कुंजी स्ट्रोक्स पढ़ता है।  

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("stream-in-image-out");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### चरण 3: सहेजने के विकल्प निर्धारित करें (TeX को PNG के रूप में सहेजें)  
DPI और कलर डेप्थ जैसे PNG‑विशिष्ट सेटिंग्स कॉन्फ़िगर करें।  
**परिभाषा:** `PngSaveOptions` PNG फ़ाइलों के सभी रास्टर‑आउटपुट पैरामीटर को समेटे हुए है।  

```java
options.setTerminalIn(new InputConsoleTerminal());
options.setTerminalOut(new OutputConsoleTerminal());
```

### चरण 4: एक इमेज डिवाइस बनाएं  
`ImageDevice` रेंडर किए गए पृष्ठों को बाइट एरे के रूप में एकत्र करता है।  
**परिभाषा:** `ImageDevice` Aspose.TeX का आउटपुट सिंक है जो प्रत्येक पृष्ठ के रास्टर डेटा को मेमोरी में संग्रहीत करता है।  

```java
PngSaveOptions pngOptions = new PngSaveOptions();
pngOptions.setResolution(300);
options.setSaveOptions(pngOptions);
```

### चरण 5: TeX जॉब चलाएँ  
`ByteArrayInputStream` के माध्यम से TeX मार्कअप फीड करें। नमूना स्रोत दो क्षैतिज रूल और एक वर्टिकल स्किप ड्रॉ करता है, लेकिन आप इसे किसी भी वैध TeX कोड से बदल सकते हैं।  
**परिभाषा:** `TeXJob` स्रोत पार्सिंग से डिवाइस रेंडरिंग तक पूरी कम्पाइलेशन पाइपलाइन को व्यवस्थित करता है।  

```java
ImageDevice device = new ImageDevice();
```

### चरण 6: टर्मिनल इनपुट संभालें  
जब कंसोल प्रॉम्प्ट करे, तो `ABC` टाइप करें, **Enter** दबाएँ, फिर `\end` टाइप करें और फिर से **Enter** दबाएँ। यह इंटरैक्टिव इनपुट हैंडलिंग को दर्शाता है और दिखाता है कि `InputConsoleTerminal` उपयोगकर्ता प्रतिक्रियाओं को कैसे कैप्चर करता है।  

```java
TeXJob job = new TeXJob(new ByteArrayInputStream(
        "\\hrule height 10pt width 95pt\\vskip10pt\\hrule height 5pt".getBytes("ASCII")),
        device, options);
job.run();
```

### चरण 7: PNG इमेज प्राप्त करें  
जॉब समाप्त होने के बाद, रेंडर किया गया PNG डेटा बाइट एरे की एरे के रूप में उपलब्ध होता है। आप इन बाइट्स को फ़ाइलों में लिख सकते हैं, नेटवर्क पर स्ट्रीम कर सकते हैं, या सीधे UI कंपोनेंट में एम्बेड कर सकते हैं। यह अस्थायी डिस्क स्टोरेज की आवश्यकता को समाप्त करता है और एंड‑टू‑एंड प्रोसेसिंग को तेज़ बनाता है।  

```java
// For further output to look fine.
options.getTerminalOut().getWriter().newLine();
```

## सामान्य समस्याएँ और ट्रबलशूटिंग

| लक्षण | संभावित कारण | समाधान |
|---------|--------------|-----|
| **कोई इमेज उत्पन्न नहीं हुई** | आउटपुट डायरेक्टरी लिखने योग्य नहीं है या `saveOptions` सेट नहीं है | `options.setSaveOptions(pngOptions)` कॉल किया गया है यह सुनिश्चित करके आउटपुट पाथ की जाँच करें। |
| **कंसोल इनपुट की प्रतीक्षा में फँस जाता है** | टर्मिनल अटैच नहीं है या `InputConsoleTerminal` गायब है | सुनिश्चित करें कि `options.setTerminalIn(new InputConsoleTerminal())` मौजूद है। |
| **कम‑रिज़ॉल्यूशन PNG** | डिफ़ॉल्ट DPI (72) उपयोग किया गया | `pngOptions.setResolution(300)` या उससे अधिक सेट करें। |
| **असमर्थित TeX कमांड्स** | ObjectTeX के साथ बंडल नहीं किए गए पैकेजों का उपयोग करना | यदि आवश्यक हो तो पूर्ण TeX इंजन (`TeXConfig.fullTeX()`) पर स्विच करें। |

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं एक ही रन में कई TeX स्निपेट्स को बदल सकता हूँ?**  
**उत्तर:** हाँ। अपने TeX स्ट्रिंग्स पर लूप चलाएँ, प्रत्येक के लिए नया `TeXJob` बनाएँ, और परिणामी `byte[][]` एरे एकत्र करें।

**प्रश्न: क्या PNG के बजाय PDF आउटपुट करना संभव है?**  
**उत्तर:** बिल्कुल। `PngSaveOptions` को `PdfSaveOptions` से बदलें और डिवाइस को उसी अनुसार समायोजित करें।

**प्रश्न: क्या Aspose.TeX यूनिकोड कैरेक्टर्स को सपोर्ट करता है?**  
**उत्तर:** हाँ। UTF‑8 एन्कोडेड बाइट स्ट्रिम प्रदान करें या इनपुट स्ट्रिम पर उपयुक्त charset सेट करें।

**प्रश्न: Aspose.TeX के लिए अस्थायी लाइसेंस कैसे प्राप्त करें?**  
**उत्तर:** आप [यहाँ](https://purchase.aspose.com/temporary-license/) से अस्थायी लाइसेंस प्राप्त कर सकते हैं।

**प्रश्न: अधिक विस्तृत API दस्तावेज़ कहाँ मिल सकता है?**  
**उत्तर:** गहरी जानकारी और उन्नत परिदृश्यों के लिए व्यापक [डॉक्यूमेंटेशन](https://reference.aspose.com/tex/java/) देखें।

## निष्कर्ष

अब आपके पास Aspose.TeX for Java का उपयोग करके **TeX को PNG में बदलने**, **जावा कंसोल इनपुट को संभालने**, और **TeX को PNG के रूप में सहेजने** का एक पूर्ण, एंड‑टू‑एंड उदाहरण है। इन स्निपेट्स को अपने एप्लिकेशन में एकीकृत करें ताकि दस्तावेज़ रेंडरिंग को स्वचालित किया जा सके, डायनेमिक इमेजेज़ जनरेट किए जा सकें, या इंटरैक्टिव TeX कंसोल बनाए जा सकें।

---

**अंतिम अपडेट:** 2026-07-05  
**परीक्षित संस्करण:** Aspose.TeX for Java 24.11  
**लेखक:** Aspose

{{< blocks/products/products-backtop-button >}}
```java
byte[][] result = device.getResult();
```

## संबंधित ट्यूटोरियल

- [जावा में Aspose.TeX लाइसेंस लोड करने का तरीका – चरण‑दर‑चरण गाइड](/tex/java/managing-licenses/)
- [जावा में TeX को PDF में बदलें, जॉब नाम ओवरराइड करें और टर्मिनल आउटपुट को ZIP में लिखें](/tex/java/customizing-output/override-job-name-zip/)
- [LaTeX को PNG में बदलें – जावा में फ़ाइल सिस्टम से LaTeX इनपुट फ़ाइलों को संभालें](/tex/java/working-with-lainputs/file-system-input/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}