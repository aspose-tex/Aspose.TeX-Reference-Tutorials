---
date: 2026-03-26
description: .NET में Aspose.TeX के साथ कस्टम tex फ़ॉर्मेट बनाना सीखें और लचीले दस्तावेज़
  निर्माण के लिए tex इनपुट डायरेक्टरी सेट करें। यह चरण‑दर‑चरण गाइड आपको फ़ॉर्मेट प्रोवाइडर
  को कॉन्फ़िगर करना, tex इनपुट डायरेक्टरी सेट करना, और XPS आउटपुट जनरेट करना दिखाता
  है।
linktitle: Creating Custom TeX Formats in .NET
second_title: Aspose.TeX .NET API
title: .NET में Aspose.TeX का उपयोग करके कस्टम tex फ़ॉर्मेट कैसे बनाएं
url: /hi/net/custom-tex-formats/create-custom-tex-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET में Aspose.TeX का उपयोग करके कस्टम tex फ़ॉर्मेट कैसे बनाएं

.NET विकास की गतिशील दुनिया में, **कस्टम tex फ़ॉर्मेट** फ़ाइलें बनाने से आप दस्तावेज़ों के टाइपसेटिंग पर सूक्ष्म नियंत्रण प्राप्त करते हैं। Aspose.TeX for .NET के साथ आप TeX इंजन को अनुकूलित कर सकते हैं, इसे एक विशिष्ट इनपुट फ़ोल्डर की ओर इंगित कर सकते हैं, और कुछ ही C# कोड की पंक्तियों से पेशेवर दिखने वाला XPS आउटपुट उत्पन्न कर सकते हैं।

## त्वरित उत्तर
- **“create custom tex format” का क्या अर्थ है?** इसका मतलब है कि आप अपने स्वयं के TeX इंजन कॉन्फ़िगरेशन और फ़ॉर्मेट फ़ाइलें परिभाषित करते हैं ताकि टाइपसेटिंग प्रक्रिया को नियंत्रित किया जा सके।  
- **मुझे कौनसी लाइब्रेरी चाहिए?** Aspose.TeX for .NET।  
- **क्या मुझे tex इनपुट डायरेक्टरी सेट करनी चाहिए?** हाँ – आप इसे `InputFileSystemDirectory` के साथ निर्दिष्ट करते हैं।  
- **मैं कौनसा आउटपुट जनरेट कर सकता हूँ?** Aspose.TeX द्वारा समर्थित कोई भी डिवाइस, जैसे XPS, PDF, या PNG।  
- **क्या उत्पादन के लिए लाइसेंस आवश्यक है?** व्यावसायिक उपयोग के लिए एक वैध Aspose.TeX लाइसेंस आवश्यक है।

## कस्टम TeX फ़ॉर्मेट क्या है?
कस्टम TeX फ़ॉर्मेट मैक्रोज़ और इंजन सेटिंग्स का एक प्री‑कम्पाइल्ड सेट है जिसे TeX प्रोसेसर आपके स्रोत फ़ाइलों को व्याख्या करने के लिए उपयोग करता है। इसे बनाकर आप कंपनी का ब्रांडिंग एम्बेड कर सकते हैं, दस्तावेज़ मानकों को लागू कर सकते हैं, या दोहराव वाले कार्यों के लिए संकलन को तेज़ कर सकते हैं।

## tex इनपुट डायरेक्टरी सेट क्यों करें?
**tex इनपुट डायरेक्टरी** सेट करने से इंजन को पता चलता है कि सहायक फ़ाइलें, कस्टम फ़ॉन्ट्स, या अतिरिक्त स्टाइल फ़ाइलें कहां खोजनी हैं। इससे आपका प्रोजेक्ट व्यवस्थित रहता है और संकलन के दौरान “फ़ाइल नहीं मिली” त्रुटियों से बचा जा सकता है।

## पूर्वापेक्षाएँ

