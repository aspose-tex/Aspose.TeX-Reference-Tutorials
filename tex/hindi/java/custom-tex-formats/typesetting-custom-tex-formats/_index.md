---
date: 2025-12-05
description: Aspose.TeX for Java का उपयोग करके TeX को टाइपसेट करना सीखें, जिसमें कस्टम
  फ़ॉर्मेट्स के चरण और अस्पोज़ की अस्थायी लाइसेंस कैसे प्राप्त करें, शामिल हैं।
language: hi
linktitle: How to Typeset TeX with Custom Formats in Java
second_title: Aspose.TeX Java API
title: जावा में कस्टम फ़ॉर्मैट्स के साथ TeX को टाइपसेट कैसे करें
url: /java/custom-tex-formats/typesetting-custom-tex-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा में कस्टम फ़ॉर्मैट्स के साथ TeX टाइपसेट कैसे करें

## परिचय

यदि आपको जावा एप्लिकेशन के भीतर **how to typeset tex** करने की आवश्यकता है, तो Aspose.TeX कस्टम TeX फ़ॉर्मैट फ़ाइलों के साथ काम करने का एक साफ़, उच्च‑प्रदर्शन तरीका प्रदान करता है। इस ट्यूटोरियल में हम आपको वह सब बताएंगे जिसकी आपको ज़रूरत है—पर्यावरण सेटअप से लेकर आपके अपने फ़ॉर्मैट का उपयोग करने वाले TeX जॉब को चलाने तक। चाहे आप एक वैज्ञानिक प्रकाशन टूल बना रहे हों या एक कस्टम रिपोर्ट जेनरेटर, नीचे दिए गए चरण आपको जल्दी से शुरू करने में मदद करेंगे।

## त्वरित उत्तर
- **मुझे कौनसी लाइब्रेरी चाहिए?** Aspose.TeX for Java  
- **क्या मैं कस्टम TeX फ़ॉर्मैट उपयोग कर सकता हूँ?** हाँ – बस `FormatProvider` को अपनी फ़ाइल की ओर इंगित करें।  
- **क्या विकास के लिए लाइसेंस चाहिए?** परीक्षण के लिए एक टेम्पररी लाइसेंस aspose काम करता है; उत्पादन के लिए पूर्ण लाइसेंस आवश्यक है।  
- **कौनसा जावा संस्करण समर्थित है?** JDK 8 या उससे ऊपर।  
- **उदाहरण कौनसा आउटपुट फ़ॉर्मैट जनरेट करता है?** XPS (आप इसे PDF, PNG, आदि में बदल सकते हैं)।

## कस्टम TeX फ़ॉर्मैट क्या है?

कस्टम TeX फ़ॉर्मैट मैक्रो और प्रिमिटिव्स का एक प्री‑कम्पाइल्ड सेट है जो TeX इंजन को आपके विशिष्ट दस्तावेज़ शैली के अनुसार अनुकूलित करता है। अपना स्वयं का `.fmt` फ़ाइल प्रदान करके, आप फ़ॉन्ट्स, लेआउट नियम और कमांड परिभाषाओं को नियंत्रित कर सकते हैं बिना हर बार स्रोत TeX को संशोधित किए।

## क्यों उपयोग करें Aspose.TeX for Java?

- **Pure Java** – कोई नेटिव बाइनरी नहीं, किसी भी JVM‑आधारित प्रोजेक्ट में एम्बेड करना आसान।  
- **High fidelity** – ऐसा आउटपुट जनरेट करता है जो LaTeX‑स्टाइल रेंडरिंग से मेल खाता है।  
- **Extensible** – कस्टम फ़ॉर्मैट्स, कई आउटपुट डिवाइस और बैच प्रोसेसिंग को सपोर्ट करता है।  
- **License flexibility** – टेम्पररी लाइसेंस aspose से शुरू करें, फिर लाइव होने पर अपग्रेड करें।

## पूर्वापेक्षाएँ

शुरू करने से पहले, सुनिश्चित करें कि आपके पास है:

