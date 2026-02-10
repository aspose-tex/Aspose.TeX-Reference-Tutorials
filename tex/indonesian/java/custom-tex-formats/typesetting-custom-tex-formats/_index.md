---
date: 2026-02-10
description: Pelajari cara membuat format TeX khusus dan cara menyusun TeX Java menggunakan
  Aspose.TeX untuk Java, termasuk penyiapan langkah demi langkah, penanganan format
  khusus, dan memperoleh lisensi sementara.
linktitle: How to Typeset TeX with Custom Formats in Java
second_title: Aspose.TeX Java API
title: Cara Membuat Format TeX Kustom dan Menyusun TeX di Java
url: /id/java/custom-tex-formats/typesetting-custom-tex-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membuat Format TeX Kustom dan Menyusun TeX di Java

## Introduction

Jika Anda perlu **membuat format tex kustom** dan menyusun TeX di dalam aplikasi Java, Aspose.TeX menyediakan cara yang bersih, berperforma tinggi untuk bekerja dengan file format TeX kustom. Dalam tutorial ini kami akan membahas semua yang Anda perlukan—from menyiapkan lingkungan hingga menjalankan pekerjaan TeX yang menggunakan format Anda sendiri. Baik Anda sedang membangun alat penerbitan ilmiah atau generator laporan kustom, langkah‑langkah di bawah ini akan membantu Anda memulai dengan cepat.

## Quick Answers
- **Perpustakaan apa yang saya butuhkan?** Aspose.TeX for Java  
- **Apakah saya dapat menggunakan format TeX kustom?** Ya – cukup arahkan `FormatProvider` ke file Anda.  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Lisensi sementara aspose cukup untuk pengujian; lisensi penuh diperlukan untuk produksi.  
- **Versi Java mana yang didukung?** JDK 8 atau lebih tinggi.  
- **Format output apa yang dihasilkan contoh ini?** XPS (Anda dapat beralih ke PDF, PNG, dll.).

## What is a Custom TeX Format?
Format TeX kustom adalah sekumpulan makro dan primitif yang telah dikompilasi sebelumnya yang menyesuaikan mesin TeX dengan gaya dokumen spesifik Anda. Dengan menyediakan file `.fmt` milik Anda, Anda dapat mengontrol font, aturan tata letak, dan definisi perintah tanpa harus memodifikasi sumber TeX setiap kali.

## Why Use Aspose.TeX for Java?
- **Pure Java** – Tanpa binari native, mudah disematkan dalam proyek berbasis JVM apa pun.  
- **Fidelity tinggi** – Menghasilkan output yang cocok dengan rendering gaya LaTeX.  
- **Dapat diperluas** – Mendukung format kustom, banyak perangkat output, dan pemrosesan batch.  
- **Fleksibilitas lisensi** – Mulai dengan lisensi sementara aspose, kemudian tingkatkan saat Anda meluncurkan.

## Prerequisites

Sebelum Anda memulai, pastikan Anda memiliki:

