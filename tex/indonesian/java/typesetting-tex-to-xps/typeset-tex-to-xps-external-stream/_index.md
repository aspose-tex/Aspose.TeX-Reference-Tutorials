---
title: Mengeset TeX ke XPS di Java dengan Aliran Eksternal
linktitle: Mengeset TeX ke XPS di Java dengan Aliran Eksternal
second_title: Aspose.TeX Java API
description: Pelajari cara mengeset TeX ke XPS di Java menggunakan Aspose.TeX. Jelajahi panduan langkah demi langkah untuk pemrosesan dokumen yang lancar.
weight: 10
url: /id/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mengeset TeX ke XPS di Java dengan Aliran Eksternal

## Perkenalan

Dalam dunia pengembangan Java, Aspose.TeX menonjol sebagai alat yang ampuh untuk menyusun dokumen TeX ke dalam berbagai format, termasuk XPS. Jika Anda ingin meningkatkan kemampuan pemrosesan dokumen aplikasi Java, tutorial ini dirancang untuk Anda. Dalam panduan langkah demi langkah ini, kami akan memandu Anda melalui proses penyusunan huruf TeX ke XPS menggunakan Aspose.TeX untuk Java dengan aliran eksternal.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

-  Java Development Kit (JDK): Pastikan Anda telah menginstal Java di sistem Anda. Anda dapat mengunduhnya dari[Di Sini](https://www.oracle.com/java/technologies/javase-downloads.html).

-  Aspose.TeX untuk Java: Unduh dan instal Aspose.TeX untuk Java. Anda dapat menemukan tautan unduhan[Di Sini](https://releases.aspose.com/tex/java/).

## Paket Impor

Mulailah dengan mengimpor paket yang diperlukan untuk memulai perjalanan konversi TeX ke XPS Anda. Sertakan cuplikan kode berikut dalam proyek Java Anda:

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

## Langkah 1: Konfigurasikan Opsi Konversi

Mulailah dengan membuat opsi konversi untuk format ObjectTeX default menggunakan kode berikut:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

Ini menetapkan dasar untuk proses penyusunan huruf.

## Langkah 2: Tentukan Nama Pekerjaan dan Direktori

Tentukan nama pekerjaan dan atur direktori kerja input dan output:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Pastikan Anda mengganti placeholder seperti "Direktori Input Anda" dengan jalur direktori Anda yang sebenarnya.

## Langkah 3: Konfigurasikan Output Terminal

Tentukan bahwa keluaran terminal harus ditulis ke file di direktori kerja keluaran:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

Langkah ini memastikan log terperinci diambil untuk proses debug.

## Langkah 4: Buka Aliran Keluaran

Buka aliran untuk menulis dokumen XPS yang dikeset:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

Ganti "Direktori Output Anda" dengan jalur yang sesuai.

## Langkah 5: Jalankan Pekerjaan

Jalankan pekerjaan konversi TeX ke XPS:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

Ini menyelesaikan prosesnya, dan Anda akan menemukan dokumen XPS pengesetan Anda di direktori keluaran yang ditentukan.

## Kesimpulan

Selamat! Anda telah berhasil mengeset TeX ke XPS di Java menggunakan Aspose.TeX. Ini membuka banyak kemungkinan untuk pemrosesan dokumen di aplikasi Java Anda. Bereksperimenlah dengan berbagai file TeX dan jelajahi beragam fitur yang ditawarkan oleh Aspose.TeX.

## FAQ

### Q1: Bisakah saya menggunakan Aspose.TeX untuk Java dengan format dokumen lain?

A1: Aspose.TeX terutama berfokus pada pemrosesan dokumen terkait TeX. Untuk format lain, jelajahi rangkaian produk Aspose yang luas.

### Q2: Apakah ada versi uji coba yang tersedia?

 A2: Ya, Anda dapat merasakan Aspose.TeX dengan mengunduh uji coba gratis[Di Sini](https://releases.aspose.com/).

### Q3: Di mana saya dapat menemukan dokumentasi yang komprehensif?

 A3: Lihat dokumentasi[Di Sini](https://reference.aspose.com/tex/java/) untuk informasi rinci dan contoh.

### Q4: Bagaimana cara mendapatkan dukungan atau mencari bantuan?

 A4: Kunjungi forum Aspose.TeX[Di Sini](https://forum.aspose.com/c/tex/47)untuk dukungan dan diskusi komunitas.

### Q5: Bisakah saya mendapatkan lisensi sementara untuk tujuan pengujian?

 A5: Ya, Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
