---
date: 2026-02-07
description: Pelajari cara membuat faktur yang dapat dicetak dengan Java dengan mengonversi
  file LaTeX ke XPS menggunakan Aspose.TeX untuk Java. Sederhana, cepat, dan sepenuhnya
  berbasis Java.
linktitle: Step by Step Conversion - LaTeX to XPS Format in Java
second_title: Aspose.TeX Java API
title: java membuat faktur yang dapat dicetak – Mengonversi LaTeX ke XPS di Java
url: /id/java/converting-lato-xps/simple-xps-conversion/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# java membuat faktur yang dapat dicetak – Konversi Langkah demi Langkah: Format LaTeX ke XPS di Java

## Perkenalan

Jika Anda perlu **java membuat faktur yang dapat dicetak** dari sumber LaTeX di dalam aplikasi Java, Anda berada di tutorial yang tepat. Dengan **Aspose.TeX for Java** Anda dapat merender file LaTeX, menangani formula kompleks, dan menghasilkan file XPS berkualitas tinggi yang mencetak tetap seperti yang Anda harapkan. Dalam beberapa menit ke depan kami akan menelusuri seluruh alur kerja, menjelaskan mengapa metode ini ideal untuk pembuatan faktur, dan menunjukkan cara menyesuaikan konversi untuk pelaporan pipa Anda sendiri.

## Jawaban Cepat
- **Library apa yang harus saya gunakan?** Aspose.TeX untuk Java
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk pengaturan dasar
- **Apa saja prasyaratnya?** JDK 8+, Aspose.TeX JAR, dan IDE (Eclipse/IntelliJ)
- **Apakah saya dapat merender formula kompleks?** Ya – Aspose.TeX sepenuhnya mendukung lingkungan matematika LaTeX
- **Apakah lisensi diperlukan untuk produksi?** Ya, lisensi komersial diperlukan untuk penggunaan non‑trial

## Bagaimana cara java membuat faktur yang dapat dicetak dengan konversi LaTeX ke XPS?

Berikut adalah penjelasan percakapan langkah demi langkah yang perlu Anda lakukan. Silakan berhenti sejenak, bereksperimen dengan kode, dan menyesuaikan pengaturan agar cocok dengan tata letak faktur Anda.

## Apa itu konversi langkah demi langkah?

*Konversi langkah demi langkah* adalah proses terarah dan bertahap yang memecah tugas besar—seperti mengubah file sumber LaTeX menjadi dokumen XPS—menjadi tindakan‑tindakan kecil yang dapat dikelola. Dengan mengikuti setiap langkah, Anda menghindari jebakan umum, menjaga kode tetap bersih, dan dapat dengan mudah menyesuaikan pengaturan individu (seperti penanganan font atau rasterisasi gambar) tanpa menulis ulang seluruh pipeline.

## Mengapa menggunakan Aspose.TeX untuk rendering lateks Java?

- **Dukungan LaTeX penuh** – Dari artikel sederhana hingga buku dengan paket khusus.
- **Tanpa biner eksternal** – Semua berjalan di Java murni, yang mengarahkan penerapan.
- **Kontrol detail** – Opsi memungkinkan Anda menentukan bagaimana rumus, grafik, dan font ditangani.
- **Output lintas‑platform** – File XPS dirender secara konsisten pada penampil Windows, macOS, dan Linux.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