कस्टमाइज़ेशन यात्रा शुरू करने से पहले, सुनिश्चित करें कि आपके पास है:

1. **Aspose.TeX for .NET** – इसे [Aspose.TeX वेबसाइट](https://releases.aspose.com/tex/net/) से डाउनलोड करें।  
2. एक **.NET विकास पर्यावरण** (Visual Studio, VS Code, या .NET CLI)।  
3. (वैकल्पिक) एक वैध **Aspose.TeX लाइसेंस** यदि आप कोड को उत्पादन में चलाने की योजना बना रहे हैं।

## नेमस्पेस इम्पोर्ट करें

सबसे पहले, उन नेमस्पेस को इम्पोर्ट करें जो आपको Aspose.TeX API तक पहुँच प्रदान करते हैं। यह कदम सुनिश्चित करता है कि हम जिन क्लासों का उपयोग करेंगे, उन्हें कंपाइलर पहचान लेगा।

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using Aspose.TeX.ResourceProviders;
using System.IO;
using System.Text;
```

## चरण 1: फ़ॉर्मेट प्रोवाइडर बनाएं

`FormatProvider` इंजन को उस फ़ोल्डर की ओर इंगित करता है जिसमें आपका कस्टम फ़ॉर्मेट फ़ाइल (`customtex.fmt`) मौजूद है। `"Your Output Directory"` को उस पथ से बदलें जहाँ आपने कम्पाइल किया हुआ फ़ॉर्मेट संग्रहीत किया है।

```csharp
using (FormatProvider formatProvider =
    new FormatProvider(new InputFileSystemDirectory("Your Output Directory"), "customtex"))
{
```

## चरण 2: रूपांतरण विकल्प कॉन्फ़िगर करें (और tex इनपुट डायरेक्टरी सेट करें)

यहाँ हम `TeXOptions` ऑब्जेक्ट बनाते हैं। `InputWorkingDirectory` पर ध्यान दें – यही वह जगह है जहाँ हम **tex इनपुट डायरेक्टरी** सेट करते हैं ताकि इंजन किसी भी सहायक फ़ाइल को ढूँढ सके।

```csharp
    TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX(formatProvider));
    options.JobName = "typeset-with-custom-format";
    options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
    options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

## चरण 3: जॉब चलाएँ

अब हम इंजन को एक सरल TeX स्ट्रिंग देते हैं, आउटपुट डिवाइस चुनते हैं (इस उदाहरण में XPS), और जॉब को निष्पादित करते हैं।

```csharp
    new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
        "Congratulations! You have successfully typeset this text with your own TeX format!\\end")),
        new XpsDevice(), options).Run();
```

## चरण 4: टर्मिनल आउटपुट को परिष्कृत करें

एक खाली पंक्ति जोड़ने से कंसोल आउटपुट पढ़ने में आसान हो जाता है, विशेष रूप से जब आप बैच में कई जॉब चलाते हैं।

```csharp
    options.TerminalOut.Writer.WriteLine();
}
// ExEnd:TypesetWithCustomTeXFormat
```

बधाई हो! आपने अब **कस्टम tex फ़ॉर्मेट** बना लिया है और इसे .NET में एक दस्तावेज़ टाइपसेट करने के लिए सफलतापूर्वक उपयोग किया है।

## सामान्य समस्याएँ और समाधान

| समस्या | कारण | समाधान |
|-------|--------|-----|
| *“Format file not found”* | `FormatProvider` में गलत पथ | सत्यापित करें कि `"Your Output Directory"` में `customtex.fmt` मौजूद है और पथ पूर्ण है या निष्पादन योग्य फ़ाइल के सापेक्ष सही है। |
| *“Cannot find input file”* | `InputWorkingDirectory` गलत फ़ोल्डर की ओर इशारा कर रहा है | सुनिश्चित करें कि `"Your Input Directory"` में TeX स्रोत फ़ाइल मौजूद है या आप स्रोत को स्ट्रीम के रूप में पास कर रहे हैं (जैसा कि उदाहरण में दिखाया गया है)। |
| *Terminal output garbled* | एन्कोडिंग असंगतता | यदि आपके TeX स्रोत में गैर‑ASCII अक्षर हैं तो `Encoding.UTF8` का उपयोग करें। |
| *XPS file is empty* | पहले की अपवाद के कारण जॉब नहीं चला | कंसोल में त्रुटि संदेश देखें; अक्सर वे गायब पैकेज या TeX स्ट्रिंग में सिंटैक्स त्रुटियों को दर्शाते हैं। |

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं Aspose.TeX for .NET को अन्य दस्तावेज़ प्रोसेसिंग लाइब्रेरीज़ के साथ उपयोग कर सकता हूँ?
A1: हाँ, Aspose.TeX को अन्य Aspose दस्तावेज़ प्रोसेसिंग लाइब्रेरीज़ के साथ सहजता से एकीकृत करने के लिए डिज़ाइन किया गया है, जिससे व्यापक दस्तावेज़ हैंडलिंग संभव हो सके।

### Q2: क्या Aspose.TeX for .NET के लिए कोई फ्री ट्रायल उपलब्ध है?
A2: हाँ, आप फ्री ट्रायल यहाँ से प्राप्त कर सकते हैं: [here](https://releases.aspose.com/)।

### Q3: मैं Aspose.TeX for .NET के लिए समर्थन कैसे प्राप्त कर सकता हूँ?
A3: समुदाय समर्थन के लिए [Aspose.TeX फ़ोरम](https://forum.aspose.com/c/tex/47) पर जाएँ या प्रीमियम समर्थन विकल्प यहाँ देखें: [here](https://purchase.aspose.com/buy)।

### Q4: क्या Aspose.TeX for .NET के लिए अस्थायी लाइसेंस उपलब्ध हैं?
A4: हाँ, आप एक अस्थायी लाइसेंस यहाँ प्राप्त कर सकते हैं: [here](https://purchase.aspose.com/temporary-license/)।

### Q5: मैं Aspose.TeX for .NET की दस्तावेज़ीकरण कहाँ पा सकता हूँ?
A5: व्यापक दस्तावेज़ीकरण यहाँ देखें: [here](https://reference.aspose.com/tex/net/)।

**अतिरिक्त प्रश्नोत्तर**

**प्रश्न: क्या मैं XPS के बजाय PDF आउटपुट कर सकता हूँ?**  
**उत्तर:** बिल्कुल। `new XpsDevice()` को `new PdfDevice()` से बदलें और आउटपुट डायरेक्टरी को उसी अनुसार समायोजित करें।

**प्रश्न: क्या हर बदलाव के बाद फ़ॉर्मेट फ़ाइल को पुनः‑कम्पाइल करना आवश्यक है?**  
**उत्तर:** हाँ। मैक्रोज़ या इंजन सेटिंग्स में कोई भी बदलाव नई `.fmt` फ़ाइल उत्पन्न करने के लिए `tex -ini` को फिर से चलाने की आवश्यकता होती है।

## निष्कर्ष

निष्कर्षतः, Aspose.TeX for .NET **कस्टम tex फ़ॉर्मेट** बनाने के परिदृश्यों के लिए एक मजबूत समाधान प्रदान करता है, जिससे डेवलपर्स को दस्तावेज़ टाइपसेटिंग पर अभूतपूर्व नियंत्रण मिलता है। विभिन्न कॉन्फ़िगरेशन के साथ प्रयोग करें, उपयुक्त tex इनपुट डायरेक्टरी सेट करें, और इस वर्कफ़्लो को अपने बड़े .NET अनुप्रयोगों में एकीकृत करके स्वचालित, उच्च‑गुणवत्ता वाले दस्तावेज़ निर्माण को प्राप्त करें।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**अंतिम अपडेट:** 2026-03-26  
**परीक्षण किया गया:** Aspose.TeX 24.11 for .NET  
**लेखक:** Aspose