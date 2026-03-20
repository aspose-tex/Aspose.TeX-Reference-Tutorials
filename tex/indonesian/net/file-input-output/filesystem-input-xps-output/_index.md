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

## Perkenalan

Selamat datang! Dalam tutorial ini Anda akan belajar **cara membuat output TeX job XPS** sambil bekerja dengan file sistem input dan output menggunakan Aspose.TeX untuk .NET. Baik Anda membangun pemroses batch, layanan web, atau utilitas desktop, langkah‑langkah di bawah ini akan menyiapkan Anda mengonfigurasi mesin, menunjuk ke file Anda, dan menghasilkan dokumen XPS yang terlihat persisten seperti sumber LaTeX asli.

Kami akan membagi proses menjadi langkah‑langkah yang jelas dan bernomor, menjelaskan “mengapa” di balik setiap baris kode, dan memberikan tip praktis yang dapat Anda terapkan segera.

## Jawaban Cepat
- **Apa yang dimaksud dengan “membuat tex job xps”?** Ini merujuk pada konfigurasi tugas Aspose.TeX yang membaca file TeX dan menulis hasilnya sebagai dokumen XPS.
- **Apakah saya memerlukan lisensi?** Lisensi sementara tersedia untuk pengujian; lisensi penuh diperlukan untuk produksi.
- **Versi .NET manakah yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Dapatkah saya mengubah format keluaran?** Ya – ganti `XpsDevice` dengan perangkat lain (PDF, PNG, dll.).
- **Apakah output konsol diperlukan?** Tidak – Anda dapat menggunakan terminal memori untuk eksekusi senyap.

## Apa itu “buat tex job xps”?

Membuat pekerjaan TeX yang menghasilkan XPS berarti menginisialisasi mesin Aspose.TeX, memberi tahu mesin di mana membaca file sumber, dan mengarahkan halaman yang dirender ke dalam paket XPS. XPS (Spesifikasi Kertas XML) adalah format tata letak tetap yang mempertahankan tipografi dan grafik vektor, menjadikannya ideal untuk pencetakan atau konversi lebih lanjut.

## Mengapa menggunakan Aspose.TeX untuk keluaran XPS?

- **Ketepatan tinggi:** Mesin mereproduksi tata letak LaTeX secara akurat dalam XPS.
- **Tidak ada ketergantungan eksternal:** Perpustakaan .NET murni, tidak memerlukan instalasi LaTeX asli.
- **I/O Fleksibel:** Bekerja dengan file sistem direktori, aliran memori, atau penyedia khusus.
- **Scalable:** Cocok untuk konversi satu file maupun pipeline pemrosesan massal.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal‑hal berikut:

