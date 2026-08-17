---
date: 2026-03-26
description: Pelajari cara membuat XPS dari TeX menggunakan Aspose.TeX untuk .NET,
  mengelola input/keluaran sistem file, dan menghasilkan dokumen XPS berkualitas tinggi.
linktitle: Create XPS from TeX with Filesystems – Aspose.TeX for .NET
second_title: Aspose.TeX .NET API
title: Buat XPS dari TeX dengan Sistem Berkas – Aspose.TeX untuk .NET
url: /id/net/file-input-output/filesystem-input-xps-output/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat XPS dari TeX dengan Filesystem – Aspose.TeX untuk .NET

## Pendahuluan

Selamat datang! Dalam tutorial ini Anda akan belajar **cara membuat XPS dari TeX** sambil bekerja dengan input dan output filesystem menggunakan Aspose.TeX untuk .NET. Baik Anda membangun pemroses batch, layanan web, atau utilitas desktop, langkah‑langkah di bawah ini akan memandu Anda mengkonfigurasi engine, menunjuk ke file Anda, dan menghasilkan dokumen XPS yang tampak persis seperti sumber LaTeX asli.  
Kami akan membagi proses menjadi langkah‑langkah berurutan yang jelas, menjelaskan “mengapa” di balik setiap baris kode, dan memberi Anda tip praktis yang dapat langsung diterapkan.

## Jawaban Cepat
- **Apa arti “create XPS from TeX”?** Ini merujuk pada mengkonfigurasi pekerjaan Aspose.TeX yang membaca file TeX dan menulis hasilnya sebagai dokumen XPS.  
- **Apakah saya memerlukan lisensi?** Lisensi sementara tersedia untuk pengujian; lisensi penuh diperlukan untuk produksi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Bisakah saya mengubah format output?** Ya – ganti `XpsDevice` dengan perangkat lain (PDF, PNG, dll.).  
- **Apakah output konsol diperlukan?** Tidak – Anda dapat menggunakan memory terminal untuk eksekusi diam.

## Cara membuat XPS dari TeX menggunakan Aspose.TeX

Membuat pekerjaan TeX yang menghasilkan XPS berarti menginisialisasi engine Aspose.TeX, memberi tahu di mana membaca file sumber, dan mengarahkan halaman yang dirender ke dalam paket XPS. XPS (XML Paper Specification) adalah format tata letak tetap yang mempertahankan tipografi dan grafik vektor, menjadikannya ideal untuk pencetakan atau konversi lebih lanjut.

## Apa itu “create tex job xps”?

Membuat pekerjaan TeX yang menghasilkan XPS berarti menginisialisasi engine Aspose.TeX, memberi tahu di mana membaca file sumber, dan mengarahkan halaman yang dirender ke dalam paket XPS. XPS (XML Paper Specification) adalah format tata letak tetap yang mempertahankan tipografi dan grafik vektor, menjadikannya ideal untuk pencetakan atau konversi lebih lanjut.

## Mengapa menggunakan Aspose.TeX untuk output XPS?

- **Fidelity tinggi:** Engine mereproduksi tata letak LaTeX secara akurat dalam XPS.  
- **Tanpa ketergantungan eksternal:** Perpustakaan .NET murni, tidak memerlukan instalasi LaTeX native.  
- **I/O fleksibel:** Bekerja dengan direktori filesystem, memory stream, atau provider khusus.  
- **Skalabel:** Cocok untuk konversi satu file atau pipeline pemrosesan massal.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal‑hal berikut:

