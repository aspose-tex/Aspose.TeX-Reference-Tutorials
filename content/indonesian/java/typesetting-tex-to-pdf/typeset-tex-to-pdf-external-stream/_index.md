---
title: Mengeset TeX ke PDF di Java dengan Aliran Eksternal
linktitle: Mengeset TeX ke PDF di Java dengan Aliran Eksternal
second_title: Aspose.TeX Java API
description: Pelajari cara mengeset TeX ke PDF di Java menggunakan aliran eksternal dengan Aspose.TeX. Ikuti panduan langkah demi langkah kami untuk integrasi yang lancar.
type: docs
weight: 10
url: /id/java/typesetting-tex-to-pdf/typeset-tex-to-pdf-external-stream/
---
## Perkenalan

Dalam dunia pengembangan Java, membuat PDF dari file TeX merupakan kebutuhan umum. Aspose.TeX untuk Java menyederhanakan proses ini, memberikan solusi efisien untuk penyusunan huruf TeX ke PDF. Dalam tutorial ini, kami akan memandu Anda melalui langkah-langkah penyusunan huruf TeX ke PDF menggunakan aliran eksternal. Pada akhirnya, Anda akan memiliki pemahaman yang jelas tentang bagaimana menerapkan proses ini dengan lancar di aplikasi Java Anda.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

- Aspose.TeX untuk Java: Pastikan Anda telah menginstal perpustakaan Aspose.TeX untuk Java. Anda dapat mengunduhnya dari[Aspose.TeX untuk dokumentasi Java](https://reference.aspose.com/tex/java/).

- Direktori Input dan Output: Siapkan direktori input dan output. Anda dapat menggunakan tautan unduhan yang disediakan untuk mendapatkan file yang diperlukan.

## Paket Impor

Mulailah dengan mengimpor paket yang diperlukan ke proyek Java Anda:

```java
package com.aspose.tex.TypesetPdfWrittenToExternalStream;

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

## Langkah 1: Buka Aliran Input dan Output

Mulailah dengan membuka aliran untuk arsip ZIP masukan (berfungsi sebagai direktori kerja masukan) dan arsip ZIP keluaran (berfungsi sebagai direktori kerja keluaran). Pastikan untuk mengganti "Direktori Input Anda" dan "Direktori Output Anda" dengan jalur direktori Anda yang sebenarnya.

```java
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "typeset-pdf-to-external-stream.zip");
```

## Langkah 2: Konfigurasikan TeXOptions

Buat objek TeXOptions dan konfigurasikan sesuai kebutuhan Anda. Tetapkan nama pekerjaan, direktori kerja masukan, direktori kerja keluaran, dan opsi lainnya.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("typeset-pdf-to-external-stream");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
options.setSaveOptions(new PdfSaveOptions());
```

## Langkah 3: Atur TeX ke PDF

Sekarang, buka aliran untuk menulis keluaran PDF ke lokasi yang diinginkan. Anda dapat memilih untuk menulisnya ke file lokal atau langsung ke arsip ZIP keluaran.

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + "file-name.pdf");
try {
    new TeXJob("hello-world", new PdfDevice(stream), options).run();
} finally {
    stream.close();
}
```

## Langkah 4: Selesaikan Arsip ZIP Keluaran

Selesaikan arsip ZIP keluaran untuk menyelesaikan proses penyusunan huruf.

```java
((OutputZipDirectory)options.getOutputWorkingDirectory()).finish();
```

## Kesimpulan

Selamat! Anda telah berhasil mengeset TeX ke PDF di Java menggunakan aliran eksternal dengan Aspose.TeX. Tutorial ini memberikan landasan yang kuat untuk menggabungkan konversi TeX ke PDF ke dalam aplikasi Java Anda dengan lancar.

## FAQ

### Q1: Dapatkah saya menyesuaikan nama file output PDF?

 A1: Ya, Anda dapat memodifikasinya`options.setJobName("typeset-pdf-to-external-stream")` untuk mengatur nama pekerjaan yang Anda inginkan.

### Q2: Bagaimana cara memecahkan masalah umum selama penyusunan huruf?

 A2: Kunjungi[Forum Aspose.TeX](https://forum.aspose.com/c/tex/47) untuk dukungan dan bantuan masyarakat.

### Q3: Apakah ada uji coba gratis yang tersedia untuk Aspose.TeX untuk Java?

 A3: Ya, Anda dapat mengakses uji coba gratis[Di Sini](https://releases.aspose.com/).

### Q4: Di mana saya dapat menemukan dokumentasi dan contoh tambahan?

 A4: Jelajahi secara komprehensif[Dokumentasi Aspose.TeX](https://reference.aspose.com/tex/java/) untuk informasi rinci.

### Q5: Bisakah saya mendapatkan lisensi sementara untuk Aspose.TeX?

 A5: Ya, Anda dapat meminta izin sementara[Di Sini](https://purchase.aspose.com/temporary-license/).