---
title: .NET'te TeX'i XPS'ye dizme
linktitle: .NET'te TeX'i XPS'ye dizme
second_title: Aspose.TeX .NET API'si
description: Aspose.TeX ile TeX belgelerini zahmetsizce .NET'te XPS'ye dönüştürün. Sorunsuz bir entegrasyon deneyimi için adım adım kılavuzumuzu keşfedin.
weight: 10
url: /tr/net/xps-output/typeset-tex-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET'te TeX'i XPS'ye dizme

## giriiş

Güçlü Aspose.TeX kütüphanesini kullanarak .NET'te TeX'ten XPS'ye dizgiye ilişkin adım adım kılavuzumuza hoş geldiniz. .NET uygulamalarınızda TeX belgelerini sorunsuz bir şekilde XPS formatına dönüştürmek istiyorsanız doğru yere geldiniz. Bu eğitimde, sorunsuz bir uygulama sağlamak için her adımı parçalara ayırarak tüm süreç boyunca size yol göstereceğiz.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

-  Aspose.TeX for .NET: Aspose.TeX kütüphanesinin kurulu olduğundan emin olun. İndirebilirsin[Burada](https://releases.aspose.com/tex/net/).

- Dokümantasyon: Dokümantasyona başvurarak kütüphaneyi tanıyın[Burada](https://reference.aspose.com/tex/net/).

- Giriş ve Çıkış Dizinleri: Giriş ve çıkış dizinlerinizi örnek kodda belirtildiği gibi ayarlayın.

Artık her şeyi ayarladığınıza göre, adım adım kılavuza geçelim.

## Ad Alanlarını İçe Aktar

.NET uygulamanızda gerekli ad alanlarını içe aktararak başlayın. Bu, TeX'i XPS'ye dizmek için gereken Aspose.TeX işlevlerine erişmenizi sağlar.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
```

## 1. Adım: Dönüştürme Seçeneklerini Ayarlayın

ObjectTeX motor uzantısında ObjectTeX biçimini belirterek dönüştürme seçeneklerini tanımlayın. Ayrıca iş adını, giriş ve çıkış dizinlerini ve terminal çıkış ayrıntılarını da ayarlayın.

```csharp
// ObjectTeX motor uzantısı üzerine varsayılan ObjectTeX formatı için dönüştürme seçenekleri oluşturun.
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
// Bir iş adı belirtin.
options.JobName = "external-file-stream";
// Giriş için bir dosya sistemi çalışma dizini belirtin.
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
// Çıktı için bir dosya sistemi çalışma dizini belirtin.
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
// Terminal çıktısının, çıktı çalışma dizinindeki bir dosyaya yazılması gerektiğini belirtin.
// Dosya adı <iş_adı>.trm'dir.
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## 2. Adım: XPS Belge Akışı Oluşturun

Dizgi XPS belgesini yazmak için bir akış açın. Dosya adının iş adıyla aynı olması gerekmez.

```csharp
using (Stream stream = File.Open(Path.Combine("Your Output Directory", options.JobName + ".xps"), FileMode.Create))
```

## 3. Adım: TeX İşini çalıştırın

Belge adını, XpsDevice'ı ve dönüştürme seçeneklerini belirterek TeX işini başlatın ve çalıştırın.

```csharp
new TeXJob("hello-world", new XpsDevice(stream), options).Run();
```

Tebrikler! Aspose.TeX'i kullanarak .NET'te TeX'i XPS'ye başarıyla dizdiniz. Özel gereksinimlerinize göre daha fazla özellik ve seçeneği keşfetmekten çekinmeyin.

## Çözüm

Bu eğitimde, Aspose.TeX'i kullanarak TeX belgelerini .NET'te XPS formatına sorunsuz bir şekilde dönüştürmek için gerekli adımları ele aldık. Bu kılavuzu takip ederek kütüphanenin yetenekleri ve projelerinizde bunlardan nasıl yararlanabileceğiniz konusunda değerli bilgiler edindiniz.

## SSS'ler

### S1: Aspose.TeX .NET Core ile uyumlu mu?

Cevap1: Evet, Aspose.TeX, .NET Core ile tamamen uyumludur.

### S2: Aspose.TeX'i ticari projeler için kullanabilir miyim?

A2: Kesinlikle! Aspose.TeX hem ticari hem de kişisel kullanım için mevcuttur.

### S3: Ek örnekleri ve kaynakları nerede bulabilirim?

 Cevap3: Aspose.TeX belgelerini inceleyin[Burada](https://reference.aspose.com/tex/net/)Daha fazla örnek ve ayrıntılı kaynaklar için.

### S4: Aspose.TeX için nasıl destek alabilirim?

 Cevap4: Aspose.TeX destek forumunu ziyaret edin[Burada](https://forum.aspose.com/c/tex/47) toplumdan yardım almak için.

### S5: Ücretsiz deneme sürümü mevcut mu?

 C5: Evet, ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
