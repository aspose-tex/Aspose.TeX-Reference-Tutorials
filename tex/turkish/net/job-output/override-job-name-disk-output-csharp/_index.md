---
title: İş Adını Geçersiz Kıl ve Terminal Çıkışını Diske Yaz (C#)
linktitle: İş Adını Geçersiz Kıl ve Terminal Çıkışını Diske Yaz (C#)
second_title: Aspose.TeX .NET API'si
description: İş adlarını geçersiz kılmak ve terminal çıktısını yakalamak için Aspose.TeX for .NET'in nasıl kullanılacağını keşfedin. Sorunsuz TeX dosya yönetimi için kapsamlı kılavuzumuzu takip edin.
weight: 10
url: /tr/net/job-output/override-job-name-disk-output-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# İş Adını Geçersiz Kıl ve Terminal Çıkışını Diske Yaz (C#)

## giriiş

C# programlama dilinde Aspose.TeX for .NET'in iş adlarını geçersiz kılmak ve terminal çıktısını diske yazmak için nasıl kullanılacağını anlatan bu adım adım kılavuza hoş geldiniz. Aspose.TeX for .NET, TeX dosyalarıyla sorunsuz bir şekilde çalışmanıza olanak tanıyan güçlü bir kütüphanedir ve bu eğitimde belirli bir göreve odaklanacağız: iş adlarını geçersiz kılmak ve terminal çıktısını yakalamak.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

-  Aspose.TeX for .NET Library: Aspose.TeX for .NET kütüphanesinin kurulu olduğundan emin olun. adresinden indirebilirsiniz.[Aspose.TeX web sitesi](https://releases.aspose.com/tex/net/).

- .NET Geliştirme Ortamı: Visual Studio gibi entegre bir geliştirme ortamı (IDE) içeren, çalışan bir .NET geliştirme ortamına sahip olun.

- Temel C# Bilgisi: C# programlama dilinin temellerine aşina olun.

- Giriş ve Çıkış Dizinleri: TeX dosyalarınız için giriş ve çıkış dizinlerini hazırlayın.

## Ad Alanlarını İçe Aktar

Aspose.TeX işlevlerine erişmek için C# kodunuza gerekli ad alanlarını eklediğinizden emin olun:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

## 1. Adım: Dönüşüm Seçenekleri Oluşturun

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

TeXConfig olarak ObjectTeX'i belirterek ConsoleAppOptions ile TeXOptions oluşturun.

## Adım 2: İş Adını Belirleyin

```csharp
options.JobName = "overridden-job-name";
```

Varsayılan adı geçersiz kılmak için iş adını belirtin.

## 3. Adım: Giriş Çalışma Dizinini Belirleyin

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

TeX dosyalarınız için giriş çalışma dizinini ayarlayın.

## Adım 4: Çıkış Çalışma Dizinini Belirleyin

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

İşlenen TeX dosyalarını kaydetmek için çıktı çalışma dizinini tanımlayın.

## Adım 5: Terminal Çıkışını Diske Yazma

```csharp
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

Terminal çıkışını, çıkış dizinindeki bir dosyaya yazılacak şekilde yapılandırın.

## Adım 6: İşi Çalıştırın

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

Bir iş adını, çıkış cihazını (XpsDevice) ve seçenekleri belirterek bir TeXJob oluşturun. Son olarak işi çalıştırın.

## Çözüm

Tebrikler! Aspose.TeX for .NET'i C# dilinde kullanarak iş adlarını geçersiz kılmayı ve terminal çıktısını diske yazmayı başarıyla öğrendiniz. Bu yetenek, TeX işleme görevlerinizi verimli bir şekilde yönetmek için değerlidir.

## SSS'ler

### S1: Aspose.TeX for .NET'i diğer .NET kütüphaneleriyle birlikte kullanabilir miyim?

Cevap1: Evet, Aspose.TeX for .NET diğer .NET kütüphaneleriyle sorunsuz bir şekilde entegre edilebilir.

### S2: Aspose.TeX for .NET'in ücretsiz deneme sürümü mevcut mu?

 A2: Evet, ücretsiz deneme sürümünü indirebilirsiniz[Burada](https://releases.aspose.com/).

### S3: Aspose.TeX for .NET desteğini nasıl alabilirim?

 A3: Ziyaret edin[Aspose.TeX forumu](https://forum.aspose.com/c/tex/47) topluluk ve destek almak için.

### S4: Aspose.TeX for .NET için geçici lisanslar mevcut mu?

 Cevap4: Evet, geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).

### S5: Aspose.TeX for .NET belgelerini nerede bulabilirim?

 A5: Belgeler mevcut[Burada](https://reference.aspose.com/tex/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
