---
title: कार्य का नाम ओवरराइड करें और जावा में ज़िप पर टर्मिनल आउटपुट लिखें
linktitle: कार्य का नाम ओवरराइड करें और जावा में ज़िप पर टर्मिनल आउटपुट लिखें
second_title: Aspose.TeX जावा एपीआई
description: Aspose.TeX के साथ जावा में नौकरी के नामों को ओवरराइड करना और ज़िप पर टर्मिनल आउटपुट लिखना सीखें। जावा डेवलपर्स के लिए एक व्यापक ट्यूटोरियल।
weight: 11
url: /hi/java/customizing-output/override-job-name-zip/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# कार्य का नाम ओवरराइड करें और जावा में ज़िप पर टर्मिनल आउटपुट लिखें

## परिचय

जावा विकास की दुनिया में, Aspose.TeX TeX फ़ाइल स्वरूपों को संभालने के लिए एक शक्तिशाली उपकरण के रूप में खड़ा है। इस ट्यूटोरियल में, हम एक विशिष्ट परिदृश्य पर ध्यान देंगे - नौकरी के नामों को ओवरराइड करना और ज़िप फ़ाइल में टर्मिनल आउटपुट लिखना। यह चरण-दर-चरण मार्गदर्शिका आपको जावा के लिए Aspose.TeX का उपयोग करने की प्रक्रिया के बारे में बताएगी।

## आवश्यक शर्तें

इससे पहले कि हम इस ट्यूटोरियल को शुरू करें, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
- जावा प्रोग्रामिंग का बुनियादी ज्ञान।
-  जावा के लिए Aspose.TeX स्थापित किया गया। यदि नहीं, तो आप इसे यहां से डाउनलोड कर सकते हैं[Aspose वेबसाइट](https://releases.aspose.com/tex/java/).
- जावा विकास परिवेश कैसे स्थापित करें इसकी समझ।

## पैकेज आयात करें

अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करके शुरुआत करें। यह सुनिश्चित करता है कि आपके पास कार्य के लिए आवश्यक Aspose.TeX कार्यात्मकताओं तक पहुंच है।

```java
package com.aspose.tex.OverridenJobNameAndTerminalOutputWrittenToZip;

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

## चरण 1: ज़िप पुरालेख खोलें

सबसे पहले, ज़िप संग्रह पर एक स्ट्रीम खोलें जो इनपुट वर्किंग डायरेक्टरी के रूप में काम करेगी। यह वह संग्रह है जिससे आपका डेटा संसाधित किया जाएगा।

```java
// इनपुट ज़िप संग्रह पर एक स्ट्रीम खोलें
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
```

## चरण 2: आउटपुट ज़िप संग्रह खोलें

इसके बाद, ज़िप संग्रह पर एक स्ट्रीम खोलें जो आउटपुट वर्किंग डायरेक्टरी के रूप में काम करेगी। यहीं पर टर्मिनल आउटपुट लिखा जाएगा।

```java
// आउटपुट ज़िप संग्रह पर एक स्ट्रीम खोलें
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "terminal-out-to-zip.zip");
```

## चरण 3: रूपांतरण विकल्प सेट करें

ऑब्जेक्टटेक्स इंजन एक्सटेंशन पर डिफ़ॉल्ट ऑब्जेक्टटेक्स प्रारूप के लिए रूपांतरण विकल्प बनाएं। इनपुट और आउटपुट दोनों के लिए कार्य का नाम और ज़िप संग्रह कार्यशील निर्देशिका निर्दिष्ट करें।

```java
// ऑब्जेक्टटेक्स प्रारूप के लिए TeX विकल्प बनाएं
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("terminal-output-to-zip");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
```

## चरण 4: टर्मिनल आउटपुट निर्दिष्ट करें

 निर्दिष्ट करें कि टर्मिनल आउटपुट को आउटपुट वर्किंग डायरेक्टरी में एक फ़ाइल में लिखा जाना चाहिए। फ़ाइल का नाम होगा`<job_name>.trm`.

```java
// टर्मिनल आउटपुट सेटिंग्स निर्दिष्ट करें
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

## चरण 5: बचत विकल्प परिभाषित करें और कार्य चलाएँ

इस मामले में बचत विकल्पों को परिभाषित करें, जैसे पीडीएफ सहेजें विकल्प। रूपांतरण निष्पादित करने के लिए TeX कार्य चलाएँ।

```java
// बचत विकल्पों को परिभाषित करें और कार्य चलाएँ
options.setSaveOptions(new PdfSaveOptions());
new TeXJob("hello-world", new PdfDevice(), options).run();
```

## चरण 6: आउटपुट ज़िप संग्रह को अंतिम रूप दें

कार्य पूरा होने के बाद, उचित समापन सुनिश्चित करने के लिए आउटपुट ज़िप संग्रह को अंतिम रूप दें।

```java
// आउटपुट ज़िप संग्रह को अंतिम रूप दें
((OutputZipDirectory) options.getOutputWorkingDirectory()).finish();
```

## निष्कर्ष

बधाई हो! आपने Aspose.TeX का उपयोग करके जावा में ज़िप फ़ाइल में नौकरी के नामों को ओवरराइड करना और टर्मिनल आउटपुट लिखना सफलतापूर्वक सीख लिया है। यह शक्तिशाली कार्यक्षमता आपके जावा विकास परियोजनाओं में लचीलापन और दक्षता जोड़ती है।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: Aspose.TeX क्या है?

A1: Aspose.TeX एक जावा लाइब्रेरी है जो डेवलपर्स को दस्तावेज़ प्रसंस्करण के लिए उन्नत कार्यक्षमता प्रदान करते हुए TeX फ़ाइल स्वरूपों के साथ काम करने की अनुमति देती है।

### Q2: मैं Aspose.TeX के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?

 A2: आप यहां से अस्थायी लाइसेंस प्राप्त कर सकते हैं[इस लिंक](https://purchase.aspose.com/temporary-license/).

### Q3: मुझे Aspose.TeX दस्तावेज़ कहां मिल सकता है?

 A3: दस्तावेज़ उपलब्ध है[यहाँ](https://reference.aspose.com/tex/java/).

### Q4: क्या Aspose.TeX का कोई निःशुल्क परीक्षण संस्करण है?

 उ4: हाँ, आप निःशुल्क परीक्षण संस्करण पा सकते हैं[यहाँ](https://releases.aspose.com/).

### Q5: मैं Aspose.TeX के बारे में कहां से सहायता मांग सकता हूं या प्रश्न पूछ सकता हूं?

 A5: पर जाएँ[Aspose.TeX फोरम](https://forum.aspose.com/c/tex/47) समर्थन और चर्चा के लिए.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
