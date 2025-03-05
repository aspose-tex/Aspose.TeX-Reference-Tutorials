---
title: Java'da Akış Girişi, Görüntü Çıkışı ve Terminal Girişi
linktitle: Java'da Akış Girişi, Görüntü Çıkışı ve Terminal Girişi
second_title: Aspose.TeX Java API'si
description: Aspose.TeX'i kullanarak Java'da akış girişini, görüntü çıkışını ve terminal girişini öğrenin. Sorunsuz entegrasyon için kapsamlı bir eğitim.
type: docs
weight: 11
url: /tr/java/advanced-io/stream-input-image-output/
---
## giriiş

Aspose.TeX for Java, geliştiricilerin TeX dosyalarıyla çalışmasına olanak tanıyan, yüksek kaliteli belgelerin oluşturulmasını ve işlenmesini kolaylaştıran güçlü bir kütüphanedir. Bu eğitimde Aspose.TeX kullanarak Java'da akış girişi alma, görüntü çıkışı oluşturma ve terminal girişini işleme sürecini inceleyeceğiz.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

- Java programlamanın temel anlayışı.
- Makinenizde Java Geliştirme Kiti (JDK) yüklü.
- Aspose.TeX kütüphanesine aşinalık.
-  Aspose.TeX for Java kuruldu. İndirebilirsin[Burada](https://releases.aspose.com/tex/java/).

## Paketleri İçe Aktar

Bu eğitim için gerekli paketlerin içe aktarıldığından emin olun. Aşağıdaki kod parçacığı gerekli içe aktarma işlemlerini gösterir:

```java
package com.aspose.tex.StreamInputImageOutputAndTerminalInput;

import java.io.ByteArrayInputStream;
import java.io.IOException;

import com.aspose.tex.InputConsoleTerminal;
import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputConsoleTerminal;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.ImageDevice;
import com.aspose.tex.rendering.PngSaveOptions;
```

## 1. Adım: Dönüştürme Seçeneklerini Ayarlayın

ObjectTeX motor uzantısında varsayılan ObjectTeX formatıyla TeX dönüştürme seçenekleri oluşturun. Bir iş adı, giriş çalışma dizini ve çıkış çalışma dizinini belirtin.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("stream-in-image-out");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

## Adım 2: Giriş ve Çıkış Terminallerini Belirleyin

Konsolu hem giriş hem de çıkış terminalleri olarak belirtin.

```java
options.setTerminalIn(new InputConsoleTerminal());
options.setTerminalOut(new OutputConsoleTerminal());
```

## 3. Adım: Kaydetme Seçeneklerini Tanımlayın

Çıktı görüntüsü için kaydetme seçeneklerini tanımlayın. Bu örnekte 300 DPI çözünürlüğe sahip PNG formatını kullanıyoruz.

```java
PngSaveOptions pngOptions = new PngSaveOptions();
pngOptions.setResolution(300);
options.setSaveOptions(pngOptions);
```

## 4. Adım: Görüntü Cihazı Oluşturun

Çıkış görüntüsünü oluşturmak için bir görüntü cihazı oluşturun.

```java
ImageDevice device = new ImageDevice();
```

## Adım 5: İşi Çalıştırın

TeX işini belirtilen giriş, cihaz ve seçeneklerle çalıştırın.

```java
TeXJob job = new TeXJob(new ByteArrayInputStream(
        "\\hrule height 10pt width 95pt\\vskip10pt\\hrule height 5pt".getBytes("ASCII")),
        device, options);
job.run();
```

## Adım 6: Terminal Girişini İşleyin

Konsol giriş istediğinde "ABC" yazın, Enter'a basın, ardından "\end" yazıp tekrar Enter'a basın.

```java
// Daha fazla çıktının iyi görünmesi için.
options.getTerminalOut().getWriter().newLine();
```

## Adım 7: Görüntü Çıktısını Alın

Bayt dizileri dizisi biçiminde görüntüler elde edebilirsiniz.

```java
byte[][] result = device.getResult();
```

Bu, Aspose.TeX kullanarak Java'da akış girişi, görüntü çıkışı ve terminal girişi için adım adım kılavuzu tamamlıyor.

## Çözüm

Aspose.TeX for Java, akış girişi, görüntü çıkışı ve terminal etkileşimi için güçlü özellikler sunarak TeX belgelerinin işlenmesi sürecini basitleştirir. Bu öğreticiyi takip ederek, bu işlevleri Java uygulamalarınıza sorunsuz bir şekilde nasıl entegre edeceğinizi öğrendiniz.

## SSS'ler

### S1: Aspose.TeX diğer Java kütüphaneleriyle uyumlu mu?

Cevap1: Evet, Aspose.TeX işlevselliği geliştirmek için diğer Java kitaplıklarıyla sorunsuz bir şekilde entegre edilebilir.

### S2: Çıktı görüntü formatını özelleştirebilir miyim?

A2: Kesinlikle! Aspose.TeX, çıktı görüntülerini kaydetmek için çeşitli seçenekler sunarak tercihlerinize göre özelleştirmeye olanak tanır.

### S3: Aspose.TeX desteği için bir topluluk forumu var mı?

 C3: Evet, destek bulabilir ve toplulukla etkileşimde bulunabilirsiniz.[Aspose.TeX forumu](https://forum.aspose.com/c/tex/47).

### S4: Aspose.TeX için nasıl geçici lisans alabilirim?

 Cevap4: Geçici lisansı şu adresten alabilirsiniz:[Burada](https://purchase.aspose.com/temporary-license/).

### S5: Aspose.TeX dokümantasyonu için ek kaynaklar var mı?

 A5: Kapsamlı olanı keşfedin[dokümantasyon](https://reference.aspose.com/tex/java/) ayrıntılı bilgiler ve örnekler için.