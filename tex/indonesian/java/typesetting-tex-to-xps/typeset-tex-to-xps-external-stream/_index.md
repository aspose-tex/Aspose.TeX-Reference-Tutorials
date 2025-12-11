---
date: 2025-12-11
description: Pelajari cara mengonversi TeX ke XPS dalam Java menggunakan Aspose.TeX.
  Panduan langkah demi langkah ini menunjukkan cara menghasilkan aliran dokumen XPS
  secara efisien.
linktitle: How to Convert TeX to XPS in Java with External Stream
second_title: Aspose.TeX Java API
title: Cara Mengonversi TeX ke XPS di Java dengan Stream Eksternal
url: /id/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengonversi TeX ke XPS di Java dengan Stream Eksternal

## Introduction

Jika Anda perlu **mengonversi TeX** menjadi output XPS berkualitas tinggi dari aplikasi Java, Aspose.TeX for Java membuat pekerjaan ini menjadi mudah. Pada tutorial ini Anda akan melihat secara tepat **cara mengonversi TeX** ke dokumen XPS menggunakan stream output eksternal, yang ideal ketika Anda ingin mengalirkan hasilnya langsung ke respons, layanan penyimpanan cloud, atau tujuan khusus lainnya. Mari kita jalani seluruh proses, mulai dari menyiapkan lingkungan hingga menulis file XPS akhir.

## Quick Answers
- **Apa yang dibahas dalam tutorial ini?** Mengonversi TeX ke XPS menggunakan Aspose.TeX dengan stream eksternal.  
- **Perpustakaan utama apa yang diperlukan?** Aspose.TeX for Java.  
- **Apakah saya memerlukan lisensi?** Lisensi sementara atau penuh diperlukan untuk penggunaan produksi.  
- **Bisakah saya menghasilkan stream dokumen XPS?** Ya – contoh menulis XPS langsung ke `OutputStream`.  
- **Versi Java apa yang didukung?** Semua JDK 8+ (tutorial ini menggunakan JDK 11 sebagai referensi).

## Prerequisites

Sebelum masuk ke kode, pastikan Anda memiliki hal‑hal berikut:

- Java Development Kit (JDK): Pastikan Java telah terpasang di sistem Anda. Anda dapat mengunduhnya dari [here](https://www.oracle.com/java/technologies/javase-downloads.html).

- Aspose.TeX for Java: Unduh dan instal Aspose.TeX for Java. Anda dapat menemukan tautan unduhan [here](https://releases.aspose.com/tex/java/).

## Import Packages

Mulailah dengan mengimpor paket yang diperlukan untuk memulai proses konversi TeX‑ke‑XPS Anda. Sertakan potongan kode berikut dalam proyek Java Anda:

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

## Step 1: Configure Conversion Options

Mulailah dengan membuat opsi konversi untuk format ObjectTeX default menggunakan kode berikut:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

Ini menyiapkan fondasi untuk proses typesetting.

## Step 2: Specify Job Name and Directories

Tentukan nama pekerjaan dan atur direktori kerja input serta output:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Pastikan Anda mengganti placeholder seperti "Your Input Directory" dengan jalur direktori Anda yang sebenarnya.

## Step 3: Configure Terminal Output

Tentukan bahwa output terminal harus ditulis ke file dalam direktori kerja output:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

Langkah ini memastikan log detail tertangkap untuk keperluan debugging.

## Step 4: Open Output Stream

Buka stream untuk menulis dokumen XPS yang telah di‑typeset:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

Ganti "Your Output Directory" dengan jalur yang sesuai.

## Step 5: Run the Job

Jalankan pekerjaan konversi TeX ke XPS:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

Ini menyelesaikan proses, dan Anda akan menemukan dokumen XPS yang dihasilkan di direktori output yang telah ditentukan.

## Common Issues and Solutions

| Issue | Why it Happens | How to Fix |
|-------|----------------|------------|
| **FileNotFoundException** when opening the stream | Jalur direktori output tidak benar atau tidak ada. | Verifikasi jalur, buat direktori terlebih dahulu, atau gunakan `Files.createDirectories`. |
| **NullPointerException** on `options.getOutputWorkingDirectory()` | `setOutputWorkingDirectory` tidak dipanggil atau mengembalikan `null`. | Pastikan Anda memanggil `options.setOutputWorkingDirectory` sebelum menggunakannya. |
| **LicenseException** at runtime | Menjalankan tanpa lisensi Aspose.TeX yang valid. | Terapkan lisensi sementara atau permanen menggunakan `License license = new License(); license.setLicense("Aspose.TeX.lic");`. |

## Frequently Asked Questions

**Q: Can I use Aspose.TeX for Java with other document formats?**  
A: Aspose.TeX primarily focuses on TeX‑related document processing. For other formats, explore Aspose's extensive product range.

**Q: Is there a trial version available?**  
A: Yes, you can experience Aspose.TeX by downloading the free trial [here](https://releases.aspose.com/).

**Q: Where can I find comprehensive documentation?**  
A: Refer to the documentation [here](https://reference.aspose.com/tex/java/) for detailed information and examples.

**Q: How do I get support or seek assistance?**  
A: Visit the Aspose.TeX forum [here](https://forum.aspose.com/c/tex/47) for community support and discussions.

**Q: Can I obtain a temporary license for testing purposes?**  
A: Yes, you can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).

## Conclusion

Selamat! Anda baru saja mempelajari **cara mengonversi TeX** ke dokumen XPS di Java menggunakan Aspose.TeX dan stream eksternal. Teknik ini memberi Anda kontrol penuh atas tujuan output XPS—apakah ke sistem file, respons web, atau bucket cloud. Jangan ragu untuk bereksperimen dengan berbagai sumber TeX, menyesuaikan `TeXOptions` untuk font khusus, atau menghubungkan stream ke pipeline generasi dokumen yang lebih besar.

---

**Last Updated:** 2025-12-11  
**Tested With:** Aspose.TeX for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}