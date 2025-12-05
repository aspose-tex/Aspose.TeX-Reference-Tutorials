---
date: 2025-12-05
description: Aspose.TeX for Java का उपयोग करके टर्मिनल आउटपुट को फ़ाइल में लिखना और
  जॉब नाम को ओवरराइड करना सीखें। पूर्ण कोड उदाहरणों के साथ इस चरण‑दर‑चरण गाइड का पालन
  करें।
language: hi
linktitle: Write Terminal Output to File and Override Job Name in Java
second_title: Aspose.TeX Java API
title: टर्मिनल आउटपुट को फ़ाइल में लिखें और जावा में जॉब नाम को ओवरराइड करें
url: /java/customizing-output/override-job-name-disk/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# टर्मिनल आउटपुट को फ़ाइल में लिखें और जावा में जॉब नाम को ओवरराइड करें

## परिचय

Aspose.TeX for Java टेक्स फ़ाइलों के साथ काम करने के लिए शक्तिशाली सुविधाएँ प्रदान करता है, जिससे डेवलपर्स टेक्स दस्तावेज़ प्रोसेसिंग पाइपलाइन को हेरफेर और अनुकूलित कर सकते हैं। इस ट्यूटोरियल में आप सीखेंगे **टर्मिनल आउटपुट को फ़ाइल में कैसे लिखें** तथा डिफ़ॉल्ट जॉब नाम को ओवरराइड करना—दो क्षमताएँ जो बैच प्रोसेसिंग और लॉगिंग पर सूक्ष्म नियंत्रण देती हैं।

## त्वरित उत्तर
- **क्या मैं जॉब नाम बदल सकता हूँ?** हाँ, जॉब चलाने से पहले `options.setJobName(...)` का उपयोग करें।  
- **टर्मिनल आउटपुट कहाँ जाता है?** यह आउटपुट वर्किंग डायरेक्टरी में `<job_name>.trm` के रूप में सहेजा जाता है।  
- **क्या इस सुविधा के लिए लाइसेंस चाहिए?** यह कार्यक्षमता किसी भी वैध Aspose.TeX लाइसेंस के साथ काम करती है; एक मुफ्त ट्रायल भी उपलब्ध है।  
- **आउटपुट फ़ाइल का फ़ॉर्मेट क्या है?** साधारण‑पाठ (plain‑text) टर्मिनल लॉग जो कंसोल आउटपुट को प्रतिबिंबित करता है।  
- **क्या यह अन्य आउटपुट डिवाइसों के साथ संगत है?** बिल्कुल—एक बार लॉग लिख दिया जाए तो आप इसे किसी भी टेक्स्ट फ़ाइल पढ़ने वाले टूल से प्रोसेस कर सकते हैं।

## पूर्वापेक्षाएँ

