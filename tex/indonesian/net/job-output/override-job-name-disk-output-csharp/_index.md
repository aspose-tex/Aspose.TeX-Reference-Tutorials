---
date: 2025-12-21
description: Pelajari cara menangkap output konsol C# menggunakan Aspose.TeX, mengganti
  nama pekerjaan, mengatur direktori input TeX, dan menulis output terminal ke sebuah
  file.
linktitle: Capture Console Output C# – Override Job Name & Write Output to Disk
second_title: Aspose.TeX .NET API
title: Tangkap Output Konsol C# – Ganti Nama Pekerjaan & Tulis Output ke Disk
url: /id/net/job-output/override-job-name-disk-output-csharp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menangkap Output Konsol C# – Menimpa Nama Pekerjaan dan Menulis Output Terminal ke Disk (C#)

## Pendahuluan

Dalam panduan langkah‑demi‑langkah ini Anda akan belajar **cara menangkap output konsol C#** saat bekerja dengan Aspose.TeX untuk .NET. Dengan menimpa nama pekerjaan dan mengarahkan output terminal ke sebuah file, Anda memperoleh kontrol penuh atas pipeline pemrosesan TeX—sempurna untuk build otomatis, skenario CI/CD, atau situasi apa pun di mana Anda perlu mencatat aliran konsol untuk analisis selanjutnya.

## Jawaban Cepat
- **Apa arti “capture console output C#”?** Itu mengarahkan aliran terminal standar yang dihasilkan oleh Aspose.TeX ke file yang Anda tentukan.  
- **Mengapa menimpa nama pekerjaan?** Menimpa memastikan nama file yang dapat diprediksi dan menghindari bentrok saat menjalankan beberapa pekerjaan.  
- **Kelas Aspose.TeX mana yang menulis output?** `OutputFileTerminal` (digunakan melalui `options.TerminalOut`).  
- **Bisakah saya mengatur folder input TeX khusus?** Ya—gunakan `options.InputWorkingDirectory` untuk **mengatur direktori input TeX**.  
- **Apakah pendekatan ini kompatibel dengan .NET Core?** Tentu saja; API yang sama bekerja pada .NET Framework dan .NET Core.

## Apa itu “capture console output C#” dalam konteks Aspose.TeX?

Menangkap output konsol berarti mengambil semua yang biasanya muncul di jendela terminal (pesan log, peringatan, detail kompilasi) dan menuliskannya ke file yang persisten. Ini sangat berguna untuk men-debug proyek TeX besar atau mengintegrasikan pemrosesan TeX ke dalam alur kerja otomatis.

## Mengapa menimpa nama pekerjaan dan menulis output terminal ke file?

- **Nama file yang dapat diprediksi:** Menimpa nama pekerjaan memungkinkan Anda menentukan nama dasar untuk file yang dihasilkan, memudahkan penulisan skrip pasca‑pemrosesan.  
- **Auditabilitas:** Menyimpan log terminal memberi Anda jejak audit lengkap dari proses kompilasi TeX.  
- **Eksekusi paralel:** Saat menjalankan beberapa pekerjaan secara bersamaan, nama pekerjaan yang unik mencegah bentrok file.  

## Prasyarat

