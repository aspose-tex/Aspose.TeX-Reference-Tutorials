---
title: जावा में LaTeX गणित को PNG में प्रस्तुत करें
linktitle: जावा में LaTeX गणित को PNG में प्रस्तुत करें
second_title: Aspose.TeX जावा एपीआई
description: Aspose.TeX के साथ जावा में PNG छवियों के लिए LaTeX गणित समीकरण प्रस्तुत करना सीखें। निर्बाध एकीकरण और असाधारण प्रदर्शन के लिए चरण-दर-चरण मार्गदर्शिका।
weight: 13
url: /hi/java/customizing-output/render-lamath-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा में LaTeX गणित को PNG में प्रस्तुत करें

## परिचय

जावा प्रोग्रामिंग की गतिशील दुनिया में, LaTeX गणित को PNG छवियों में प्रस्तुत करना एक सामान्य आवश्यकता है। जावा के लिए Aspose.TeX इस कार्य के लिए एक शक्तिशाली समाधान प्रदान करता है, जो निर्बाध एकीकरण और असाधारण प्रदर्शन प्रदान करता है। इस ट्यूटोरियल में, हम Aspose.TeX का उपयोग करके LaTeX गणित समीकरणों को PNG प्रारूप में प्रस्तुत करने की प्रक्रिया से गुजरेंगे।

## आवश्यक शर्तें

ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

- जावा विकास वातावरण: सुनिश्चित करें कि आपकी मशीन पर जावा विकास वातावरण स्थापित है।

-  जावा के लिए Aspose.TeX: जावा के लिए Aspose.TeX को डाउनलोड और इंस्टॉल करें[डाउनलोड पेज](https://releases.aspose.com/tex/java/).

## पैकेज आयात करें

अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करके शुरुआत करें। यह सुनिश्चित करता है कि आपके पास LaTeX रेंडरिंग के लिए आवश्यक कक्षाओं और विधियों तक पहुंच है।

```java
package com.aspose.tex.PngLaTeXMathRenderer;

import java.awt.Color;
import java.io.ByteArrayOutputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.OutputStream;

import com.aspose.tex.PngMathRenderer;
import com.aspose.tex.PngMathRendererOptions;

import util.Utils;
```

## चरण 1: रेंडरिंग विकल्प सेट करें

सबसे पहले, LaTeX रेंडरिंग प्रक्रिया को अनुकूलित करने के लिए रेंडरिंग विकल्प बनाएं। रिज़ॉल्यूशन, प्रस्तावना, स्केलिंग फ़ैक्टर, टेक्स्ट का रंग, पृष्ठभूमि का रंग और बहुत कुछ जैसे पैरामीटर सेट करें।

```java
//छवि रिज़ॉल्यूशन को 150 डीपीआई पर सेट करके रेंडरिंग विकल्प बनाएं।
PngMathRendererOptions options = new PngMathRendererOptions();
options.setResolution(150);
options.setPreamble("\\usepackage{amsmath}\r\n\\usepackage{amsfonts}\r\n\\usepackage{amssymb}\r\n\\usepackage{color}");
options.setScale(3000);
options.setTextColor(Color.BLACK);
options.setBackgroundColor(Color.WHITE);
options.setLogStream(new ByteArrayOutputStream());
options.showTerminal(true);
```

## चरण 2: आउटपुट आयाम परिभाषित करें

परिणामी छवि के आयामों को संग्रहीत करने के लिए एक वेरिएबल बनाएं।

```java
com.aspose.tex.Size2D size = new com.aspose.tex.Size2D.Float();
```

## चरण 3: LaTeX गणित को PNG में प्रस्तुत करें

LaTeX गणित समीकरण को PNG छवि में प्रस्तुत करने के लिए PngMathRenderer वर्ग का उपयोग करें। LaTeX समीकरण, आउटपुट स्ट्रीम, रेंडरिंग विकल्प और आकार चर निर्दिष्ट करें।

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + "math-formula.png");
try {
    new PngMathRenderer().render("\\begin{equation*}\r\n" +
        "e^x = x^{\\color{red}0} + x^{\\color{red}1} + \\frac{x^{\\color{red}2}}{2} + \\frac{x^{\\color{red}3}}{6} + \\cdots = \\sum_{n\\geq 0} \\frac{x^{\\color{red}n}}{n!}\r\n" +
        "\\end{equation*}", stream, options, size);
} finally {
    if (stream != null)
        stream.close();
}
```

## चरण 4: परिणाम प्रदर्शित करें

अंत में, रेंडरिंग प्रक्रिया के बारे में अतिरिक्त जानकारी प्रदर्शित करें, जैसे त्रुटि रिपोर्ट और परिणामी छवि का आकार।

```java
System.out.println(options.getErrorReport());
System.out.println();
System.out.println("Size: " + size.getWidth() + "x" + size.getHeight());
```

## निष्कर्ष

बधाई हो! आपने Aspose.TeX का उपयोग करके जावा में PNG छवियों में LaTeX गणित समीकरणों को प्रस्तुत करना सफलतापूर्वक सीख लिया है। यह शक्तिशाली लाइब्रेरी जटिल रेंडरिंग कार्यों को सरल बनाती है, डेवलपर्स को गणितीय अभिव्यक्तियों को संभालने के लिए एक मजबूत उपकरण प्रदान करती है।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं प्रस्तुत गणित समीकरणों के रंग को अनुकूलित कर सकता हूँ?

 A1: हाँ, आप सेटिंग करके टेक्स्ट का रंग कस्टमाइज़ कर सकते हैं`setTextColor` रेंडरिंग विकल्पों में विधि।

### Q2: मैं जेनरेट की गई पीएनजी छवि के लिए आउटपुट निर्देशिका कैसे बदल सकता हूं?

 A2: आउटपुट निर्देशिका पथ को संशोधित करें`FileOutputStream` चरण 3 में कंस्ट्रक्टर।

### Q3: क्या जावा के लिए Aspose.TeX द्वारा समर्थित अन्य आउटपुट प्रारूप हैं?

A3: नवीनतम संस्करण के अनुसार, Aspose.TeX मुख्य रूप से PNG प्रारूप में रेंडरिंग का समर्थन करता है। समर्थित प्रारूपों पर अपडेट के लिए दस्तावेज़ की जाँच करें।

### Q4: क्या Aspose.TeX के लिए अस्थायी लाइसेंस उपलब्ध है?

 उ4: हाँ, आप Aspose.TeX के लिए एक अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).

### Q5: मैं Aspose.TeX से संबंधित मुद्दों पर कहां सहायता मांग सकता हूं या चर्चा कर सकता हूं?

 A5: पर जाएँ[Aspose.TeX फोरम](https://forum.aspose.com/c/tex/47) समर्थन मांगने, प्रश्न पूछने और समुदाय के साथ जुड़ने के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