1. **Java Development Kit (JDK)** – JDK 8 atau yang lebih baru terpasang. Unduh dari [Java website](https://www.oracle.com/java/technologies/javase-downloads.html) jika belum.  
2. **Aspose.TeX library for Java** – Dapatkan JAR terbaru dari [Aspose.TeX for Java download page](https://releases.aspose.com/tex/java/).  
3. **Your custom TeX format file** – Letakkan file `.fmt` yang telah dikompilasi (misalnya `customtex.fmt`) di folder yang akan menjadi direktori output.  

> **Tip pro:** Jika Anda sedang mengevaluasi produk, minta *lisensi sementara aspose* dari portal Aspose; ini menghapus watermark evaluasi untuk periode terbatas.

## Import Packages

First, add the required imports to your Java project. These classes give you access to the format provider, job configuration, and rendering device.

```java
package com.aspose.tex.TypesetWithCustomTeXFormat;

import java.io.ByteArrayInputStream;
import java.io.IOException;

import com.aspose.tex.FormatProvider;
import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

## Step‑by‑Step Guide

### Step 1: Create a Format Provider

`FormatProvider` menunjuk ke direktori yang berisi file format TeX kustom Anda. Ganti `"Your Output Directory"` dengan jalur sebenarnya tempat `customtex.fmt` berada.

```java
final FormatProvider formatProvider = new FormatProvider(
        new InputFileSystemDirectory("Your Output Directory"), "customtex");
```

### Step 2: Set Conversion Options

Konfigurasikan pekerjaan untuk menggunakan mesin ObjectTeX (mesin yang memahami format kustom). Di sini kami juga menetapkan nama pekerjaan dan menentukan direktori kerja input/output.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX(formatProvider));
options.setJobName("typeset-with-custom-format");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### Step 3: Run the TeX Job

Buat instance `TeXJob`, berikan potongan TeX sederhana, dan instruksikan untuk merender hasilnya dengan `XpsDevice`. Potongan tersebut diakhiri dengan `\end` untuk menutup dokumen.

```java
new TeXJob(new ByteArrayInputStream(
        "Congratulations! You have successfully typeset this text with your own TeX format!\\end".getBytes("ASCII")),
        new XpsDevice(), options).run();
```

### Step 4: Finalize Output

Setelah pekerjaan selesai, tambahkan baris baru ke output terminal agar konsol tetap rapi.

```java
options.getTerminalOut().getWriter().newLine();
```

### Step 5: Close the Format Provider

Setelah selesai, tutup provider untuk melepaskan handle file dan membebaskan sumber daya.

```java
formatProvider.close();
```

## Common Use Cases

- **Pembuatan makalah ilmiah otomatis** – Gunakan format yang telah dikompilasi sebelumnya yang menyertakan makro khusus jurnal.  
- **Pembuatan laporan dinamis** – Hasilkan faktur atau sertifikat secara langsung tanpa harus membangun ulang sumber LaTeX setiap kali.  
- **Pemrosesan batch koleksi dokumen besar** – Muat format kustom sekali dan gunakan kembali untuk ratusan file, secara signifikan mengurangi waktu pemrosesan.

## Common Issues and Solutions

| Issue | Cause | Fix |
|-------|-------|-----|
| **“File format tidak ditemukan”** | Path yang salah di `FormatProvider` | Verifikasi bahwa direktori dan nama file (`customtex.fmt`) sudah benar dan dapat diakses. |
| **Kesalahan enkoding** | Karakter non‑ASCII dalam string TeX | Gunakan enkoding UTF‑8 (`"UTF-8"` alih-alih `"ASCII"`). |
| **Output tidak dihasilkan** | Direktori output tidak memiliki izin menulis | Pastikan proses Java memiliki akses menulis ke `"Your Output Directory"`. |
| **Watermark lisensi** | Menggunakan hanya lisensi evaluasi | Terapkan *lisensi sementara aspose* untuk pengujian atau beli lisensi penuh untuk produksi. |

**Sumber Daya Terkait:** [Aspose.TeX API Reference](https://docs.aspose.com/tex/java/) | [Download Free Trial](https://releases.aspose.com/tex/java/)

## Frequently Asked Questions

**T: Apakah saya dapat menggunakan Aspose.TeX bersama dengan perpustakaan Java lain?**  
J: Tentu saja. API ini pure Java dan dapat bekerja bersama perpustakaan seperti Apache PDFBox, iText, atau Spring Boot.

**T: Di mana saya dapat mendapatkan lisensi sementara aspose untuk evaluasi?**  
J: Minta satu dari [Aspose temporary license page](https://purchase.aspose.com/temporary-license/). Ini menghapus watermark evaluasi hingga 30 hari.

**T: Apakah Aspose.TeX mendukung format output selain XPS?**  
J: Ya. Anda dapat mengganti `new XpsDevice()` dengan `new PdfDevice()`, `new PngDevice()`, dll., tergantung kebutuhan Anda.

**T: Bagaimana cara men-debug pekerjaan TeX yang gagal?**  
J: Aktifkan logging verbose dengan memanggil `options.setLogLevel(LogLevel.DEBUG);` dan periksa output konsol untuk pesan error terperinci.

**T: Apakah ada trial gratis yang tersedia?**  
J: Ya – unduh binary trial dari [Aspose.TeX download page](https://releases.aspose.com/tex/java/).

**T: Dapatkah saya membuat beberapa format kustom dalam aplikasi yang sama?**  
J: Ya. Instansiasi `FormatProvider` terpisah untuk setiap file `.fmt` dan berikan provider yang sesuai ke `TeXConfig.objectTeX()`.

## Conclusion

Anda sekarang tahu **cara membuat format tex kustom** dan **cara menyusun tex di Java** dalam aplikasi Java menggunakan Aspose.TeX. Dengan mengikuti langkah‑langkah di atas, Anda dapat mengintegrasikan penyusunan berkualitas tinggi ke dalam alur kerja berbasis Java apa pun, bereksperimen dengan file format Anda sendiri, dan beralih dari prototipe ke produksi dengan lisensi yang tepat.

---

**Last Updated:** 2026-02-10  
**Tested With:** Aspose.TeX for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}