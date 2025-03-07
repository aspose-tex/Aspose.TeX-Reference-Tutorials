---
title: जावा में LaTeX गणित को SVG में प्रस्तुत करें
linktitle: जावा में LaTeX गणित को SVG में प्रस्तुत करें
second_title: Aspose.TeX जावा एपीआई
description: Aspose.TeX का उपयोग करके जावा में SVG में LaTeX गणित समीकरणों को प्रस्तुत करना सीखें। सटीक और आकर्षक परिणामों के लिए हमारी चरण-दर-चरण मार्गदर्शिका का पालन करें।
weight: 15
url: /hi/java/customizing-output/render-lamath-svg/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा में LaTeX गणित को SVG में प्रस्तुत करें

## परिचय

Aspose.TeX का उपयोग करके जावा में SVG में LaTeX गणित समीकरण प्रस्तुत करने पर इस व्यापक मार्गदर्शिका में आपका स्वागत है। चाहे आप एक अनुभवी डेवलपर हों या सिर्फ जावा से शुरुआत कर रहे हों, यह ट्यूटोरियल आपको चरण दर चरण प्रक्रिया के बारे में बताएगा, यह सुनिश्चित करते हुए कि आप सटीक और आकर्षक परिणाम प्राप्त करें। 

## आवश्यक शर्तें

इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

- जावा प्रोग्रामिंग की बुनियादी समझ.
- एक कार्यशील जावा विकास वातावरण।
-  जावा लाइब्रेरी के लिए Aspose.TeX स्थापित किया गया। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tex/java/).

## पैकेज आयात करें

इस चरण में, हम LaTeX गणित रेंडरिंग प्रक्रिया को शुरू करने के लिए आवश्यक पैकेज आयात करेंगे। सुनिश्चित करें कि आपने अपने जावा कोड में निम्नलिखित पैकेज शामिल किए हैं:

```java
package com.aspose.tex.SvgLaTeXMathRenderer;

import java.awt.Color;
import java.io.ByteArrayOutputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.OutputStream;

import com.aspose.tex.MathRendererOptions;
import com.aspose.tex.SvgMathRenderer;
import com.aspose.tex.SvgMathRendererOptions;

import util.Utils;
```

## SVG को LaTeX गणित प्रस्तुत करना

आइए प्रक्रिया में आपका मार्गदर्शन करने के लिए उदाहरण को कई चरणों में विभाजित करें।

### चरण 1: रेंडरिंग विकल्प बनाएं

```java
MathRendererOptions options = new SvgMathRendererOptions();
options.setPreamble("\\usepackage{amsmath}\r\n\\usepackage{amsfonts}\r\n\\usepackage{amssymb}\r\n\\usepackage{color}");
options.setScale(3000);
options.setTextColor(Color.BLACK);
options.setBackgroundColor(Color.WHITE);
options.setLogStream(new ByteArrayOutputStream());
options.showTerminal(true);
```

इस चरण में, हम प्रस्तावना, स्केलिंग कारक, पाठ और पृष्ठभूमि रंग, लॉग स्ट्रीम और टर्मिनल डिस्प्ले प्राथमिकताओं को निर्दिष्ट करते हुए रेंडरिंग विकल्प सेट करते हैं।

### चरण 2: आउटपुट आयाम और स्ट्रीम सेट करें

```java
com.aspose.tex.Size2D size = new com.aspose.tex.Size2D.Float();
final OutputStream stream = new FileOutputStream("Your Output Directory" + "math-formula.svg");
```

यहां, हम आउटपुट छवि के आयामों को परिभाषित करते हैं और एसवीजी फ़ाइल के लिए आउटपुट स्ट्रीम बनाते हैं।

### चरण 3: रेंडरिंग चलाएँ

```java
new SvgMathRenderer().render("\\begin{equation*}\r\n" +
    "e^x = x^{\\color{red}0} + x^{\\color{red}1} + \\frac{x^{\\color{red}2}}{2} + \\frac{x^{\\color{red}3}}{6} + \\cdots = \\sum_{n\\geq 0} \\frac{x^{\\color{red}n}}{n!}\r\n" +
    "\\end{equation*}", stream, options, size);
```

यह मुख्य चरण है जहां वास्तविक प्रतिपादन होता है। अपना LaTeX गणित समीकरण, आउटपुट स्ट्रीम, विकल्प और आकार प्रदान करें।

### चरण 4: परिणाम प्रदर्शित करें

```java
System.out.println(options.getErrorReport());
System.out.println();
System.out.println("Size: " + size.getWidth() + "x" + size.getHeight());
```

अंत में, किसी भी त्रुटि रिपोर्ट और परिणामी छवि का आकार प्रदर्शित करें।

## निष्कर्ष

बधाई हो! आपने Aspose.TeX का उपयोग करके जावा में SVG के लिए LaTeX गणित समीकरणों को सफलतापूर्वक प्रस्तुत किया है। यह चरण-दर-चरण मार्गदर्शिका यह सुनिश्चित करती है कि आप प्रक्रिया के प्रत्येक पहलू को समझें, जिससे यह किसी भी कौशल स्तर पर डेवलपर्स के लिए सुलभ हो सके।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या Aspose.TeX अन्य जावा लाइब्रेरीज़ के साथ संगत है?

A1: Aspose.TeX को आपकी परियोजनाओं में लचीलापन प्रदान करते हुए, अन्य जावा लाइब्रेरीज़ के साथ सहजता से काम करने के लिए डिज़ाइन किया गया है।

### Q2: क्या मैं प्रस्तुत समीकरणों के स्वरूप को अनुकूलित कर सकता हूँ?

ए2: बिल्कुल! रेंडरिंग विकल्प आपको रंग, स्केलिंग और विभिन्न अन्य दृश्य पहलुओं को नियंत्रित करने की अनुमति देते हैं।

### Q3: क्या Aspose.TeX समर्थन के लिए कोई सामुदायिक मंच है?

 उ3: हाँ, आप सहायता प्राप्त कर सकते हैं और समुदाय के साथ जुड़ सकते हैं[Aspose.TeX फोरम](https://forum.aspose.com/c/tex/47).

### Q4: मैं Aspose.TeX के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?

 ए4: विजिट करें[यहाँ](https://purchase.aspose.com/temporary-license/) अस्थायी लाइसेंस की जानकारी के लिए.

### Q5: मुझे अधिक विस्तृत दस्तावेज कहां मिल सकते हैं?

 A5: यहां विस्तृत दस्तावेज़ देखें[Aspose.TeX जावा दस्तावेज़ीकरण](https://reference.aspose.com/tex/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