कोड में डुबने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- जावा प्रोग्रामिंग मूलभूत सिद्धांतों की ठोस समझ।  
- Aspose.TeX for Java स्थापित हो (आधिकारिक [Aspose.TeX Java documentation](https://reference.aspose.com/tex/java/) से डाउनलोड करें)।  
- एक जावा IDE या बिल्ड टूल (Maven/Gradle) तैयार हो ताकि सैंपल को कंपाइल और रन किया जा सके।

## पैकेज इम्पोर्ट करें

शुरू करने के लिए, आवश्यक पैकेजों को अपने जावा प्रोजेक्ट में इम्पोर्ट करें। अपने जावा फ़ाइल में, निम्नलिखित इम्पोर्ट्स शामिल करें:

```java
package com.aspose.tex.OverridenJobNameAndTerminalOutputWrittenToDisk;

import java.io.IOException;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

> **प्रो टिप:** `util.Utils` इम्पोर्ट केवल तभी रखें जब आपको Aspose सैंपल यूटिलिटीज़ के हेल्पर मेथड्स की आवश्यकता हो; अन्यथा कोड को साफ रखने के लिए इसे हटा सकते हैं।

## जावा में टर्मिनल आउटपुट को फ़ाइल में कैसे लिखें

नीचे एक चरण‑दर‑चरण गाइड है जो दिखाता है कि कैसे कन्वर्ज़न विकल्पों को कॉन्फ़िगर करें, जॉब नाम को ओवरराइड करें, और टर्मिनल आउटपुट को डिस्क पर फ़ाइल में निर्देशित करें।

### चरण 1: कन्वर्ज़न विकल्प बनाएं

पहले, एक `TeXOptions` इंस्टेंस बनाएं जो डिफ़ॉल्ट ObjectTeX कॉन्फ़िगरेशन का उपयोग करता है। यह ऑब्जेक्ट कन्वर्ज़न प्रक्रिया के सभी सेटिंग्स को रखेगा।

```java
// ExStart:OverrideJobName-WriteTerminalOutputToFileSystem
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
// ExEnd:OverrideJobName-WriteTerminalOutputToFileSystem
```

### चरण 2: जॉब नाम और वर्किंग डायरेक्टरी निर्दिष्ट करें

अगला, एक कस्टम जॉब नाम सेट करें और परिभाषित करें कि इनपुट और आउटपुट फ़ाइलें कहाँ स्थित हैं। यदि आप जॉब नाम सेट नहीं करते हैं, तो `TeXJob` कंस्ट्रक्टर का पहला आर्ग्यूमेंट स्वचालित रूप से जॉब नाम बन जाता है।

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

> **जॉब नाम को ओवरराइड क्यों करें?**  
> जॉब नाम को ओवरराइड करने से लॉग फ़ाइलें और उत्पन्न आर्टिफैक्ट्स को पहचानना आसान हो जाता है, विशेषकर जब आप समानांतर में कई जॉब चलाते हैं या बैच प्रोसेसिंग को स्वचालित करते हैं।

### चरण 3: टर्मिनल आउटपुट को फ़ाइल सिस्टम में लिखें

Aspose.TeX को बताएं कि वह कंसोल पर सामान्यतः दिखने वाले सभी आउटपुट को कैप्चर करे और उसे फ़ाइल में लिखे। फ़ाइल का नाम `<job_name>.trm` होगा और इसे ऊपर परिभाषित आउटपुट वर्किंग डायरेक्टरी में रखा जाएगा।

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### चरण 4: जॉब चलाएँ

अंत में, इच्छित इनपुट फ़ाइल (यहाँ हम एक साधारण “hello‑world” उदाहरण का उपयोग करते हैं) और XPS रेंडरिंग डिवाइस के साथ एक `TeXJob` बनाएं। फिर `run()` को कॉल करके कन्वर्ज़न को निष्पादित करें।

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
```

जब जॉब समाप्त हो जाएगा, तो आपको **Your Output Directory** के अंदर `overridden-job-name.trm` नाम की फ़ाइल मिलेगी जिसमें पूरा टर्मिनल लॉग होगा।

## सामान्य समस्याएँ और ट्रबलशूटिंग

| समस्या | कारण | समाधान |
|-------|-------|-----|
| **`.trm` फ़ाइल नहीं बनी** | `setTerminalOut` नहीं बुलाया गया या आउटपुट डायरेक्टरी मौजूद नहीं है | सुनिश्चित करें कि आउटपुट डायरेक्टरी मौजूद है और `options.setTerminalOut(...)` को `job.run()` से पहले चलाया गया है। |
| **फ़ाइल नाम ओवरराइड किए गए नाम जैसा नहीं है** | जॉब नाम सही तरीके से सेट नहीं किया गया | सुनिश्चित करें कि `options.setJobName("your‑desired‑name")` को `TeXJob` बनाने **से पहले** कॉल किया गया है। |
| **खाली लॉग फ़ाइल** | लॉगिंग शुरू होने से पहले अपवाद (Exceptions) फेंके गए | `job.run()` को try‑catch ब्लॉक में रखें और मिसिंग फ़ॉन्ट्स या खराब TeX स्रोत के लिए अपवाद स्टैक ट्रेस जांचें। |

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं Aspose.TeX for Java को अन्य जावा लाइब्रेरीज़ के साथ उपयोग कर सकता हूँ?**  
**उत्तर:** हाँ, Aspose.TeX को अन्य जावा लाइब्रेरीज़ के साथ सहजता से एकीकृत करने के लिए डिज़ाइन किया गया है, जिससे आप एक ही वर्कफ़्लो में PDF, इमेज, या डेटाबेस यूटिलिटीज़ को संयोजित कर सकते हैं।

**प्रश्न: Aspose.TeX for Java के लिए समर्थन कहाँ मिल सकता है?**  
**उत्तर:** समुदाय सहायता के लिए [Aspose.TeX forum](https://forum.aspose.com/c/tex/47) पर जाएँ, या Aspose सपोर्ट पोर्टल के माध्यम से एक सपोर्ट टिकट खोलें।

**प्रश्न: क्या Aspose.TeX for Java के लिए मुफ्त ट्रायल उपलब्ध है?**  
**उत्तर:** बिल्कुल। आप पूरी तरह कार्यात्मक ट्रायल को [Aspose.TeX free trial page](https://releases.aspose.com/) से डाउनलोड कर सकते हैं।

**प्रश्न: परीक्षण के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?**  
**उत्तर:** 30‑दिन के मूल्यांकन लाइसेंस के लिए [Aspose temporary license](https://purchase.aspose.com/temporary-license/) पर अस्थायी‑लाइसेंस अनुरोध फ़ॉर्म का उपयोग करें।

**प्रश्न: स्थायी लाइसेंस कहाँ खरीद सकता हूँ?**  
**उत्तर:** सीधे [Aspose.TeX buying page](https://purchase.aspose.com/buy) से लाइसेंस खरीदें।

## निष्कर्ष

इस गाइड में हमने दिखाया कि कैसे Aspose.TeX for Java का उपयोग करके **टर्मिनल आउटपुट को फ़ाइल में लिखें** और डिफ़ॉल्ट जॉब नाम को ओवरराइड करें। ये क्षमताएँ आपको डिबगिंग के लिए विस्तृत लॉग रखने, बैच प्रोसेसिंग को स्वचालित करने, और एक साफ़, व्यवस्थित आउटपुट संरचना बनाए रखने में मदद करती हैं—जो प्रोडक्शन‑ग्रेड दस्तावेज़ कन्वर्ज़न पाइपलाइन के लिए आवश्यक है।

---

**अंतिम अपडेट:** 2025-12-05  
**परीक्षित संस्करण:** Aspose.TeX 24.11 for Java  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}