---
date: 2026-02-10
description: Aspose.TeX for Java kullanarak özel tex formatı oluşturmayı ve tex java’yı
  nasıl biçimlendireceğinizi öğrenin; adım adım kurulum, özel format işleme ve geçici
  lisans edinmeyi içeren.
linktitle: How to Typeset TeX with Custom Formats in Java
second_title: Aspose.TeX Java API
title: Java'da Özel TeX Formatı Oluşturma ve TeX'i Biçimlendirme
url: /tr/java/custom-tex-formats/typesetting-custom-tex-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java'da Özel TeX Formatı Oluşturma ve TeX'i Türlemek

## Introduction

Eğer bir Java uygulaması içinde **özel tex formatı oluşturmak** ve TeX'i türlemek istiyorsanız, Aspose.TeX, özel TeX format dosyalarıyla çalışmak için temiz ve yüksek performanslı bir yol sunar. Bu öğreticide, ortamı kurmaktan kendi formatınızı kullanan bir TeX işini çalıştırmaya kadar ihtiyacınız olan her şeyi adım adım göstereceğiz. Bilimsel yayınlama aracı ya da özel rapor oluşturucu geliştiriyor olun, aşağıdaki adımlar sizi hızlı bir şekilde çalışır duruma getirecek.

## Quick Answers
- **Hangi kütüphane gerekiyor?** Aspose.TeX for Java  
- **Özel bir TeX formatı kullanabilir miyim?** Evet – sadece `FormatProvider`'ı dosyanıza yönlendirin.  
- **Geliştirme için lisansa ihtiyacım var mı?** Test için geçici bir aspose lisansı yeterli; üretim için tam lisans gerekir.  
- **Hangi Java sürümü destekleniyor?** JDK 8 ve üzeri.  
- **Örnekte hangi çıktı formatı üretiliyor?** XPS (PDF, PNG vb. formatlara geçebilirsiniz).

## What is a Custom TeX Format?
Özel bir TeX formatı, TeX motorunu belirli belge stilinize göre uyarlayan önceden derlenmiş makrolar ve ilkelere sahip bir settir. Kendi `.fmt` dosyanızı sağlayarak, her seferinde kaynak TeX'i değiştirmeden yazı tiplerini, düzen kurallarını ve komut tanımlarını kontrol edebilirsiniz.

## Why Use Aspose.TeX for Java?
- **Saf Java** – Yerel ikili dosyalar yok, herhangi bir JVM tabanlı projeye kolayca gömülebilir.  
- **Yüksek doğruluk** – LaTeX‑stilinde render ile eşleşen çıktı üretir.  
- **Genişletilebilir** – Özel formatları, birden çok çıktı cihazını ve toplu işleme destekler.  
- **Lisans esnekliği** – Önce geçici bir aspose lisansı ile başlayın, yayına alırken yükseltin.

## Prerequisites

