---
title: Input Aliran, Output Gambar, dan Input Terminal di Java
linktitle: Input Aliran, Output Gambar, dan Input Terminal di Java
second_title: Aspose.TeX Java API
description: Pelajari input aliran, output gambar, dan input terminal di Java menggunakan Aspose.TeX. Tutorial komprehensif untuk integrasi yang lancar.
type: docs
weight: 11
url: /id/java/advanced-io/stream-input-image-output/
---
## Perkenalan

Aspose.TeX untuk Java adalah perpustakaan canggih yang memungkinkan pengembang bekerja dengan file TeX, memfasilitasi pembuatan dan manipulasi dokumen berkualitas tinggi. Dalam tutorial ini, kita akan menjelajahi proses mengambil input aliran, menghasilkan output gambar, dan menangani input terminal di Java menggunakan Aspose.TeX.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

- Pemahaman dasar pemrograman Java.
- Java Development Kit (JDK) diinstal pada mesin Anda.
- Keakraban dengan perpustakaan Aspose.TeX.
-  Aspose.TeX untuk Java diinstal. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/tex/java/).

## Paket Impor

Pastikan Anda telah mengimpor paket yang diperlukan untuk tutorial ini. Cuplikan kode berikut menunjukkan impor yang diperlukan:

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

## Langkah 1: Siapkan Opsi Konversi

Buat opsi konversi TeX dengan format ObjectTeX default pada ekstensi mesin ObjectTeX. Tentukan nama pekerjaan, direktori kerja masukan, dan direktori kerja keluaran.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("stream-in-image-out");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

## Langkah 2: Tentukan Terminal Input dan Output

Tentukan konsol sebagai terminal input dan output.

```java
options.setTerminalIn(new InputConsoleTerminal());
options.setTerminalOut(new OutputConsoleTerminal());
```

## Langkah 3: Tentukan Opsi Penyimpanan

Tentukan opsi penyimpanan untuk gambar keluaran. Pada contoh ini kami menggunakan format PNG dengan resolusi 300 DPI.

```java
PngSaveOptions pngOptions = new PngSaveOptions();
pngOptions.setResolution(300);
options.setSaveOptions(pngOptions);
```

## Langkah 4: Buat Perangkat Gambar

Buat perangkat gambar untuk menghasilkan gambar keluaran.

```java
ImageDevice device = new ImageDevice();
```

## Langkah 5: Jalankan Pekerjaan

Jalankan pekerjaan TeX dengan input, perangkat, dan opsi yang ditentukan.

```java
TeXJob job = new TeXJob(new ByteArrayInputStream(
        "\\hrule height 10pt width 95pt\\vskip10pt\\hrule height 5pt".getBytes("ASCII")),
        device, options);
job.run();
```

## Langkah 6: Tangani Input Terminal

Saat konsol meminta masukan, ketik "ABC", tekan Enter, lalu ketik "\end" dan tekan Enter lagi.

```java
// Agar keluaran selanjutnya terlihat baik-baik saja.
options.getTerminalOut().getWriter().newLine();
```

## Langkah 7: Ambil Output Gambar

Anda dapat memperoleh gambar dalam bentuk array array byte.

```java
byte[][] result = device.getResult();
```

Ini melengkapi panduan langkah demi langkah untuk input aliran, output gambar, dan input terminal di Java menggunakan Aspose.TeX.

## Kesimpulan

Aspose.TeX untuk Java menyederhanakan proses penanganan dokumen TeX, menawarkan fitur canggih untuk input aliran, output gambar, dan interaksi terminal. Dengan mengikuti tutorial ini, Anda telah mempelajari cara mengintegrasikan fungsi-fungsi ini ke dalam aplikasi Java Anda dengan lancar.

## FAQ

### Q1: Apakah Aspose.TeX kompatibel dengan perpustakaan Java lainnya?

A1: Ya, Aspose.TeX dapat diintegrasikan dengan perpustakaan Java lainnya untuk meningkatkan fungsionalitas.

### Q2: Dapatkah saya menyesuaikan format gambar keluaran?

A2: Tentu saja! Aspose.TeX menyediakan berbagai opsi untuk menyimpan gambar keluaran, memungkinkan penyesuaian berdasarkan preferensi Anda.

### Q3: Apakah ada forum komunitas untuk dukungan Aspose.TeX?

 A3: Ya, Anda dapat memperoleh dukungan dan berinteraksi dengan komunitas di[Forum Aspose.TeX](https://forum.aspose.com/c/tex/47).

### Q4: Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.TeX?

 A4: Anda bisa mendapatkan lisensi sementara dari[Di Sini](https://purchase.aspose.com/temporary-license/).

### Q5: Apakah ada sumber daya tambahan untuk dokumentasi Aspose.TeX?

 A5: Jelajahi secara komprehensif[dokumentasi](https://reference.aspose.com/tex/java/) untuk wawasan dan contoh terperinci.