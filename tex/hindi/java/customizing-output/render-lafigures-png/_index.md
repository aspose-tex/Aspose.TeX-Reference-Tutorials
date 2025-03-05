---
title: जावा में LaTeX आकृतियों को PNG में प्रस्तुत करें
linktitle: जावा में LaTeX आकृतियों को PNG में प्रस्तुत करें
second_title: Aspose.TeX जावा एपीआई
description: Aspose.TeX के साथ जावा में आसानी से LaTeX आंकड़ों को PNG में प्रस्तुत करें। निर्बाध एकीकरण के लिए इस गाइड का पालन करें।
type: docs
weight: 12
url: /hi/java/customizing-output/render-lafigures-png/
---
## परिचय

जावा विकास की दुनिया में, पीएनजी के लिए लाटेक्स आंकड़े प्रस्तुत करना एक चुनौतीपूर्ण लेकिन आवश्यक कार्य हो सकता है। जावा के लिए Aspose.TeX अपनी शक्तिशाली विशेषताओं के साथ बचाव के लिए आता है, जो इस प्रक्रिया को कुशल और निर्बाध बनाता है। यह चरण-दर-चरण मार्गदर्शिका आपको Aspose.TeX का उपयोग करके LaTeX आंकड़ों को PNG में प्रस्तुत करने की पूरी प्रक्रिया के बारे में बताएगी।

## आवश्यक शर्तें

इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

- आपके सिस्टम पर जावा डेवलपमेंट किट (जेडीके) स्थापित है।
-  जावा लाइब्रेरी के लिए Aspose.TeX डाउनलोड किया गया। आप इसे यहां से प्राप्त कर सकते हैं[लिंक को डाउनलोड करें](https://releases.aspose.com/tex/java/).
- LaTeX और जावा प्रोग्रामिंग का बुनियादी ज्ञान।

## पैकेज आयात करें

आरंभ करने के लिए, आपको Java के लिए Aspose.TeX से आवश्यक पैकेज आयात करने होंगे। ये पैकेज पीएनजी को लाटेक्स आंकड़े प्रस्तुत करने के लिए आवश्यक उपकरण और कार्यक्षमता प्रदान करते हैं।

```java
package com.aspose.tex.PngLaTeXFigureRenderer;

import java.awt.Color;
import java.io.ByteArrayOutputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.OutputStream;

import com.aspose.tex.PngFigureRenderer;
import com.aspose.tex.PngFigureRendererOptions;

import util.Utils;
```

## चरण 1: रेंडरिंग विकल्प सेट करें

छवि रिज़ॉल्यूशन, प्रस्तावना, स्केलिंग कारक, पृष्ठभूमि रंग, लॉग स्ट्रीम और टर्मिनल आउटपुट दृश्यता जैसे पैरामीटर सेट करके रेंडरिंग विकल्प बनाएं।

```java
PngFigureRendererOptions options = new PngFigureRendererOptions();
options.setResolution(96);
options.setPreamble("\\usepackage{pict2e}");
options.setScale(3000);
options.setBackgroundColor(Color.WHITE);
options.setLogStream(new ByteArrayOutputStream());
options.showTerminal(true);
```

## चरण 2: LaTeX चित्र को परिभाषित करें

उस LaTeX आकृति को परिभाषित करें जिसे आप प्रस्तुत करना चाहते हैं। इसमें जटिल गणितीय समीकरण, आरेख, या कोई अन्य LaTeX सामग्री शामिल हो सकती है।

```java
String latexFigure = "\\setlength{\\unitlength}{0.8cm}\r\n" +
                    "\\begin{picture}(6,5)\r\n" +
                    "\\thicklines\r\n" +
                    // ... (आपका LaTeX चित्र सामग्री)
                    "\\end{picture}";
```

## चरण 3: प्रस्तुत करें और सहेजें

LaTeX आकृति को PNG छवि में प्रस्तुत करें और इसे निर्दिष्ट आउटपुट निर्देशिका में सहेजें।

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + "text-and-formula.png");
try {
    new PngFigureRenderer().render(latexFigure, stream, options, size);
} finally {
    if (stream != null)
        stream.close();
}
```

## चरण 4: परिणाम प्रदर्शित करें

किसी भी त्रुटि रिपोर्ट और परिणामी छवि के आयामों सहित परिणाम दिखाएं।

```java
System.out.println(options.getErrorReport());
System.out.println();
System.out.println("Size: " + size.getWidth() + "x" + size.getHeight());
// ExEnd:PngLaTeXचित्रा रेंडरर
```

## निष्कर्ष

बधाई हो! आपने Aspose.TeX का उपयोग करके जावा में PNG में LaTeX आंकड़े प्रस्तुत करना सफलतापूर्वक सीख लिया है। यह शक्तिशाली उपकरण प्रक्रिया को सरल बनाता है, जिससे आप अपने जावा अनुप्रयोगों में LaTeX सामग्री को सहजता से एकीकृत कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं अन्य जावा लाइब्रेरीज़ के साथ जावा के लिए Aspose.TeX का उपयोग कर सकता हूँ?

A1: हां, Java के लिए Aspose.TeX को अन्य जावा लाइब्रेरीज़ के साथ अच्छी तरह से काम करने के लिए डिज़ाइन किया गया है, जो आपकी विकास प्रक्रिया में लचीलापन प्रदान करता है।

### Q2: क्या Java के लिए Aspose.TeX का निःशुल्क परीक्षण उपलब्ध है?

 उ2: हां, आप निःशुल्क परीक्षण संस्करण तक पहुंच सकते हैं[यहाँ](https://releases.aspose.com/).

### Q3: मैं जावा के लिए Aspose.TeX के लिए समर्थन कैसे प्राप्त कर सकता हूं?

 A3: पर जाएँ[Aspose.TeX फोरम](https://forum.aspose.com/c/tex/47) किसी भी समर्थन या प्रश्न के लिए।

### Q4: अस्थायी लाइसेंस क्या है, और मैं इसे कैसे प्राप्त कर सकता हूं?

 A4: आप Aspose.TeX के लिए अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).

### Q5: मैं जावा के लिए Aspose.TeX के लिए विस्तृत दस्तावेज़ कहां पा सकता हूं?

 A5: दस्तावेज़ उपलब्ध है[यहाँ](https://reference.aspose.com/tex/java/).