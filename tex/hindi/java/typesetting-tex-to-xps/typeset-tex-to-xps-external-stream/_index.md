---
date: 2026-02-20
description: Aspose.TeX का उपयोग करके जावा में TeX को XPS में कैसे परिवर्तित करें,
  सीखें। यह चरण‑दर‑चरण गाइड आपको दिखाता है कि TeX फ़ाइलों को कैसे परिवर्तित करें और
  XPS दस्तावेज़ स्ट्रीम को कुशलतापूर्वक उत्पन्न करें।
linktitle: How to Convert TeX to XPS in Java with External Stream
second_title: Aspose.TeX Java API
title: जावा में बाहरी स्ट्रीम के साथ TeX को XPS में कैसे बदलें
url: /hi/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java में External Stream के साथ TeX को XPS में कैसे कनवर्ट करें

## परिचय

यदि आपको **TeX** फ़ाइलों को Java एप्लिकेशन से उच्च‑गुणवत्ता वाले XPS आउटपुट में **कनवर्ट** करना है, तो Aspose.TeX for Java यह काम आसान बना देता है। इस ट्यूटोरियल में आप देखेंगे कि **TeX को XPS** दस्तावेज़ में कैसे बदलें, वह भी एक बाहरी आउटपुट स्ट्रीम का उपयोग करके, जो तब आदर्श है जब आप परिणाम को सीधे किसी प्रतिक्रिया, क्लाउड स्टोरेज सेवा, या किसी कस्टम गंतव्य पर पाइप करना चाहते हैं। चलिए पूरे प्रोसेस को देखते हैं, पर्यावरण सेटअप से लेकर अंतिम XPS फ़ाइल लिखने तक।

## त्वरित उत्तर
- **यह ट्यूटोरियल क्या कवर करता है?** Aspose.TeX के साथ External Stream का उपयोग करके TeX को XPS में बदलना।  
- **कौन सी मुख्य लाइब्रेरी आवश्यक है?** Aspose.TeX for Java।  
- **क्या मुझे लाइसेंस चाहिए?** प्रोडक्शन उपयोग के लिए एक टेम्पररी या फुल लाइसेंस आवश्यक है।  
- **क्या मैं XPS दस्तावेज़ स्ट्रीम बना सकता हूँ?** हाँ – उदाहरण XPS को सीधे एक `OutputStream` में लिखता है।  
- **कौन सा Java संस्करण समर्थित है?** कोई भी JDK 8+ (ट्यूटोरियल में संदर्भ के तौर पर JDK 11 उपयोग किया गया है)।

## External Stream का उपयोग करके TeX को XPS में कैसे कनवर्ट करें

यह सेक्शन समर्पित हेडिंग में मुख्य कीवर्ड दोहराता है, जिससे पाठकों और AI इंजन को सटीक समाधान आसानी से मिल सके।

## पूर्वापेक्षाएँ

