---
date: 2026-09-04
description: Pelajari cara menghasilkan PDF dari TeX di Java menggunakan Aspose.TeX,
  mengatur working directories, dan membuat custom TeX format files untuk consistent
  typesetting.
keywords:
- generate pdf from tex
- set working directories
- create custom tex format
- set tex input directory
- set tex output directory
lastmod: 2026-09-04
linktitle: Buat custom TeX formats untuk consistent typesetting di Java
og_description: Hasilkan PDF dari TeX di Java dengan Aspose.TeX. Pelajari cara mengatur
  working directories, membuat custom TeX formats, dan memastikan consistent typesetting.
og_image_alt: Screenshot of Java code generating PDF from TeX using Aspose.TeX
og_title: Hasilkan PDF dari TeX dan buat custom formats di Java
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to generate PDF from TeX in Java using Aspose.TeX, set working
    directories, and create custom TeX format files for consistent typesetting.
  headline: How to generate PDF from TeX and create formats in Java
  type: TechArticle
- description: Learn how to generate PDF from TeX in Java using Aspose.TeX, set working
    directories, and create custom TeX format files for consistent typesetting.
  name: How to generate PDF from TeX and create formats in Java
  steps:
  - name: Initialize TeX options (create a “no‑format” engine)
    text: The `TeXOptions` class lets you configure the TeX engine before any format
      is loaded.
  - name: Set the TeX input directory
    text: '`setInputWorkingDirectory` points the engine at the folder that contains
      your source `.tex` files, style packages, and any custom fonts. Using an absolute
      path during development avoids confusion with the IDE’s default working directory.
      > **Pro tip:** Keep your input folder read‑only in production '
  - name: Set the TeX output directory
    text: '`setOutputWorkingDirectory` defines where the engine writes compiled PDFs,
      log files, and auxiliary data. Separating output from source makes cleanup easier
      and enables you to archive results automatically.'
  - name: Run the format creation command
    text: Calling `createFormat("customtex", options)` tells Aspose.TeX to compile
      all packages referenced in the input directory into a binary format file named
      `customtex.fmt`. This step typically finishes within seconds, even for large
      collections of packages, because the engine only parses each macro once
  - name: Clean up the terminal output (optional)
    text: A simple `System.out.println()` adds a newline after the process finishes,
      keeping the console output tidy when you chain multiple conversions in a batch
      job.
  type: HowTo
