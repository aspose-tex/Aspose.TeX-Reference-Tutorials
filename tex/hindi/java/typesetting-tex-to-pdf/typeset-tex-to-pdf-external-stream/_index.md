---
title: बाहरी स्ट्रीम के साथ जावा में TeX को PDF में टाइप करें
linktitle: बाहरी स्ट्रीम के साथ जावा में TeX को PDF में टाइप करें
second_title: Aspose.TeX जावा एपीआई
description: Aspose.TeX के साथ बाहरी स्ट्रीम का उपयोग करके जावा में TeX को PDF में टाइप करना सीखें। निर्बाध एकीकरण के लिए हमारी चरण-दर-चरण मार्गदर्शिका का पालन करें।
weight: 10
url: /hi/java/typesetting-tex-to-pdf/typeset-tex-to-pdf-external-stream/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# बाहरी स्ट्रीम के साथ जावा में TeX को PDF में टाइप करें

## परिचय

जावा विकास की दुनिया में, TeX फ़ाइलों से PDF बनाना एक सामान्य आवश्यकता है। जावा के लिए Aspose.TeX इस प्रक्रिया को सरल बनाता है, TeX को PDF में टाइप करने के लिए एक कुशल समाधान प्रदान करता है। इस ट्यूटोरियल में, हम आपको बाहरी स्ट्रीम का उपयोग करके TeX को PDF में टाइप करने के चरणों के बारे में बताएंगे। अंत तक, आपको इस बात की स्पष्ट समझ हो जाएगी कि इस प्रक्रिया को अपने जावा अनुप्रयोगों में निर्बाध रूप से कैसे कार्यान्वित किया जाए।

## आवश्यक शर्तें

ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

- जावा के लिए Aspose.TeX: सुनिश्चित करें कि आपके पास Java के लिए Aspose.TeX लाइब्रेरी स्थापित है। आप इसे यहां से डाउनलोड कर सकते हैं[जावा दस्तावेज़ीकरण के लिए Aspose.TeX](https://reference.aspose.com/tex/java/).

- इनपुट और आउटपुट निर्देशिकाएँ: इनपुट और आउटपुट निर्देशिकाएँ तैयार करें। आवश्यक फ़ाइलें प्राप्त करने के लिए आप दिए गए डाउनलोड लिंक का उपयोग कर सकते हैं।

## पैकेज आयात करें

अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करके प्रारंभ करें:

```java
package com.aspose.tex.TypesetPdfWrittenToExternalStream;

import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.io.OutputStream;

import com.aspose.tex.InputZipDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.OutputZipDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.PdfDevice;
import com.aspose.tex.rendering.PdfSaveOptions;

import util.Utils;
```

## चरण 1: इनपुट और आउटपुट स्ट्रीम खोलें

इनपुट ज़िप संग्रह (इनपुट कार्यशील निर्देशिका के रूप में कार्य करना) और आउटपुट ज़िप संग्रह (आउटपुट कार्यशील निर्देशिका के रूप में कार्य करना) के लिए स्ट्रीम खोलकर शुरुआत करें। "आपकी इनपुट निर्देशिका" और "आपकी आउटपुट निर्देशिका" को अपने वास्तविक निर्देशिका पथों से बदलना सुनिश्चित करें।

```java
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "typeset-pdf-to-external-stream.zip");
```

## चरण 2: TeXOptions कॉन्फ़िगर करें

TeXOptions ऑब्जेक्ट बनाएं और इसे अपनी आवश्यकताओं के अनुसार कॉन्फ़िगर करें। कार्य का नाम, इनपुट वर्किंग डायरेक्टरी, आउटपुट वर्किंग डायरेक्टरी और अन्य विकल्प सेट करें।

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("typeset-pdf-to-external-stream");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
options.setSaveOptions(new PdfSaveOptions());
```

## चरण 3: TeX को PDF में टाइप करें

अब, आउटपुट पीडीएफ को वांछित स्थान पर लिखने के लिए एक स्ट्रीम खोलें। आप इसे स्थानीय फ़ाइल में या सीधे आउटपुट ज़िप संग्रह में लिखना चुन सकते हैं।

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + "file-name.pdf");
try {
    new TeXJob("hello-world", new PdfDevice(stream), options).run();
} finally {
    stream.close();
}
```

## चरण 4: आउटपुट ज़िप संग्रह को अंतिम रूप दें

टाइपसेटिंग प्रक्रिया को पूरा करने के लिए आउटपुट ज़िप संग्रह को समाप्त करें।

```java
((OutputZipDirectory)options.getOutputWorkingDirectory()).finish();
```

## निष्कर्ष

बधाई हो! आपने Aspose.TeX के साथ बाहरी स्ट्रीम का उपयोग करके जावा में TeX को PDF में सफलतापूर्वक टाइप कर लिया है। यह ट्यूटोरियल आपके जावा अनुप्रयोगों में टीएक्स से पीडीएफ रूपांतरण को सहजता से शामिल करने के लिए एक मजबूत आधार प्रदान करता है।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं आउटपुट पीडीएफ के फ़ाइल नाम को अनुकूलित कर सकता हूँ?

 A1: हाँ, आप संशोधित कर सकते हैं`options.setJobName("typeset-pdf-to-external-stream")` अपनी इच्छित नौकरी का नाम सेट करने के लिए.

### Q2: मैं टाइपसेटिंग के दौरान सामान्य समस्याओं का निवारण कैसे करूँ?

 A2: पर जाएँ[Aspose.TeX फोरम](https://forum.aspose.com/c/tex/47) सामुदायिक समर्थन और सहायता के लिए।

### Q3: क्या Java के लिए Aspose.TeX का निःशुल्क परीक्षण उपलब्ध है?

 उ3: हाँ, आप नि:शुल्क परीक्षण का उपयोग कर सकते हैं[यहाँ](https://releases.aspose.com/).

### Q4: मुझे अतिरिक्त दस्तावेज़ और उदाहरण कहां मिल सकते हैं?

 ए4: व्यापक का अन्वेषण करें[Aspose.TeX दस्तावेज़ीकरण](https://reference.aspose.com/tex/java/) विस्तृत जानकारी के लिए.

### Q5: क्या मैं Aspose.TeX के लिए अस्थायी लाइसेंस प्राप्त कर सकता हूँ?

 A5: हाँ, आप अस्थायी लाइसेंस का अनुरोध कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
