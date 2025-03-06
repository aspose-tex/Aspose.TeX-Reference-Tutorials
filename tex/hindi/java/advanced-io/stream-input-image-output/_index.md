---
title: जावा में स्ट्रीम इनपुट, इमेज आउटपुट और टर्मिनल इनपुट
linktitle: जावा में स्ट्रीम इनपुट, इमेज आउटपुट और टर्मिनल इनपुट
second_title: Aspose.TeX जावा एपीआई
description: Aspose.TeX का उपयोग करके जावा में स्ट्रीम इनपुट, इमेज आउटपुट और टर्मिनल इनपुट सीखें। निर्बाध एकीकरण के लिए एक व्यापक ट्यूटोरियल।
weight: 11
url: /hi/java/advanced-io/stream-input-image-output/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा में स्ट्रीम इनपुट, इमेज आउटपुट और टर्मिनल इनपुट

## परिचय

जावा के लिए Aspose.TeX एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को TeX फ़ाइलों के साथ काम करने की अनुमति देती है, जिससे उच्च गुणवत्ता वाले दस्तावेज़ों के निर्माण और हेरफेर की सुविधा मिलती है। इस ट्यूटोरियल में, हम Aspose.TeX का उपयोग करके जावा में स्ट्रीम इनपुट लेने, इमेज आउटपुट जेनरेट करने और टर्मिनल इनपुट को संभालने की प्रक्रिया का पता लगाएंगे।

## आवश्यक शर्तें

ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:

- जावा प्रोग्रामिंग की बुनियादी समझ.
- आपकी मशीन पर जावा डेवलपमेंट किट (जेडीके) स्थापित है।
- Aspose.TeX लाइब्रेरी से परिचित।
-  जावा के लिए Aspose.TeX स्थापित किया गया। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tex/java/).

## पैकेज आयात करें

सुनिश्चित करें कि आपके पास इस ट्यूटोरियल के लिए आवश्यक पैकेज आयातित हैं। निम्नलिखित कोड स्निपेट आवश्यक आयात दर्शाता है:

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

## चरण 1: रूपांतरण विकल्प सेट करें

ऑब्जेक्टटेक्स इंजन एक्सटेंशन पर डिफ़ॉल्ट ऑब्जेक्टटेक्स प्रारूप के साथ टीएक्स रूपांतरण विकल्प बनाएं। कार्य का नाम, इनपुट कार्यशील निर्देशिका और आउटपुट कार्यशील निर्देशिका निर्दिष्ट करें।

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("stream-in-image-out");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

## चरण 2: इनपुट और आउटपुट टर्मिनल निर्दिष्ट करें

कंसोल को इनपुट और आउटपुट टर्मिनल दोनों के रूप में निर्दिष्ट करें।

```java
options.setTerminalIn(new InputConsoleTerminal());
options.setTerminalOut(new OutputConsoleTerminal());
```

## चरण 3: बचत विकल्पों को परिभाषित करें

आउटपुट छवि के लिए बचत विकल्प परिभाषित करें। इस उदाहरण में, हम 300 डीपीआई के रिज़ॉल्यूशन के साथ पीएनजी प्रारूप का उपयोग करते हैं।

```java
PngSaveOptions pngOptions = new PngSaveOptions();
pngOptions.setResolution(300);
options.setSaveOptions(pngOptions);
```

## चरण 4: इमेज डिवाइस बनाएं

आउटपुट छवि उत्पन्न करने के लिए एक छवि उपकरण बनाएं।

```java
ImageDevice device = new ImageDevice();
```

## चरण 5: कार्य चलाएँ

निर्दिष्ट इनपुट, डिवाइस और विकल्पों के साथ TeX कार्य चलाएँ।

```java
TeXJob job = new TeXJob(new ByteArrayInputStream(
        "\\hrule height 10pt width 95pt\\vskip10pt\\hrule height 5pt".getBytes("ASCII")),
        device, options);
job.run();
```

## चरण 6: टर्मिनल इनपुट संभालें

जब कंसोल इनपुट के लिए संकेत देता है, तो "एबीसी" टाइप करें, एंटर दबाएं, फिर "\end" टाइप करें और फिर से एंटर दबाएं।

```java
// आगे का आउटपुट ठीक दिखने के लिए।
options.getTerminalOut().getWriter().newLine();
```

## चरण 7: छवि आउटपुट पुनर्प्राप्त करें

आप बाइट सरणियों की एक श्रृंखला के रूप में छवियां प्राप्त कर सकते हैं।

```java
byte[][] result = device.getResult();
```

यह Aspose.TeX का उपयोग करके जावा में स्ट्रीम इनपुट, इमेज आउटपुट और टर्मिनल इनपुट के लिए चरण-दर-चरण मार्गदर्शिका को पूरा करता है।

## निष्कर्ष

जावा के लिए Aspose.TeX, TeX दस्तावेज़ों को संभालने की प्रक्रिया को सरल बनाता है, स्ट्रीम इनपुट, इमेज आउटपुट और टर्मिनल इंटरैक्शन के लिए मजबूत सुविधाएँ प्रदान करता है। इस ट्यूटोरियल का अनुसरण करके, आपने सीखा है कि इन कार्यात्मकताओं को अपने जावा अनुप्रयोगों में सहजता से कैसे एकीकृत किया जाए।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या Aspose.TeX अन्य जावा लाइब्रेरीज़ के साथ संगत है?

A1: हां, कार्यक्षमता बढ़ाने के लिए Aspose.TeX को अन्य जावा लाइब्रेरी के साथ सहजता से एकीकृत किया जा सकता है।

### Q2: क्या मैं आउटपुट छवि प्रारूप को अनुकूलित कर सकता हूँ?

ए2: बिल्कुल! Aspose.TeX आउटपुट छवियों को सहेजने के लिए विभिन्न विकल्प प्रदान करता है, जो आपकी प्राथमिकताओं के आधार पर अनुकूलन की अनुमति देता है।

### Q3: क्या Aspose.TeX समर्थन के लिए कोई सामुदायिक मंच है?

 उ3: हाँ, आप समर्थन पा सकते हैं और समुदाय के साथ बातचीत कर सकते हैं[Aspose.TeX फोरम](https://forum.aspose.com/c/tex/47).

### Q4: मैं Aspose.TeX के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?

 A4: आप यहां से अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).

### Q5: क्या Aspose.TeX दस्तावेज़ीकरण के लिए कोई अतिरिक्त संसाधन हैं?

 A5: व्यापक का अन्वेषण करें[प्रलेखन](https://reference.aspose.com/tex/java/) विस्तृत जानकारी और उदाहरणों के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