- questions:
  - answer: You can refer to the [Aspose.TeX for Java documentation](https://reference.aspose.com/tex/java/)
      for comprehensive API details and usage examples.
    question: Where can I find the documentation for Aspose.TeX for Java?
  - answer: You can download the library from the [Aspose.TeX download page](https://releases.aspose.com/tex/java/).
    question: How can I download Aspose.TeX for Java?
  - answer: You can buy Aspose.TeX for Java from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.TeX for Java?
  - answer: Yes, you can access the free trial version on the [Aspose.TeX free trial
      download page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.TeX for Java?
  - answer: You can seek support on the [Aspose.TeX forum](https://forum.aspose.com/c/tex/47).
    question: How can I get support for Aspose.TeX for Java?
  type: FAQPage
second_title: Aspose.TeX Java API
tags:
- generate pdf
- Aspose.TeX
- Java typesetting
- custom tex format
title: Cara menghasilkan PDF dari TeX dan membuat format di Java
url: /id/java/custom-format/creating-custom-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghasilkan PDF dari TeX dan membuat format di Java

Menghasilkan PDF dari TeX adalah kebutuhan umum ketika Anda membutuhkan dokumen ilmiah atau matematika berkualitas tinggi dalam alur kerja berbasis Java. Dalam tutorial ini Anda akan menemukan cara **membuat format TeX khusus** dengan Aspose.TeX, **mengatur direktori input dan output TeX**, dan akhirnya **menghasilkan PDF dari TeX** secara berulang dan efisien. Pada akhir tutorial Anda akan memiliki file `.fmt` yang dapat digunakan kembali yang menjamin gaya yang identik untuk setiap dokumen yang diproses.

## Jawaban Cepat
- **Apa arti “create custom TeX format”?** Itu mengompilasi sekumpulan makro, font, dan aturan tata letak menjadi sebuah file biner yang dimuat engine secara instan.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis sudah cukup untuk pengembangan; lisensi komersial diperlukan untuk penyebaran produksi.  
- **Versi JDK mana yang diperlukan?** Java 8 atau lebih tinggi (Java 17 LTS disarankan).  
- **Bisakah saya mengubah folder input saat runtime?** Ya—panggil `setInputWorkingDirectory` pada objek options.  
- **Apakah folder output dapat dikonfigurasi?** Tentu—gunakan `setOutputWorkingDirectory` untuk mengontrol tempat PDF dan log ditulis.

## Cara membuat format untuk TeX di Java?

`TeXOptions` adalah objek konfigurasi yang mengontrol pengaturan engine Aspose.TeX. Pertama, buat instance objek `TeXOptions`, arahkan ke folder sumber Anda, tentukan tempat menulis hasil, dan akhirnya panggil `createFormat("customtex", options)`. Metode `createFormat` mengompilasi file sumber menjadi file biner `.fmt` yang dapat digunakan kembali, yang dapat Anda muat untuk menghasilkan PDF selanjutnya. Pendekatan ini mengurangi waktu kompilasi hingga 70 % dan menjamin tata letak yang konsisten di semua dokumen.

## Mengapa mengatur direktori input dan output TeX?

Menetapkan direktori input memberi tahu engine di mana menemukan sumber `.tex`, file font, dan paket tambahan, sementara direktori output menentukan tempat penyimpanan PDF yang dikompilasi, file log, dan artefak sementara. Konfigurasi direktori yang tepat menghilangkan kesalahan “file not found”, menjaga struktur proyek tetap bersih, dan memungkinkan Anda menjalankan beberapa konversi secara paralel tanpa bentrok.

## Prasyarat
Sebelum kita menyelam ke dalam kode, pastikan Anda memiliki:

- **Aspose.TeX for Java** – unduh dari [Aspose.TeX download page](https://releases.aspose.com/tex/java/).
- **Direktori kerja** – tentukan folder *input* (tempat file `.tex` Anda berada) dan folder *output* (tempat PDF yang dihasilkan akan disimpan). Ganti `"Your Input Directory"` dan `"Your Output Directory"` dalam potongan kode dengan jalur aktual Anda.
- **Java Development Kit (JDK)** – versi 8 atau lebih baru terpasang dan dikonfigurasi di IDE atau sistem build Anda.

## Impor paket
Kelas `TeXOptions` mengkonfigurasi engine Aspose.TeX, dan utilitas `FileHelper` menyediakan bantuan sistem file sederhana yang digunakan dalam proyek contoh.

```java
package com.aspose.tex.CustomTeXFormatFileCreation;

import java.io.IOException;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;

import util.Utils;
```

## Panduan langkah‑demi‑langkah untuk membuat format TeX khusus

### Langkah 1: Inisialisasi opsi TeX (buat engine “tanpa format”)

Kelas `TeXOptions` memungkinkan Anda mengkonfigurasi engine TeX sebelum format apa pun dimuat.

```java
// Create TeX engine options for no format upon ObjectTeX engine extension.
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectIniTeX());
```

### Langkah 2: Atur direktori input TeX

`setInputWorkingDirectory` mengarahkan engine ke folder yang berisi file `.tex` sumber Anda, paket gaya, dan font khusus apa pun. Menggunakan jalur absolut selama pengembangan menghindari kebingungan dengan direktori kerja default IDE.

```java
// Specify a file system working directory for the input.
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
```

> **Pro tip:** Jaga folder input Anda hanya-baca di produksi untuk mencegah modifikasi tidak sengaja pada file TeX sumber.

### Langkah 3: Atur direktori output TeX

`setOutputWorkingDirectory` menentukan tempat engine menulis PDF yang dikompilasi, file log, dan data tambahan. Memisahkan output dari sumber memudahkan pembersihan dan memungkinkan Anda mengarsipkan hasil secara otomatis.

```java
// Specify a file system working directory for the output.
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### Langkah 4: Jalankan perintah pembuatan format

Memanggil `createFormat("customtex", options)` memberi tahu Aspose.TeX untuk mengompilasi semua paket yang direferensikan dalam direktori input menjadi file format biner bernama `customtex.fmt`. Langkah ini biasanya selesai dalam hitungan detik, bahkan untuk koleksi paket yang besar, karena engine hanya mem-parsing setiap makro satu kali.

```java
// Run format creation.
TeXJob.createFormat("customtex", options);
```

Setelah pemanggilan selesai, Anda akan menemukan `customtex.fmt` di dalam folder output. Memuat file ini pada run selanjutnya mengurangi waktu kompilasi untuk setiap dokumen hingga **70 %**, menurut benchmark Aspose.

### Langkah 5: Bersihkan output terminal (opsional)

`System.out.println()` sederhana menambahkan baris baru setelah proses selesai, menjaga output konsol tetap rapi ketika Anda menautkan beberapa konversi dalam pekerjaan batch.

```java
// For further output to look fine.
options.getTerminalOut().getWriter().newLine();
// ExEnd:CreateCustomTeXFormatFile
```

## Masalah umum & solusi
| Issue | Cause | Fix |
|-------|-------|-----|
| **“File not found” untuk sumber .tex** | Jalur direktori input tidak benar | Verifikasi bahwa jalur yang diberikan ke `setInputWorkingDirectory` cocok dengan folder yang berisi file `.tex` Anda. |
| **Permission denied pada folder output** | Hak menulis tidak ada | Pastikan proses Java memiliki izin menulis untuk direktori yang diatur melalui `setOutputWorkingDirectory`. |
| **Pembuatan format macet** | Terlalu banyak paket yang dimuat | Pra‑kompilasi hanya paket yang Anda butuhkan; Aspose.TeX dapat menangani **60+** format input tanpa memuat seluruh distribusi TeX. |

## Pertanyaan yang sering diajukan

**Q: Di mana saya dapat menemukan dokumentasi untuk Aspose.TeX for Java?**  
A: Anda dapat merujuk ke [Aspose.TeX for Java documentation](https://reference.aspose.com/tex/java/) untuk detail API yang komprehensif dan contoh penggunaan.

**Q: Bagaimana cara mengunduh Aspose.TeX for Java?**  
A: Anda dapat mengunduh pustaka tersebut dari [Aspose.TeX download page](https://releases.aspose.com/tex/java/).

**Q: Di mana saya dapat membeli Aspose.TeX for Java?**  
A: Anda dapat membeli Aspose.TeX for Java dari [purchase page](https://purchase.aspose.com/buy).

**Q: Apakah tersedia versi percobaan gratis untuk Aspose.TeX for Java?**  
A: Ya, Anda dapat mengakses versi percobaan gratis di [Aspose.TeX free trial download page](https://releases.aspose.com/).

**Q: Bagaimana saya dapat mendapatkan dukungan untuk Aspose.TeX for Java?**  
A: Anda dapat mencari dukungan di [Aspose.TeX forum](https://forum.aspose.com/c/tex/47).

## Kesimpulan
Anda kini memiliki resep lengkap yang siap produksi untuk **menghasilkan PDF dari TeX** dengan Aspose.TeX untuk Java. Dengan **mengatur direktori input TeX** dan **mengatur direktori output TeX**, Anda memperoleh kontrol penuh atas tempat file sumber dibaca dan tempat hasil ditulis, menghasilkan typesetting yang andal dan dapat diulang di semua proyek Java Anda. Gunakan kembali file `customtex.fmt` pada run selanjutnya untuk menikmati kompilasi yang lebih cepat dan tata letak yang konsisten.

---

**Terakhir Diperbarui:** 2026-09-04  
**Diuji Dengan:** Aspose.TeX for Java 24.11  
**Penulis:** Aspose

## Tutorial Terkait

- [Menyusun Format Tex Kustom](/tex/java/custom-tex-formats/typesetting-custom-tex-formats/)
- [Cara Membaca TeX – Panduan Java Mengatur Direktori Input dengan Aspose.TeX for Java](/tex/java/advanced-io/required-input-directory/)
- [Cara Mengonversi TeX ke XPS di Java – Panduan Langkah demi Langkah](/tex/java/typesetting-tex-to-xps/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}