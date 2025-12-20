---
date: 2025-12-20
description: Pelajari cara membuat output XPS pekerjaan TeX menggunakan Aspose.TeX
  untuk .NET, mengelola input/keluaran sistem file, dan menghasilkan dokumen XPS berkualitas
  tinggi.
linktitle: Create TeX Job XPS Output with Filesystems – Aspose.TeX for .NET
second_title: Aspose.TeX .NET API
title: Buat Output XPS Pekerjaan TeX dengan Sistem File – Aspose.TeX untuk .NET
url: /id/net/file-input-output/filesystem-input-xps-output/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Output XPS Pekerjaan TeX dengan Sistem File – Aspose.TeX untuk .NET

## Introduction

Selamat datang! Dalam tutorial ini Anda akan belajar **how to create TeX job XPS output** sambil bekerja dengan input dan output sistem file menggunakan Aspose.TeX untuk .NET. Baik Anda membangun pemroses batch, layanan web, atau utilitas desktop, langkah‑langkah di bawah ini akan memandu Anda mengonfigurasi engine, menunjuk ke file Anda, dan menghasilkan dokumen XPS yang terlihat persis seperti sumber LaTeX asli.

Kami akan membagi proses menjadi langkah‑langkah yang jelas dan bernomor, menjelaskan “mengapa” di balik setiap baris kode, dan memberikan tip praktis yang dapat Anda terapkan segera.

## Quick Answers
- **What does “create tex job xps” mean?** It refers to configuring an Aspose.TeX job that reads TeX files and writes the result as an XPS document.  
- **Do I need a license?** A temporary license is available for testing; a full license is required for production.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Can I change the output format?** Yes – replace `XpsDevice` with another device (PDF, PNG, etc.).  
- **Is console output required?** No – you can use a memory terminal for silent execution.

## What is “create tex job xps”?

Membuat pekerjaan TeX yang menghasilkan XPS berarti menginisialisasi engine Aspose.TeX, memberi tahu engine di mana membaca file sumber, dan mengarahkan halaman yang dirender ke dalam paket XPS. XPS (XML Paper Specification) adalah format tata letak tetap yang mempertahankan tipografi dan grafik vektor, menjadikannya ideal untuk pencetakan atau konversi lebih lanjut.

## Why use Aspose.TeX for XPS output?

- **High fidelity:** Engine mereproduksi tata letak LaTeX secara akurat dalam XPS.  
- **No external dependencies:** Perpustakaan .NET murni, tidak memerlukan instalasi LaTeX native.  
- **Flexible I/O:** Bekerja dengan direktori sistem file, aliran memori, atau penyedia khusus.  
- **Scalable:** Cocok untuk konversi satu file maupun pipeline pemrosesan massal.

## Prerequisites

Sebelum kita mulai, pastikan Anda memiliki hal‑hal berikut:

- **Aspose.TeX for .NET** – unduh versi terbaru dari [Aspose website](https://releases.aspose.com/tex/net/).  
- **.NET development environment** – Visual Studio, Rider, atau VS Code dengan .NET SDK.  
- **Input & output folders** – buat dua direktori di mesin Anda (misalnya `C:\TeX\Input` dan `C:\TeX\Output`).  
- **License (optional for testing)** – Anda dapat memperoleh lisensi sementara dari portal Aspose.

## Import Namespaces

Pertama, bawa namespace yang diperlukan ke dalam ruang lingkup sehingga Anda dapat mengakses pembantu sistem file dan perangkat XPS.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

Namespace ini menyediakan `InputFileSystemDirectory`, `OutputFileSystemDirectory`, dan `XpsDevice`, yang esensial untuk alur kerja **create tex job xps**.

## Step 1: Create Conversion Options

Kita mulai dengan membangun objek `TeXOptions` yang memberi tahu engine untuk menggunakan konfigurasi ObjectTeX (default untuk kebanyakan sumber LaTeX).

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

> **Pro tip:** `ConsoleAppOptions` menetapkan nilai default yang masuk akal untuk aplikasi bergaya console, tetapi Anda dapat menyesuaikan opsi nanti jika diperlukan.

## Step 2: Specify Input and Output Directories

Tunjuk engine ke folder yang telah Anda siapkan sebelumnya. Ganti string placeholder dengan jalur sebenarnya di mesin Anda.

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Sekarang pekerjaan TeX tahu di mana menemukan file `.tex` dan ke mana menaruh file XPS yang dihasilkan.

## Step 3: Choose an Output Terminal

Terminal mengontrol di mana pesan status ditulis. Untuk debugging cepat kita akan tetap menggunakan console, tetapi Anda dapat beralih ke memory terminal untuk eksekusi diam.

```csharp
options.TerminalOut = new OutputConsoleTerminal(); // Default value. Arbitrary assignment.
```

> **Why this matters:** Menggunakan console terminal memberi Anda umpan balik langsung tentang peringatan atau kesalahan kompilasi, yang mempercepat pemecahan masalah.

## Step 4: Run the TeX Job

Buat instance `TeXJob`, beri nama yang mudah diingat, lampirkan `XpsDevice`, dan jalankan.

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

Saat `Run()` selesai, Anda akan menemukan file `hello-world.xps` di direktori output.

## Step 5: Fine‑Tune the Console Output

Menambahkan baris kosong setelah pekerjaan selesai membuat log console lebih mudah dibaca, terutama saat Anda menjalankan banyak pekerjaan secara batch.

```csharp
options.TerminalOut.Writer.WriteLine();
```

## Common Issues and Solutions

| Issue | Cause | Fix |
|-------|-------|-----|
| **XPS file is empty** | Path direktori output tidak tepat atau tidak dapat ditulisi. | Verifikasi path yang diberikan ke `OutputFileSystemDirectory` dan pastikan proses memiliki izin menulis. |
| **Compilation errors** | Sumber LaTeX menggunakan paket yang tidak disertakan dalam ObjectTeX. | Beralih ke konfigurasi mesin TeX penuh (`TeXConfig.FullTeX()`) atau tambahkan file paket yang hilang ke direktori input. |
| **Console hangs** | Terminal menunggu input karena prompt interaktif. | Gunakan `OutputMemoryTerminal` untuk menekan prompt interaktif dalam skrip otomatis. |

## Frequently Asked Questions

**Q1: Can I use a different output format instead of XPS?**  
A1: Yes, Aspose.TeX supports PDF, PNG, SVG, and other formats. Replace `new XpsDevice()` with the appropriate device class (e.g., `new PdfDevice()`).

**Q2: Is a temporary license available for testing purposes?**  
A2: Yes, you can obtain a temporary license for testing from [this link](https://purchase.aspose.com/temporary-license/).

**Q3: Where can I find additional documentation?**  
A3: Refer to the [Aspose.TeX for .NET documentation](https://reference.aspose.com/tex/net/) for detailed information.

**Q4: How can I get community support or ask questions?**  
A4: Visit the [Aspose.TeX forum](https://forum.aspose.com/c/tex/47) for community support and discussions.

**Q5: Are there any sample projects available?**  
A5: Explore the Aspose.TeX GitHub repository for sample projects and code snippets.

## Conclusion

Dengan mengikuti langkah‑langkah di atas, Anda kini tahu cara **create TeX job XPS output** menggunakan Aspose.TeX untuk .NET, mengelola folder input dan output, serta menyempurnakan proses untuk skenario pengembangan maupun produksi. Jangan ragu untuk bereksperimen dengan perangkat output lain, mengintegrasikan logika ini ke dalam alur kerja yang lebih besar, atau mengotomatiskan konversi batch.

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.TeX 24.11 for .NET (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}