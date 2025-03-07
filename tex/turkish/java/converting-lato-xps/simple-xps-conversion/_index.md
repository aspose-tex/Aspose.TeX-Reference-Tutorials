---
title: LaTeX'i Java'da Kolaylıkla XPS Formatına Dönüştürün
linktitle: LaTeX'i Java'da Kolaylıkla XPS Formatına Dönüştürün
second_title: Aspose.TeX Java API'si
description: Aspose.TeX'i kullanarak LaTeX'i Java'da zahmetsizce XPS'ye dönüştürün. Sorunsuz entegrasyon için adım adım kılavuzumuzu izleyin.
weight: 10
url: /tr/java/converting-lato-xps/simple-xps-conversion/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# LaTeX'i Java'da Kolaylıkla XPS Formatına Dönüştürün

## giriiş

Java uygulamalarınızda LaTeX belgelerini sorunsuz bir şekilde XPS formatına dönüştürmek mi istiyorsunuz? Aspose.TeX for Java, bunu kolaylıkla başarabilmenizi sağlayan güçlü bir çözüm sunar. Bu adım adım kılavuzda, Aspose.TeX'i kullanarak LaTeX'i XPS'ye dönüştürme sürecinde size yol göstereceğiz.

## Önkoşullar

Dönüştürme sürecine dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:

- Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
-  Aspose.TeX for Java kütüphanesi indirildi. İndirme linkini bulabilirsiniz[Burada](https://releases.aspose.com/tex/java/).

## Paketleri İçe Aktar

Başlamak için Java projeniz için gerekli paketleri içe aktarın. Aspose.TeX kütüphanesini proje bağımlılıklarınıza dahil ettiğinizden emin olun.

```java
package com.aspose.tex.LaTeXXpsConversionSimplest;

import java.io.ByteArrayInputStream;
import java.io.IOException;
import java.util.Calendar;
import java.util.GregorianCalendar;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.Interaction;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;
import com.aspose.tex.rendering.XpsSaveOptions;

import util.Utils;
```

Şimdi sağlanan kod örneklerini kullanarak dönüştürme sürecini birden çok adıma ayıralım.

## Adım 1: Giriş ve Çıkış Dizinlerini Ayarlayın

```java
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

LaTeX giriş dosyanızın bulunduğu ve dönüştürülen XPS dosyasını kaydetmek istediğiniz dizinleri belirtin.

## Adım 2: TeX Seçeneklerini Yapılandırın

Dönüştürme sürecini ihtiyaçlarınıza göre özelleştirmek için çeşitli seçenekleri yapılandırın.

```java
options.setInteraction(Interaction.NonstopMode);
options.setDateTime(new GregorianCalendar(2022, Calendar.DECEMBER, 18).getTime());
options.ignoreMissingPackages(true);
options.noLigatures(true);
options.repeat(true);
```

Etkileşim modunu, başlıktaki tarihi, eksik paketlerin işlenmesini, bitişik harfleri ve tekrarı gerektiği gibi ayarlayın.

## 3. Adım: XPS Kaydetme Seçeneklerini Başlatın

```java
options.setSaveOptions(new XpsSaveOptions());
```

XPS formatında kaydetme seçeneklerini başlatın.

## 4. Adım: XPS Kaydetme Seçeneklerini Özelleştirin

```java
options.getSaveOptions().rasterizeFormulas(true);
options.getSaveOptions().rasterizeIncludedGraphics(true);
options.getSaveOptions().subsetFonts(true);
```

Formüllerin, dahil edilen grafiklerin ve yazı tipi alt kümelerinin dönüştürülmesini denetlemek için XPS kaydetme seçeneklerini özelleştirin.

## Adım 5: LaTeX'i XPS'ye Dönüştürmeyi çalıştırın

```java
new TeXJob("Your Input Directory" + "sample.ltx", new XpsDevice(), options).run();
```

Belirtilen giriş dosyası, çıkış cihazı (XpsDevice) ve seçeneklerle bir TeX işi çalıştırarak dönüştürme işlemini başlatın.

## Ek Örnekler

Farklı giriş kaynaklarını kullanan ek dönüştürme yöntemlerini keşfedin:

### Giriş Akışını Kullan

```java
new TeXJob(new ByteArrayInputStream(
    "\\documentclass{article} \\begin{document} Hello, World! \\end{document}".getBytes("ASCII")),
    new XpsDevice(), options).run();
```

### Ana Giriş Terminalini Kullan

```java
new TeXJob(new XpsDevice(), options).run();
```

## Çözüm

Aspose.TeX for Java ile LaTeX'i XPS'e dönüştürmek çocuk oyuncağı. Bu adımları izleyin, seçenekleri özelleştirin ve bu işlevselliği Java uygulamalarınıza sorunsuz bir şekilde entegre edin.

## SSS'ler

### S1: Karmaşık formüllere sahip LaTeX belgelerini Aspose.TeX kullanarak dönüştürebilir miyim?

A1: Kesinlikle! Aspose.TeX, dönüştürme işlemi sırasında karmaşık formülleri sorunsuz bir şekilde işler.

### S2: Aspose.TeX for Java'nın deneme sürümü mevcut mu?

 Cevap2: Evet, ücretsiz deneme sürümünü bulabilirsiniz[Burada](https://releases.aspose.com/).

### S3: Aspose.TeX için nasıl destek alabilirim?

 A3: Ziyaret edin[Aspose.TeX forumu](https://forum.aspose.com/c/tex/47) yardım ve topluluk desteği için.

### S4: Aspose.TeX için geçici lisanslar mevcut mu?

 Cevap4: Evet, geçici lisanslar alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).

### S5: Aspose.TeX belgelerini nerede bulabilirim?

 A5: Bkz.[dokümantasyon](https://reference.aspose.com/tex/java/) kapsamlı rehberlik için.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
