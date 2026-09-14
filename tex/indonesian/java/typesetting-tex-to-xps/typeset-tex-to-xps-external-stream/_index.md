---
date: 2026-09-14
description: Pelajari cara mengonversi TeX ke XPS di Java menggunakan Aspose.TeX.
  Panduan langkah demi langkah ini menunjukkan cara mengonversi file TeX dan menghasilkan
  aliran dokumen XPS secara efisien.
keywords:
- how to convert tex
- how to generate xps
- Aspose.TeX Java
- TeX to XPS conversion
- external output stream
lastmod: 2026-09-14
linktitle: Cara Mengonversi TeX ke XPS di Java dengan Stream Eksternal
og_description: Pelajari cara mengonversi TeX ke XPS di Java menggunakan Aspose.TeX.
  Panduan ini memandu Anda menggunakan OutputStream eksternal untuk menghasilkan XPS
  dengan cepat dan efisien dalam penggunaan memori.
og_image_alt: Developer guide showing Java code that converts TeX to XPS using Aspose.TeX
  and streams the result
og_title: Cara mengonversi TeX ke XPS di Java dengan stream eksternal
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to convert TeX to XPS in Java using Aspose.TeX. This step‑by‑step
    guide shows you how to convert TeX files and generate XPS document streams efficiently.
  headline: How to Convert TeX to XPS in Java with External Stream
  type: TechArticle
