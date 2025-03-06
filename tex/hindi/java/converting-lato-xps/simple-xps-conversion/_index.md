---
title: आसानी से जावा में LaTeX को XPS फॉर्मेट में बदलें
linktitle: आसानी से जावा में LaTeX को XPS फॉर्मेट में बदलें
second_title: Aspose.TeX जावा एपीआई
description: Aspose.TeX का उपयोग करके जावा में आसानी से LaTeX को XPS में बदलें। निर्बाध एकीकरण के लिए हमारी चरण-दर-चरण मार्गदर्शिका का पालन करें।
weight: 10
url: /hi/java/converting-lato-xps/simple-xps-conversion/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# आसानी से जावा में LaTeX को XPS फॉर्मेट में बदलें

## परिचय

क्या आप अपने जावा अनुप्रयोगों में LaTeX दस्तावेज़ों को XPS प्रारूप में निर्बाध रूप से परिवर्तित करना चाहते हैं? Java के लिए Aspose.TeX एक शक्तिशाली समाधान प्रदान करता है, जिससे आप इसे आसानी से प्राप्त कर सकते हैं। इस चरण-दर-चरण मार्गदर्शिका में, हम आपको Aspose.TeX का उपयोग करके LaTeX को XPS में परिवर्तित करने की प्रक्रिया के बारे में बताएंगे।

## आवश्यक शर्तें

रूपांतरण प्रक्रिया में उतरने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

- आपके सिस्टम पर जावा डेवलपमेंट किट (जेडीके) स्थापित है।
-  जावा लाइब्रेरी के लिए Aspose.TeX डाउनलोड किया गया। आप डाउनलोड लिंक पा सकते हैं[यहाँ](https://releases.aspose.com/tex/java/).

## पैकेज आयात करें

आरंभ करने के लिए, अपने जावा प्रोजेक्ट के लिए आवश्यक पैकेज आयात करें। सुनिश्चित करें कि आप अपने प्रोजेक्ट निर्भरता में Aspose.TeX लाइब्रेरी को शामिल करें।

```java
package com.aspose.tex.LaTeXXpsConversionSimplest;

import java.io.ByteArrayInputStream;
import java.io.IOException;
import java.util.Calendar;
import java.util.GregorianCalendar;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.Interaction;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;
import com.aspose.tex.rendering.XpsSaveOptions;

import util.Utils;
```

आइए अब दिए गए कोड उदाहरणों का उपयोग करके रूपांतरण प्रक्रिया को कई चरणों में विभाजित करें।

## चरण 1: इनपुट और आउटपुट निर्देशिकाएँ सेट करें

```java
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

उन निर्देशिकाओं को निर्दिष्ट करें जहां आपकी LaTeX इनपुट फ़ाइल स्थित है और जहां आप परिवर्तित XPS फ़ाइल को सहेजना चाहते हैं।

## चरण 2: TeX विकल्प कॉन्फ़िगर करें

अपनी आवश्यकताओं के अनुसार रूपांतरण प्रक्रिया को अनुकूलित करने के लिए विभिन्न विकल्पों को कॉन्फ़िगर करें।

```java
options.setInteraction(Interaction.NonstopMode);
options.setDateTime(new GregorianCalendar(2022, Calendar.DECEMBER, 18).getTime());
options.ignoreMissingPackages(true);
options.noLigatures(true);
options.repeat(true);
```

आवश्यकतानुसार इंटरेक्शन मोड, शीर्षक में तारीख, लापता पैकेजों का प्रबंधन, संयुक्ताक्षर और दोहराव को समायोजित करें।

## चरण 3: XPS सेव विकल्प प्रारंभ करें

```java
options.setSaveOptions(new XpsSaveOptions());
```

XPS प्रारूप में बचत के लिए विकल्पों को प्रारंभ करें।

## चरण 4: एक्सपीएस सेव विकल्पों को अनुकूलित करें

```java
options.getSaveOptions().rasterizeFormulas(true);
options.getSaveOptions().rasterizeIncludedGraphics(true);
options.getSaveOptions().subsetFonts(true);
```

फ़ॉर्मूले, शामिल ग्राफ़िक्स और फ़ॉन्ट सबसेटिंग के रूपांतरण को नियंत्रित करने के लिए XPS सेव विकल्पों को अनुकूलित करें।

## चरण 5: LaTeX से XPS रूपांतरण चलाएँ

```java
new TeXJob("Your Input Directory" + "sample.ltx", new XpsDevice(), options).run();
```

निर्दिष्ट इनपुट फ़ाइल, आउटपुट डिवाइस (XpsDevice), और विकल्पों के साथ TeX कार्य चलाकर रूपांतरण प्रक्रिया आरंभ करें।

## अतिरिक्त उदाहरण

विभिन्न इनपुट स्रोतों का उपयोग करके अतिरिक्त रूपांतरण विधियों का अन्वेषण करें:

### इनपुटस्ट्रीम का प्रयोग करें

```java
new TeXJob(new ByteArrayInputStream(
    "\\documentclass{article} \\begin{document} Hello, World! \\end{document}".getBytes("ASCII")),
    new XpsDevice(), options).run();
```

### मुख्य इनपुट टर्मिनल का उपयोग करें

```java
new TeXJob(new XpsDevice(), options).run();
```

## निष्कर्ष

जावा के लिए Aspose.TeX के साथ, LaTeX को XPS में परिवर्तित करना आसान है। इन चरणों का पालन करें, विकल्पों को अनुकूलित करें, और इस कार्यक्षमता को अपने जावा अनुप्रयोगों में सहजता से एकीकृत करें।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं Aspose.TeX का उपयोग करके LaTeX दस्तावेज़ों को जटिल फ़ार्मुलों के साथ परिवर्तित कर सकता हूँ?

A1: बिल्कुल! Aspose.TeX रूपांतरण प्रक्रिया के दौरान जटिल सूत्रों को सहजता से संभालता है।

### Q2: क्या जावा के लिए Aspose.TeX का कोई परीक्षण संस्करण उपलब्ध है?

 उ2: हाँ, आप निःशुल्क परीक्षण संस्करण पा सकते हैं[यहाँ](https://releases.aspose.com/).

### Q3: मैं Aspose.TeX के लिए समर्थन कैसे प्राप्त कर सकता हूं?

 A3: पर जाएँ[Aspose.TeX फोरम](https://forum.aspose.com/c/tex/47) सहायता और सामुदायिक समर्थन के लिए।

### Q4: क्या Aspose.TeX के लिए अस्थायी लाइसेंस उपलब्ध हैं?

 उ4: हाँ, आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).

### Q5: मुझे Aspose.TeX के लिए दस्तावेज़ कहाँ मिल सकते हैं?

 A5: का संदर्भ लें[प्रलेखन](https://reference.aspose.com/tex/java/) व्यापक मार्गदर्शन के लिए.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
