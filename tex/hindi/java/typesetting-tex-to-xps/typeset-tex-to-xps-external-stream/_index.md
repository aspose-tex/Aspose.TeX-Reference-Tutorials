---
date: 2025-12-11
description: Aspose.TeX का उपयोग करके जावा में TeX को XPS में कैसे बदलें, सीखें। यह
  चरण‑दर‑चरण गाइड आपको दिखाता है कि XPS दस्तावेज़ स्ट्रीम को प्रभावी ढंग से कैसे उत्पन्न
  किया जाए।
linktitle: How to Convert TeX to XPS in Java with External Stream
second_title: Aspose.TeX Java API
title: जावा में बाहरी स्ट्रीम के साथ TeX को XPS में कैसे परिवर्तित करें
url: /hi/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java में बाहरी स्ट्रीम के साथ TeX को XPS में कैसे परिवर्तित करें

## Introduction

यदि आपको **TeX** फ़ाइलों को Java एप्लिकेशन से उच्च‑गुणवत्ता वाले XPS आउटपुट में **परिवर्तित** करने की आवश्यकता है, तो Aspose.TeX for Java इस काम को सरल बनाता है। इस ट्यूटोरियल में आप देखेंगे कि **TeX को** XPS दस्तावेज़ में बाहरी आउटपुट स्ट्रीम का उपयोग करके कैसे बदलें, जो तब आदर्श है जब आप परिणाम को सीधे किसी प्रतिक्रिया, क्लाउड स्टोरेज सेवा, या किसी कस्टम गंतव्य में पाइप करना चाहते हैं। चलिए पूरे प्रक्रिया को देखते हैं, पर्यावरण सेटअप से लेकर अंतिम XPS फ़ाइल लिखने तक।

## Quick Answers
- **यह ट्यूटोरियल क्या कवर करता है?** Aspose.TeX के साथ बाहरी स्ट्रीम का उपयोग करके TeX को XPS में बदलना।  
- **कौन सी मुख्य लाइब्रेरी आवश्यक है?** Aspose.TeX for Java।  
- **क्या मुझे लाइसेंस चाहिए?** उत्पादन उपयोग के लिए एक अस्थायी या पूर्ण लाइसेंस आवश्यक है।  
- **क्या मैं XPS दस्तावेज़ स्ट्रीम बना सकता हूँ?** हाँ – उदाहरण XPS को सीधे एक `OutputStream` में लिखता है।  
- **कौन सा Java संस्करण समर्थित है?** कोई भी JDK 8+ (ट्यूटोरियल में संदर्भ के रूप में JDK 11 उपयोग किया गया है)।

## Prerequisites

