---
title: İş Adını Geçersiz Kıl ve Terminal Çıkışını Zip'e Yaz (C#)
linktitle: İş Adını Geçersiz Kıl ve Terminal Çıkışını Zip'e Yaz (C#)
second_title: Aspose.TeX .NET API'si
description: Aspose.TeX for .NET kullanarak iş adlarını nasıl geçersiz kılacağınızı ve terminal çıktısını bir ZIP dosyasına nasıl yazacağınızı öğrenin. C# örnekleriyle adım adım kılavuz.
type: docs
weight: 11
url: /tr/net/job-output/override-job-name-zip-output-csharp/
---
## giriiş

Bu eğitimde, Aspose.TeX for .NET kullanarak iş adının nasıl geçersiz kılınacağını ve terminal çıktısının bir ZIP dosyasına nasıl yazılacağını inceleyeceğiz. Aspose.TeX, geliştiricilerin .NET uygulamalarında TeX belgeleriyle çalışmasına olanak tanıyan güçlü bir kütüphanedir. Bu özel örnekte, ortak bir göreve odaklanacağız: iş adını geçersiz kılma özelliğiyle terminal çıktısını bir ZIP dosyasına yazmak.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- C# hakkında çalışma bilgisi
- Aspose.TeX for .NET kuruldu
- Çalışma dizini için ZIP arşivini girin
- Terminal çıktısı için çıktı ZIP arşivi

## Ad Alanlarını İçe Aktar

Koda dalmadan önce C# projenize gerekli ad alanlarını eklediğinizden emin olun:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Pdf;
using System.IO;
```

Şimdi, süreç boyunca size yol göstermesi için örneği birden fazla adıma ayıralım.

## 1. Adım: Giriş ve Çıkış ZIP Akışlarını Açın

```csharp
using (Stream inZipStream = File.Open(Path.Combine("Your Input Directory", "zip-in.zip"), FileMode.Open))
using (Stream outZipStream = File.Open(Path.Combine("Your Output Directory", "terminal-out-to-zip.zip"), FileMode.Create))
{
    // 1. adımın kodu buraya gelecek
}
```

## 2. Adım: Dönüştürme Seçeneklerini Ayarlayın

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
options.JobName = "terminal-output-to-zip";
options.InputWorkingDirectory = new InputZipDirectory(inZipStream, "in");
options.OutputWorkingDirectory = new OutputZipDirectory(outZipStream);
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## 3. Adım: Kaydetme Seçeneklerini Tanımlayın

```csharp
options.SaveOptions = new PdfSaveOptions();
```

## Adım 4: TeX İşini Çalıştırın

```csharp
new TeXJob("hello-world", new PdfDevice(), options).Run();
```

## Adım 5: Çıktı ZIP Arşivini Sonlandırın

```csharp
((OutputZipDirectory)options.OutputWorkingDirectory).Finish();
```

## Çözüm

Tebrikler! Aspose.TeX for .NET'i kullanarak iş adını nasıl geçersiz kılacağınızı ve terminal çıktısını bir ZIP dosyasına nasıl yazacağınızı başarıyla öğrendiniz. Bu teknik, C# uygulamalarınızda TeX belgeleriyle uğraşırken inanılmaz derecede yararlı olabilir.

## SSS'ler

### S1: Aspose.TeX for .NET'i VB.NET gibi diğer .NET dilleriyle kullanabilir miyim?

Cevap1: Evet, Aspose.TeX for .NET tüm .NET dilleriyle uyumludur.

### S2: Aspose.TeX for .NET ile ilgili daha fazla belgeyi nerede bulabilirim?

 A2: Ziyaret edin[dokümantasyon](https://reference.aspose.com/tex/net/) detaylı bilgi için.

### S3: Aspose.TeX için nasıl geçici lisans alabilirim?

 A3: Bir[geçici lisans](https://purchase.aspose.com/temporary-license/) test amaçlı.

### S4: Aspose.TeX desteği için bir topluluk forumu var mı?

 A4: Evet, katılın[Aspose.TeX forumu](https://forum.aspose.com/c/tex/47) topluluk desteği için.

### S5: Aspose.TeX for .NET'i nereden satın alabilirim?

 Cevap5: Aspose.TeX'i satın alabilirsiniz[Burada](https://purchase.aspose.com/buy).