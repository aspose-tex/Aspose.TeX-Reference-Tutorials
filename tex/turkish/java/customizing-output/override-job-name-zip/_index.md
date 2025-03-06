---
title: Java'da İş Adını Geçersiz Kıl ve Terminal Çıkışını Zip'e Yaz
linktitle: Java'da İş Adını Geçersiz Kıl ve Terminal Çıkışını Zip'e Yaz
second_title: Aspose.TeX Java API'si
description: Aspose.TeX ile Java'da iş adlarını nasıl geçersiz kılacağınızı ve terminal çıktısını ZIP'e yazmayı öğrenin. Java geliştiricileri için kapsamlı bir eğitim.
weight: 11
url: /tr/java/customizing-output/override-job-name-zip/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java'da İş Adını Geçersiz Kıl ve Terminal Çıkışını Zip'e Yaz

## giriiş

Java geliştirme dünyasında Aspose.TeX, TeX dosya formatlarını yönetmek için güçlü bir araç olarak öne çıkıyor. Bu eğitimde, iş adlarının geçersiz kılınması ve terminal çıktısının bir zip dosyasına yazılması gibi belirli bir senaryoyu inceleyeceğiz. Bu adım adım kılavuz, Aspose.TeX for Java'yı kullanma sürecinde size yol gösterecektir.

## Önkoşullar

Bu eğitime başlamadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
- Java programlamanın temel bilgisi.
-  Java için Aspose.TeX'i yükledim. Değilse, adresinden indirebilirsiniz.[Web sitesi](https://releases.aspose.com/tex/java/).
- Java geliştirme ortamının nasıl kurulacağının anlaşılması.

## Paketleri İçe Aktar

Gerekli paketleri Java projenize aktararak başlayın. Bu, görev için gereken Aspose.TeX işlevlerine erişmenizi sağlar.

```java
package com.aspose.tex.OverridenJobNameAndTerminalOutputWrittenToZip;

import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.io.OutputStream;

import com.aspose.tex.InputZipDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.OutputZipDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.PdfDevice;
import com.aspose.tex.rendering.PdfSaveOptions;

import util.Utils;
```

## 1. Adım: ZIP Arşivlerini açın

Öncelikle ZIP arşivinde giriş çalışma dizini görevi görecek bir akış açın. Bu, verilerinizin işleneceği arşivdir.

```java
// Giriş ZIP arşivinde bir akış açın
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
```

## Adım 2: Çıktı ZIP Arşivini Açın

Daha sonra, ZIP arşivinde çıktı çalışma dizini olarak görev yapacak bir akış açın. Terminal çıkışının yazılacağı yer burasıdır.

```java
// Çıktı ZIP arşivinde bir akış açın
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "terminal-out-to-zip.zip");
```

## 3. Adım: Dönüştürme Seçeneklerini Ayarlayın

ObjectTeX motor uzantısında varsayılan ObjectTeX formatı için dönüştürme seçenekleri oluşturun. Hem giriş hem de çıkış için bir iş adı ve ZIP arşivi çalışma dizinleri belirtin.

```java
// ObjectTeX formatı için TeX seçenekleri oluşturun
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("terminal-output-to-zip");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
```

## Adım 4: Terminal Çıkışını Belirleyin

 Terminal çıktısının, çıktı çalışma dizinindeki bir dosyaya yazılması gerektiğini belirtin. Dosya adı şöyle olacak`<job_name>.trm`.

```java
// Terminal çıkış ayarlarını belirtin
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

## Adım 5: Kaydetme Seçeneklerini Tanımlayın ve İşi Çalıştırın

Bu durumda PDF kaydetme seçenekleri gibi kaydetme seçeneklerini tanımlayın. Dönüştürmeyi yürütmek için TeX işini çalıştırın.

```java
// Kaydetme seçeneklerini tanımlayın ve işi çalıştırın
options.setSaveOptions(new PdfSaveOptions());
new TeXJob("hello-world", new PdfDevice(), options).run();
```

## Adım 6: Çıktı ZIP Arşivini Sonlandırın

İş tamamlandıktan sonra, düzgün bir şekilde tamamlandığından emin olmak için çıktı ZIP arşivini sonlandırın.

```java
// Çıktı ZIP arşivini sonlandırın
((OutputZipDirectory) options.getOutputWorkingDirectory()).finish();
```

## Çözüm

Tebrikler! Aspose.TeX'i kullanarak Java'da iş adlarını nasıl geçersiz kılacağınızı ve terminal çıktısını bir ZIP dosyasına nasıl yazacağınızı başarıyla öğrendiniz. Bu güçlü işlevsellik, Java geliştirme projelerinize esneklik ve verimlilik katar.

## SSS'ler

### S1: Aspose.TeX nedir?

Cevap1: Aspose.TeX, geliştiricilerin TeX dosya formatlarıyla çalışmasına olanak tanıyan ve belge işleme için gelişmiş işlevler sağlayan bir Java kütüphanesidir.

### S2: Aspose.TeX için nasıl geçici lisans alabilirim?

 Cevap2: Geçici lisansı şu adresten alabilirsiniz:[bu bağlantı](https://purchase.aspose.com/temporary-license/).

### S3: Aspose.TeX belgelerini nerede bulabilirim?

 A3: Belgeler mevcut[Burada](https://reference.aspose.com/tex/java/).

### S4: Aspose.TeX'in ücretsiz deneme sürümü var mı?

 Cevap4: Evet, ücretsiz deneme sürümünü bulabilirsiniz[Burada](https://releases.aspose.com/).

### S5: Aspose.TeX ile ilgili nereden destek alabilirim veya soru sorabilirim?

 A5: ziyaret edin[Aspose.TeX forumu](https://forum.aspose.com/c/tex/47) Destek ve tartışmalar için.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
