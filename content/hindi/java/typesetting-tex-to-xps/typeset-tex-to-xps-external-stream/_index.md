---
title: बाह्य स्ट्रीम के साथ जावा में TeX से XPS टाइपसेट करें
linktitle: बाह्य स्ट्रीम के साथ जावा में TeX से XPS टाइपसेट करें
second_title: Aspose.TeX जावा एपीआई
description: Aspose.TeX का उपयोग करके जावा में TeX को XPS में टाइप करना सीखें। निर्बाध दस्तावेज़ प्रसंस्करण के लिए चरण-दर-चरण मार्गदर्शन देखें।
type: docs
weight: 10
url: /hi/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
---
## परिचय

जावा विकास की दुनिया में, Aspose.TeX TeX दस्तावेज़ों को XPS सहित विभिन्न स्वरूपों में टाइप करने के लिए एक शक्तिशाली उपकरण के रूप में खड़ा है। यदि आप अपने जावा एप्लिकेशन की दस्तावेज़ प्रसंस्करण क्षमताओं को बढ़ाना चाहते हैं, तो यह ट्यूटोरियल आपके लिए तैयार किया गया है। इस चरण-दर-चरण मार्गदर्शिका में, हम आपको बाहरी स्ट्रीम के साथ जावा के लिए Aspose.TeX का उपयोग करके TeX को XPS में टाइप करने की प्रक्रिया के बारे में बताएंगे।

## आवश्यक शर्तें

ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

-  जावा डेवलपमेंट किट (जेडीके): सुनिश्चित करें कि आपके सिस्टम पर जावा स्थापित है। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://www.oracle.com/java/technologies/javase-downloads.html).

-  जावा के लिए Aspose.TeX: जावा के लिए Aspose.TeX डाउनलोड और इंस्टॉल करें। आप डाउनलोड लिंक पा सकते हैं[यहाँ](https://releases.aspose.com/tex/java/).

## पैकेज आयात करें

अपनी TeX से XPS रूपांतरण यात्रा शुरू करने के लिए आवश्यक पैकेज आयात करके शुरुआत करें। अपने जावा प्रोजेक्ट में निम्नलिखित कोड स्निपेट शामिल करें:

```java
package com.aspose.tex.TypesetXpsWrittenToExternalStream;

import java.io.FileOutputStream;
import java.io.IOException;
import java.io.OutputStream;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

## चरण 1: रूपांतरण विकल्प कॉन्फ़िगर करें

निम्नलिखित कोड का उपयोग करके डिफ़ॉल्ट ऑब्जेक्टटेक्स प्रारूप के लिए रूपांतरण विकल्प बनाकर शुरुआत करें:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

यह टाइपसेटिंग प्रक्रिया के लिए आधार तैयार करता है।

## चरण 2: कार्य का नाम और निर्देशिकाएँ निर्दिष्ट करें

कार्य का नाम परिभाषित करें और इनपुट और आउटपुट कार्यशील निर्देशिका सेट करें:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

सुनिश्चित करें कि आप "आपकी इनपुट निर्देशिका" जैसे प्लेसहोल्डर्स को अपने वास्तविक निर्देशिका पथों से बदल दें।

## चरण 3: टर्मिनल आउटपुट कॉन्फ़िगर करें

निर्दिष्ट करें कि टर्मिनल आउटपुट को आउटपुट वर्किंग डायरेक्टरी में एक फ़ाइल में लिखा जाना चाहिए:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

यह चरण सुनिश्चित करता है कि डिबगिंग के लिए विस्तृत लॉग कैप्चर किए गए हैं।

## चरण 4: आउटपुट स्ट्रीम खोलें

टाइपसेट XPS दस्तावेज़ लिखने के लिए एक स्ट्रीम खोलें:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

"आपकी आउटपुट निर्देशिका" को उचित पथ से बदलें।

## चरण 5: कार्य चलाएँ

TeX से XPS रूपांतरण कार्य निष्पादित करें:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

यह प्रक्रिया पूरी हो जाती है, और आपको अपना टाइपसेट XPS दस्तावेज़ निर्दिष्ट आउटपुट निर्देशिका में मिलेगा।

## निष्कर्ष

बधाई हो! आपने Aspose.TeX का उपयोग करके जावा में TeX को XPS में सफलतापूर्वक टाइपसेट कर लिया है। यह आपके जावा अनुप्रयोगों में दस्तावेज़ प्रसंस्करण के लिए संभावनाओं की दुनिया खोलता है। विभिन्न TeX फ़ाइलों के साथ प्रयोग करें और Aspose.TeX द्वारा प्रदान की जाने वाली विविध सुविधाओं का पता लगाएं।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं जावा के लिए अन्य दस्तावेज़ प्रारूपों के साथ Aspose.TeX का उपयोग कर सकता हूँ?

A1: Aspose.TeX मुख्य रूप से TeX-संबंधित दस्तावेज़ प्रसंस्करण पर केंद्रित है। अन्य प्रारूपों के लिए, Aspose की व्यापक उत्पाद श्रृंखला का पता लगाएं।

### Q2: क्या कोई परीक्षण संस्करण उपलब्ध है?

 उ2: हाँ, आप नि:शुल्क परीक्षण डाउनलोड करके Aspose.TeX का अनुभव कर सकते हैं[यहाँ](https://releases.aspose.com/).

### Q3: मुझे व्यापक दस्तावेज कहां मिल सकते हैं?

 A3: दस्तावेज़ देखें[यहाँ](https://reference.aspose.com/tex/java/) विस्तृत जानकारी और उदाहरणों के लिए.

### Q4: मुझे सहायता कैसे मिलेगी या सहायता कैसे मिलेगी?

 A4: Aspose.TeX फोरम पर जाएँ[यहाँ](https://forum.aspose.com/c/tex/47)सामुदायिक समर्थन और चर्चा के लिए।

### Q5: क्या मैं परीक्षण उद्देश्यों के लिए अस्थायी लाइसेंस प्राप्त कर सकता हूँ?

 A5: हाँ, आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).