1. **Java Development Kit (JDK)** – JDK 8 या नया स्थापित हो। यदि अभी तक नहीं किया है तो आधिकारिक [Java website](https://www.oracle.com/java/technologies/javase-downloads.html) से डाउनलोड करें।  
2. **Aspose.TeX library for Java** – नवीनतम JAR को [Aspose.TeX for Java download page](https://releases.aspose.com/tex/java/) से प्राप्त करें।  
3. **Your custom TeX format file** – संकलित `.fmt` (जैसे `customtex.fmt`) को उस फ़ोल्डर में रखें जो आउटपुट डायरेक्टरी के रूप में कार्य करेगा।  

> **Pro tip:** यदि आप उत्पाद का मूल्यांकन कर रहे हैं, तो Aspose पोर्टल से *temporary license aspose* का अनुरोध करें; यह सीमित अवधि के लिए मूल्यांकन वॉटरमार्क को हटाता है।

## पैकेज इम्पोर्ट करें

पहले, अपने जावा प्रोजेक्ट में आवश्यक इम्पोर्ट्स जोड़ें। ये क्लासेज आपको फ़ॉर्मैट प्रोवाइडर, जॉब कॉन्फ़िगरेशन और रेंडरिंग डिवाइस तक पहुँच देती हैं।

```java
package com.aspose.tex.TypesetWithCustomTeXFormat;

import java.io.ByteArrayInputStream;
import java.io.IOException;

import com.aspose.tex.FormatProvider;
import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

## चरण‑दर‑चरण गाइड

### चरण 1: फ़ॉर्मैट प्रोवाइडर बनाएं

`FormatProvider` उस डायरेक्टरी की ओर इशारा करता है जिसमें आपका कस्टम TeX फ़ॉर्मैट फ़ाइल है। `"Your Output Directory"` को उस वास्तविक पथ से बदलें जहाँ `customtex.fmt` स्थित है।

```java
final FormatProvider formatProvider = new FormatProvider(
        new InputFileSystemDirectory("Your Output Directory"), "customtex");
```

### चरण 2: रूपांतरण विकल्प सेट करें

जॉब को ObjectTeX इंजन (जो कस्टम फ़ॉर्मैट्स को समझता है) का उपयोग करने के लिए कॉन्फ़िगर करें। यहाँ हम जॉब का नाम सेट करते हैं और इनपुट/आउटपुट कार्य डायरेक्टरी निर्दिष्ट करते हैं।

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX(formatProvider));
options.setJobName("typeset-with-custom-format");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### चरण 3: TeX जॉब चलाएँ

एक `TeXJob` इंस्टेंस बनाएं, उसे एक सरल TeX स्निपेट दें, और परिणाम को `XpsDevice` के साथ रेंडर करने को कहें। स्निपेट `\end` के साथ समाप्त होता है ताकि दस्तावेज़ बंद हो जाए।

```java
new TeXJob(new ByteArrayInputStream(
        "Congratulations! You have successfully typeset this text with your own TeX format!\\end".getBytes("ASCII")),
        new XpsDevice(), options).run();
```

### चरण 4: आउटपुट को अंतिम रूप दें

जॉब समाप्त होने के बाद, टर्मिनल आउटपुट में एक लाइन ब्रेक जोड़ें ताकि कंसोल साफ़ रहे।

```java
options.getTerminalOut().getWriter().newLine();
```

### चरण 5: फ़ॉर्मैट प्रोवाइडर बंद करें

जब आप समाप्त कर लें, प्रोवाइडर को बंद करें ताकि फ़ाइल हैंडल रिलीज़ हों और संसाधन मुक्त हों।

```java
formatProvider.close();
```

## सामान्य समस्याएँ और समाधान

| समस्या | कारण | समाधान |
|-------|-------|-----|
| **“Format file not found”** | `FormatProvider` में गलत पथ | `customtex.fmt` फ़ाइल और डायरेक्टरी सही और सुलभ हैं, यह सत्यापित करें। |
| **Encoding errors** | TeX स्ट्रिंग में गैर‑ASCII अक्षर | `"UTF-8"` एन्कोडिंग का उपयोग करें, `"ASCII"` के बजाय। |
| **Output not generated** | आउटपुट डायरेक्टरी में लिखने की अनुमति नहीं है | सुनिश्चित करें कि जावा प्रक्रिया को `"Your Output Directory"` में लिखने की अनुमति है। |
| **License watermark** | केवल मूल्यांकन लाइसेंस का उपयोग करना | परीक्षण के लिए *temporary license aspose* लागू करें या उत्पादन के लिए पूर्ण लाइसेंस खरीदें। |

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं Aspose.TeX को अन्य जावा लाइब्रेरीज़ के साथ उपयोग कर सकता हूँ?**  
**उत्तर:** बिल्कुल। API शुद्ध जावा है और Apache PDFBox, iText, या Spring Boot जैसी लाइब्रेरीज़ के साथ काम करता है।

**प्रश्न: मूल्यांकन के लिए मैं temporary license aspose कहाँ से प्राप्त कर सकता हूँ?**  
**उत्तर:** इसे [Aspose temporary license page](https://purchase.aspose.com/temporary-license/) से अनुरोध करें। यह 30 दिनों तक मूल्यांकन वॉटरमार्क को हटाता है।

**प्रश्न: क्या Aspose.TeX XPS के अलावा अन्य आउटपुट फ़ॉर्मैट्स को सपोर्ट करता है?**  
**उत्तर:** हाँ। आप अपनी आवश्यकता के अनुसार `new XpsDevice()` को `new PdfDevice()`, `new PngDevice()` आदि से बदल सकते हैं।

**प्रश्न: विफल हो रहे TeX जॉब को कैसे डिबग करें?**  
**उत्तर:** `options.setLogLevel(LogLevel.DEBUG);` कॉल करके विस्तृत लॉगिंग सक्षम करें और विस्तृत त्रुटि संदेशों के लिए कंसोल आउटपुट देखें।

**प्रश्न: क्या कोई मुफ्त ट्रायल उपलब्ध है?**  
**उत्तर:** हाँ – ट्रायल बाइनरीज़ को [Aspose.TeX download page](https://releases.aspose.com/tex/java/) से डाउनलोड करें।

## निष्कर्ष

अब आप जानते हैं **how to typeset tex** को जावा एप्लिकेशन में Aspose.TeX के साथ कस्टम TeX फ़ॉर्मैट का उपयोग करके कैसे टाइपसेट किया जाता है। ऊपर दिए गए चरणों का पालन करके, आप किसी भी जावा‑आधारित वर्कफ़्लो में उच्च‑गुणवत्ता वाला टाइपसेटिंग एकीकृत कर सकते हैं, अपने स्वयं के फ़ॉर्मैट फ़ाइलों के साथ प्रयोग कर सकते हैं, और उचित लाइसेंस के साथ प्रोटोटाइप से उत्पादन तक जा सकते हैं।

---

**Last Updated:** 2025-12-05  
**Tested With:** Aspose.TeX for Java 24.10  
**Author:** Aspose  
**Related Resources:** [Aspose.TeX API Reference](https://docs.aspose.com/tex/java/) | [Download Free Trial](https://releases.aspose.com/tex/java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}