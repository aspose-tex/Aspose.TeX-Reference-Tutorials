---
title: Konversi LaTeX ke Format XPS di Java dengan Mudah
linktitle: Konversi LaTeX ke Format XPS di Java dengan Mudah
second_title: Aspose.TeX Java API
description: Konversi LaTeX ke XPS dengan mudah di Java menggunakan Aspose.TeX. Ikuti panduan langkah demi langkah kami untuk integrasi yang lancar.
weight: 10
url: /id/java/converting-lato-xps/simple-xps-conversion/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konversi LaTeX ke Format XPS di Java dengan Mudah

## Perkenalan

Apakah Anda ingin mengonversi dokumen LaTeX ke format XPS dengan lancar di aplikasi Java Anda? Aspose.TeX untuk Java memberikan solusi yang kuat, memungkinkan Anda mencapai hal ini dengan mudah. Dalam panduan langkah demi langkah ini, kami akan memandu Anda melalui proses mengonversi LaTeX ke XPS menggunakan Aspose.TeX.

## Prasyarat

Sebelum mendalami proses konversi, pastikan Anda memiliki prasyarat berikut:

- Java Development Kit (JDK) diinstal pada sistem Anda.
-  Aspose.TeX untuk perpustakaan Java diunduh. Anda dapat menemukan tautan unduhan[Di Sini](https://releases.aspose.com/tex/java/).

## Paket Impor

Untuk memulai, impor paket yang diperlukan untuk proyek Java Anda. Pastikan Anda menyertakan pustaka Aspose.TeX dalam dependensi proyek Anda.

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

Sekarang mari kita bagi proses konversi menjadi beberapa langkah menggunakan contoh kode yang disediakan.

## Langkah 1: Tetapkan Direktori Input dan Output

```java
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Tentukan direktori tempat file input LaTeX Anda berada dan tempat Anda ingin menyimpan file XPS yang dikonversi.

## Langkah 2: Konfigurasikan Opsi TeX

Konfigurasikan berbagai opsi untuk menyesuaikan proses konversi sesuai kebutuhan Anda.

```java
options.setInteraction(Interaction.NonstopMode);
options.setDateTime(new GregorianCalendar(2022, Calendar.DECEMBER, 18).getTime());
options.ignoreMissingPackages(true);
options.noLigatures(true);
options.repeat(true);
```

Sesuaikan mode interaksi, tanggal pada judul, penanganan paket yang hilang, pengikat, dan pengulangan sesuai kebutuhan.

## Langkah 3: Inisialisasi Opsi Penyimpanan XPS

```java
options.setSaveOptions(new XpsSaveOptions());
```

Inisialisasi opsi untuk menyimpan dalam format XPS.

## Langkah 4: Sesuaikan Opsi Penyimpanan XPS

```java
options.getSaveOptions().rasterizeFormulas(true);
options.getSaveOptions().rasterizeIncludedGraphics(true);
options.getSaveOptions().subsetFonts(true);
```

Sesuaikan opsi penyimpanan XPS untuk mengontrol konversi rumus, grafik yang disertakan, dan subpengaturan font.

## Langkah 5: Jalankan Konversi LaTeX ke XPS

```java
new TeXJob("Your Input Directory" + "sample.ltx", new XpsDevice(), options).run();
```

Memulai proses konversi dengan menjalankan pekerjaan TeX dengan file input, perangkat output (XpsDevice), dan opsi yang ditentukan.

## Contoh Tambahan

Jelajahi metode konversi tambahan menggunakan sumber masukan yang berbeda:

### Gunakan InputStream

```java
new TeXJob(new ByteArrayInputStream(
    "\\documentclass{article} \\begin{document} Hello, World! \\end{document}".getBytes("ASCII")),
    new XpsDevice(), options).run();
```

### Gunakan Terminal Masukan Utama

```java
new TeXJob(new XpsDevice(), options).run();
```

## Kesimpulan

Dengan Aspose.TeX untuk Java, mengonversi LaTeX ke XPS sangatlah mudah. Ikuti langkah-langkah berikut, sesuaikan opsi, dan integrasikan fungsi ini dengan lancar ke dalam aplikasi Java Anda.

## FAQ

### Q1: Bisakah saya mengonversi dokumen LaTeX dengan rumus kompleks menggunakan Aspose.TeX?

A1: Tentu saja! Aspose.TeX menangani rumus kompleks dengan lancar selama proses konversi.

### Q2: Apakah ada versi uji coba yang tersedia untuk Aspose.TeX untuk Java?

 A2: Ya, Anda dapat menemukan versi uji coba gratis[Di Sini](https://releases.aspose.com/).

### Q3: Bagaimana saya bisa mendapatkan dukungan untuk Aspose.TeX?

 A3: Kunjungi[Forum Aspose.TeX](https://forum.aspose.com/c/tex/47) untuk bantuan dan dukungan masyarakat.

### Q4: Apakah lisensi sementara tersedia untuk Aspose.TeX?

 A4: Ya, Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).

### Q5: Di mana saya dapat menemukan dokumentasi untuk Aspose.TeX?

 A5: Lihat[dokumentasi](https://reference.aspose.com/tex/java/) untuk panduan komprehensif.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
