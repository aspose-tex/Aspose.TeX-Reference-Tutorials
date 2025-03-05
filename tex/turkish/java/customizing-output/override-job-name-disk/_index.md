---
title: Java'da İş Adını Geçersiz Kıl ve Terminal Çıkışını Yaz
linktitle: Java'da İş Adını Geçersiz Kıl ve Terminal Çıkışını Yaz
second_title: Aspose.TeX Java API'si
description: Aspose.TeX for Java'yı kullanarak iş adlarını geçersiz kılma ve terminal çıktısını yazmaya ilişkin adım adım kılavuzu keşfedin. Güçlü özelleştirme seçenekleriyle belge işleme sürecinizi geliştirin.
type: docs
weight: 10
url: /tr/java/customizing-output/override-job-name-disk/
---
## giriiş

Aspose.TeX for Java, TeX dosyalarıyla çalışmak için güçlü özellikler sunarak geliştiricilerin TeX belge işlemeyi değiştirmesine ve özelleştirmesine olanak tanır. Bu eğitimde, Java'da Aspose.TeX kullanarak iş adını geçersiz kılma ve terminal çıktısını dosya sistemine yazma sürecinde size rehberlik edeceğiz.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Java programlama konusunda çalışma bilgisi.
-  Aspose.TeX for Java kuruldu. adresinden indirebilirsiniz.[Aspose.TeX Java belgeleri](https://reference.aspose.com/tex/java/).

## Paketleri İçe Aktar

Başlamak için gerekli paketleri Java projenize aktarın. Java dosyanıza aşağıdaki içe aktarmaları ekleyin:

```java
package com.aspose.tex.OverridenJobNameAndTerminalOutputWrittenToDisk;

import java.io.IOException;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

## İş Adını Geçersiz Kıl ve Terminal Çıkışını Yaz

### 1. Adım: Dönüşüm Seçenekleri Oluşturun

ObjectTeX motor uzantısında varsayılan ObjectTeX formatı için dönüştürme seçenekleri oluşturarak başlayın. Aşağıdaki kod parçacığını kullanın:

```java
//ExStart:OverrideJobName-WriteTerminalOutputToFileSystem
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

### Adım 2: İş Adını ve Çalışma Dizinlerini Belirleyin

Bir iş adı, giriş çalışma dizini ve çıkış çalışma dizinini belirtin. İşin adı belirtilmezse TeXJob yapıcısının ilk argümanı iş adı olarak alınacaktır. Aşağıdaki kod parçacığını kullanın:

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### Adım 3: Terminal Çıkışını Dosya Sistemine Yazma

 Terminal çıktısının, çıktı çalışma dizinindeki bir dosyaya yazılması gerektiğini belirtin. Dosya adı şöyle olacak`<job_name>.trm`. Aşağıdaki kodu ekleyin:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### Adım 4: İşi Çalıştırın

Belirtilen seçenekleri ve iş adını kullanarak TeX işini çalıştırın. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
// ExEnd:OverrideJobName-WriteTerminalOutputToFileSystem
```

Tebrikler! Java'da Aspose.TeX'i kullanarak iş adını ve yazılı terminal çıktısını dosya sistemine başarıyla geçersiz kıldınız.

## Çözüm

Bu eğitimde, iş adını geçersiz kılmak ve terminal çıktısını yakalamak için Aspose.TeX for Java'yı nasıl kullanabileceğimizi araştırdık. Bu özellikler, geliştiricilerin TeX belge işleme üzerinde ayrıntılı kontrole sahip olmalarını sağlayarak özelleştirmeyi ve esnekliği artırır.

## SSS'ler

### S1: Aspose.TeX for Java'yı diğer Java kütüphaneleriyle birlikte kullanabilir miyim?

Cevap1: Evet, Aspose.TeX for Java, belge işleme yeteneklerinizi geliştirmek için diğer Java kitaplıklarıyla sorunsuz bir şekilde entegre olacak şekilde tasarlanmıştır.

### S2: Aspose.TeX for Java desteğini nerede bulabilirim?

 A2: Ziyaret edin[Aspose.TeX forumu](https://forum.aspose.com/c/tex/47) Karşılaşabileceğiniz her türlü sorunla ilgili topluluk desteği ve yardım için.

### S3: Aspose.TeX for Java'nın ücretsiz deneme sürümü mevcut mu?

 Cevap3: Evet, Aspose.TeX for Java'nın ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.aspose.com/).

### S4: Aspose.TeX for Java için nasıl geçici lisans alabilirim?

 A4: Bunu takip edin[bağlantı](https://purchase.aspose.com/temporary-license/) Test ve değerlendirme amacıyla geçici bir lisans almak.

### S5: Aspose.TeX for Java'yı nereden satın alabilirim?

 A5: ziyaret edin[satın alma sayfası](https://purchase.aspose.com/buy) Aspose.TeX for Java lisansını almak için.