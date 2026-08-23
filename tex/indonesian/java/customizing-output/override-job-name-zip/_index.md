---
date: 2026-08-23
description: Pelajari cara membuat dokumen PDF dari TeX, mengubah nama pekerjaan,
  dan menulis output terminal ke file ZIP menggunakan Aspose.TeX untuk Java. Panduan
  langkah demi langkah untuk pengembang Java.
keywords:
- create pdf document from tex
- Aspose.TeX Java
- TeX to PDF conversion
lastmod: 2026-08-23
linktitle: Konversi TeX ke PDF, Ubah Nama Pekerjaan, dan Tulis Output Terminal ke
  ZIP di Java
og_description: Pelajari cara membuat dokumen PDF dari TeX, menyesuaikan nama pekerjaan,
  dan menangkap output terminal dalam ZIP menggunakan Aspose.TeX untuk Java – panduan
  cepat 10 menit.
og_image_alt: Developer guide showing Java code to convert TeX to PDF and zip logs
og_title: Buat dokumen PDF dari TeX, ubah nama pekerjaan, dan kompres log menjadi
  ZIP di Java
schemas:
- author: Aspose
  dateModified: '2026-08-23'
  description: Learn how to create PDF document from TeX, override the job name, and
    write terminal output to a ZIP file using Aspose.TeX for Java. Step‑by‑step guide
    for Java developers.
  headline: How to create PDF document from TeX and zip logs in Java
  type: TechArticle