- **Aspose.TeX for .NET** – unduh versi terbaru dari [situs web Aspose](https://releases.aspose.com/tex/net/).
- **.NET development environment** – Visual Studio, Rider, atau VS Code dengan .NET SDK.
- **Input & output folders** – buat dua direktori di mesin Anda (misalnya `C:\TeX\Input` dan `C:\TeX\Output`).
- **Lisensi (opsional untuk pengujian)** – Anda dapat memperoleh lisensi sementara dari portal Aspose.

## Impor Namespace

Pertama, bawa namespace yang diperlukan ke dalam ruang lingkup sehingga Anda dapat mengakses pembantu sistem file dan perangkat XPS.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

Namespace ini menyediakan `InputFileSystemDirectory`, `OutputFileSystemDirectory`, dan `XpsDevice`, yang esensial untuk alur kerja **create tex job xps**.

## Langkah 1: Buat Opsi Konversi

Kita mulai dengan membangun objek `TeXOptions` yang memberi tahu engine untuk menggunakan konfigurasi ObjectTeX (default untuk kebanyakan sumber LaTeX).

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

> **Pro tip:** `ConsoleAppOptions` menetapkan nilai default yang masuk akal untuk aplikasi bergaya console, tetapi Anda dapat menyesuaikan opsi nanti jika diperlukan.

## Langkah 2: Tentukan Direktori Input dan Output

Tunjuk engine ke folder yang telah Anda siapkan sebelumnya. Ganti string placeholder dengan jalur sebenarnya di mesin Anda.

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Sekarang pekerjaan TeX tahu di mana menemukan file `.tex` dan ke mana menaruh file XPS yang dihasilkan.

## Langkah 3: Pilih Terminal Output

Terminal mengontrol di mana pesan status ditulis. Untuk debugging cepat kita akan tetap menggunakan console, tetapi Anda dapat beralih ke memory terminal untuk eksekusi diam.

```csharp
options.TerminalOut = new OutputConsoleTerminal(); // Default value. Arbitrary assignment.
```

> **Why this matters:** Menggunakan console terminal memberi Anda umpan balik langsung tentang peringatan atau kesalahan kompilasi, yang mempercepat pemecahan masalah.

## Langkah 4: Jalankan Job TeX

Buat instance `TeXJob`, beri nama yang mudah diingat, lampirkan `XpsDevice`, dan jalankan.

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

Saat `Run()` selesai, Anda akan menemukan file `hello-world.xps` di direktori output.

## Langkah 5: Sempurnakan Output Konsol

Menambahkan baris kosong setelah pekerjaan selesai membuat log console lebih mudah dibaca, terutama saat Anda menjalankan banyak pekerjaan secara batch.

```csharp
options.TerminalOut.Writer.WriteLine();
```

## Masalah Umum dan Solusinya

| Edisi | Penyebab | Perbaiki |
|-------|-------|-----|
| **File XPS kosong** | Output direktori jalur tidak tepat atau tidak dapat ditulisi. | Jalur verifikasi yang diberikan ke `OutputFileSystemDirectory` dan pastikan proses memiliki izin menulis. |
| **Kesalahan kompilasi** | Sumber LaTeX menggunakan paket yang tidak disertakan dalam ObjectTeX. | Beralih ke konfigurasi mesin TeX penuh (`TeXConfig.FullTeX()`) atau tambahkan file paket yang hilang ke input direktori. |
| **Konsol hang** | Terminal menunggu input karena interaktif. | Gunakan `OutputMemoryTerminal` untuk menekan prompt interaktif dalam skrip otomatis. |

## Pertanyaan yang Sering Diajukan

**Q1: ​​Bisakah saya menggunakan format output lain selain XPS?**
A1: Ya, Aspose.TeX mendukung PDF, PNG, SVG, dan format lainnya. Ganti `new XpsDevice()` dengan kelas perangkat yang sesuai (misalnya, `new PdfDevice()`).

**T2: Apakah lisensi sementara tersedia untuk tujuan pengujian?**
J2: Ya, Anda dapat memperoleh lisensi sementara untuk pengujian dari [tautan ini](https://purchase.aspose.com/temporary-license/).

**T3: Di mana saya dapat menemukan dokumentasi tambahan?**
J3: Lihat [dokumentasi Aspose.TeX untuk .NET](https://reference.aspose.com/tex/net/) untuk informasi detail.

**T4: Bagaimana saya bisa mendapatkan dukungan komunitas atau mengajukan pertanyaan?**
J4: Kunjungi [forum Aspose.TeX](https://forum.aspose.com/c/tex/47) untuk dukungan dan diskusi komunitas.

**T5: Apakah ada proyek contoh yang tersedia?**
J5: Jelajahi repositori GitHub Aspose.TeX untuk proyek contoh dan cuplikan kode.

## Kesimpulan

Dengan mengikuti langkah‑langkah di atas, Anda kini mengetahui cara **membuat output TeX job XPS** menggunakan Aspose.TeX untuk .NET, mengelola folder input dan output, serta menyempurnakan proses untuk skenario pengembangan dan produksi. Jangan ragu untuk bereksperimen dengan perangkat output lain, mengintegrasikan logika ini ke dalam alur kerja yang lebih besar, atau mengotomatiskan konversi batch.

---

**Terakhir Diperbarui:** 20-12-2025
**Diuji Dengan:** Aspose.TeX 24.11 untuk .NET (terbaru pada saat penulisan)
**Penulis:** Beranggapan  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}