1. **Java Development Kit (JDK)** – JDK 8 veya daha yeni bir sürüm kurulu. Henüz kurmadıysanız resmi [Java web sitesinden](https://www.oracle.com/java/technologies/javase-downloads.html) indirin.  
2. **Aspose.TeX library for Java** – En son JAR dosyasını [Aspose.TeX for Java indirme sayfasından](https://releases.aspose.com/tex/java/) alın.  
3. **Your custom TeX format file** – Derlenmiş `.fmt` dosyasını (ör. `customtex.fmt`) çıktı dizini olarak kullanılacak bir klasöre koyun.  

> **Pro tip:** Ürünü değerlendiriyorsanız, Aspose portalından *geçici bir aspose lisansı* talep edin; bu, değerlendirme filigranını sınırlı bir süre için kaldırır.

## Import Packages

First, add the required imports to your Java project. These classes give you access to the format provider, job configuration, and rendering device.

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

## Step‑by‑Step Guide

### Step 1: Create a Format Provider

`FormatProvider`, özel TeX format dosyanızı içeren dizini gösterir. `"Your Output Directory"` ifadesini `customtex.fmt` dosyanızın bulunduğu gerçek yol ile değiştirin.

```java
final FormatProvider formatProvider = new FormatProvider(
        new InputFileSystemDirectory("Your Output Directory"), "customtex");
```

### Step 2: Set Conversion Options

İşi, özel formatları anlayan ObjectTeX motorunu kullanacak şekilde yapılandırın. Burada ayrıca iş adını ayarlıyor ve giriş/çıkış çalışma dizinlerini belirtiyoruz.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX(formatProvider));
options.setJobName("typeset-with-custom-format");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### Step 3: Run the TeX Job

Bir `TeXJob` örneği oluşturun, ona basit bir TeX kod parçası verin ve sonucu bir `XpsDevice` ile render etmesini söyleyin. Kod parçası belgeyi kapatmak için `\end` ile sonlanır.

```java
new TeXJob(new ByteArrayInputStream(
        "Congratulations! You have successfully typeset this text with your own TeX format!\\end".getBytes("ASCII")),
        new XpsDevice(), options).run();
```

### Step 4: Finalize Output

İş tamamlandıktan sonra, terminal çıktısına bir satır sonu ekleyerek konsolun düzenli kalmasını sağlayın.

```java
options.getTerminalOut().getWriter().newLine();
```

### Step 5: Close the Format Provider

İşiniz bittiğinde, dosya tanıtıcılarını serbest bırakmak ve kaynakları temizlemek için sağlayıcıyı kapatın.

```java
formatProvider.close();
```

## Common Use Cases

- **Otomatik bilimsel makale üretimi** – Dergiye özgü makroları içeren önceden derlenmiş bir format kullanın.  
- **Dinamik rapor oluşturma** – LaTeX kaynaklarını her seferinde yeniden derlemeden faturalar veya sertifikalar anında oluşturun.  
- **Büyük belge koleksiyonlarının toplu işlenmesi** – Özel bir formatı bir kez yükleyip yüzlerce dosyada yeniden kullanın, işlem süresini büyük ölçüde azaltır.

## Common Issues and Solutions

| Issue | Cause | Fix |
|-------|-------|-----|
| **“Format dosyası bulunamadı”** | `FormatProvider` içinde yanlış yol | Dizin ve dosya adının (`customtex.fmt`) doğru ve erişilebilir olduğunu doğrulayın. |
| **Kodlama hataları** | TeX dizesindeki ASCII dışı karakterler | `UTF-8` kodlamasını (`"ASCII"` yerine) kullanın. |
| **Çıktı oluşturulmadı** | Çıktı dizininde yazma izni yok | Java sürecinin `"Your Output Directory"` dizinine yazma izni olduğundan emin olun. |
| **Lisans filigranı** | Sadece değerlendirme lisansı kullanılıyor | Test için *geçici bir aspose lisansı* uygulayın veya üretim için tam lisans satın alın. |

**Related Resources:** [Aspose.TeX API Reference](https://docs.aspose.com/tex/java/) | [Download Free Trial](https://releases.aspose.com/tex/java/)

## Frequently Asked Questions

**Q: Aspose.TeX'i diğer Java kütüphaneleriyle birlikte kullanabilir miyim?**  
A: Kesinlikle. API saf Java'dır ve Apache PDFBox, iText veya Spring Boot gibi kütüphanelerle birlikte çalışır.

**Q: Değerlendirme için geçici bir aspose lisansı nereden alınır?**  
A: [Aspose geçici lisans sayfasından](https://purchase.aspose.com/temporary-license/) bir tane isteyin. Bu, değerlendirme filigranını 30 güne kadar kaldırır.

**Q: Aspose.TeX XPS dışındaki çıktı formatlarını destekliyor mu?**  
A: Evet. İhtiyacınıza göre `new XpsDevice()` ifadesini `new PdfDevice()`, `new PngDevice()` vb. ile değiştirebilirsiniz.

**Q: Başarısız bir TeX işini nasıl hata ayıklayabilirim?**  
A: `options.setLogLevel(LogLevel.DEBUG);` çağrısı yaparak ayrıntılı günlüklemeyi etkinleştirin ve konsol çıktısını inceleyerek hata mesajlarını detaylı şekilde görebilirsiniz.

**Q: Ücretsiz deneme sürümü mevcut mu?**  
A: Evet – deneme ikili dosyalarını [Aspose.TeX indirme sayfasından](https://releases.aspose.com/tex/java/) indirebilirsiniz.

**Q: Aynı uygulamada birden fazla özel format oluşturabilir miyim?**  
A: Evet. Her `.fmt` dosyası için ayrı bir `FormatProvider` örneği oluşturup uygun sağlayıcıyı `TeXConfig.objectTeX()` metoduna geçirebilirsiniz.

## Conclusion

Artık **özel tex formatı nasıl oluşturulur** ve **java içinde tex nasıl türlenir** konularını Aspose.TeX kullanarak bir Java uygulamasında yapabildiğinizi biliyorsunuz. Yukarıdaki adımları izleyerek yüksek kaliteli tipografi işlemlerini herhangi bir Java‑tabanlı iş akışına entegre edebilir, kendi format dosyalarınızla deneyler yapabilir ve uygun bir lisansla prototip aşamasından üretime geçebilirsiniz.

---

**Last Updated:** 2026-02-10  
**Tested With:** Aspose.TeX for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}