- questions:
  - answer: Aspose.TeX is a Java library that enables developers to **create PDF document
      from TeX** sources, manipulate TeX documents, and perform advanced rendering
      without external LaTeX installations.
    question: What is Aspose.TeX?
  - answer: You can get a temporary license from the [Aspose.TeX temporary license
      page](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.TeX?
  - answer: The documentation is available on the [Aspose.TeX Java documentation page](https://reference.aspose.com/tex/java/).
    question: Where can I find the official Aspose.TeX documentation?
  - answer: Yes, you can download the free trial from the [Aspose.TeX free trial page](https://releases.aspose.com/).
    question: Is there a free trial version of Aspose.TeX?
  - answer: Visit the [Aspose.TeX forum](https://forum.aspose.com/c/tex/47) for community
      support and official assistance.
    question: Where can I ask for help if I run into problems?
  type: FAQPage
second_title: Aspose.TeX Java API
tags:
- TeX conversion
- Aspose.TeX
- Java PDF generation
title: Cara membuat dokumen PDF dari TeX dan mengompres log menjadi ZIP di Java
url: /id/java/customizing-output/override-job-name-zip/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat dokumen PDF dari TeX dan zip log di Java

## Pendahuluan

Jika Anda perlu **membuat dokumen PDF dari TeX** sambil memiliki kontrol penuh atas nama pekerjaan dan log terminal, Aspose.TeX for Java membuatnya sederhana. Dalam tutorial ini kami akan membahas skenario dunia nyata: mengganti nama pekerjaan, mengarahkan output terminal ke dalam arsip ZIP, dan akhirnya menghasilkan dokumen PDF. Pada akhir tutorial Anda akan memiliki potongan kode yang dapat digunakan kembali dan dapat dimasukkan ke dalam proyek Java mana pun.

## Jawaban Cepat
- **Apa yang dicapai tutorial ini?** Menunjukkan cara membuat dokumen PDF dari TeX, menetapkan nama pekerjaan khusus, dan menangkap output terminal dalam file ZIP.  
- **Perpustakaan apa yang diperlukan?** Aspose.TeX for Java (versi terbaru).  
- **Apakah saya memerlukan lisensi?** Lisensi sementara cukup untuk evaluasi; lisensi penuh diperlukan untuk produksi.  
- **File output apa yang dihasilkan?** Dokumen PDF dan log terminal `<job_name>.trm` di dalam ZIP output.  
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk menyalin kode dan menjalankannya.

## Apa itu “mengonversi TeX ke PDF”?

Mengonversi TeX ke PDF berarti mengambil file sumber TeX (atau kumpulan file TeX) dan merendernya menjadi dokumen PDF. Aspose.TeX menyediakan mesin berperforma tinggi yang menangani seluruh pipeline kompilasi TeX tanpa memerlukan distribusi LaTeX eksternal.

## Mengapa mengganti nama pekerjaan dan menulis output terminal ke ZIP?

Mengganti nama pekerjaan memungkinkan Anda menandai setiap proses kompilasi dengan pengenal yang bermakna (misalnya, nomor build). Menulis output terminal ke ZIP menjaga log (`*.trm`) bersama dengan PDF yang dihasilkan, yang menyederhanakan pengarsipan, audit, dan debugging dalam pipeline otomatis.

## Mengapa ini penting

Ketika Anda menghasilkan PDF dari TeX di lingkungan produksi, Anda sering perlu menjaga artefak build tetap teratur. Mengganti nama pekerjaan memungkinkan Anda menandai setiap run dengan pengenal yang bermakna (misalnya, nomor build). Mengemas log terminal ke dalam ZIP yang sama dengan PDF memberi Anda paket tunggal yang portabel yang dapat diarsipkan atau dikirim ke layanan hilir tanpa kehilangan konteks.

## Kasus penggunaan umum
- **Pembuatan laporan otomatis** – pekerjaan malam hari membuat PDF dari templat TeX dan menyimpan log untuk keperluan audit.  
- **Pipeline CI/CD** – pengembang dapat melihat pesan kompilasi yang tepat ketika build gagal, tanpa harus menelusuri file log terpisah.  
- **Layanan dokumen berbasis cloud** – layanan web menerima ZIP sumber TeX, memprosesnya, dan mengembalikan ZIP yang berisi PDF dan log kompilasinya.

## Prasyarat

Sebelum Anda memulai, pastikan Anda memiliki:

- Lingkungan pengembangan Java yang berfungsi (JDK 8 atau lebih tinggi).  
- Aspose.TeX for Java diunduh dari [Halaman unduhan Aspose.TeX Java](https://releases.aspose.com/tex/java/).  
- Pemahaman dasar tentang aliran I/O Java.  

## Impor paket

Namespace `com.aspose.tex` berisi semua kelas yang diperlukan untuk konversi, sementara kelas standar `java.io` menangani aliran ZIP. Mengimpor paket-paket ini memberi Anda akses ke API Aspose.TeX dan utilitas I/O Java.

## Langkah 1: buka arsip zip input

Kelas `InputZipDirectory` mewakili file ZIP yang menyediakan file sumber TeX ke mesin konversi. Ini berfungsi sebagai **direktori kerja input** untuk pekerjaan.

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

## Langkah 2: buka arsip zip output

Kelas `OutputZipDirectory` membuat file ZIP yang akan menerima artefak yang dihasilkan seperti PDF dan log terminal. Ini adalah **direktori kerja output**.

```java
// Open a stream on the input ZIP archive
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
```

## Langkah 3: atur opsi konversi (termasuk nama pekerjaan)

`ConversionOptions` (khususnya `ObjectTeXOptions`) memungkinkan Anda mengonfigurasi proses kompilasi. Dengan memanggil `setJobName("MyBuild_123")` Anda mengganti pengenal pekerjaan default, yang kemudian muncul dalam nama file log dan metadata internal.

```java
// Open a stream on the output ZIP archive
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "terminal-out-to-zip.zip");
```

## Langkah 4: arahkan output terminal ke file dalam ZIP

Memanggil `options.setTerminalOut("MyBuild_123.trm")` memberi tahu Aspose.TeX untuk menulis seluruh output konsol kompiler ke file bernama `<job_name>.trm` di dalam ZIP output. File ini berisi peringatan, kesalahan, dan pesan informatif yang penting untuk pemecahan masalah.  
`setTerminalOut` menentukan nama file untuk log output terminal.

```java
// Create TeX options for ObjectTeX format
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("terminal-output-to-zip");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
```

## Langkah 5: definisikan opsi penyimpanan dan jalankan pekerjaan

Objek `SavingOptions` memilih perangkat rendering—dalam hal ini, PDF. Objek `Job` mengikat bersama direktori input, direktori output, dan opsi konversi serta mengatur proses. Memanggil `job.run()` mengeksekusi seluruh pipeline TeX‑ke‑PDF, menulis PDF ke ZIP output, dan membuat file log `.trm`. `run()` memulai pekerjaan konversi dan memblokir hingga selesai.

```java
// Specify terminal output settings
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

## Langkah 6: selesaikan arsip ZIP output

Setelah pekerjaan selesai, Anda harus memanggil `outputZip.finish()` untuk menutup aliran ZIP dan memastikan arsip valid. `finish()` menyelesaikan arsip ZIP dan menulis direktori pusat. Melewatkan langkah ini dapat merusak ZIP, membuat PDF atau log tidak dapat dibaca.

```java
// Define saving options and run the job
options.setSaveOptions(new PdfSaveOptions());
new TeXJob("hello-world", new PdfDevice(), options).run();
```

## Tips dan praktik terbaik

- **Gunakan kembali aliran**: Jika Anda memproses banyak pekerjaan TeX secara berurutan, biarkan aliran input dan output tetap terbuka dan hanya ubah `JobName` di antara run.  
- **Inspeksi log**: Buka file `<job_name>.trm` dengan editor teks apa pun untuk melihat peringatan atau kesalahan yang dikeluarkan kompiler TeX.  
- **Kinerja**: Aspose.TeX dapat memproses dokumen hingga 500 halaman dengan menggunakan kurang dari 1 GB memori heap pada server tipikal. Untuk file yang lebih besar, tingkatkan ukuran heap JVM (`-Xmx2g`).  
- **Keamanan**: Saat menangani sumber TeX yang tidak terpercaya, jalankan konversi dalam lingkungan sandbox untuk mengurangi potensi makro berbahaya.

## Masalah umum dan solusi

| Masalah | Penyebab kemungkinan | Solusi |
|-------|--------------|-----|
| **PDF kosong** | Input ZIP tidak berisi file `*.tex` yang valid atau file tidak ditempatkan di bawah folder `in`. | Verifikasi struktur ZIP (`in/yourfile.tex`). |
| **File `.trm` hilang** | `setTerminalOut` tidak dipanggil atau direktori output bukan `OutputZipDirectory`. | Pastikan `options.setTerminalOut(...)` dijalankan sebelum `run()`. |
| **`IOException` pada finish** | Aliran output sudah ditutup di tempat lain. | Panggil `finish()` hanya sekali, setelah pekerjaan selesai. |
| **Konversi gagal dengan kesalahan TeX** | Sumber TeX mengandung kesalahan sintaks. | Buka log `<job_name>.trm` yang dihasilkan untuk melihat pesan kesalahan detail. |

## Pertanyaan yang sering diajukan

**Q: Apa itu Aspose.TeX?**  
A: Aspose.TeX adalah perpustakaan Java yang memungkinkan pengembang **membuat dokumen PDF dari TeX** sumber, memanipulasi dokumen TeX, dan melakukan rendering lanjutan tanpa instalasi LaTeX eksternal.

**Q: Bagaimana saya dapat memperoleh lisensi sementara untuk Aspose.TeX?**  
A: Anda dapat mendapatkan lisensi sementara dari [halaman lisensi sementara Aspose.TeX](https://purchase.aspose.com/temporary-license/).

**Q: Di mana saya dapat menemukan dokumentasi resmi Aspose.TeX?**  
A: Dokumentasi tersedia di [halaman dokumentasi Aspose.TeX Java](https://reference.aspose.com/tex/java/).

**Q: Apakah ada versi percobaan gratis Aspose.TeX?**  
A: Ya, Anda dapat mengunduh percobaan gratis dari [halaman percobaan gratis Aspose.TeX](https://releases.aspose.com/).

**Q: Di mana saya dapat meminta bantuan jika mengalami masalah?**  
A: Kunjungi [forum Aspose.TeX](https://forum.aspose.com/c/tex/47) untuk dukungan komunitas dan bantuan resmi.

## Kesimpulan

Anda kini telah melihat cara **membuat dokumen PDF dari TeX**, mengganti nama pekerjaan, dan menangkap output terminal di dalam arsip ZIP menggunakan Aspose.TeX for Java. Pendekatan ini sangat berguna dalam pipeline build otomatis, di mana menjaga log bersama artefak yang dihasilkan menyederhanakan debugging dan jejak audit. Silakan sesuaikan kode dengan struktur proyek Anda sendiri, atau kembangkan ke format output lain yang didukung oleh Aspose.TeX.

---

**Last Updated:** 2026-08-23  
**Tested With:** Aspose.TeX for Java 24.11 (latest at time of writing)  
**Author:** Aspose  








```java
// Finalize the output ZIP archive
((OutputZipDirectory) options.getOutputWorkingDirectory()).finish();
```

## Tutorial Terkait

- [Buat Arsip ZIP di Java dengan Aspose.TeX – Panduan Lengkap](/tex/java/zip-archives/)
- [Java generate PDF from LaTeX: Advanced Conversion Options with Aspose.TeX](/tex/java/converting-lato-pdf/advanced-pdf-conversion/)
- [How to Load Aspose.TeX License in Java – Step‑by‑Step Guide](/tex/java/managing-licenses/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}