- **Aspose.TeX untuk .NET** – unduh versi terbaru dari [situs Aspose](https://releases.aspose.com/tex/net/).  
- **Lingkungan pengembangan .NET** – Visual Studio, Rider, atau VS Code dengan .NET SDK.  
- **Folder input & output** – buat dua direktori di mesin Anda (misalnya `C:\TeX\Input` dan `C:\TeX\Output`).  
- **Lisensi (opsional untuk pengujian)** – Anda dapat memperoleh lisensi sementara dari portal Aspose.

## Impor Namespace

Pertama, masukkan namespace yang diperlukan ke dalam ruang lingkup sehingga Anda dapat mengakses helper filesystem dan perangkat XPS.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

Namespace ini menyediakan `InputFileSystemDirectory`, `OutputFileSystemDirectory`, dan `XpsDevice`, yang penting untuk alur kerja **create XPS from TeX**.

## Langkah 1: Buat Opsi Konversi

Kami mulai dengan membuat objek `TeXOptions` yang memberi tahu engine untuk menggunakan konfigurasi ObjectTeX (default untuk kebanyakan sumber LaTeX).

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

> **Tip pro:** `ConsoleAppOptions` menetapkan nilai default yang masuk akal untuk aplikasi bergaya konsol, tetapi Anda dapat menyesuaikan opsi nanti jika diperlukan.

## Langkah 2: Tentukan Direktori Input dan Output

Arahkan engine ke folder yang telah Anda siapkan sebelumnya. Ganti string placeholder dengan jalur sebenarnya di mesin Anda.

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Sekarang pekerjaan TeX tahu di mana menemukan file `.tex` dan ke mana menaruh file XPS yang dihasilkan.

## Langkah 3: Pilih Terminal Output

Terminal mengontrol ke mana pesan status dituliskan. Untuk debugging cepat kami akan tetap menggunakan konsol, tetapi Anda dapat beralih ke memory terminal untuk eksekusi diam.

```csharp
options.TerminalOut = new OutputConsoleTerminal(); // Default value. Arbitrary assignment.
```

> **Mengapa ini penting:** Menggunakan terminal konsol memberi Anda umpan balik langsung tentang peringatan atau kesalahan kompilasi, yang mempercepat pemecahan masalah.

## Langkah 4: Jalankan Pekerjaan TeX

Buat instance `TeXJob`, beri nama yang mudah dipahami, lampirkan `XpsDevice`, dan jalankan.

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

Setelah `Run()` selesai, Anda akan menemukan file `hello-world.xps` di direktori output.

## Langkah 5: Sesuaikan Output Konsol

Menambahkan baris kosong setelah pekerjaan selesai membuat log konsol lebih mudah dibaca, terutama saat Anda menjalankan beberapa pekerjaan dalam batch.

```csharp
options.TerminalOut.Writer.WriteLine();
```

## Kasus Penggunaan Umum

| Skenario | Mengapa XPS? | Bagaimana potongan kode membantu |
|----------|--------------|-----------------------------------|
| **Konversi batch makalah akademik** | Mempertahankan tata letak persis untuk pencetakan arsip. | Pendekatan berbasis filesystem memungkinkan Anda menunjuk ke folder berisi file `.tex` dan menghasilkan sekumpulan file XPS yang cocok. |
| **Layanan web yang merender LaTeX secara langsung** | XPS dapat langsung di‑stream ke browser yang mendukungnya. | Dengan mengganti `XpsDevice` dengan memory stream Anda dapat mengembalikan dokumen tanpa menyentuh disk. |
| **Alat penerbitan desktop** | Membutuhkan pratinjau tata letak tetap sebelum konversi ke PDF. | Pekerjaan yang sama dapat dihubungkan ke perangkat PDF kemudian untuk distribusi akhir. |

## Masalah Umum dan Solusinya

| Masalah | Penyebab | Solusi |
|---------|----------|--------|
| **File XPS kosong** | Jalur direktori output tidak benar atau tidak dapat ditulisi. | Verifikasi jalur yang diberikan ke `OutputFileSystemDirectory` dan pastikan proses memiliki izin menulis. |
| **Kesalahan kompilasi** | Sumber LaTeX menggunakan paket yang tidak disertakan dalam ObjectTeX. | Beralih ke konfigurasi mesin TeX penuh (`TeXConfig.FullTeX()`) atau tambahkan file paket yang hilang ke direktori input. |
| **Konsol hang** | Terminal menunggu input karena prompt interaktif. | Gunakan `OutputMemoryTerminal` untuk menekan prompt interaktif dalam skrip otomatis. |

## Pertanyaan yang Sering Diajukan

**Q1: Bisakah saya menggunakan format output lain selain XPS?**  
A1: Ya, Aspose.TeX mendukung PDF, PNG, SVG, dan format lainnya. Ganti `new XpsDevice()` dengan kelas perangkat yang sesuai (misalnya `new PdfDevice()`).

**Q2: Apakah lisensi sementara tersedia untuk tujuan pengujian?**  
A2: Ya, Anda dapat memperoleh lisensi sementara untuk pengujian dari [tautan ini](https://purchase.aspose.com/temporary-license/).

**Q3: Di mana saya dapat menemukan dokumentasi tambahan?**  
A3: Lihat [dokumentasi Aspose.TeX untuk .NET](https://reference.aspose.com/tex/net/) untuk informasi detail.

**Q4: Bagaimana saya dapat mendapatkan dukungan komunitas atau mengajukan pertanyaan?**  
A4: Kunjungi [forum Aspose.TeX](https://forum.aspose.com/c/tex/47) untuk dukungan komunitas dan diskusi.

**Q5: Apakah ada proyek contoh yang tersedia?**  
A5: Jelajahi repositori Aspose.TeX di GitHub untuk proyek contoh dan potongan kode.

## Kesimpulan

Dengan mengikuti langkah‑langkah di atas, Anda kini tahu cara **membuat XPS dari TeX** menggunakan Aspose.TeX untuk .NET, mengelola folder input dan output Anda, serta menyesuaikan proses untuk skenario pengembangan dan produksi. Jangan ragu bereksperimen dengan perangkat output lain, mengintegrasikan logika ini ke dalam alur kerja yang lebih besar, atau mengotomatisasi konversi batch.

---

**Terakhir Diperbarui:** 2026-03-26  
**Diuji Dengan:** Aspose.TeX 24.11 for .NET (latest at time of writing)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}