---
title: Aspose.TeX (C#) के साथ LaTeX आंकड़े SVG में प्रस्तुत करें
linktitle: Aspose.TeX (C#) के साथ LaTeX आंकड़े SVG में प्रस्तुत करें
second_title: Aspose.TeX .NET एपीआई
description: Aspose.TeX के साथ .NET में दस्तावेज़ रेंडरिंग बढ़ाएँ। गणितीय अभिव्यक्तियों के निर्बाध एकीकरण के लिए C# में LaTeX आंकड़ों को SVG में प्रस्तुत करना सीखें।
weight: 11
url: /hi/net/render-latex-figures/svg-latex-figure-renderer-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.TeX (C#) के साथ LaTeX आंकड़े SVG में प्रस्तुत करें

## परिचय

यदि आप LaTeX आंकड़ों का उपयोग करके .NET में अपनी दस्तावेज़ रेंडरिंग क्षमताओं को बढ़ाना चाहते हैं, तो Aspose.TeX आपके लिए उपयुक्त समाधान है। इस चरण-दर-चरण मार्गदर्शिका में, हम आपको C# में Aspose.TeX का उपयोग करके SVG में LaTeX आंकड़े प्रस्तुत करने के बारे में बताएंगे। इस ट्यूटोरियल के अंत तक, आपको प्रक्रिया की स्पष्ट समझ हो जाएगी, जो आपको अपने दस्तावेज़ों में उच्च गुणवत्ता वाले गणितीय अभिव्यक्तियों और आंकड़ों को सहजता से शामिल करने के लिए सशक्त बनाएगी।

## आवश्यक शर्तें

इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

- C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान।
-  .NET लाइब्रेरी के लिए Aspose.TeX स्थापित किया गया। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tex/net/).

## नामस्थान आयात करें

अपने C# कोड में, आवश्यक नामस्थान आयात करना सुनिश्चित करें:

```csharp
using Aspose.TeX.Features;
```

अब, आइए ट्यूटोरियल को कई चरणों में विभाजित करें:

## चरण 1: रेंडरिंग विकल्प बनाएं

```csharp
FigureRendererOptions options = new SvgFigureRendererOptions();
options.Preamble = "\\usepackage{pict2e}";
options.Scale = 3000;
options.BackgroundColor = Color.White;
options.LogStream = new System.IO.MemoryStream();
options.ShowTerminal = true;
```

यहां, हम प्रस्तावना, स्केलिंग कारक, पृष्ठभूमि रंग, लॉग स्ट्रीम और टर्मिनल आउटपुट दिखाना है या नहीं, यह निर्दिष्ट करते हुए रेंडरिंग विकल्प सेट करते हैं।

## चरण 2: आयाम और आउटपुट स्ट्रीम को परिभाषित करें

```csharp
SizeF size = new SizeF();
using (Stream stream = File.Open(Path.Combine("Your Output Directory", "text-and-formula.svg"), FileMode.Create))
{
    // प्रतिपादन चलाएँ.
    new SvgFigureRenderer().Render("Your LaTeX Code", stream, options, out size);
}
```

"आपकी आउटपुट निर्देशिका" को अपनी इच्छित निर्देशिका से बदलें और एक स्ट्रिंग के रूप में अपना LaTeX कोड प्रदान करें।

## चरण 3: परिणाम प्रदर्शित करें

```csharp
Console.Out.WriteLine(options.ErrorReport);
Console.Out.WriteLine();
Console.Out.WriteLine("Size: " + size);
```

यह चरण किसी भी त्रुटि रिपोर्ट और परिणामी छवि का आकार प्रदर्शित करता है।

## निष्कर्ष

बधाई हो! आपने C# में Aspose.TeX का उपयोग करके LaTeX आंकड़ों को SVG में प्रस्तुत करना सफलतापूर्वक सीख लिया है। अब, आप गणितीय अभिव्यक्तियों और आंकड़ों को अपने .NET अनुप्रयोगों में निर्बाध रूप से एकीकृत कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या Aspose.TeX का उपयोग निःशुल्क है?

 A1: Aspose.TeX निःशुल्क परीक्षण प्रदान करता है। आप इसे एक्सेस कर सकते हैं[यहाँ](https://releases.aspose.com/).

### Q2: मुझे Aspose.TeX दस्तावेज़ कहां मिल सकता है?

 A2: दस्तावेज़ देखें[यहाँ](https://reference.aspose.com/tex/net/).

### Q3: मुझे Aspose.TeX के लिए समर्थन कैसे मिलेगा?

 उ3: सहायता मंच पर जाएँ[यहाँ](https://forum.aspose.com/c/tex/47).

### Q4: क्या मैं Aspose.TeX खरीद सकता हूँ?

 A4: हाँ, आप Aspose.TeX खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).

### Q5: क्या मुझे अस्थायी लाइसेंस की आवश्यकता है?

 A5: यदि आवश्यक हो, तो आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
