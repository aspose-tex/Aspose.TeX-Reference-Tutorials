---
title: Aspose.TeX (C#) के साथ LaTeX आंकड़ों को PNG में प्रस्तुत करें
linktitle: Aspose.TeX (C#) के साथ LaTeX आंकड़ों को PNG में प्रस्तुत करें
second_title: Aspose.TeX .NET एपीआई
description: C# में Aspose.TeX का उपयोग करके PNG में LaTeX आंकड़े प्रस्तुत करने पर एक व्यापक मार्गदर्शिका देखें। कोड उदाहरणों के साथ चरण-दर-चरण सीखें।
weight: 10
url: /hi/net/render-latex-figures/png-latex-figure-renderer-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.TeX (C#) के साथ LaTeX आंकड़ों को PNG में प्रस्तुत करें

## परिचय

यदि आप .NET में टाइपसेटिंग और दस्तावेज़ निर्माण की दुनिया में गहराई से उतर रहे हैं, तो आप संभवतः LaTeX आंकड़े प्रस्तुत करने की चुनौतियों से परिचित होंगे। इस चरण-दर-चरण मार्गदर्शिका में, हम यह पता लगाएंगे कि C# का उपयोग करके LaTeX आंकड़ों को PNG प्रारूप में प्रस्तुत करने के लिए .NET के लिए Aspose.TeX का उपयोग कैसे करें। Aspose.TeX, LaTeX दस्तावेज़ों को संभालने के लिए एक शक्तिशाली और लचीला समाधान प्रदान करता है, जो इसे दस्तावेज़ निर्माण और स्वरूपण के साथ काम करने वाले डेवलपर्स के लिए एक अमूल्य उपकरण बनाता है।

## आवश्यक शर्तें

इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

-  .NET लाइब्रेरी के लिए Aspose.TeX: सुनिश्चित करें कि आपके पास .NET के लिए Aspose.TeX लाइब्रेरी स्थापित है। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tex/net/).

## नामस्थान आयात करें

अपने C# कोड में, आवश्यक नामस्थान आयात करके प्रारंभ करें। यह चरण सुनिश्चित करता है कि आपके पास आवश्यक कक्षाओं और कार्यात्मकताओं तक पहुंच है।

```csharp
using Aspose.TeX.Features;
```

## LaTeX आकृतियों को PNG में प्रस्तुत करें

### चरण 1: रेंडरिंग विकल्प सेट करें

रेंडरिंग विकल्प बनाकर और छवि रिज़ॉल्यूशन, प्रस्तावना, स्केलिंग कारक, पृष्ठभूमि रंग और बहुत कुछ जैसे पैरामीटर सेट करके प्रारंभ करें।

```csharp
FigureRendererOptions options = new PngFigureRendererOptions() { Resolution = 150 };
options.Preamble = "\\usepackage{pict2e}";
options.Scale = 3000;
options.BackgroundColor = System.Drawing.Color.White;
options.LogStream = new System.IO.MemoryStream();
options.ShowTerminal = true;
```

### चरण 2: आउटपुट स्ट्रीम और आयाम परिभाषित करें

परिणामी छवि के आयामों को संग्रहीत करने के लिए पीएनजी छवि और चर के लिए एक आउटपुट स्ट्रीम बनाएं।

```csharp
System.Drawing.SizeF size = new System.Drawing.SizeF();
using (System.IO.Stream stream = System.IO.File.Open(
   System.IO.Path.Combine("Your Output Directory", "text-and-formula.png"), System.IO.FileMode.Create))
{
    // रेंडरिंग के लिए कोड यहां जाता है
}
```

### चरण 3: रेंडरिंग चलाएँ

Aspose.TeX लाइब्रेरी का उपयोग करके रेंडरिंग प्रक्रिया लागू करें। LaTeX कोड, आउटपुट स्ट्रीम, रेंडरिंग विकल्प और आकार चर प्रदान करें।

```csharp
new PngFigureRenderer().Render(@"\setlength{\unitlength}{0.8cm}
\begin{picture}(6,5)
    % LaTeX figure code goes here
\end{picture}", stream, options, out size);
```

### चरण 4: परिणाम प्रदर्शित करें

अंत में, किसी भी त्रुटि रिपोर्ट और प्रस्तुत छवि के आकार सहित परिणाम प्रदर्शित करें।

```csharp
System.Console.Out.WriteLine(options.ErrorReport);
System.Console.Out.WriteLine();
System.Console.Out.WriteLine("Size: " + size);
```

## निष्कर्ष

.NET के लिए Aspose.TeX के साथ, LaTeX आंकड़ों को PNG प्रारूप में प्रस्तुत करना एक सहज प्रक्रिया बन जाती है। इस ट्यूटोरियल ने आपको रेंडरिंग विकल्प सेट करने से लेकर अंतिम परिणाम प्रदर्शित करने तक आवश्यक चरणों के बारे में बताया है।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या Aspose.TeX सभी LaTeX कमांड के साथ संगत है?

 A1: Aspose.TeX LaTeX कमांड की एक विस्तृत श्रृंखला का समर्थन करता है, लेकिन इसे संदर्भित करने की अनुशंसा की जाती है[प्रलेखन](https://reference.aspose.com/tex/net/) विस्तृत जानकारी के लिए.

### Q2: क्या मैं खरीदने से पहले Aspose.TeX आज़मा सकता हूँ?

 उ2: हां, आप निःशुल्क परीक्षण संस्करण तलाश सकते हैं[यहाँ](https://releases.aspose.com/).

### Q3: मुझे Aspose.TeX के लिए समर्थन कैसे मिलेगा?

 A3: पर जाएँ[Aspose.TeX फोरम](https://forum.aspose.com/c/tex/47)सामुदायिक समर्थन और चर्चा के लिए।

### Q4: मुझे Aspose.TeX के लिए अस्थायी लाइसेंस कहां मिल सकते हैं?

 A4: अस्थायी लाइसेंस उपलब्ध हैं[यहाँ](https://purchase.aspose.com/temporary-license/).

### Q5: Aspose.TeX के लिए मूल्य निर्धारण संरचना क्या है?

A5: मूल्य निर्धारण विवरण देखें और खरीदारी करें[यहाँ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
