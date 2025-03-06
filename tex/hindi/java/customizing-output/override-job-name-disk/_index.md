---
title: कार्य का नाम ओवरराइड करें और जावा में टर्मिनल आउटपुट लिखें
linktitle: कार्य का नाम ओवरराइड करें और जावा में टर्मिनल आउटपुट लिखें
second_title: Aspose.TeX जावा एपीआई
description: जावा के लिए Aspose.TeX का उपयोग करके नौकरी के नामों को ओवरराइड करने और टर्मिनल आउटपुट लिखने पर चरण-दर-चरण मार्गदर्शिका देखें। शक्तिशाली अनुकूलन विकल्पों के साथ अपने दस्तावेज़ प्रसंस्करण को बढ़ाएं।
weight: 10
url: /hi/java/customizing-output/override-job-name-disk/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# कार्य का नाम ओवरराइड करें और जावा में टर्मिनल आउटपुट लिखें

## परिचय

जावा के लिए Aspose.TeX, TeX फ़ाइलों के साथ काम करने के लिए शक्तिशाली सुविधाएँ प्रदान करता है, जिससे डेवलपर्स को TeX दस्तावेज़ प्रसंस्करण में हेरफेर और अनुकूलित करने की अनुमति मिलती है। इस ट्यूटोरियल में, हम जावा में Aspose.TeX का उपयोग करके फ़ाइल सिस्टम में नौकरी के नाम को ओवरराइड करने और टर्मिनल आउटपुट लिखने की प्रक्रिया के माध्यम से आपका मार्गदर्शन करेंगे।

## आवश्यक शर्तें

इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

- जावा प्रोग्रामिंग का कार्यसाधक ज्ञान।
-  जावा के लिए Aspose.TeX स्थापित किया गया। आप इसे यहां से डाउनलोड कर सकते हैं[Aspose.TeX जावा दस्तावेज़ीकरण](https://reference.aspose.com/tex/java/).

## पैकेज आयात करें

आरंभ करने के लिए, अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करें। अपनी जावा फ़ाइल में, निम्नलिखित आयात शामिल करें:

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

## कार्य का नाम ओवरराइड करें और टर्मिनल आउटपुट लिखें

### चरण 1: रूपांतरण विकल्प बनाएँ

ऑब्जेक्टटेक्स इंजन एक्सटेंशन पर डिफ़ॉल्ट ऑब्जेक्टटेक्स प्रारूप के लिए रूपांतरण विकल्प बनाकर शुरुआत करें। निम्नलिखित कोड स्निपेट का उपयोग करें:

```java
//एक्सस्टार्ट:ओवरराइडजॉबनेम-राइटटर्मिनलआउटपुटटूफाइलसिस्टम
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

### चरण 2: कार्य का नाम और कार्य निर्देशिकाएँ निर्दिष्ट करें

कार्य का नाम, इनपुट कार्यशील निर्देशिका और आउटपुट कार्यशील निर्देशिका निर्दिष्ट करें। यदि कार्य का नाम निर्दिष्ट नहीं है, तो TeXJob कंस्ट्रक्टर का पहला तर्क कार्य के नाम के रूप में लिया जाएगा। निम्नलिखित कोड स्निपेट का उपयोग करें:

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### चरण 3: फ़ाइल सिस्टम में टर्मिनल आउटपुट लिखें

 निर्दिष्ट करें कि टर्मिनल आउटपुट को आउटपुट वर्किंग डायरेक्टरी में एक फ़ाइल में लिखा जाना चाहिए। फ़ाइल का नाम होगा`<job_name>.trm`. निम्नलिखित कोड जोड़ें:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### चरण 4: कार्य चलाएँ

निर्दिष्ट विकल्पों और कार्य नाम का उपयोग करके TeX कार्य चलाएँ। यहां बताया गया है कि आप यह कैसे कर सकते हैं:

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
// ExEnd:ओवरराइडजॉबनेम-राइटटर्मिनलआउटपुटटूफाइलसिस्टम
```

बधाई हो! आपने जावा में Aspose.TeX का उपयोग करके फ़ाइल सिस्टम में कार्य नाम और लिखित टर्मिनल आउटपुट को सफलतापूर्वक ओवरराइड कर दिया है।

## निष्कर्ष

इस ट्यूटोरियल में, हमने पता लगाया कि कार्य नाम को ओवरराइड करने और टर्मिनल आउटपुट कैप्चर करने के लिए जावा के लिए Aspose.TeX का उपयोग कैसे करें। ये सुविधाएँ डेवलपर्स को TeX दस्तावेज़ प्रसंस्करण पर बेहतर नियंत्रण रखने, अनुकूलन और लचीलेपन को बढ़ाने के लिए सशक्त बनाती हैं।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं अन्य जावा लाइब्रेरीज़ के साथ जावा के लिए Aspose.TeX का उपयोग कर सकता हूँ?

A1: हां, जावा के लिए Aspose.TeX को आपकी दस्तावेज़ प्रसंस्करण क्षमताओं को बढ़ाने के लिए अन्य जावा पुस्तकालयों के साथ सहजता से एकीकृत करने के लिए डिज़ाइन किया गया है।

### Q2: मुझे जावा के लिए Aspose.TeX के लिए समर्थन कहां मिल सकता है?

 A2: पर जाएँ[Aspose.TeX फोरम](https://forum.aspose.com/c/tex/47) आपके सामने आने वाली किसी भी समस्या के लिए सामुदायिक समर्थन और सहायता के लिए।

### Q3: क्या Java के लिए Aspose.TeX का निःशुल्क परीक्षण उपलब्ध है?

 उ3: हां, आप जावा के लिए Aspose.TeX के निःशुल्क परीक्षण संस्करण तक पहुंच सकते हैं[यहाँ](https://releases.aspose.com/).

### Q4: मैं जावा के लिए Aspose.TeX के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?

 A4: इसका पालन करें[जोड़ना](https://purchase.aspose.com/temporary-license/) परीक्षण और मूल्यांकन उद्देश्यों के लिए एक अस्थायी लाइसेंस प्राप्त करना।

### Q5: मैं जावा के लिए Aspose.TeX कहां से खरीद सकता हूं?

 A5: पर जाएँ[खरीद पृष्ठ](https://purchase.aspose.com/buy) जावा के लिए Aspose.TeX का लाइसेंस प्राप्त करने के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