कोड में डुबकी लगाने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- Java Development Kit (JDK): सुनिश्चित करें कि आपके सिस्टम पर Java स्थापित है। आप इसे [here](https://www.oracle.com/java/technologies/javase-downloads.html) से डाउनलोड कर सकते हैं।

- Aspose.TeX for Java: Aspose.TeX for Java डाउनलोड और इंस्टॉल करें। डाउनलोड लिंक आप [here](https://releases.aspose.com/tex/java/) पर पा सकते हैं।

## Import Packages

अपने TeX‑to‑XPS रूपांतरण यात्रा को शुरू करने के लिए आवश्यक पैकेज इम्पोर्ट करें। अपने Java प्रोजेक्ट में निम्न कोड स्निपेट शामिल करें:

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

## Step 1: Configure Conversion Options

डिफ़ॉल्ट ObjectTeX फ़ॉर्मेट के लिए रूपांतरण विकल्प बनाने के लिए नीचे दिया गया कोड उपयोग करें:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

यह टाइपसेटिंग प्रक्रिया की नींव स्थापित करता है।

## Step 2: Specify Job Name and Directories

एक जॉब नाम निर्धारित करें और इनपुट तथा आउटपुट कार्य निर्देशिकाएँ सेट करें:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

"Your Input Directory" जैसे प्लेसहोल्डर को अपने वास्तविक पाथ से बदलें।

## Step 3: Configure Terminal Output

निर्दिष्ट करें कि टर्मिनल आउटपुट को आउटपुट कार्य निर्देशिका में एक फ़ाइल में लिखा जाना चाहिए:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

यह कदम डिबगिंग के लिए विस्तृत लॉग कैप्चर करता है।

## Step 4: Open Output Stream

टाइपसेटेड XPS दस्तावेज़ लिखने के लिए एक स्ट्रीम खोलें:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

"Your Output Directory" को उचित पाथ से बदलें।

## Step 5: Run the Job

TeX से XPS रूपांतरण जॉब को निष्पादित करें:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

यह प्रक्रिया पूर्ण करता है, और आप निर्दिष्ट आउटपुट निर्देशिका में निर्मित XPS दस्तावेज़ पाएँगे।

## Common Issues and Solutions

| Issue | Why it Happens | How to Fix |
|-------|----------------|------------|
| **FileNotFoundException** when opening the stream | आउटपुट डायरेक्टरी पाथ गलत है या मौजूद नहीं है। | पाथ सत्यापित करें, पहले से डायरेक्टरी बनाएं, या `Files.createDirectories` का उपयोग करें। |
| **NullPointerException** on `options.getOutputWorkingDirectory()` | `setOutputWorkingDirectory` को कॉल नहीं किया गया या `null` लौटाया। | `options.setOutputWorkingDirectory` को उपयोग करने से पहले कॉल करना सुनिश्चित करें। |
| **LicenseException** at runtime | वैध Aspose.TeX लाइसेंस के बिना चलाया गया। | अस्थायी या स्थायी लाइसेंस लागू करें: `License license = new License(); license.setLicense("Aspose.TeX.lic");`. |

## Frequently Asked Questions

**Q: क्या मैं Aspose.TeX for Java को अन्य दस्तावेज़ फ़ॉर्मेट के साथ उपयोग कर सकता हूँ?**  
A: Aspose.TeX मुख्यतः TeX‑संबंधित दस्तावेज़ प्रोसेसिंग पर केंद्रित है। अन्य फ़ॉर्मेट के लिए Aspose की विस्तृत उत्पाद श्रृंखला देखें।

**Q: क्या कोई ट्रायल संस्करण उपलब्ध है?**  
A: हाँ, आप मुफ्त ट्रायल डाउनलोड करके Aspose.TeX का अनुभव ले सकते हैं [here](https://releases.aspose.com/).

**Q: विस्तृत दस्तावेज़ीकरण कहाँ मिल सकता है?**  
A: विस्तृत जानकारी और उदाहरणों के लिए दस्तावेज़ीकरण देखें [here](https://reference.aspose.com/tex/java/)।

**Q: समर्थन या सहायता कैसे प्राप्त करूँ?**  
A: समुदाय समर्थन और चर्चा के लिए Aspose.TeX फ़ोरम पर जाएँ [here](https://forum.aspose.com/c/tex/47)।

**Q: क्या परीक्षण के लिए अस्थायी लाइसेंस प्राप्त कर सकता हूँ?**  
A: हाँ, आप अस्थायी लाइसेंस यहाँ से प्राप्त कर सकते हैं [here](https://purchase.aspose.com/temporary-license/)।

## Conclusion

बधाई हो! आपने अभी-अभी **TeX को** Java में Aspose.TeX और बाहरी स्ट्रीम का उपयोग करके XPS दस्तावेज़ में बदलना सीख लिया है। यह तकनीक आपको XPS आउटपुट के गंतव्य पर पूर्ण नियंत्रण देती है—चाहे वह फ़ाइल सिस्टम हो, वेब प्रतिक्रिया हो, या क्लाउड बकेट। विभिन्न TeX स्रोतों के साथ प्रयोग करने, कस्टम फ़ॉन्ट्स के लिए `TeXOptions` को समायोजित करने, या स्ट्रीम को बड़े दस्तावेज़‑जनरेशन पाइपलाइन में जोड़ने में संकोच न करें।

---

**Last Updated:** 2025-12-11  
**Tested With:** Aspose.TeX for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}