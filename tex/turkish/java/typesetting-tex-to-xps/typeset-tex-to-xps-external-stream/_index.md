---
title: Harici Akış ile Java'da TeX'i XPS'ye ayarlayın
linktitle: Harici Akış ile Java'da TeX'i XPS'ye ayarlayın
second_title: Aspose.TeX Java API'si
description: Aspose.TeX'i kullanarak Java'da TeX'i XPS'ye nasıl dizeceğinizi öğrenin. Sorunsuz belge işleme için adım adım kılavuzu keşfedin.
weight: 10
url: /tr/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Harici Akış ile Java'da TeX'i XPS'ye ayarlayın

## giriiş

Java geliştirme dünyasında Aspose.TeX, TeX belgelerini XPS dahil çeşitli formatlara dizmek için güçlü bir araç olarak öne çıkıyor. Java uygulamanızın belge işleme yeteneklerini geliştirmek istiyorsanız bu eğitim tam size göre. Bu adım adım kılavuzda, Aspose.TeX for Java'yı harici bir akışla kullanarak TeX'i XPS'ye dizme sürecinde size yol göstereceğiz.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:

-  Java Geliştirme Kiti (JDK): Sisteminizde Java'nın kurulu olduğundan emin olun. Şuradan indirebilirsiniz[Burada](https://www.oracle.com/java/technologies/javase-downloads.html).

-  Aspose.TeX for Java: Aspose.TeX for Java'yı indirip yükleyin. İndirme linkini bulabilirsiniz[Burada](https://releases.aspose.com/tex/java/).

## Paketleri İçe Aktar

TeX'ten XPS'ye dönüşüm yolculuğunuzu başlatmak için gerekli paketleri içe aktararak başlayın. Java projenize aşağıdaki kod parçacığını ekleyin:

```java
package com.aspose.tex.TypesetXpsWrittenToExternalStream;

import java.io.FileOutputStream;
import java.io.IOException;
import java.io.OutputStream;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

## 1. Adım: Dönüşüm Seçeneklerini Yapılandırın

Aşağıdaki kodu kullanarak varsayılan ObjectTeX formatı için dönüştürme seçenekleri oluşturarak başlayın:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

Bu, dizgi sürecinin temelini oluşturur.

## Adım 2: İş Adını ve Dizinleri Belirleyin

Bir iş adı tanımlayın ve giriş ve çıkış çalışma dizinlerini ayarlayın:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

"Giriş Dizininiz" gibi yer tutucuları gerçek dizin yollarınızla değiştirdiğinizden emin olun.

## Adım 3: Terminal Çıkışını Yapılandırma

Terminal çıktısının, çıktı çalışma dizinindeki bir dosyaya yazılması gerektiğini belirtin:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

Bu adım, hata ayıklama için ayrıntılı günlüklerin yakalanmasını sağlar.

## 4. Adım: Çıkış Akışını Açın

Dizgi XPS belgesini yazmak için bir akış açın:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

"Çıktı Dizininiz"i uygun yolla değiştirin.

## Adım 5: İşi Çalıştırın

TeX'ten XPS'ye dönüştürme işini yürütün:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

Bu işlemi tamamlar ve dizgi XPS belgenizi belirtilen çıktı dizininde bulacaksınız.

## Çözüm

Tebrikler! Aspose.TeX'i kullanarak Java'da TeX'i XPS'ye başarıyla dizdiniz. Bu, Java uygulamalarınızda belge işleme için bir olasılıklar dünyasının kapılarını açar. Farklı TeX dosyalarıyla denemeler yapın ve Aspose.TeX'in sunduğu çeşitli özellikleri keşfedin.

## SSS'ler

### S1: Aspose.TeX for Java'yı diğer belge formatlarıyla kullanabilir miyim?

Cevap1: Aspose.TeX öncelikli olarak TeX ile ilgili belge işlemeye odaklanır. Diğer formatlar için Aspose'un geniş ürün yelpazesini inceleyin.

### S2: Deneme sürümü mevcut mu?

 Cevap2: Evet, ücretsiz deneme sürümünü indirerek Aspose.TeX deneyimini yaşayabilirsiniz[Burada](https://releases.aspose.com/).

### S3: Kapsamlı belgeleri nerede bulabilirim?

 A3: Belgelere bakın[Burada](https://reference.aspose.com/tex/java/) detaylı bilgi ve örnekler için.

### S4: Nasıl destek alabilirim veya yardım alabilirim?

 Cevap4: Aspose.TeX forumunu ziyaret edin[Burada](https://forum.aspose.com/c/tex/47)topluluk desteği ve tartışmalar için.

### S5: Test amaçlı geçici lisans alabilir miyim?

 Cevap5: Evet, geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