कोड में डुबकी लगाने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- Java Development Kit (JDK): सुनिश्चित करें कि आपके सिस्टम पर Java इंस्टॉल है। आप इसे [यहाँ](https://www.oracle.com/java/technologies/javase-downloads.html) से डाउनलोड कर सकते हैं।

- Aspose.TeX for Java: Aspose.TeX for Java डाउनलोड और इंस्टॉल करें। डाउनलोड लिंक आप [यहाँ](https://releases.aspose.com/tex/java/) पा सकते हैं।

## पैकेज इम्पोर्ट करें

अपने TeX‑to‑XPS कन्वर्ज़न यात्रा की शुरुआत के लिए आवश्यक पैकेज इम्पोर्ट करें। अपने Java प्रोजेक्ट में नीचे दिया गया कोड स्निपेट शामिल करें:

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

## चरण 1: कन्वर्ज़न विकल्प कॉन्फ़िगर करें

डिफ़ॉल्ट ObjectTeX फॉर्मेट के लिए कन्वर्ज़न विकल्प बनाकर शुरू करें, नीचे दिया गया कोड उपयोग करें:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

यह टाइपसेटिंग प्रोसेस की नींव स्थापित करता है।

## चरण 2: जॉब नाम और डायरेक्टरी निर्धारित करें

एक जॉब नाम परिभाषित करें और इनपुट तथा आउटपुट वर्किंग डायरेक्टरी सेट करें:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

"Your Input Directory" जैसे प्लेसहोल्डर को अपने वास्तविक डायरेक्टरी पाथ से बदलें।

## चरण 3: टर्मिनल आउटपुट कॉन्फ़िगर करें

निर्दिष्ट करें कि टर्मिनल आउटपुट को आउटपुट वर्किंग डायरेक्टरी में एक फ़ाइल में लिखा जाए:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

यह चरण डिबगिंग के लिए विस्तृत लॉग कैप्चर करता है।

## चरण 4: आउटपुट स्ट्रीम खोलें

टाइपसेटेड XPS दस्तावेज़ लिखने के लिए एक स्ट्रीम खोलें:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

"Your Output Directory" को उपयुक्त पाथ से बदलें।

## चरण 5: जॉब चलाएँ

TeX से XPS कन्वर्ज़न जॉब को निष्पादित करें:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

यह प्रक्रिया पूरी हो जाती है, और आप निर्दिष्ट आउटपुट डायरेक्टरी में उत्पन्न XPS दस्तावेज़ पाएँगे।

## यह क्यों महत्वपूर्ण है

एक बाहरी `OutputStream` का उपयोग करने से आपको XPS डेटा के गंतव्य पर पूर्ण नियंत्रण मिलता है—चाहे आप इसे सीधे वेब क्लाइंट को भेज रहे हों, क्लाउड स्टोरेज में सहेज रहे हों, या किसी अन्य प्रोसेसिंग पाइपलाइन में जोड़ रहे हों। यह मध्यवर्ती फ़ाइलों की आवश्यकता को समाप्त करता है और I/O ओवरहेड को कम करता है, जो उच्च‑थ्रूपुट या सर्वर‑लेस वातावरण में विशेष रूप से मूल्यवान है।

## सामान्य समस्याएँ और समाधान

| समस्या | क्यों होता है | कैसे ठीक करें |
|-------|--------------|--------------|
| **FileNotFoundException** जब स्ट्रीम खोल रहे हों | आउटपुट डायरेक्टरी पाथ गलत है या मौजूद नहीं है। | पाथ को सत्यापित करें, पहले से डायरेक्टरी बनाएं, या `Files.createDirectories` का उपयोग करें। |
| **NullPointerException** `options.getOutputWorkingDirectory()` पर | `setOutputWorkingDirectory` कॉल नहीं किया गया या `null` लौटाया। | `options.setOutputWorkingDirectory` को उपयोग करने से पहले कॉल करना सुनिश्चित करें। |
| **LicenseException** रनटाइम पर | वैध Aspose.TeX लाइसेंस के बिना चल रहा है। | एक टेम्पररी या स्थायी लाइसेंस लागू करें: `License license = new License(); license.setLicense("Aspose.TeX.lic");` |

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं Aspose.TeX for Java को अन्य दस्तावेज़ फ़ॉर्मेट के साथ उपयोग कर सकता हूँ?**  
उत्तर: Aspose.TeX मुख्यतः TeX‑संबंधित दस्तावेज़ प्रोसेसिंग पर केंद्रित है। अन्य फ़ॉर्मेट के लिए Aspose के विस्तृत उत्पाद रेंज को देखें।

**प्रश्न: क्या कोई ट्रायल संस्करण उपलब्ध है?**  
उत्तर: हाँ, आप मुफ्त ट्रायल डाउनलोड कर सकते हैं [यहाँ](https://releases.aspose.com/)।

**प्रश्न: विस्तृत दस्तावेज़ीकरण कहाँ मिल सकता है?**  
उत्तर: विस्तृत जानकारी और उदाहरणों के लिए दस्तावेज़ीकरण देखें [यहाँ](https://reference.aspose.com/tex/java/)।

**प्रश्न: समर्थन या सहायता कैसे प्राप्त करूँ?**  
उत्तर: समुदाय समर्थन और चर्चा के लिए Aspose.TeX फ़ोरम देखें [यहाँ](https://forum.aspose.com/c/tex/47)।

**प्रश्न: क्या परीक्षण उद्देश्यों के लिए टेम्पररी लाइसेंस प्राप्त किया जा सकता है?**  
उत्तर: हाँ, आप टेम्पररी लाइसेंस प्राप्त कर सकते हैं [यहाँ](https://purchase.aspose.com/temporary-license/)।

## निष्कर्ष

बधाई हो! आपने अभी सीखा **कैसे TeX को XPS** दस्तावेज़ में Java के साथ Aspose.TeX और एक बाहरी स्ट्रीम का उपयोग करके बदलें। यह तकनीक आपको XPS आउटपुट के गंतव्य पर पूर्ण नियंत्रण देती है—चाहे वह फ़ाइल सिस्टम हो, वेब प्रतिक्रिया हो, या क्लाउड बकेट। विभिन्न TeX स्रोतों के साथ प्रयोग करने, कस्टम फ़ॉन्ट्स के लिए `TeXOptions` को समायोजित करने, या स्ट्रीम को बड़े दस्तावेज़‑जनरेशन पाइपलाइन में जोड़ने में संकोच न करें।

---

**अंतिम अपडेट:** 2026-02-20  
**परीक्षित संस्करण:** Aspose.TeX for Java 24.11 (लेखन समय पर नवीनतम)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}