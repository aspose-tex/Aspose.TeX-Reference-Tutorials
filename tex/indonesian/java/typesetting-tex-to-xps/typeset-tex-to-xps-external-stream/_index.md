---
date: 2026-02-20
description: Pelajari cara mengonversi TeX ke XPS dalam Java menggunakan Aspose.TeX.
  Panduan langkah demi langkah ini menunjukkan cara mengonversi file TeX dan menghasilkan
  aliran dokumen XPS secara efisien.
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

## Pendahuluan

Jika Anda perlu **mengonversi file TeX** menjadi output XPS berkualitas tinggi dari aplikasi Java, Aspose.TeX untuk Java membuat pekerjaan ini menjadi mudah. Pada tutorial ini Anda akan melihat secara tepat **cara mengonversi TeX** ke dokumen XPS menggunakan stream output eksternal, yang ideal ketika Anda ingin mengalirkan hasil langsung ke respons, layanan penyimpanan cloud, atau tujuan khusus lainnya. Mari kita jalani seluruh proses, mulai dari menyiapkan lingkungan hingga menulis file XPS akhir.

## Jawaban Cepat
- **Apa yang dibahas dalam tutorial ini?** Mengonversi TeX ke XPS menggunakan Aspose.TeX dengan stream eksternal.  
- **Perpustakaan utama apa yang dibutuhkan?** Aspose.TeX untuk Java.  
- **Apakah saya memerlukan lisensi?** Lisensi sementara atau penuh diperlukan untuk penggunaan produksi.  
- **Bisakah saya menghasilkan stream dokumen XPS?** Ya – contoh menulis XPS langsung ke `OutputStream`.  
- **Versi Java apa yang didukung?** Semua JDK 8+ (tutorial ini menggunakan JDK 11 sebagai referensi).

## Cara Mengonversi TeX ke XPS Menggunakan Stream Eksternal

Bagian ini mengulangi kata kunci inti dalam judul khusus, memudahkan pembaca dan mesin AI menemukan solusi yang tepat.

## Prasyarat

Sebelum menyelam ke kode, pastikan Anda memiliki hal‑hal berikut:

- Java Development Kit (JDK): Pastikan Java telah terpasang di sistem Anda. Anda dapat mengunduhnya dari [sini](https://www.oracle.com/java/technologies/javase-downloads.html).

- Aspose.TeX untuk Java: Unduh dan instal Aspose.TeX untuk Java. Anda dapat menemukan tautan unduhan [sini](https://releases.aspose.com/tex/java/).

## Impor Paket

Mulailah dengan mengimpor paket yang diperlukan untuk memulai perjalanan konversi TeX‑ke‑XPS Anda. Sertakan potongan kode berikut dalam proyek Java Anda:

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

## Langkah 1: Konfigurasi Opsi Konversi

Mulailah dengan membuat opsi konversi untuk format ObjectTeX default menggunakan kode berikut:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

Ini menyiapkan fondasi untuk proses typesetting.

## Langkah 2: Tentukan Nama Pekerjaan dan Direktori

Definisikan nama pekerjaan dan atur direktori kerja input serta output:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Pastikan Anda mengganti placeholder seperti "Your Input Directory" dengan jalur direktori Anda yang sebenarnya.

## Langkah 3: Konfigurasi Output Terminal

Tentukan bahwa output terminal harus ditulis ke file di direktori kerja output:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

Langkah ini memastikan log detail tertangkap untuk debugging.

## Langkah 4: Buka Stream Output

Buka stream untuk menulis dokumen XPS yang telah di‑typeset:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

Ganti "Your Output Directory" dengan jalur yang sesuai.

## Langkah 5: Jalankan Pekerjaan

Eksekusi pekerjaan konversi TeX ke XPS:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

Ini menyelesaikan proses, dan Anda akan menemukan dokumen XPS yang dihasilkan di direktori output yang telah ditentukan.

## Mengapa Ini Penting

Menggunakan `OutputStream` eksternal memberi Anda kontrol penuh atas tujuan data XPS—apakah Anda mengirimnya langsung ke klien web, menyimpannya di penyimpanan cloud, atau menghubungkannya ke pipeline pemrosesan lain. Ini menghilangkan kebutuhan akan file perantara dan mengurangi overhead I/O, yang sangat berharga dalam lingkungan throughput tinggi atau tanpa server.

## Masalah Umum dan Solusinya

| Masalah | Mengapa Terjadi | Cara Memperbaiki |
|-------|----------------|------------|
| **FileNotFoundException** saat membuka stream | Jalur direktori output tidak benar atau tidak ada. | Verifikasi jalur, buat direktori terlebih dahulu, atau gunakan `Files.createDirectories`. |
| **NullPointerException** pada `options.getOutputWorkingDirectory()` | `setOutputWorkingDirectory` tidak dipanggil atau mengembalikan `null`. | Pastikan Anda memanggil `options.setOutputWorkingDirectory` sebelum menggunakannya. |
| **LicenseException** saat runtime | Menjalankan tanpa lisensi Aspose.TeX yang valid. | Terapkan lisensi sementara atau permanen menggunakan `License license = new License(); license.setLicense("Aspose.TeX.lic");`. |

## FAQ

**T: Bisakah saya menggunakan Aspose.TeX untuk Java dengan format dokumen lain?**  
J: Aspose.TeX fokus pada pemrosesan dokumen terkait TeX. Untuk format lain, jelajahi rangkaian produk Aspose yang luas.

**T: Apakah ada versi trial yang tersedia?**  
J: Ya, Anda dapat mencoba Aspose.TeX dengan mengunduh trial gratis [sini](https://releases.aspose.com/).

**T: Di mana saya dapat menemukan dokumentasi lengkap?**  
J: Lihat dokumentasi [sini](https://reference.aspose.com/tex/java/) untuk informasi detail dan contoh.

**T: Bagaimana cara mendapatkan dukungan atau bantuan?**  
J: Kunjungi forum Aspose.TeX [sini](https://forum.aspose.com/c/tex/47) untuk dukungan komunitas dan diskusi.

**T: Bisakah saya memperoleh lisensi sementara untuk tujuan pengujian?**  
J: Ya, Anda dapat memperoleh lisensi sementara [sini](https://purchase.aspose.com/temporary-license/).

## Kesimpulan

Selamat! Anda baru saja mempelajari **cara mengonversi TeX** ke dokumen XPS di Java menggunakan Aspose.TeX dan stream eksternal. Teknik ini memberi Anda kontrol penuh atas tujuan output XPS—apakah itu sistem file, respons web, atau bucket cloud. Jangan ragu untuk bereksperimen dengan sumber TeX yang berbeda, menyesuaikan `TeXOptions` untuk font khusus, atau menghubungkan stream ke pipeline generasi dokumen yang lebih besar.

---

**Terakhir Diperbarui:** 2026-02-20  
**Diuji Dengan:** Aspose.TeX untuk Java 24.11 (terbaru pada saat penulisan)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}