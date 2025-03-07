---
title: Ganti Nama Pekerjaan dan Tulis Output Terminal ke Zip di Java
linktitle: Ganti Nama Pekerjaan dan Tulis Output Terminal ke Zip di Java
second_title: Aspose.TeX Java API
description: Pelajari cara mengganti nama pekerjaan dan menulis output terminal ke ZIP di Java dengan Aspose.TeX. Tutorial komprehensif untuk pengembang Java.
weight: 11
url: /id/java/customizing-output/override-job-name-zip/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ganti Nama Pekerjaan dan Tulis Output Terminal ke Zip di Java

## Perkenalan

Dalam dunia pengembangan Java, Aspose.TeX menonjol sebagai alat yang ampuh untuk menangani format file TeX. Dalam tutorial ini, kita akan mempelajari skenario spesifik – mengganti nama pekerjaan dan menulis output terminal ke file zip. Panduan langkah demi langkah ini akan memandu Anda melalui proses menggunakan Aspose.TeX untuk Java.

## Prasyarat

Sebelum kita memulai tutorial ini, pastikan Anda memiliki prasyarat berikut:
- Pengetahuan dasar tentang pemrograman Java.
-  Menginstal Aspose.TeX untuk Java. Jika belum, Anda dapat mendownloadnya dari[Asumsikan situs web](https://releases.aspose.com/tex/java/).
- Pemahaman tentang cara menyiapkan lingkungan pengembangan Java.

## Paket Impor

Mulailah dengan mengimpor paket yang diperlukan ke proyek Java Anda. Hal ini memastikan bahwa Anda memiliki akses ke fungsionalitas Aspose.TeX yang diperlukan untuk tugas tersebut.

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

## Langkah 1: Buka Arsip ZIP

Pertama, buka aliran pada arsip ZIP yang akan berfungsi sebagai direktori kerja masukan. Ini adalah arsip tempat data Anda akan diproses.

```java
// Buka aliran pada arsip ZIP masukan
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
```

## Langkah 2: Buka Arsip ZIP Keluaran

Selanjutnya, buka aliran pada arsip ZIP yang akan berfungsi sebagai direktori kerja keluaran. Di sinilah keluaran terminal akan ditulis.

```java
// Buka aliran pada arsip ZIP keluaran
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "terminal-out-to-zip.zip");
```

## Langkah 3: Tetapkan Opsi Konversi

Buat opsi konversi untuk format ObjectTeX default pada ekstensi mesin ObjectTeX. Tentukan nama pekerjaan dan direktori kerja arsip ZIP untuk input dan output.

```java
// Buat opsi TeX untuk format ObjectTeX
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("terminal-output-to-zip");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
```

## Langkah 4: Tentukan Output Terminal

 Tentukan bahwa keluaran terminal harus ditulis ke file di direktori kerja keluaran. Nama filenya adalah`<job_name>.trm`.

```java
// Tentukan pengaturan keluaran terminal
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

## Langkah 5: Tentukan Opsi Penyimpanan dan Jalankan Pekerjaan

Tentukan opsi penyimpanan, seperti opsi penyimpanan PDF dalam kasus ini. Jalankan pekerjaan TeX untuk menjalankan konversi.

```java
// Tentukan opsi penyimpanan dan jalankan pekerjaan
options.setSaveOptions(new PdfSaveOptions());
new TeXJob("hello-world", new PdfDevice(), options).run();
```

## Langkah 6: Selesaikan Arsip ZIP Keluaran

Setelah pekerjaan selesai, selesaikan arsip ZIP keluaran untuk memastikan penyelesaian yang benar.

```java
// Selesaikan arsip ZIP keluaran
((OutputZipDirectory) options.getOutputWorkingDirectory()).finish();
```

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara mengganti nama pekerjaan dan menulis keluaran terminal ke file ZIP di Java menggunakan Aspose.TeX. Fungsionalitas canggih ini menambah fleksibilitas dan efisiensi pada proyek pengembangan Java Anda.

## FAQ

### Q1: Apa itu Aspose.TeX?

A1: Aspose.TeX adalah perpustakaan Java yang memungkinkan pengembang untuk bekerja dengan format file TeX, menyediakan fungsionalitas tingkat lanjut untuk pemrosesan dokumen.

### Q2: Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.TeX?

 A2: Anda bisa mendapatkan lisensi sementara dari[Link ini](https://purchase.aspose.com/temporary-license/).

### Q3: Di mana saya dapat menemukan dokumentasi Aspose.TeX?

 A3: Dokumentasi tersedia[Di Sini](https://reference.aspose.com/tex/java/).

### Q4: Apakah ada versi uji coba gratis Aspose.TeX?

 A4: Ya, Anda dapat menemukan versi uji coba gratis[Di Sini](https://releases.aspose.com/).

### Q5: Di mana saya dapat mencari dukungan atau mengajukan pertanyaan tentang Aspose.TeX?

 A5: Kunjungi[Forum Aspose.TeX](https://forum.aspose.com/c/tex/47) untuk dukungan dan diskusi.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
