---
date: 2025-12-11
description: Java'da Aspose.TeX kullanarak TeX'i XPS'ye nasıl dönüştüreceğinizi öğrenin.
  Bu adım adım rehber, XPS belge akışlarını verimli bir şekilde nasıl oluşturacağınızı
  gösterir.
linktitle: How to Convert TeX to XPS in Java with External Stream
second_title: Aspose.TeX Java API
title: Java'da Dış Akış Kullanarak TeX'i XPS'e Nasıl Dönüştürürsünüz
url: /tr/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java'da Dış Akış Kullanarak TeX'i XPS'e Dönüştürme

## Giriş

Java uygulamasından yüksek kaliteli XPS çıktısı elde etmek için **TeX** dosyalarını **dönüştürmeniz** gerekiyorsa, Aspose.TeX for Java işi oldukça basitleştirir. Bu öğreticide, dış bir çıktı akışı kullanarak **TeX'i XPS** belgesine nasıl dönüştüreceğinizi tam olarak göreceksiniz; bu, sonucu doğrudan bir yanıt, bulut depolama hizmeti veya herhangi bir özel hedefe yönlendirmek istediğinizde idealdir. Ortamı kurmaktan son XPS dosyasını yazmaya kadar tüm süreci adım adım inceleyelim.

## Hızlı Yanıtlar
- **Bu öğreticinin kapsamı nedir?** Aspose.TeX ile dış akış kullanarak TeX'i XPS'e dönüştürme.  
- **Hangi ana kütüphane gereklidir?** Aspose.TeX for Java.  
- **Lisans gerekli mi?** Üretim kullanımı için geçici veya tam bir lisans gereklidir.  
- **XPS belge akışları oluşturabilir miyim?** Evet – örnek XPS'i doğrudan bir `OutputStream`'e yazar.  
- **Hangi Java sürümü destekleniyor?** JDK 8+ (öğreticide referans olarak JDK 11 kullanılmıştır).

## Önkoşullar

Koda başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Java Development Kit (JDK): Sisteminizde Java yüklü olduğundan emin olun. [buradan](https://www.oracle.com/java/technologies/javase-downloads.html) indirebilirsiniz.

- Aspose.TeX for Java: Aspose.TeX for Java'ı indirin ve kurun İndirme bağlantısını [burada](https://releases.aspose.com/tex/java/) bulabilirsiniz.

## Paketleri İçe Aktarma

TeX‑to‑XPS dönüşüm yolculuğunuza başlamak için gerekli paketleri içe aktararak başlayın. Aşağıdaki kod parçacığını Java projenize ekleyin:

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

## Adım 1: Dönüşüm Seçeneklerini Yapılandırma

Aşağıdaki kodu kullanarak varsayılan ObjectTeX formatı için dönüşüm seçeneklerini oluşturarak başlayın:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

Bu, dizgi sürecinin temelini oluşturur.

## Adım 2: İş Adını ve Dizinleri Belirleme

Bir iş adı tanımlayın ve giriş ile çıkış çalışma dizinlerini ayarlayın:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

“Your Input Directory” gibi yer tutucuları gerçek dizin yollarınızla değiştirdiğinizden emin olun.

## Adım 3: Terminal Çıktısını Yapılandırma

Terminal çıktısının çıkış çalışma dizinindeki bir dosyaya yazılmasını belirtin:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

Bu adım, hata ayıklama için ayrıntılı günlüklerin kaydedilmesini sağlar.

## Adım 4: Çıktı Akışını Açma

Dizgi XPS belgesini yazmak için bir akış açın:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

“Your Output Directory” ifadesini uygun yol ile değiştirin.

## Adım 5: İşi Çalıştırma

TeX'ten XPS'e dönüşüm işini yürütün:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

Bu işlem tamamlandığında, oluşturulan XPS belgesini belirtilen çıkış dizininde bulacaksınız.

## Yaygın Sorunlar ve Çözümleri

| Sorun | Neden Oluşur | Nasıl Çözülür |
|-------|----------------|------------|
| **FileNotFoundException** akışı açarken | Çıkış dizini yolu hatalı veya mevcut değil. | Yolu doğrulayın, dizini önceden oluşturun veya `Files.createDirectories` kullanın. |
| **NullPointerException** `options.getOutputWorkingDirectory()` üzerinde | `setOutputWorkingDirectory` çağrılmadı veya `null` döndürdü. | Kullanımdan önce `options.setOutputWorkingDirectory` çağırdığınızdan emin olun. |
| **LicenseException** çalışma zamanında | Geçerli bir Aspose.TeX lisansı olmadan çalıştırılıyor. | `License license = new License(); license.setLicense("Aspose.TeX.lic");` kodunu kullanarak geçici veya kalıcı bir lisans uygulayın. |

## Sıkça Sorulan Sorular

**S: Aspose.TeX for Java'ı diğer belge formatlarıyla kullanabilir miyim?**  
C: Aspose.TeX öncelikle TeX‑ile ilgili belge işleme üzerine odaklanır. Diğer formatlar için Aspose'un geniş ürün yelpazesini inceleyin.

**S: Deneme sürümü mevcut mu?**  
C: Evet, ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) indirerek Aspose.TeX'i deneyimleyebilirsiniz.

**S: Kapsamlı belgeleri nerede bulabilirim?**  
C: Ayrıntılı bilgi ve örnekler için belgeleri [buradan](https://reference.aspose.com/tex/java/) inceleyin.

**S: Destek nasıl alınır veya yardım istenir?**  
C: Topluluk desteği ve tartışmalar için Aspose.TeX forumunu [buradan](https://forum.aspose.com/c/tex/47) ziyaret edin.

**S: Test amaçlı geçici bir lisans alabilir miyim?**  
C: Evet, geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.

## Sonuç

Tebrikler! Aspose.TeX ve dış bir akış kullanarak Java'da **TeX'i XPS** belgesine nasıl dönüştüreceğinizi yeni öğrendiniz. Bu teknik, XPS çıktısının nereye gideceği üzerinde tam kontrol sağlar—dosya sistemi, web yanıtı veya bulut deposu olsun. Farklı TeX kaynaklarıyla denemeler yapmaktan, `TeXOptions`'ı özel yazı tipleri için ayarlamaktan veya akışı daha büyük bir belge‑oluşturma hattına entegre etmekten çekinmeyin.

---

**Son Güncelleme:** 2025-12-11  
**Test Edilen Sürüm:** Aspose.TeX for Java 24.11 (yazım zamanındaki en son sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}