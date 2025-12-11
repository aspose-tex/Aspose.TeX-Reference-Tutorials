---
date: 2025-12-09
description: जावा में लेटेक्स आकृतियों को SVG में रेंडर करना सीखें और Aspose.TeX का
  उपयोग करके जावा में लेटेक्स PNG विकल्पों को बदलना खोजें। सहज एकीकरण के लिए इस चरण‑दर‑चरण
  मार्गदर्शिका का पालन करें।
linktitle: How to Render LaTeX Figures to SVG in Java
second_title: Aspose.TeX Java API
title: जावा में LaTeX चित्रों को SVG में कैसे रेंडर करें
url: /hi/java/customizing-output/render-lafigures-svg/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा में LaTeX फ़िगर्स को SVG में रेंडर कैसे करें

Java एप्लिकेशन में LaTeX फ़िगर्स बनाना और रेंडर करना कठिन लग सकता है, लेकिन रिपोर्ट, वैज्ञानिक पेपर या वेब कंटेंट के लिए उच्च‑गुणवत्ता, स्केलेबल ग्राफ़िक्स की आवश्यकता अक्सर होती है। इस ट्यूटोरियल में आप **LaTeX फ़िगर्स को सीधे SVG में रेंडर करने** का तरीका सीखेंगे, और यह भी देखेंगे कि जब रास्टर इमेज की आवश्यकता हो तो वही Aspose.TeX इंजन **java convert latex png** वर्कफ़्लो के लिए कैसे उपयोग किया जा सकता है।

## त्वरित उत्तर
- **ट्यूटोरियल में कौन सी लाइब्रेरी उपयोग की गई है?** Aspose.TeX for Java  
- **कौन सा आउटपुट फ़ॉर्मेट दिखाया गया है?** स्केलेबल वेक्टर ग्राफ़िक्स (SVG)  
- **क्या मैं PNG इमेज भी बना सकता हूँ?** हाँ – वही रेंडरर क्लास बदलकर PNG आउटपुट कर सकता है।  
- **क्या प्रोडक्शन उपयोग के लिए लाइसेंस चाहिए?** मूल्यांकन के लिए एक टेम्पररी लाइसेंस उपलब्ध है; व्यावसायिक प्रोजेक्ट्स के लिए पूर्ण लाइसेंस आवश्यक है।  
- **कौन सा Java संस्करण समर्थित है?** Aspose.TeX के साथ कोई भी Java 8+ रनटाइम काम करता है।

## जावा में “how to render latex” क्या है?
LaTeX को रेंडर करना मतलब वैज्ञानिक टाइपसेटिंग के लिए उपयोग की जाने वाली मार्कअप भाषा को एक दृश्य प्रतिनिधित्व में बदलना है जिसे आपका प्रोग्राम प्रदर्शित या सहेज सके। Aspose.TeX LaTeX स्रोत को पार्स करता है, पैकेज प्रोसेस करता है, और आपके द्वारा चुने गए फ़ॉर्मेट में ग्राफ़िक्स बनाता है – हमारे मामले में SVG।

## LaTeX फ़िगर्स को SVG में रेंडर क्यों करें?
- **स्केलेबिलिटी:** SVG बिना गुणवत्ता खोए स्केल होता है, रिस्पॉन्सिव UI या हाई‑रेज़ोल्यूशन प्रिंट के लिए परफेक्ट।  
- **एडिटेबिलिटी:** SVG फ़ाइलें वेक्टर ग्राफ़िक्स एडिटर्स में अभी भी एडिटेबल रहती हैं।  
- **परफ़ॉर्मेंस:** लाइन‑आर्ट और डायग्राम के लिए वेक्टर ग्राफ़िक्स अक्सर रास्टर समकक्षों से छोटे होते हैं।  

