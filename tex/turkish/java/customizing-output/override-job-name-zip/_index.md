---
date: 2026-02-15
description: Aspose.TeX for Java kullanarak TeX'i PDF'ye dönüştürmeyi, iş adlarını
  geçersiz kılmayı ve terminal çıktısını bir ZIP dosyasına yazmayı öğrenin. Java geliştiricileri
  için adım adım rehber.
linktitle: Convert TeX to PDF, Override Job Name and Write Terminal Output to ZIP
  in Java
second_title: Aspose.TeX Java API
title: TeX'i PDF'ye dönüştür, iş adını geçersiz kıl ve terminal çıktısını Java'da
  ZIP'e yaz
url: /tr/java/customizing-output/override-job-name-zip/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# TeX'i PDF'ye Dönüştürme, İş Adını Geçersiz Kılma ve Terminal Çıktısını ZIP'e Yazma Java'da

## Giriş

TeX'i **PDF'ye dönüştürmeniz** ve iş adını ve terminal günlüklerini tam kontrol altında tutmanız gerekiyorsa, Aspose.TeX for Java bunu basit hale getirir. Bu öğreticide gerçek bir senaryoyu adım adım inceleyeceğiz: iş adını geçersiz kılma, terminal çıktısını bir ZIP arşivine yönlendirme ve sonunda bir PDF belgesi üretme. Sonunda, herhangi bir Java projesine ekleyebileceğiniz yeniden kullanılabilir bir kod parçacığına sahip olacaksınız.

## Hızlı Yanıtlar
- **Bu öğreticinin amacı nedir?** TeX'i PDF'ye dönüştürmeyi, özel bir iş adı ayarlamayı ve terminal çıktısını bir ZIP dosyasında yakalamayı gösterir.  
- **Hangi kütüphane gereklidir?** Aspose.TeX for Java (en son sürüm).  
- **Lisans gerekli mi?** Değerlendirme için geçici bir lisans yeterlidir; üretim için tam lisans gerekir.  
- **Hangi çıktı dosyaları oluşturulur?** PDF belgesi ve çıktı ZIP içinde bir `<job_name>.trm` terminal günlüğü.  
- **Uygulama ne kadar sürer?** Kodu kopyalayıp çalıştırmak yaklaşık 10‑15 dakikadır.

## “TeX'i PDF'ye dönüştürmek” nedir?
TeX'i PDF'ye dönüştürmek, bir TeX kaynak dosyasını (veya bir dizi TeX dosyasını) alıp PDF belgesi olarak oluşturmak anlamına gelir. Aspose.TeX, harici bir LaTeX dağıtımına ihtiyaç duymadan tam TeX derleme hattını yöneten yüksek performanslı bir motor sağlar.

## İş adını neden geçersiz kılmalı ve terminal çıktısını ZIP'e yazmalıyız?
- **Açıklık:** Özel bir iş adı günlük dosyalarında görünür, otomatikleştirilmiş boru hatlarında çalışmaları tanımlamayı kolaylaştırır.  
- **Taşınabilirlik:** Terminal çıktısını (`*.trm`) bir ZIP içinde saklamak, tüm artefaktları bir arada tutar; bu, CI/CD veya bulut tabanlı işleme için kullanışlıdır.  
- **Hata Ayıklama:** Terminal günlüğü, TeX hatalarını gidermenize yardımcı olan ayrıntılı derleme mesajları içerir.

## Bunun önemi nedir
Üretim ortamında TeX'ten PDF oluştururken, derleme artefaktlarını düzenli tutmanız gerekir. İş adını geçersiz kılmak, her çalışmayı anlamlı bir tanımlayıcıyla (örneğin bir derleme numarası) etiketlemenizi sağlar. Terminal günlüğünü PDF ile aynı ZIP içinde paketlemek, bağlamı kaybetmeden arşivlenebilen veya alt hizmetlere gönderilebilen tek bir taşınabilir paket oluşturur.

## Yaygın kullanım senaryoları
- **Otomatik rapor oluşturma** – gecelik bir iş, TeX şablonlarından PDF'ler oluşturur ve denetim amaçlı günlükleri saklar.  
- **CI/CD boru hatları** – geliştiriciler, bir derleme başarısız olduğunda ayrı günlük dosyalarına bakmadan tam derleme mesajlarını görebilir.  
- **Bulut tabanlı belge hizmetleri** – bir web servisi TeX kaynaklarının ZIP'ini alır, işler ve PDF ile derleme günlüğünü içeren bir ZIP döndürür.

## Ön Koşullar

Başlamadan önce şunların olduğundan emin olun:

