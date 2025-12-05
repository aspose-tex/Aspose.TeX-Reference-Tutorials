---
date: 2025-12-05
description: Aspose.TeX for Java kullanarak terminal çıktısını dosyaya yazmayı ve
  bir iş adını geçersiz kılmayı öğrenin. Tam kod örnekleriyle adım adım bu kılavuzu
  izleyin.
language: tr
linktitle: Write Terminal Output to File and Override Job Name in Java
second_title: Aspose.TeX Java API
title: Terminal Çıktısını Dosyaya Yaz ve Java'da İş Adını Geçersiz Kıl
url: /java/customizing-output/override-job-name-disk/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Uçbirim Çıktısını Dosyaya Yazma ve Java'da İş Adını Geçersiz Kılma

## Giriş

Aspose.TeX for Java, TeX dosyalarıyla çalışmak için güçlü özellikler sunar ve geliştiricilerin TeX belge işleme hattını manipüle edip özelleştirmesine olanak tanır. Bu öğreticide **uçbirim çıktısını dosyaya nasıl yazacağınızı** ve varsayılan iş adını nasıl geçersiz kılacağınızı öğreneceksiniz—bu iki yetenek, toplu işleme ve günlük tutma üzerinde ince ayar kontrolü sağlar.

## Hızlı Yanıtlar
- **İş adını değiştirebilir miyim?** Evet, işi çalıştırmadan önce `options.setJobName(...)` kullanın.  
- **Uçbirim çıktısı nereye gidiyor?** Çıktı çalışma dizininde `<job_name>.trm` olarak kaydedilir.  
- **Bu özellik için lisansa ihtiyacım var mı?** İşlevsellik geçerli bir Aspose.TeX lisansı ile çalışır; ücretsiz deneme sürümü de mevcuttur.  
- **Çıktı dosyasının formatı nedir?** Konsol çıktısını yansıtan düz metin terminal günlüğüdür.  
- **Diğer çıktı aygıtlarıyla uyumlu mu?** Kesinlikle—günlük yazıldıktan sonra metin dosyalarını okuyabilen herhangi bir araçla işleyebilirsiniz.

## Ön Koşullar

