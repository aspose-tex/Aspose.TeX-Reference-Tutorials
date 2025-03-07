---
title: Aspose.TeX (C#) ile LaTeX Şekillerini PNG'ye dönüştürün
linktitle: Aspose.TeX (C#) ile LaTeX Şekillerini PNG'ye dönüştürün
second_title: Aspose.TeX .NET API'si
description: C# dilinde Aspose.TeX kullanarak LaTeX rakamlarını PNG'ye dönüştürmeye ilişkin kapsamlı kılavuzu keşfedin. Kod örnekleriyle adım adım öğrenin.
weight: 10
url: /tr/net/render-latex-figures/png-latex-figure-renderer-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.TeX (C#) ile LaTeX Şekillerini PNG'ye dönüştürün

## giriiş

.NET'te dizgi ve belge oluşturma dünyasını araştırıyorsanız, muhtemelen LaTeX rakamlarını oluşturmanın zorluklarına aşinasınızdır. Bu adım adım kılavuzda, LaTeX rakamlarını C# kullanarak PNG formatına dönüştürmek için Aspose.TeX for .NET'in nasıl kullanılacağını keşfedeceğiz. Aspose.TeX, LaTeX belgelerinin işlenmesi için güçlü ve esnek bir çözüm sunarak onu belge oluşturma ve biçimlendirmeyle çalışan geliştiriciler için paha biçilmez bir araç haline getiriyor.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

-  Aspose.TeX for .NET Library: Aspose.TeX for .NET kütüphanesinin kurulu olduğundan emin olun. İndirebilirsin[Burada](https://releases.aspose.com/tex/net/).

## Ad Alanlarını İçe Aktar

C# kodunuzda gerekli ad alanlarını içe aktararak başlayın. Bu adım, gerekli sınıflara ve işlevlere erişmenizi sağlar.

```csharp
using Aspose.TeX.Features;
```

## LaTeX Rakamlarını PNG'ye Dönüştür

### 1. Adım: Oluşturma Seçeneklerini Ayarlayın

Oluşturma seçenekleri oluşturarak ve görüntü çözünürlüğü, giriş bölümü, ölçeklendirme faktörü, arka plan rengi ve daha fazlası gibi parametreleri ayarlayarak başlayın.

```csharp
FigureRendererOptions options = new PngFigureRendererOptions() { Resolution = 150 };
options.Preamble = "\\usepackage{pict2e}";
options.Scale = 3000;
options.BackgroundColor = System.Drawing.Color.White;
options.LogStream = new System.IO.MemoryStream();
options.ShowTerminal = true;
```

### Adım 2: Çıkış Akışını ve Boyutlarını Tanımlayın

Ortaya çıkan görüntünün boyutlarını depolamak için PNG görüntüsü ve değişkenler için bir çıkış akışı oluşturun.

```csharp
System.Drawing.SizeF size = new System.Drawing.SizeF();
using (System.IO.Stream stream = System.IO.File.Open(
   System.IO.Path.Combine("Your Output Directory", "text-and-formula.png"), System.IO.FileMode.Create))
{
    // Oluşturma kodu buraya gelecek
}
```

### 3. Adım: İşlemeyi Çalıştırın

Aspose.TeX kütüphanesini kullanarak işleme sürecini uygulayın. LaTeX kodunu, çıktı akışını, işleme seçeneklerini ve boyut değişkenini sağlayın.

```csharp
new PngFigureRenderer().Render(@"\setlength{\unitlength}{0.8cm}
\begin{picture}(6,5)
    % LaTeX figure code goes here
\end{picture}", stream, options, out size);
```

### Adım 4: Sonuçları Görüntüleyin

Son olarak, hata raporları ve oluşturulan görüntünün boyutu da dahil olmak üzere sonuçları görüntüleyin.

```csharp
System.Console.Out.WriteLine(options.ErrorReport);
System.Console.Out.WriteLine();
System.Console.Out.WriteLine("Size: " + size);
```

## Çözüm

Aspose.TeX for .NET ile LaTeX rakamlarını PNG formatına dönüştürmek sorunsuz bir süreç haline geliyor. Bu eğitim, işleme seçeneklerinin ayarlanmasından nihai sonuçların görüntülenmesine kadar temel adımlarda size yol gösterdi.

## SSS'ler

### S1: Aspose.TeX tüm LaTeX komutlarıyla uyumlu mu?

 Cevap1: Aspose.TeX çok çeşitli LaTeX komutlarını destekler, ancak şu adrese başvurmanız önerilir:[dokümantasyon](https://reference.aspose.com/tex/net/) detaylı bilgi için.

### S2: Satın almadan önce Aspose.TeX'i deneyebilir miyim?

 C2: Evet, ücretsiz deneme sürümünü keşfedebilirsiniz[Burada](https://releases.aspose.com/).

### S3: Aspose.TeX desteğini nasıl alabilirim?

 A3: Ziyaret edin[Aspose.TeX forumu](https://forum.aspose.com/c/tex/47)topluluk desteği ve tartışmalar için.

### S4: Aspose.TeX'in geçici lisanslarını nerede bulabilirim?

 Cevap4: Geçici lisanslar mevcut[Burada](https://purchase.aspose.com/temporary-license/).

### S5: Aspose.TeX'in fiyatlandırma yapısı nedir?

Cevap5: Fiyatlandırma ayrıntılarını keşfedin ve satın alma işlemi yapın[Burada](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
