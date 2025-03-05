---
title: Harici Akış ile Java'da TeX'i PDF'ye ayarlayın
linktitle: Harici Akış ile Java'da TeX'i PDF'ye ayarlayın
second_title: Aspose.TeX Java API'si
description: Aspose.TeX ile harici akışları kullanarak Java'da TeX'i PDF'ye nasıl dizeceğinizi öğrenin. Sorunsuz entegrasyon için adım adım kılavuzumuzu izleyin.
type: docs
weight: 10
url: /tr/java/typesetting-tex-to-pdf/typeset-tex-to-pdf-external-stream/
---
## giriiş

Java geliştirme dünyasında TeX dosyalarından PDF oluşturmak yaygın bir gereksinimdir. Aspose.TeX for Java, TeX'i PDF'ye dizmek için etkili bir çözüm sağlayarak bu süreci basitleştirir. Bu eğitimde, harici akışları kullanarak TeX'i PDF'ye dizme adımlarında size yol göstereceğiz. Sonunda, bu süreci Java uygulamalarınızda sorunsuz bir şekilde nasıl uygulayacağınıza dair net bir anlayışa sahip olacaksınız.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:

- Aspose.TeX for Java: Aspose.TeX for Java kütüphanesinin kurulu olduğundan emin olun. adresinden indirebilirsiniz.[Java belgeleri için Aspose.TeX](https://reference.aspose.com/tex/java/).

- Giriş ve Çıkış Dizinleri: Giriş ve çıkış dizinlerini hazırlayın. Gerekli dosyaları almak için sağlanan indirme bağlantısını kullanabilirsiniz.

## Paketleri İçe Aktar

Gerekli paketleri Java projenize aktararak başlayın:

```java
package com.aspose.tex.TypesetPdfWrittenToExternalStream;

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

## 1. Adım: Giriş ve Çıkış Akışlarını Açın

Giriş ZIP arşivi (girdi çalışma dizini görevi görür) ve çıktı ZIP arşivi (çıktı çalışma dizini görevi görür) için akışları açarak başlayın. "Giriş Dizininiz" ve "Çıktı Dizininiz"i gerçek dizin yollarınızla değiştirdiğinizden emin olun.

```java
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "typeset-pdf-to-external-stream.zip");
```

## Adım 2: TeXOptions'ı yapılandırın

TeXOptions nesnesini oluşturun ve gereksinimlerinize göre yapılandırın. İş adını, giriş çalışma dizinini, çıkış çalışma dizinini ve diğer seçenekleri ayarlayın.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("typeset-pdf-to-external-stream");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
options.setSaveOptions(new PdfSaveOptions());
```

## 3. Adım: TeX'i PDF'ye ayarlayın

Şimdi çıktı PDF'sini istediğiniz konuma yazmak için bir akış açın. Bunu yerel bir dosyaya veya doğrudan çıktı ZIP arşivine yazmayı seçebilirsiniz.

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + "file-name.pdf");
try {
    new TeXJob("hello-world", new PdfDevice(stream), options).run();
} finally {
    stream.close();
}
```

## Adım 4: Çıktı ZIP Arşivini Sonlandırın

Dizgi işlemini tamamlamak için çıktı ZIP arşivini bitirin.

```java
((OutputZipDirectory)options.getOutputWorkingDirectory()).finish();
```

## Çözüm

Tebrikler! Aspose.TeX ile harici akışları kullanarak Java'da TeX'i PDF'ye başarıyla dizdiniz. Bu eğitim, TeX'ten PDF'ye dönüştürmeyi Java uygulamalarınıza sorunsuz bir şekilde dahil etmek için sağlam bir temel sağlar.

## SSS'ler

### S1: Çıktı PDF'sinin dosya adını özelleştirebilir miyim?

 A1: Evet, değiştirebilirsiniz`options.setJobName("typeset-pdf-to-external-stream")` İstediğiniz işin adını ayarlamak için

### S2: Dizgi sırasında sık karşılaşılan sorunları nasıl gideririm?

 A2: Ziyaret edin[Aspose.TeX forumu](https://forum.aspose.com/c/tex/47) Toplumsal destek ve yardım için.

### S3: Aspose.TeX for Java'nın ücretsiz deneme sürümü mevcut mu?

 C3: Evet, ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.aspose.com/).

### S4: Ek belgeleri ve örnekleri nerede bulabilirim?

 A4: Kapsamlı olanı keşfedin[Aspose.TeX belgeleri](https://reference.aspose.com/tex/java/) detaylı bilgi için.

### S5: Aspose.TeX için geçici bir lisans alabilir miyim?

 Cevap5: Evet, geçici lisans talep edebilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).