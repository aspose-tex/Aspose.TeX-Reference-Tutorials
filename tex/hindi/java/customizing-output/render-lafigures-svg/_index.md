---
title: जावा में SVG के लिए LaTeX आंकड़े प्रस्तुत करें
linktitle: जावा में SVG के लिए LaTeX आंकड़े प्रस्तुत करें
second_title: Aspose.TeX जावा एपीआई
description: Aspose.TeX का उपयोग करके जावा में SVG में आसानी से LaTeX आंकड़े प्रस्तुत करना सीखें। निर्बाध एकीकरण के लिए इस चरण-दर-चरण मार्गदर्शिका का पालन करें।
weight: 14
url: /hi/java/customizing-output/render-lafigures-svg/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा में SVG के लिए LaTeX आंकड़े प्रस्तुत करें

## परिचय

जावा में LaTeX आंकड़े बनाना और प्रस्तुत करना विभिन्न अनुप्रयोगों के लिए एक जटिल लेकिन महत्वपूर्ण कार्य हो सकता है। इस ट्यूटोरियल में, हम यह पता लगाएंगे कि Java के लिए Aspose.TeX का उपयोग करके SVG में LaTeX आंकड़े कैसे प्रस्तुत किए जाएं। Aspose.TeX, LaTeX दस्तावेजों को संभालने और उन्हें SVG सहित विभिन्न प्रारूपों में परिवर्तित करने के लिए शक्तिशाली कार्यक्षमता प्रदान करता है।

## आवश्यक शर्तें

ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:

- जावा विकास वातावरण: सुनिश्चित करें कि आपके सिस्टम पर जावा विकास वातावरण स्थापित है।
-  जावा के लिए Aspose.TeX: जावा के लिए Aspose.TeX लाइब्रेरी को डाउनलोड और इंस्टॉल करें[लिंक को डाउनलोड करें](https://releases.aspose.com/tex/java/).
- LaTeX की बुनियादी समझ: बुनियादी LaTeX सिंटैक्स और आकृति निर्माण से खुद को परिचित करें।

## पैकेज आयात करें

आरंभ करने के लिए, Aspose.TeX से आवश्यक पैकेज आयात करें। ये पैकेज एसवीजी को लाटेक्स आंकड़े प्रस्तुत करने के लिए आवश्यक उपकरण प्रदान करेंगे।

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

प्रस्तावना, स्केलिंग कारक, पृष्ठभूमि रंग, लॉग स्ट्रीम और टर्मिनल आउटपुट दृश्यता जैसे पैरामीटर निर्दिष्ट करते हुए, रेंडरिंग विकल्प बनाएं।

```java
SvgFigureRendererOptions options = new SvgFigureRendererOptions();
options.setPreamble("\\usepackage{pict2e}");
options.setScale(3000);
options.setBackgroundColor(Color.WHITE);
options.setLogStream(new ByteArrayOutputStream());
options.showTerminal(true);
```

## चरण 2: LaTeX चित्र और आउटपुट निर्देशिका को परिभाषित करें

उस LaTeX आकृति को परिभाषित करें जिसे आप प्रस्तुत करना चाहते हैं और SVG फ़ाइल के लिए आउटपुट निर्देशिका निर्दिष्ट करें।

```java
com.aspose.tex.Size2D size = new com.aspose.tex.Size2D.Float();
final OutputStream stream = new FileOutputStream("Your Output Directory" + "text-and-formula.svg");
```

## चरण 3: रेंडरिंग चलाएँ

 का उपयोग करके रेंडरिंग प्रक्रिया चलाएँ`SvgFigureRenderer` कक्षा।

```java
new SvgFigureRenderer().render("\\setlength{\\unitlength}{0.8cm}\r\n" +
    // LaTeX चित्र सामग्री
    "\\begin{picture}(6,5)\r\n" +
    // ... (आंकड़ा विवरण)
    "\\end{picture}", stream, options, size);
```

## चरण 4: आउटपुट स्ट्रीम बंद करें

रेंडरिंग के बाद आउटपुट स्ट्रीम को बंद करना सुनिश्चित करें।

```java
if (stream != null)
    stream.close();
```

## चरण 5: परिणाम प्रदर्शित करें

किसी भी त्रुटि रिपोर्ट और परिणामी एसवीजी छवि के आयाम प्रदर्शित करें।

```java
System.out.println(options.getErrorReport());
System.out.println();
System.out.println("Size: " + size.getWidth() + "x" + size.getHeight());
```

इन चरणों का पालन करके, आप जावा के लिए Aspose.TeX का उपयोग करके SVG को LaTeX आंकड़े सहजता से प्रस्तुत कर सकते हैं।

## निष्कर्ष

जावा में SVG के लिए LaTeX आंकड़े प्रस्तुत करना Aspose.TeX के साथ कुशलतापूर्वक प्राप्त किया जा सकता है। इस चरण-दर-चरण मार्गदर्शिका ने आपको रेंडरिंग विकल्प सेट करने से लेकर अंतिम परिणाम प्रदर्शित करने तक की प्रक्रिया से अवगत कराया है। इस शक्तिशाली सुविधा की अपनी समझ और अनुप्रयोग को बढ़ाने के लिए विभिन्न LaTeX आंकड़ों के साथ प्रयोग करें।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं Aspose.TeX का उपयोग करके जटिल गणितीय अभिव्यक्तियों के साथ LaTeX आंकड़े प्रस्तुत कर सकता हूं?

A1: हां, Aspose.TeX जटिल गणितीय अभिव्यक्तियों के साथ LaTeX आंकड़े प्रस्तुत करने का समर्थन करता है।

### Q2: क्या जावा के लिए Aspose.TeX के लिए एक अस्थायी लाइसेंस उपलब्ध है?

 उ2: हां, आप यहां से अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).

### Q3: मैं जावा के लिए Aspose.TeX के लिए समर्थन कैसे प्राप्त कर सकता हूं?

 A3: पर जाएँ[Aspose.TeX फोरम](https://forum.aspose.com/c/tex/47) समुदाय-आधारित समर्थन के लिए.

### Q4: Aspose.TeX का उपयोग करके मैं LaTeX आंकड़ों को किन प्रारूपों में परिवर्तित कर सकता हूं?

A4: Aspose.TeX एसवीजी, पीएनजी और अन्य सहित विभिन्न प्रारूपों में रूपांतरण की अनुमति देता है।

### Q5: मैं जावा के लिए Aspose.TeX के लिए विस्तृत दस्तावेज़ कहां पा सकता हूं?

 A5: का संदर्भ लें[Aspose.TeX दस्तावेज़ीकरण](https://reference.aspose.com/tex/java/) विस्तृत जानकारी के लिए.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