Kodun içine dalmadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Java programlama temellerine sağlam bir anlayış.  
- Aspose.TeX for Java yüklü (resmi [Aspose.TeX Java belgeleri](https://reference.aspose.com/tex/java/) üzerinden indirin).  
- Örneği derleyip çalıştırmak için bir Java IDE veya yapı aracı (Maven/Gradle) hazır.

## Paketleri İçe Aktarma

Başlamak için gerekli paketleri Java projenize dahil edin. Java dosyanıza aşağıdaki importları ekleyin:

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

> **İpucu:** `util.Utils` importunu yalnızca Aspose örnek yardımcı metodlarına ihtiyacınız varsa tutun; aksi takdirde kodu temiz tutmak için kaldırabilirsiniz.

## Java'da Uçbirim Çıktısını Dosyaya Yazma

Aşağıda, dönüşüm seçeneklerini yapılandırma, iş adını geçersiz kılma ve uçbirim çıktısını diske yönlendirme adımlarını gösteren adım‑adım bir rehber bulacaksınız.

### Adım 1: Dönüştürme Seçeneklerini Oluşturma

Öncelikle, varsayılan ObjectTeX yapılandırmasını kullanan bir `TeXOptions` örneği oluşturun. Bu nesne, dönüşüm sürecinin tüm ayarlarını tutacaktır.

```java
// ExStart:OverrideJobName-WriteTerminalOutputToFileSystem
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
// ExEnd:OverrideJobName-WriteTerminalOutputToFileSystem
```

### Adım 2: İş Adını ve Çalışma Dizinlerini Belirleme

Sonra, özel bir iş adı ayarlayın ve giriş‑çıkış dosyalarının nerede bulunacağını tanımlayın. İş adı ayarlamazsanız, `TeXJob` yapıcısının ilk argümanı otomatik olarak iş adı olur.

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

> **İş adını neden geçersiz kılmalıyım?**  
> İş adını geçersiz kılmak, günlük dosyalarını ve oluşturulan artefaktları tanımlamayı kolaylaştırır; özellikle birden fazla işi paralel çalıştırdığınızda veya toplu işleme otomasyonu yaptığınızda faydalıdır.

### Adım 3: Uçbirim Çıktısını Dosya Sistemine Yazma

Aspose.TeX'in normalde konsola yazacak tüm çıktıyı yakalayıp bir dosyaya yazmasını sağlayın. Dosya, `<job_name>.trm` adıyla ve yukarıda tanımladığınız çıktı çalışma dizinine yerleştirilecektir.

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### Adım 4: İşi Çalıştırma

Son olarak, istediğiniz giriş dosyası (burada basit bir “hello‑world” örneği) ve XPS render aygıtı ile bir `TeXJob` oluşturun. Ardından `run()` metodunu çağırarak dönüşümü yürütün.

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
```

İş tamamlandığında, **Çıktı Dizininiz** içinde `overridden-job-name.trm` adlı bir dosya bulacaksınız; bu dosya tam uçbirim günlüğünü içerir.

## Yaygın Tuzaklar ve Sorun Giderme

| Sorun | Neden | Çözüm |
|-------|-------|------|
| **`.trm` dosyası oluşturulmadı** | `setTerminalOut` çağrılmadı veya çıktı dizini eksik | Çıktı dizininin var olduğunu ve `options.setTerminalOut(...)` kodunun `job.run()` öncesinde çalıştırıldığını doğrulayın. |
| **Dosya adı geçersiz kılınan adı göstermiyor** | İş adı doğru ayarlanmamış | `options.setJobName("istediğiniz‑ad")` kodunun **`TeXJob` oluşturulmadan önce** çağrıldığından emin olun. |
| **Günlük dosyası boş** | Günlük başlamadan önce istisna atılıyor | `job.run()` kodunu bir try‑catch bloğuna alın ve eksik fontlar veya hatalı TeX kaynağı gibi istisnaları inceleyin. |

## Sık Sorulan Sorular

**S: Aspose.TeX for Java’yı diğer Java kütüphaneleriyle birlikte kullanabilir miyim?**  
C: Evet, Aspose.TeX diğer Java kütüphaneleriyle sorunsuz entegrasyon için tasarlanmıştır; aynı iş akışında PDF, görüntü veya veritabanı yardımcılarını birleştirebilirsiniz.

**S: Aspose.TeX for Java için destek nereden alınır?**  
C: Topluluk yardımı için [Aspose.TeX forumunu](https://forum.aspose.com/c/tex/47) ziyaret edin veya Aspose destek portalı üzerinden bir destek bileti açın.

**S: Aspose.TeX for Java için ücretsiz deneme mevcut mu?**  
C: Kesinlikle. [Aspose.TeX ücretsiz deneme sayfasından](https://releases.aspose.com/) tam işlevsel bir deneme sürümü indirebilirsiniz.

**S: Test amaçlı geçici bir lisans nasıl alınır?**  
C: 30‑günlük değerlendirme lisansı almak için [Aspose geçici lisans](https://purchase.aspose.com/temporary-license/) formunu kullanın.

**S: Kalıcı bir lisans nereden satın alınır?**  
C: Lisansı doğrudan [Aspose.TeX satın alma sayfasından](https://purchase.aspose.com/buy) temin edebilirsiniz.

## Sonuç

Bu rehberde, Aspose.TeX for Java kullanarak **uçbirim çıktısını dosyaya yazma** ve varsayılan iş adını geçersiz kılma yöntemlerini gösterdik. Bu yetenekler, hata ayıklama için ayrıntılı günlükler tutmanıza, toplu işleme otomasyonu yapmanıza ve üretim‑düzeyi belge dönüşüm hatları için temiz, düzenli bir çıktı yapısı oluşturmanıza olanak tanır.

---

**Son Güncelleme:** 2025-12-05  
**Test Edilen Sürüm:** Aspose.TeX 24.11 for Java  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}