- Java Development Kit (JDK) 8 atau yang lebih baru terpasang.
- Library Aspose.TeX untuk Java (unduh dari halaman resmi [halaman unduh Aspose.TeX Java](https://releases.aspose.com/tex/java/)).
- IDE Java atau alat build (Maven/Gradle) untuk menambahkan JAR ke classpath proyek Anda.

## Impor Paket

Langkah pertama adalah mengimpor kelas‑kelas yang diperlukan. Pertahankan blok impor tetap seperti yang ditampilkan—ini memastikan kode dapat dikompilasi tanpa modifikasi.

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

Sekarang mari kita telusuri langkah‑langkah konversi, menjelaskan tujuan setiap fragmen kode.

## Langkah 1: Atur Direktori Input dan Output

Anda perlu memberi tahu Aspose.TeX di mana menemukan file sumber `.ltx` dan ke mana menulis file XPS yang dihasilkan.

```java
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

*Tip:* Ganti `"Your Input Directory"` dan `"Your Output Directory"` dengan jalur absolut atau relatif yang ada di mesin Anda.

## Langkah 2: Konfigurasi Opsi TeX

Opsi‑opsi ini mengontrol perilaku mesin LaTeX selama konversi. Sesuaikan agar cocok dengan kebutuhan dokumen Anda.

```java
options.setInteraction(Interaction.NonstopMode);
options.setDateTime(new GregorianCalendar(2022, Calendar.DECEMBER, 18).getTime());
options.ignoreMissingPackages(true);
options.noLigatures(true);
options.repeat(true);
```

- **Interaction mode** – `NonstopMode` melanjutkan pemrosesan meskipun menemukan error.  
- **DateTime** – Menetapkan tanggal yang muncul pada halaman judul dokumen.  
- **ignoreMissingPackages** – Mencegah pekerjaan gagal ketika sebuah paket tidak ditemukan.  
- **noLigatures** – Menonaktifkan ligatur tipografis jika Anda lebih suka karakter polos.  
- **repeat** – Memungkinkan mesin menjalankan kembali untuk referensi silang.

## Langkah 3: Inisialisasi Opsi Penyimpanan XPS

Buat instance `XpsSaveOptions` yang akan menyimpan pengaturan khusus XPS.

```java
options.setSaveOptions(new XpsSaveOptions());
```

## Langkah 4: Kustomisasi Opsi Penyimpanan XPS

Sesuaikan cara output XPS menangani formula, grafik, dan font.

```java
options.getSaveOptions().rasterizeFormulas(true);
options.getSaveOptions().rasterizeIncludedGraphics(true);
options.getSaveOptions().subsetFonts(true);
```

- **rasterizeFormulas** – Mengonversi ekspresi matematika menjadi gambar, memastikan mereka tampil dengan benar pada semua penampil XPS.  
- **rasterizeIncludedGraphics** – Memaksa grafik yang disematkan untuk dirasterisasi, yang dapat meningkatkan kompatibilitas.  
- **subsetFonts** – Menyertakan hanya glyph yang digunakan dalam dokumen, mengurangi ukuran file.

## Langkah 5: Jalankan Konversi LaTeX ke XPS

Akhirnya, jalankan pekerjaan konversi. `TeXJob` menggabungkan file input, perangkat output (`XpsDevice`), dan semua opsi yang telah Anda konfigurasikan.

```java
new TeXJob("Your Input Directory" + "sample.ltx", new XpsDevice(), options).run();
```

Setelah pemanggilan `run()` selesai, Anda akan menemukan `sample.xps` di direktori output yang Anda tentukan sebelumnya. File XPS ini dapat dikirim langsung ke printer atau disematkan dalam bundel faktur PDF.

## Contoh Tambahan

### Gunakan InputStream (Konversi string LaTeX secara langsung)

Jika Anda lebih suka memberi sumber LaTeX dari memori alih‑alih file, bungkus sumber tersebut dalam `ByteArrayInputStream`.

```java
new TeXJob(new ByteArrayInputStream(
    "\\documentclass{article} \\begin{document} Hello, World! \\end{document}".getBytes("ASCII")),
    new XpsDevice(), options).run();
```

### Gunakan Terminal Input Utama (Biarkan Aspose.TeX menemukan file secara otomatis)

Ketika Anda tidak perlu menentukan jalur file secara eksplisit, Anda dapat mengandalkan terminal input default.

```java
new TeXJob(new XpsDevice(), options).run();
```

## Kasus & Tip Penggunaan Umum

| Skenario | Mengapa Pendekatan Ini Membantu |
|----------|--------------------------|
| **Membuat faktur yang dapat dicetak** | XPS mempertahankan kesetiaan tata letak di seluruh printer Windows, menjadikannya sempurna untuk keluaran faktur berkualitas tinggi. |
| **Konversi makalah akademis secara batch** | Langkah‑demi‑langkah API memungkinkan Anda memproses banyak file `.ltx` dengan kode minimal. |
| **Menyematkan persamaan LaTeX dalam alat pelaporan** | Formula rasterisasi memastikan hasilnya benar-benar bahkan pada perangkat berdaya rendah. |

**Tips pro:** Bungkus logika konversi dalam metode utilitas sehingga Anda dapat menggunakannya kembali di berbagai modul aplikasi Anda.

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya mengonversi dokumen LaTeX dengan rumus kompleks menggunakan Aspose.TeX?**
J: Tentu saja. Mesin ini sepenuhnya mendukung paket matematika AMS dan akan merasterisasi rumus ketika `rasterizeFormulas(true)` diatur.

**T: Apakah ada versi uji coba yang tersedia untuk Aspose.TeX untuk Java?**
J: Ya, Anda dapat mengunduh versi uji coba gratis dari [halaman unduhan Aspose.TeX Java](https://releases.aspose.com/tex/java/).

**T: Bagaimana saya bisa mendapatkan dukungan untuk Aspose.TeX?**
J: Kunjungi [forum Aspose.TeX](https://forum.aspose.com/c/tex/47) untuk bantuan komunitas, atau buka tiket dukungan melalui akun Aspose Anda.

**T: Apakah lisensi sementara tersedia untuk Aspose.TeX?**
J: Ya, lisensi sementara dapat diperoleh melalui [halaman lisensi sementara Aspose](https://purchase.aspose.com/temporary-license/).

**T: Di mana saya dapat menemukan dokumentasi untuk Aspose.TeX?**
J: Dokumentasi API yang komprehensif tersedia di [Referensi Java Aspose.TeX](https://reference.aspose.com/tex/java/).

---

**Terakhir Diperbarui:** 2026-02-07
**Diuji Dengan:** Aspose.TeX 24.11 untuk Java
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}