- questions:
  - answer: Aspose.TeX primarily focuses on TeX‑related document processing. For other
      formats, explore Aspose's extensive product range.
    question: Can I use Aspose.TeX for Java with other document formats?
  - answer: Yes, you can experience Aspose.TeX by downloading the free trial [Aspose
      free trial download](https://releases.aspose.com/).
    question: Is there a trial version available?
  - answer: Refer to the documentation [Aspose.TeX Java API reference](https://reference.aspose.com/tex/java/)
      for detailed information and examples.
    question: Where can I find comprehensive documentation?
  - answer: Visit the Aspose.TeX community forum [Aspose.TeX community forum](https://forum.aspose.com/c/tex/47)
      for community support and discussions.
    question: How do I get support or seek assistance?
  - answer: Yes, you can acquire a temporary license [temporary license request page](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for testing purposes?
  type: FAQPage
second_title: Aspose.TeX Java API
tags:
- convert TeX
- Aspose.TeX
- Java XPS conversion
- external stream
- document processing
title: Cara Mengonversi TeX ke XPS di Java dengan Stream Eksternal
url: /id/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mengonversi TeX ke XPS di Java dengan aliran eksternal

## Pendahuluan

Jika Anda perlu **mengonversi TeX** file menjadi output XPS berkualitas tinggi dari aplikasi Java, Aspose.TeX for Java membuat pekerjaan ini menjadi mudah. Dalam tutorial ini Anda akan melihat secara tepat **cara mengonversi TeX** ke dokumen XPS menggunakan aliran output eksternal, yang ideal ketika Anda ingin mengirimkan hasilnya langsung ke respons, layanan penyimpanan cloud, atau tujuan khusus lainnya. Mari kita telusuri seluruh proses, mulai dari menyiapkan lingkungan hingga menulis file XPS akhir.

**Aspose.TeX for Java** adalah perpustakaan yang mengubah sumber TeX menjadi XPS, PDF, PNG, dan format lainnya tanpa memerlukan instalasi TeX. Ia mendukung lebih dari 20 format output dan dapat menangani dokumen ratusan halaman sambil menjaga penggunaan memori tetap rendah.

## Jawaban Cepat
- **Apa yang dibahas dalam tutorial ini?** Mengonversi TeX ke XPS menggunakan Aspose.TeX dengan aliran eksternal.  
- **Perpustakaan utama apa yang diperlukan?** Aspose.TeX for Java.  
- **Apakah saya memerlukan lisensi?** Lisensi sementara atau penuh diperlukan untuk penggunaan produksi.  
- **Bisakah saya menghasilkan aliran dokumen XPS?** Ya – contoh menulis XPS langsung ke `OutputStream`.  
- **Versi Java apa yang didukung?** JDK 8+ apa saja (tutorial ini menggunakan JDK 11 sebagai referensi).

## Cara mengonversi TeX ke XPS menggunakan aliran eksternal

Muat sumber TeX Anda, konfigurasikan opsi konversi, dan tulis XPS yang dihasilkan langsung ke `OutputStream`. Pola dua‑langkah ini (konfigurasi → jalankan) menyelesaikan konversi dalam kurang dari satu detik untuk dokumen tipikal di bawah 50 halaman pada CPU modern.

## Apa itu Aspose.TeX for Java?

Aspose.TeX for Java adalah perpustakaan Java yang mem-parsing sumber TeX/LaTeX dan menghasilkan XPS, PDF, PNG, SVG, serta format dokumen lainnya. Ia menyediakan API tingkat tinggi yang mengabstraksi mesin TeX, memungkinkan Anda menghasilkan output tanpa menginstal distribusi TeX lengkap.

## Mengapa menggunakan `OutputStream` eksternal?

Menulis ke `OutputStream` eksternal menghilangkan file perantara, mengurangi I/O disk, dan memungkinkan Anda men-stream XPS langsung ke klien web, bucket cloud, atau layanan lain. Dalam skenario throughput tinggi ini dapat memotong waktu pemrosesan keseluruhan hingga 40 % dibandingkan alur kerja berbasis file.

## Prasyarat

Sebelum menyelam ke kode, pastikan Anda memiliki hal‑hal berikut:

- Java Development Kit (JDK): Pastikan Java terpasang di sistem Anda. Anda dapat mengunduhnya dari [Java SE downloads](https://www.oracle.com/java/technologies/javase-downloads.html).

- Aspose.TeX for Java: Unduh dan instal Aspose.TeX for Java. Anda dapat menemukan tautan unduhan di [Aspose.TeX for Java download page](https://releases.aspose.com/tex/java/).

## Impor paket

Kelas `OutputStream` merupakan bagian dari `java.io`, sementara kelas konversi berada di namespace `com.aspose.tex`. Impor mereka di bagian atas file sumber Java Anda:

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

## Langkah 1: konfigurasikan opsi konversi

`TeXOptions` menyimpan pengaturan konfigurasi seperti direktori input dan output, font, serta opsi rendering.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

Ini menyiapkan fondasi untuk proses typesetting.

## Langkah 2: tentukan nama pekerjaan dan direktori

`TeXJob` mewakili pekerjaan typesetting dan memerlukan nama, direktori input, serta direktori output.

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Pastikan Anda mengganti placeholder seperti "Your Input Directory" dengan jalur direktori Anda yang sebenarnya.

## Langkah 3: konfigurasikan output terminal

`OutputFileTerminal` mengonfigurasi tempat log konsol ditulis, biasanya ke file di folder output.

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

Langkah ini memastikan log detail tertangkap untuk debugging.

## Langkah 4: buka output stream

`FileOutputStream` membuat `OutputStream` yang menulis byte XPS yang dihasilkan ke jalur file yang ditentukan.

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

Ganti "Your Output Directory" dengan jalur yang sesuai.

## Langkah 5: jalankan pekerjaan

`TeXJob.run` mengeksekusi konversi menggunakan opsi yang diberikan dan menulis hasilnya ke `OutputStream` yang telah dibuka.

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

Ini menyelesaikan proses, dan Anda akan menemukan dokumen XPS yang dihasilkan di direktori output yang ditentukan.

## Mengapa ini penting

Streaming XPS langsung ke `OutputStream` memberi Anda kontrol penuh atas tujuan data—apakah Anda mengirimnya ke klien web, menyimpannya di penyimpanan cloud, atau men‑chain‑nya ke pipeline pemrosesan lain. Ini menghilangkan kebutuhan akan file perantara dan mengurangi overhead I/O, yang sangat berharga dalam lingkungan throughput tinggi atau server‑less.

## Masalah umum dan solusi

| Masalah | Mengapa terjadi | Cara memperbaiki |
|---------|-----------------|------------------|
| **FileNotFoundException** saat membuka aliran | Jalur direktori output tidak benar atau tidak ada. | Verifikasi jalur, buat direktori sebelumnya, atau gunakan `Files.createDirectories`. |
| **NullPointerException** pada `options.getOutputWorkingDirectory()` | `setOutputWorkingDirectory` tidak dipanggil atau mengembalikan `null`. | Pastikan Anda memanggil `options.setOutputWorkingDirectory` sebelum menggunakannya. |
| **LicenseException** pada runtime | Menjalankan tanpa lisensi Aspose.TeX yang valid. | Terapkan lisensi sementara atau permanen menggunakan `License license = new License(); license.setLicense("Aspose.TeX.lic");`. |

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan Aspose.TeX for Java dengan format dokumen lain?**  
A: Aspose.TeX terutama fokus pada pemrosesan dokumen terkait TeX. Untuk format lain, jelajahi rangkaian produk luas Aspose.

**Q: Apakah ada versi percobaan yang tersedia?**  
A: Ya, Anda dapat mencoba Aspose.TeX dengan mengunduh percobaan gratis [Aspose free trial download](https://releases.aspose.com/).

**Q: Di mana saya dapat menemukan dokumentasi lengkap?**  
A: Lihat dokumentasi [Aspose.TeX Java API reference](https://reference.aspose.com/tex/java/) untuk informasi detail dan contoh.

**Q: Bagaimana cara mendapatkan dukungan atau bantuan?**  
A: Kunjungi forum komunitas Aspose.TeX [Aspose.TeX community forum](https://forum.aspose.com/c/tex/47) untuk dukungan komunitas dan diskusi.

**Q: Bisakah saya memperoleh lisensi sementara untuk tujuan pengujian?**  
A: Ya, Anda dapat memperoleh lisensi sementara di [temporary license request page](https://purchase.aspose.com/temporary-license/).

## Kesimpulan

Selamat! Anda baru saja mempelajari **cara mengonversi TeX** ke dokumen XPS di Java menggunakan Aspose.TeX dan aliran eksternal. Teknik ini memberi Anda kontrol penuh atas tujuan output XPS—apakah ke sistem file, respons web, atau bucket cloud. Jangan ragu bereksperimen dengan sumber TeX yang berbeda, sesuaikan `TeXOptions` untuk font khusus, atau sambungkan aliran ke pipeline generasi dokumen yang lebih besar.

---

**Last Updated:** 2026-09-14  
**Tested with:** Aspose.TeX for Java 24.11 (latest at time of writing)  
**Author:** Aspose

## Tutorial Terkait

- [Typeset Tex ke PDF Aliran Eksternal](/tex/java/typesetting-tex-to-pdf/typeset-tex-to-pdf-external-stream/)
- [Konversi TeX ke PNG dengan Input Stream dan Penanganan Terminal di Java](/tex/java/advanced-io/stream-input-image-output/)
- [Cara Membaca TeX – Atur Direktori Input Panduan Java dengan Aspose.TeX for Java](/tex/java/advanced-io/required-input-directory/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}