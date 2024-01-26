---
title: Ganti Nama Pekerjaan dan Tulis Output Terminal di Java
linktitle: Ganti Nama Pekerjaan dan Tulis Output Terminal di Java
second_title: Aspose.TeX Java API
description: Jelajahi panduan langkah demi langkah tentang mengganti nama pekerjaan dan menulis keluaran terminal menggunakan Aspose.TeX untuk Java. Tingkatkan pemrosesan dokumen Anda dengan opsi penyesuaian yang canggih.
type: docs
weight: 10
url: /id/java/customizing-output/override-job-name-disk/
---
## Perkenalan

Aspose.TeX untuk Java menyediakan fitur canggih untuk bekerja dengan file TeX, memungkinkan pengembang untuk memanipulasi dan menyesuaikan pemrosesan dokumen TeX. Dalam tutorial ini, kami akan memandu Anda melalui proses penggantian nama pekerjaan dan penulisan output terminal ke sistem file menggunakan Aspose.TeX di Java.

## Prasyarat

Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:

- Pengetahuan kerja tentang pemrograman Java.
-  Aspose.TeX untuk Java diinstal. Anda dapat mengunduhnya dari[Dokumentasi Aspose.TeX Java](https://reference.aspose.com/tex/java/).

## Paket Impor

Untuk memulai, impor paket yang diperlukan ke proyek Java Anda. Di file Java Anda, sertakan impor berikut:

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

## Ganti Nama Pekerjaan dan Tulis Output Terminal

### Langkah 1: Buat Opsi Konversi

Mulailah dengan membuat opsi konversi untuk format ObjectTeX default pada ekstensi mesin ObjectTeX. Gunakan cuplikan kode berikut:

```java
//ExStart:OverrideJobName-WriteTerminalOutputToFileSystem
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

### Langkah 2: Tentukan Nama Pekerjaan dan Direktori Kerja

Tentukan nama pekerjaan, direktori kerja masukan, dan direktori kerja keluaran. Jika nama tugas tidak ditentukan, argumen pertama konstruktor TeXJob akan diambil sebagai nama tugas. Gunakan cuplikan kode berikut:

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### Langkah 3: Tulis Output Terminal ke Sistem File

 Tentukan bahwa keluaran terminal harus ditulis ke file di direktori kerja keluaran. Nama filenya adalah`<job_name>.trm`. Tambahkan kode berikut:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### Langkah 4: Jalankan Pekerjaan

Jalankan pekerjaan TeX menggunakan opsi dan nama pekerjaan yang ditentukan. Inilah cara Anda melakukannya:

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
// ExEnd:OverrideJobName-WriteTerminalOutputToFileSystem
```

Selamat! Anda telah berhasil mengganti nama pekerjaan dan menulis keluaran terminal ke sistem file menggunakan Aspose.TeX di Java.

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara memanfaatkan Aspose.TeX untuk Java untuk mengganti nama pekerjaan dan menangkap keluaran terminal. Fitur-fitur ini memberdayakan pengembang untuk memiliki kendali penuh atas pemrosesan dokumen TeX, meningkatkan penyesuaian dan fleksibilitas.

## FAQ

### Q1: Bisakah saya menggunakan Aspose.TeX untuk Java dengan perpustakaan Java lainnya?

A1: Ya, Aspose.TeX untuk Java dirancang untuk berintegrasi secara lancar dengan pustaka Java lainnya guna meningkatkan kemampuan pemrosesan dokumen Anda.

### Q2: Di mana saya dapat menemukan dukungan untuk Aspose.TeX untuk Java?

 A2: Kunjungi[Forum Aspose.TeX](https://forum.aspose.com/c/tex/47) untuk dukungan komunitas dan bantuan dengan masalah apa pun yang mungkin Anda temui.

### Q3: Apakah ada uji coba gratis yang tersedia untuk Aspose.TeX untuk Java?

 A3: Ya, Anda dapat mengakses Aspose.TeX versi uji coba gratis untuk Java[Di Sini](https://releases.aspose.com/).

### Q4: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.TeX untuk Java?

 A4: Ikuti ini[tautan](https://purchase.aspose.com/temporary-license/) untuk mendapatkan izin sementara untuk tujuan pengujian dan evaluasi.

### Q5: Di mana saya dapat membeli Aspose.TeX untuk Java?

 A5: Kunjungi[halaman pembelian](https://purchase.aspose.com/buy) untuk memperoleh lisensi Aspose.TeX untuk Java.