- Çalışan bir Java geliştirme ortamı (JDK 8 veya daha yenisi).  
- Aspose.TeX for Java, [Aspose web sitesinden](https://releases.aspose.com/tex/java/) indirilmiş.  
- Java I/O akışları hakkında temel bilgi.

## Paketleri İçe Aktarma

Gerekli sınıfları içe aktararak başlayın. Bu, Aspose.TeX API'sine ve standart Java I/O yardımcı programlarına erişmenizi sağlar.

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

## Adım 1: Giriş ZIP Arşivini Açma

İlk olarak, TeX kaynak dosyalarını içeren ZIP dosyasına işaret eden bir akış açarız. Bu arşiv, dönüşüm işi için **giriş çalışma dizini** olarak görev yapar.

```java
// Open a stream on the input ZIP archive
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
```

## Adım 2: Çıkış ZIP Arşivini Açma

Sonra, oluşturulan PDF ve terminal günlüğünü alacak ZIP dosyası için bir akış oluşturun. Bu, **çıkış çalışma dizini** dir.

```java
// Open a stream on the output ZIP archive
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "terminal-out-to-zip.zip");
```

## Adım 3: Dönüşüm Seçeneklerini Ayarlama (iş adı dahil)

Burada ObjectTeX formatı için dönüşüm seçeneklerini yapılandırır, özel bir iş adı belirler ve giriş ile çıkış ZIP dizinlerini bağlarız.

```java
// Create TeX options for ObjectTeX format
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("terminal-output-to-zip");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
```

## Adım 4: Terminal Çıktısını ZIP İçindeki Bir Dosyaya Yönlendirme

Aspose.TeX'e, derleme terminal çıktısını çıkış ZIP içinde `<job_name>.trm` adlı bir dosyaya yazmasını söyleriz.

```java
// Specify terminal output settings
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

## Adım 5: Kaydetme Seçeneklerini Tanımlama ve İşi Çalıştırma

İstenen renderleme cihazını (PDF) ayarlayın ve işi yürütün. Bu adım **TeX'i PDF'ye dönüştürür** ve sonucu çıkış ZIP içinde saklar.

```java
// Define saving options and run the job
options.setSaveOptions(new PdfSaveOptions());
new TeXJob("hello-world", new PdfDevice(), options).run();
```

## Adım 6: Çıkış ZIP Arşivini Tamamlama

İş tamamlandıktan sonra, arşivin geçerli olmasını sağlamak için ZIP akışını düzgün bir şekilde kapatmalıyız.

```java
// Finalize the output ZIP archive
((OutputZipDirectory) options.getOutputWorkingDirectory()).finish();
```

## İpuçları ve En İyi Uygulamalar

- **Akışları yeniden kullanın**: Ardışık birçok TeX işi işliyorsanız, giriş ve çıkış akışlarını açık tutun ve yalnızca çalıştırmalar arasında `JobName`'i değiştirin.  
- **Günlük inceleme**: `<job_name>.trm` dosyasını herhangi bir metin düzenleyiciyle açarak TeX derleyicisinin ürettiği uyarı ve hataları görebilirsiniz.  
- **Performans**: Büyük belgeler için, PDF renderleme sırasında `OutOfMemoryError` oluşmasını önlemek amacıyla JVM yığın boyutunu (`-Xmx2g`) artırmayı düşünün.  
- **Güvenlik**: Güvenilmeyen TeX kaynaklarıyla çalışırken, olası kötü amaçlı makroları azaltmak için dönüşümü izole bir ortamda (sandbox) çalıştırın.

## Yaygın Sorunlar ve Çözümler

| Sorun | Muhtemel Neden | Çözüm |
|-------|----------------|------|
| **Boş PDF** | Giriş ZIP içinde geçerli bir `*.tex` dosyası yok veya dosya `in` klasörüne yerleştirilmemiş. | ZIP yapısını doğrulayın (`in/yourfile.tex`). |
| **`.trm` dosyası eksik** | `setTerminalOut` çağrılmamış veya çıktı dizini bir `OutputZipDirectory` değil. | `run()`'dan önce `options.setTerminalOut(...)` çağrıldığından emin olun. |
| **`IOException` on finish** | Çıktı akışı başka bir yerde zaten kapatılmış. | İş tamamlandıktan sonra `finish()`'ı yalnızca bir kez çağırın. |
| **TeX hatalarıyla dönüşüm başarısız** | TeX kaynağı sözdizimi hataları içeriyor. | Oluşturulan `<job_name>.trm` günlüğünü açarak ayrıntılı hata mesajlarını inceleyin. |

## Sıkça Sorulan Sorular

**S: Aspose.TeX nedir?**  
C: Aspose.TeX, geliştiricilerin TeX kaynaklarından **PDF oluşturmasını**, TeX belgelerini manipüle etmesini ve harici LaTeX kurulumları olmadan gelişmiş renderleme yapmasını sağlayan bir Java kütüphanesidir.

**S: Aspose.TeX için geçici bir lisans nasıl alabilirim?**  
C: Geçici bir lisansı [bu bağlantıdan](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.

**S: Resmi Aspose.TeX belgelerini nerede bulabilirim?**  
C: Belgeler [burada](https://reference.aspose.com/tex/java/) mevcuttur.

**S: Aspose.TeX'in ücretsiz deneme sürümü var mı?**  
C: Evet, ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) indirebilirsiniz.

**S: Sorun yaşarsam nereden yardım alabilirim?**  
C: Topluluk desteği ve resmi yardım için [Aspose.TeX forumunu](https://forum.aspose.com/c/tex/47) ziyaret edin.

## Sonuç

Artık Aspose.TeX for Java kullanarak **TeX'i PDF'ye dönüştürmeyi**, iş adını geçersiz kılmayı ve terminal çıktısını bir ZIP arşivinde yakalamayı gördünüz. Bu yaklaşım, günlükleri oluşturulan artefaktlarla birlikte tutmanın hata ayıklamayı ve denetim izlerini basitleştirdiği otomatik derleme boru hatalarında özellikle faydalıdır. Kodu kendi proje yapınıza uyarlamaktan veya Aspose.TeX'in desteklediği diğer çıktı formatlarına genişletmekten çekinmeyin.

---

**Son Güncelleme:** 2026-02-15  
**Test Edilen Versiyon:** Aspose.TeX for Java 24.11 (yazım zamanındaki en son)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}