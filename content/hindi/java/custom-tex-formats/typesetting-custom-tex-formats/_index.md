---
title: जावा में कस्टम टीएक्स प्रारूपों के साथ टाइपसेटिंग
linktitle: जावा में कस्टम टीएक्स प्रारूपों के साथ टाइपसेटिंग
second_title: Aspose.TeX जावा एपीआई
description: Aspose.TeX के साथ जावा में कुशल टाइपसेटिंग का अन्वेषण करें। कस्टम TeX प्रारूप आसान बनाये गये। निर्बाध विकास अनुभव के लिए अभी डाउनलोड करें।
type: docs
weight: 10
url: /hi/java/custom-tex-formats/typesetting-custom-tex-formats/
---
## परिचय

जावा विकास के क्षेत्र में, Aspose.TeX कस्टम TeX प्रारूपों के साथ टाइपसेटिंग के लिए एक अमूल्य उपकरण साबित होता है। यह ट्यूटोरियल वैयक्तिकृत TeX प्रारूपों का उपयोग करके कुशल टाइपसेटिंग प्राप्त करने के लिए जावा के लिए Aspose.TeX का उपयोग करने की प्रक्रिया के बारे में विस्तार से बताएगा। चाहे आप अनुभवी डेवलपर हों या नवागंतुक, यह मार्गदर्शिका आपको निर्बाध रूप से चरणों के माध्यम से चलने के लिए डिज़ाइन की गई है।

## आवश्यक शर्तें

इस यात्रा पर निकलने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:

1.  जावा डेवलपमेंट किट (जेडीके): जावा के लिए Aspose.TeX को आपके सिस्टम पर एक कार्यशील जेडीके की आवश्यकता होती है। यदि इंस्टॉल नहीं है, तो नवीनतम संस्करण डाउनलोड करें और सेट अप करें[जावा की वेबसाइट](https://www.oracle.com/java/technologies/javase-downloads.html).

2.  Aspose.TeX लाइब्रेरी: जावा के लिए Aspose.TeX लाइब्रेरी प्राप्त करें। आप इसे यहां से डाउनलोड कर सकते हैं[जावा डाउनलोड पेज के लिए Aspose.TeX](https://releases.aspose.com/tex/java/).

3. कस्टम टीएक्स प्रारूप फ़ाइल: अपनी कस्टम टीएक्स प्रारूप फ़ाइल तैयार करें और सुनिश्चित करें कि यह आपकी वांछित आउटपुट निर्देशिका में सहेजी गई है।

## पैकेज आयात करें

आरंभ करने के लिए, अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करें। जावा की शक्तिशाली टाइपसेटिंग क्षमताओं का उपयोग करने के लिए Aspose.TeX लाइब्रेरी का उपयोग करें।

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

अब, आइए इस प्रक्रिया को चरण-दर-चरण निर्देशों की एक श्रृंखला में विभाजित करें:

## चरण 1: प्रारूप प्रदाता बनाएँ

फ़ाइल सिस्टम इनपुट कार्यशील निर्देशिका का उपयोग करके एक प्रारूप प्रदाता बनाकर शुरुआत करें। यह निर्देशिका आपकी कस्टम TeX प्रारूप फ़ाइल को रखेगी।

```java
final FormatProvider formatProvider = new FormatProvider(
		new InputFileSystemDirectory("Your Output Directory"), "customtex");
```

## चरण 2: रूपांतरण विकल्प सेट करें

अपने कस्टम प्रारूप के लिए रूपांतरण विकल्प बनाएं, विशेष रूप से ऑब्जेक्टटेक्स इंजन एक्सटेंशन के अनुरूप।

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX(formatProvider));
options.setJobName("typeset-with-custom-format");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

## चरण 3: TeX जॉब चलाएँ

TeXJob को इंस्टेंट करें और इसे अपने निर्दिष्ट विकल्पों और कस्टम टेक्स्ट सामग्री के साथ चलाएं।

```java
new TeXJob(new ByteArrayInputStream(
        "Congratulations! You have successfully typeset this text with your own TeX format!\\end".getBytes("ASCII")),
        new XpsDevice(), options).run();
```

## चरण 4: आउटपुट को अंतिम रूप दें

आवश्यक लाइन ब्रेक जोड़कर एक स्वच्छ और पठनीय आउटपुट सुनिश्चित करें।

```java
options.getTerminalOut().getWriter().newLine();
```

## चरण 5: प्रारूप प्रदाता को बंद करें

अंत में, टाइपसेटिंग प्रक्रिया को पूरा करने के लिए प्रारूप प्रदाता को बंद करें।

```java
formatProvider.close();
```

## निष्कर्ष

बधाई हो! आपने कस्टम TeX प्रारूप के साथ Java के लिए Aspose.TeX का उपयोग करके एक सफल टाइपसेटिंग प्रक्रिया पूरी कर ली है। इस ट्यूटोरियल का उद्देश्य जटिल चरणों के माध्यम से आपका मार्गदर्शन करना है, जिससे पूरी यात्रा आसान और अधिक समझने योग्य हो जाएगी।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं अन्य जावा लाइब्रेरीज़ के साथ Aspose.TeX का उपयोग कर सकता हूँ?

A1: हां, Aspose.TeX को कार्यक्षमता बढ़ाने के लिए विभिन्न जावा लाइब्रेरी के साथ सहजता से एकीकृत करने के लिए डिज़ाइन किया गया है।

### Q2: मुझे और सहायता और समर्थन कहां मिल सकता है?

 ए2: अन्वेषण करें[Aspose.TeX फोरम](https://forum.aspose.com/c/tex/47)सामुदायिक समर्थन और चर्चा के लिए।

### Q3: क्या Aspose.TeX के लिए कोई निःशुल्क परीक्षण उपलब्ध है?

 उ3: हाँ, आप नि:शुल्क परीक्षण का उपयोग कर सकते हैं[यहाँ](https://releases.aspose.com/).

### Q4: मैं Aspose.TeX के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?

 A4: पर जाएँ[अस्थायी लाइसेंस पृष्ठ](https://purchase.aspose.com/temporary-license/) अस्थायी लाइसेंसिंग विकल्पों के लिए।

### Q5: मैं Aspose.TeX लाइब्रेरी कहां से खरीद सकता हूं?

 A5: पर जाकर अपनी प्रति सुरक्षित करें[खरीद पृष्ठ](https://purchase.aspose.com/buy).