---
title: Aspose.TeX (C#) ile LaTeX Şekillerini SVG'ye dönüştürün
linktitle: Aspose.TeX (C#) ile LaTeX Şekillerini SVG'ye dönüştürün
second_title: Aspose.TeX .NET API'si
description: Aspose.TeX ile .NET'te belge görüntülemeyi geliştirin. Matematiksel ifadelerin sorunsuz entegrasyonu için LaTeX rakamlarını C# dilinde SVG'ye nasıl dönüştüreceğinizi öğrenin.
type: docs
weight: 11
url: /tr/net/render-latex-figures/svg-latex-figure-renderer-csharp/
---
## giriiş

LaTeX rakamlarını kullanarak .NET'te belge oluşturma yeteneklerinizi geliştirmek istiyorsanız Aspose.TeX sizin çözümünüzdür. Bu adım adım kılavuzda, C# dilinde Aspose.TeX kullanarak LaTeX rakamlarını SVG'ye dönüştürme konusunda size yol göstereceğiz. Bu eğitimin sonunda süreci net bir şekilde anlayacak ve yüksek kaliteli matematiksel ifadeleri ve rakamları belgelerinize sorunsuz bir şekilde dahil edebileceksiniz.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Temel C# programlama dili bilgisi.
-  Aspose.TeX for .NET kütüphanesi kuruldu. İndirebilirsin[Burada](https://releases.aspose.com/tex/net/).

## Ad Alanlarını İçe Aktar

C# kodunuzda gerekli ad alanlarını içe aktardığınızdan emin olun:

```csharp
using Aspose.TeX.Features;
```

Şimdi öğreticiyi birden fazla adıma ayıralım:

## 1. Adım: Oluşturma Seçenekleri Oluşturun

```csharp
FigureRendererOptions options = new SvgFigureRendererOptions();
options.Preamble = "\\usepackage{pict2e}";
options.Scale = 3000;
options.BackgroundColor = Color.White;
options.LogStream = new System.IO.MemoryStream();
options.ShowTerminal = true;
```

Burada, girişi, ölçeklendirme faktörünü, arka plan rengini, günlük akışını ve terminal çıktısının gösterilip gösterilmeyeceğini belirterek oluşturma seçeneklerini ayarlıyoruz.

## 2. Adım: Boyutları ve Çıkış Akışını Tanımlayın

```csharp
SizeF size = new SizeF();
using (Stream stream = File.Open(Path.Combine("Your Output Directory", "text-and-formula.svg"), FileMode.Create))
{
    // Oluşturmayı çalıştırın.
    new SvgFigureRenderer().Render("Your LaTeX Code", stream, options, out size);
}
```

"Çıktı Dizininiz"i istediğiniz dizinle değiştirin ve LaTeX kodunuzu bir dize olarak sağlayın.

## 3. Adım: Sonuçları Görüntüleyin

```csharp
Console.Out.WriteLine(options.ErrorReport);
Console.Out.WriteLine();
Console.Out.WriteLine("Size: " + size);
```

Bu adım, tüm hata raporlarını ve ortaya çıkan görüntünün boyutunu görüntüler.

## Çözüm

Tebrikler! C# dilinde Aspose.TeX kullanarak LaTeX rakamlarını SVG'ye nasıl aktaracağınızı başarıyla öğrendiniz. Artık matematiksel ifadeleri ve rakamları .NET uygulamalarınıza sorunsuz bir şekilde entegre edebilirsiniz.

## SSS'ler

### S1: Aspose.TeX'in kullanımı ücretsiz mi?

 Cevap1: Aspose.TeX ücretsiz deneme sürümü sunuyor. Erişebilirsin[Burada](https://releases.aspose.com/).

### S2: Aspose.TeX belgelerini nerede bulabilirim?

 A2: Belgelere bakın[Burada](https://reference.aspose.com/tex/net/).

### S3: Aspose.TeX desteğini nasıl alabilirim?

 Cevap 3: Destek forumunu ziyaret edin[Burada](https://forum.aspose.com/c/tex/47).

### S4: Aspose.TeX'i satın alabilir miyim?

 Cevap4: Evet, Aspose.TeX'i satın alabilirsiniz[Burada](https://purchase.aspose.com/buy).

### S5: Geçici bir lisansa ihtiyacım var mı?

 Cevap5: Gerekirse geçici lisans alabilirsiniz.[Burada](https://purchase.aspose.com/temporary-license/).