## पूर्वापेक्षाएँ
- Java डेवलपमेंट एनवायरनमेंट (JDK 8 या नया)।  
- Aspose.TeX for Java – आधिकारिक [download link](https://releases.aspose.com/tex/java/) से डाउनलोड करें।  
- LaTeX फ़िगर सिंटैक्स (जैसे `picture` environment) की बुनियादी समझ।  

## पैकेज इम्पोर्ट करें
पहले, आवश्यक Aspose.TeX क्लासेज़ को अपने प्रोजेक्ट में लाएँ।

```java
package com.aspose.tex.SvgLaTeXFigureRenderer;

import java.awt.Color;
import java.io.ByteArrayOutputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.OutputStream;

import com.aspose.tex.SvgFigureRenderer;
import com.aspose.tex.SvgFigureRendererOptions;

import util.Utils;
```

## चरण 1: रेंडरिंग विकल्प सेट करें
रेंडरर को LaTeX स्रोत को कैसे प्रोसेस करना है, जैसे स्केलिंग और बैकग्राउंड, कॉन्फ़िगर करें।

```java
SvgFigureRendererOptions options = new SvgFigureRendererOptions();
options.setPreamble("\\usepackage{pict2e}");
options.setScale(3000);
options.setBackgroundColor(Color.WHITE);
options.setLogStream(new ByteArrayOutputStream());
options.showTerminal(true);
```

## चरण 2: LaTeX फ़िगर और आउटपुट डायरेक्टरी परिभाषित करें
वह फ़िगर निर्दिष्ट करें जिसे आप रेंडर करना चाहते हैं और SVG फ़ाइल कहाँ सेव होगी।

```java
com.aspose.tex.Size2D size = new com.aspose.tex.Size2D.Float();
final OutputStream stream = new FileOutputStream("Your Output Directory" + "text-and-formula.svg");
```

## चरण 3: रेंडरिंग चलाएँ
LaTeX स्रोत को रेंडरर के साथ आउटपुट स्ट्रीम, विकल्प और साइज प्लेसहोल्डर के साथ पास करें।

```java
new SvgFigureRenderer().render("\\setlength{\\unitlength}{0.8cm}\r\n" +
    // LaTeX figure content
    "\\begin{picture}(6,5)\r\n" +
    // ... (figure details)
    "\\end{picture}", stream, options, size);
```

## चरण 4: आउटपुट स्ट्रीम बंद करें
सिस्टम रिसोर्सेज़ को रिलीज़ करने के लिए हमेशा स्ट्रीम को बंद करें।

```java
if (stream != null)
    stream.close();
```

## चरण 5: परिणाम दिखाएँ
रेंडरिंग के बाद, आप किसी भी एरर मैसेज और अंतिम इमेज डाइमेंशन को देख सकते हैं।

```java
System.out.println(options.getErrorReport());
System.out.println();
System.out.println("Size: " + size.getWidth() + "x" + size.getHeight());
```

इन चरणों का पालन करके आप Aspose.TeX for Java का उपयोग करके LaTeX फ़िगर्स को सहजता से SVG में रेंडर कर सकते हैं।

## सामान्य समस्याएँ और समाधान
- **पैकेज गायब:** यदि आपका फ़िगर डिफ़ॉल्ट प्रीऐम्बल में न शामिल पैकेज उपयोग करता है, तो `options.setPreamble("\\usepackage{...}")` के माध्यम से जोड़ें।  
- **गलत यूनिट लंबाई:** `\\setlength{\\unitlength}{...}` को अपनी आवश्यक स्केल के अनुसार समायोजित करें।  
- **फ़ाइल परमिशन त्रुटियाँ:** सुनिश्चित करें कि आउटपुट डायरेक्टरी मौजूद है और आपके एप्लिकेशन को लिखने की अनुमति है।

## अक्सर पूछे जाने वाले प्रश्न

**Q1: क्या मैं Aspose.TeX के साथ जटिल गणितीय अभिव्यक्तियों वाले LaTeX फ़िगर्स रेंडर कर सकता हूँ?**  
A: हाँ, Aspose.TeX जटिल गणितीय मार्कअप को पूरी तरह सपोर्ट करता है और इसे सटीक रूप से SVG में रेंडर करेगा।

**Q2: क्या Aspose.TeX for Java के लिए एक टेम्पररी लाइसेंस उपलब्ध है?**  
A: हाँ, आप इसे [here](https://purchase.aspose.com/temporary-license/) से प्राप्त कर सकते हैं।

**Q3: मैं Aspose.TeX for Java के लिए सपोर्ट कैसे प्राप्त करूँ?**  
A: समुदाय‑आधारित सहायता के लिए [Aspose.TeX forum](https://forum.aspose.com/c/tex/47) पर जाएँ।

**Q4: Aspose.TeX के साथ मैं LaTeX फ़िगर्स को किन फ़ॉर्मेट्स में बदल सकता हूँ?**  
A: SVG के अलावा, आप PNG, JPEG, PDF और अन्य रास्टर या वेक्टर फ़ॉर्मेट्स में आउटपुट कर सकते हैं।

**Q5: Aspose.TeX for Java की विस्तृत डॉक्यूमेंटेशन कहाँ मिल सकती है?**  
A: व्यापक API विवरण के लिए [Aspose.TeX documentation](https://reference.aspose.com/tex/java/) देखें।

---

**अंतिम अपडेट:** 2025-12-09  
**टेस्टेड संस्करण:** Aspose.TeX 24.11 for Java  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}