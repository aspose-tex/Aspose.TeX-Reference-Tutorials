---
date: 2026-02-10
description: जानें कि कैसे कस्टम TeX फ़ॉर्मेट बनाएं और Aspose.TeX for Java का उपयोग
  करके TeX Java को टाइपसेट करें, जिसमें चरण‑दर‑चरण सेटअप, कस्टम फ़ॉर्मेट हैंडलिंग,
  और अस्थायी लाइसेंस प्राप्त करना शामिल है।
linktitle: How to Typeset TeX with Custom Formats in Java
second_title: Aspose.TeX Java API
title: जावा में कस्टम TeX फ़ॉर्मेट कैसे बनाएं और TeX टाइपसेट करें
url: /hi/java/custom-tex-formats/typesetting-custom-tex-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा में कस्टम TeX फ़ॉर्मेट कैसे बनाएं और TeX को टाइपसेट करें

## परिचय

यदि आपको **कस्टम tex फ़ॉर्मेट बनाना** है और जावा एप्लिकेशन के भीतर TeX को टाइपसेट करना है, तो Aspose.TeX कस्टम TeX फ़ॉर्मेट फ़ाइलों के साथ काम करने का एक साफ़, उच्च‑प्रदर्शन तरीका प्रदान करता है। इस ट्यूटोरियल में हम आपको वह सब दिखाएंगे जिसकी आपको आवश्यकता है—पर्यावरण सेटअप से लेकर आपके अपने फ़ॉर्मेट का उपयोग करने वाले TeX जॉब को चलाने तक। चाहे आप एक वैज्ञानिक प्रकाशन टूल बना रहे हों या एक कस्टम रिपोर्ट जेनरेटर, नीचे दिए गए चरण आपको जल्दी से शुरू करने में मदद करेंगे।

## त्वरित उत्तर
- **मुझे कौनसी लाइब्रेरी चाहिए?** Aspose.TeX for Java  
- **क्या मैं कस्टम TeX फ़ॉर्मेट उपयोग कर सकता हूँ?** हाँ – बस `FormatProvider` को अपनी फ़ाइल की ओर इंगित करें।  
- **क्या मुझे विकास के लिए लाइसेंस चाहिए?** परीक्षण के लिए एक temporary license aspose काम करता है; उत्पादन के लिए पूर्ण लाइसेंस आवश्यक है।  
- **कौनसा जावा संस्करण समर्थित है?** JDK 8 या उससे ऊपर।  
- **उदाहरण कौनसा आउटपुट फ़ॉर्मेट जनरेट करता है?** XPS (आप अपनी आवश्यकता अनुसार PDF, PNG, आदि में बदल सकते हैं)।

## कस्टम TeX फ़ॉर्मेट क्या है?
कस्टम TeX फ़ॉर्मेट मैक्रोज़ और प्रिमिटिव्स का एक प्री‑कम्पाइल्ड सेट है जो TeX इंजन को आपके विशिष्ट दस्तावेज़ शैली के अनुसार ढालता है। अपना स्वयं का `.fmt` फ़ाइल प्रदान करके आप फ़ॉन्ट्स, लेआउट नियम, और कमांड परिभाषाओं को नियंत्रित कर सकते हैं बिना हर बार स्रोत TeX को बदलें।

## जावा के लिए Aspose.TeX क्यों उपयोग करें?
- **Pure Java** – कोई नेटिव बाइनरी नहीं, किसी भी JVM‑आधारित प्रोजेक्ट में एम्बेड करना आसान।  
- **High fidelity** – ऐसा आउटपुट जनरेट करता है जो LaTeX‑स्टाइल रेंडरिंग से मेल खाता है।  
- **Extensible** – कस्टम फ़ॉर्मेट, कई आउटपुट डिवाइस, और बैच प्रोसेसिंग को सपोर्ट करता है।  
- **License flexibility** – पहले एक temporary license aspose से शुरू करें, फिर लाइव होने पर अपग्रेड करें।

## पूर्वापेक्षाएँ

शुरू करने से पहले सुनिश्चित करें कि आपके पास है:

1. **Java Development Kit (JDK)** – JDK 8 या नया स्थापित हो। यदि अभी तक नहीं किया है तो आधिकारिक [Java website](https://www.oracle.com/java/technologies/javase-downloads.html) से डाउनलोड करें।  
2. **Aspose.TeX library for Java** – नवीनतम JAR को [Aspose.TeX for Java download page](https://releases.aspose.com/tex/java/) से प्राप्त करें।  
3. **Your custom TeX format file** – संकलित `.fmt` (जैसे `customtex.fmt`) को उस फ़ोल्डर में रखें जो आउटपुट डायरेक्टरी के रूप में कार्य करेगा।  

> **Pro tip:** यदि आप उत्पाद का मूल्यांकन कर रहे हैं, तो Aspose पोर्टल से *temporary license aspose* का अनुरोध करें; यह सीमित अवधि के लिए मूल्यांकन वॉटरमार्क को हटा देता है।

## इम्पोर्ट पैकेज

सबसे पहले, अपने जावा प्रोजेक्ट में आवश्यक इम्पोर्ट जोड़ें। ये क्लासेज़ आपको फ़ॉर्मेट प्रोवाइडर, जॉब कॉन्फ़िगरेशन, और रेंडरिंग डिवाइस तक पहुँच देती हैं।

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

## स्टेप‑बाय‑स्टेप गाइड

### स्टेप 1: फ़ॉर्मेट प्रोवाइडर बनाएं

`FormatProvider` उस डायरेक्टरी की ओर इशारा करता है जिसमें आपका कस्टम TeX फ़ॉर्मेट फ़ाइल है। `"Your Output Directory"` को वास्तविक पथ से बदलें जहाँ `customtex.fmt` स्थित है।

```java
final FormatProvider formatProvider = new FormatProvider(
        new InputFileSystemDirectory("Your Output Directory"), "customtex");
```

### स्टेप 2: रूपांतरण विकल्प सेट करें

जॉब को ObjectTeX इंजन (जो कस्टम फ़ॉर्मेट समझता है) उपयोग करने के लिए कॉन्फ़िगर करें। यहाँ हम जॉब का नाम सेट करते हैं और इनपुट/आउटपुट वर्किंग डायरेक्टरी निर्दिष्ट करते हैं।

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX(formatProvider));
options.setJobName("typeset-with-custom-format");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### स्टेप 3: TeX जॉब चलाएँ

एक `TeXJob` इंस्टेंस बनाएं, उसे एक सरल TeX स्निपेट दें, और `XpsDevice` के साथ परिणाम रेंडर करने को कहें। स्निपेट `\end` पर समाप्त होता है जिससे दस्तावेज़ बंद हो जाता है।

```java
new TeXJob(new ByteArrayInputStream(
        "Congratulations! You have successfully typeset this text with your own TeX format!\\end".getBytes("ASCII")),
        new XpsDevice(), options).run();
```

### स्टेप 4: आउटपुट को अंतिम रूप दें

जॉब समाप्त होने के बाद, टर्मिनल आउटपुट में एक लाइन ब्रेक जोड़ें ताकि कंसोल साफ़ रहे।

```java
options.getTerminalOut().getWriter().newLine();
```

### स्टेप 5: फ़ॉर्मेट प्रोवाइडर बंद करें

जब आप समाप्त कर लें, प्रोवाइडर को बंद करें ताकि फ़ाइल हैंडल रिलीज़ हो जाएँ और संसाधन मुक्त हों।

```java
formatProvider.close();
```

## सामान्य उपयोग केस

- **ऑटोमेटेड वैज्ञानिक पेपर जनरेशन** – ऐसा प्री‑कम्पाइल्ड फ़ॉर्मेट उपयोग करें जिसमें जर्नल‑स्पेसिफिक मैक्रोज़ एम्बेड हों।  
- **डायनामिक रिपोर्ट निर्माण** – हर बार LaTeX स्रोत को पुनः बनाये बिना इनवॉइस या सर्टिफ़िकेट ऑन‑द‑फ़्लाई जनरेट करें।  
- **बड़े दस्तावेज़ संग्रह की बैच प्रोसेसिंग** – एक बार कस्टम फ़ॉर्मेट लोड करें और सैकड़ों फ़ाइलों के लिए पुनः उपयोग करें, जिससे प्रोसेसिंग समय काफी घटे।

## सामान्य समस्याएँ और समाधान

| समस्या | कारण | समाधान |
|-------|-------|-----|
| **“Format file not found”** | `FormatProvider` में गलत पथ | डायरेक्टरी और फ़ाइलनाम (`customtex.fmt`) को सही और एक्सेसिबल होने की पुष्टि करें। |
| **Encoding errors** | TeX स्ट्रिंग में गैर‑ASCII अक्षर | UTF‑8 एन्कोडिंग उपयोग करें (`"UTF-8"` बजाय `"ASCII"`)। |
| **Output not generated** | आउटपुट डायरेक्टरी में लिखने की अनुमति नहीं | सुनिश्चित करें कि जावा प्रोसेस को `"Your Output Directory"` में लिखने की अनुमति है। |
| **License watermark** | केवल एवाल्यूएशन लाइसेंस उपयोग कर रहे हैं | परीक्षण के लिए *temporary license aspose* लागू करें या उत्पादन के लिए पूर्ण लाइसेंस खरीदें। |

**संबंधित संसाधन:** [Aspose.TeX API Reference](https://docs.aspose.com/tex/java/) | [Download Free Trial](https://releases.aspose.com/tex/java/)

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं Aspose.TeX को अन्य जावा लाइब्रेरीज़ के साथ उपयोग कर सकता हूँ?**  
A: बिल्कुल। API शुद्ध जावा है और Apache PDFBox, iText, या Spring Boot जैसी लाइब्रेरीज़ के साथ सहजता से काम करता है।

**Q: मूल्यांकन के लिए temporary license aspose कहाँ से प्राप्त करूँ?**  
A: इसे [Aspose temporary license page](https://purchase.aspose.com/temporary-license/) से अनुरोध करें। यह 30 दिनों तक एवाल्यूएशन वॉटरमार्क को हटा देता है।

**Q: क्या Aspose.TeX XPS के अलावा अन्य आउटपुट फ़ॉर्मेट सपोर्ट करता है?**  
A: हाँ। आप `new XpsDevice()` को `new PdfDevice()`, `new PngDevice()` आदि से बदल सकते हैं, आपकी आवश्यकता के अनुसार।

**Q: फेल हो रहे TeX जॉब को कैसे डिबग करूँ?**  
A: `options.setLogLevel(LogLevel.DEBUG);` कॉल करके विस्तृत लॉगिंग सक्षम करें और कंसोल आउटपुट में विस्तृत त्रुटि संदेश देखें।

**Q: क्या कोई फ्री ट्रायल उपलब्ध है?**  
A: हाँ – ट्रायल बाइनरीज़ को [Aspose.TeX download page](https://releases.aspose.com/tex/java/) से डाउनलोड करें।

**Q: क्या मैं एक ही एप्लिकेशन में कई कस्टम फ़ॉर्मेट बना सकता हूँ?**  
A: हाँ। प्रत्येक `.fmt` फ़ाइल के लिए एक अलग `FormatProvider` इंस्टैंसिएट करें और उपयुक्त प्रोवाइडर को `TeXConfig.objectTeX()` में पास करें।

## निष्कर्ष

आप अब जानते हैं **कस्टम tex फ़ॉर्मेट कैसे बनाएं** और **जावा एप्लिकेशन में tex को कैसे टाइपसेट करें** Aspose.TeX का उपयोग करके। ऊपर दिए गए चरणों का पालन करके आप किसी भी जावा‑आधारित वर्कफ़्लो में उच्च‑गुणवत्ता टाइपसेटिंग को एकीकृत कर सकते हैं, अपने स्वयं के फ़ॉर्मेट फ़ाइलों के साथ प्रयोग कर सकते हैं, और उचित लाइसेंस के साथ प्रोटोटाइप से प्रोडक्शन तक आसानी से पहुँच सकते हैं।

---

**अंतिम अपडेट:** 2026-02-10  
**परीक्षित संस्करण:** Aspose.TeX for Java 24.10  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}