- **Pustaka Aspose.TeX untuk .NET:** Pastikan Anda telah menginstal pustaka Aspose.TeX untuk .NET. Anda dapat mengunduhnya dari [situs web Aspose.TeX](https://releases.aspose.com/tex/net/).
- **Lingkungan Pengembangan .NET:** Miliki lingkungan pengembangan .NET yang berfungsi, termasuk lingkungan pengembangan terintegrasi (IDE) seperti Visual Studio.
- **Pengetahuan Dasar C#:** Familiaritas dengan dasar-dasar bahasa pemrograman C#.
- **Direktori Input dan Output:** Siapkan direktori input dan output untuk file TeX Anda.

## Impor Namespace

Dalam kode C# Anda, pastikan untuk menyertakan namespace yang diperlukan untuk mengakses fungsionalitas Aspose.TeX:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

## Langkah 1: Buat Opsi Konversi

Pertama, kita membuat instance `TeXOptions` yang memberi tahu Aspose.TeX bahwa kita menjalankan dalam skenario aplikasi konsol.

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

Buat `TeXOptions` dengan `ConsoleAppOptions`, menentukan `ObjectTeX` sebagai `TeXConfig`.

## Langkah 2: Tentukan Nama Pekerjaan (Timpa Default)

Menimpa nama pekerjaan memberi kita kontrol atas nama dasar semua artefak yang dihasilkan.

```csharp
options.JobName = "overridden-job-name";
```

Tentukan nama pekerjaan untuk menimpa nama default.

## Langkah 3: Atur Direktori Input TeX

Beritahu Aspose.TeX di mana menemukan file sumber `.tex` Anda. Ini adalah langkah **mengatur direktori input tex**.

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

Atur direktori kerja input untuk file TeX Anda.

## Langkah 4: Tentukan Direktori Kerja Output

Tentukan di mana file yang diproses dan log konsol yang ditangkap akan disimpan.

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Tentukan direktori kerja output untuk menyimpan file TeX yang diproses.

## Langkah 5: Tulis Output Terminal ke File

Sekarang kami mengarahkan aliran konsol ke file fisik di direktori output. Ini memenuhi persyaratan **menulis output terminal ke file**.

```csharp
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

Konfigurasikan output terminal agar ditulis ke file di direktori output.

## Langkah 6: Jalankan Pekerjaan

Akhirnya, kami membuat `TeXJob` dengan nama pekerjaan yang ditimpa, perangkat output XPS, dan opsi yang telah kami konfigurasikan. Menjalankan pekerjaan akan menghasilkan file XPS dan menangkap log konsol.

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

Buat `TeXJob`, menentukan nama pekerjaan, perangkat output (`XpsDevice`), dan opsi. Akhirnya, jalankan pekerjaan.

## Masalah Umum & Pemecahan Masalah

| Gejala | Penyebab Kemungkinan | Solusi |
|---------|----------------------|--------|
| Tidak ada file output yang dibuat | Jalur direktori output tidak benar atau tidak memiliki izin menulis | Verifikasi `options.OutputWorkingDirectory` mengarah ke folder yang valid dan proses memiliki akses menulis. |
| Log terminal kosong | `TerminalOut` tidak disetel atau ditimpa kemudian | Pastikan `options.TerminalOut = new OutputFileTerminal(...);` dijalankan sebelum `job.Run();`. |
| Pekerjaan gagal dengan “file tidak ditemukan” | Direktori input tidak diatur dengan benar | Periksa kembali jalur yang diberikan ke `InputFileSystemDirectory` dan pastikan file `.tex` ada di sana. |

## Pertanyaan yang Sering Diajukan

### Q1: Bisakah saya menggunakan Aspose.TeX untuk .NET dengan pustaka .NET lainnya?

A1: Ya, Aspose.TeX untuk .NET dapat diintegrasikan dengan pustaka .NET lainnya secara mulus.

### Q2: Apakah tersedia versi percobaan gratis untuk Aspose.TeX untuk .NET?

A2: Ya, Anda dapat mengunduh versi percobaan gratis [di sini](https://releases.aspose.com/).

### Q3: Bagaimana saya dapat mendapatkan dukungan untuk Aspose.TeX untuk .NET?

A3: Kunjungi [forum Aspose.TeX](https://forum.aspose.com/c/tex/47) untuk mendapatkan dukungan komunitas dan bantuan.

### Q4: Apakah lisensi sementara tersedia untuk Aspose.TeX untuk .NET?

A4: Ya, Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

### Q5: Di mana saya dapat menemukan dokumentasi untuk Aspose.TeX untuk .NET?

A5: Dokumentasi tersedia [di sini](https://reference.aspose.com/tex/net/).

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara **menangkap output konsol C#** dengan menimpa nama pekerjaan, mengatur direktori input TeX, dan menulis output terminal ke file menggunakan Aspose.TeX untuk .NET. Teknik ini mempermudah pencatatan, meningkatkan keterlacakan, dan membuat pipeline pemrosesan TeX otomatis lebih kuat.

---

**Terakhir Diperbarui:** 2025-12-21  
**Diuji Dengan:** Aspose.TeX 24.11 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}