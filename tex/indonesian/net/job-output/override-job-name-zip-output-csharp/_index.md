---
title: Ganti Nama Pekerjaan dan Tulis Output Terminal ke Zip (C#)
linktitle: Ganti Nama Pekerjaan dan Tulis Output Terminal ke Zip (C#)
second_title: Aspose.TeX .NET API
description: Pelajari cara mengganti nama pekerjaan dan menulis output terminal ke file ZIP menggunakan Aspose.TeX untuk .NET. Panduan langkah demi langkah dengan contoh C#.
type: docs
weight: 11
url: /id/net/job-output/override-job-name-zip-output-csharp/
---
## Perkenalan

Dalam tutorial ini, kita akan mempelajari cara mengganti nama pekerjaan dan menulis output terminal ke file ZIP menggunakan Aspose.TeX untuk .NET. Aspose.TeX adalah perpustakaan canggih yang memungkinkan pengembang untuk bekerja dengan dokumen TeX dalam aplikasi .NET mereka. Dalam contoh khusus ini, kita akan fokus pada tugas umum – menulis keluaran terminal ke file ZIP dengan kemampuan untuk mengganti nama pekerjaan.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

- Pengetahuan kerja tentang C#
- Aspose.TeX untuk .NET diinstal
- Masukkan arsip ZIP untuk direktori kerja
- Arsip ZIP keluaran untuk keluaran terminal

## Impor Namespace

Sebelum mendalami kodenya, pastikan untuk menyertakan namespace yang diperlukan dalam proyek C# Anda:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Pdf;
using System.IO;
```

Sekarang, mari kita bagi contoh ini menjadi beberapa langkah untuk memandu Anda melalui prosesnya.

## Langkah 1: Buka Aliran ZIP Input dan Output

```csharp
using (Stream inZipStream = File.Open(Path.Combine("Your Input Directory", "zip-in.zip"), FileMode.Open))
using (Stream outZipStream = File.Open(Path.Combine("Your Output Directory", "terminal-out-to-zip.zip"), FileMode.Create))
{
    // Kode untuk langkah 1 ada di sini
}
```

## Langkah 2: Tetapkan Opsi Konversi

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
options.JobName = "terminal-output-to-zip";
options.InputWorkingDirectory = new InputZipDirectory(inZipStream, "in");
options.OutputWorkingDirectory = new OutputZipDirectory(outZipStream);
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## Langkah 3: Tentukan Opsi Penyimpanan

```csharp
options.SaveOptions = new PdfSaveOptions();
```

## Langkah 4: Jalankan Pekerjaan TeX

```csharp
new TeXJob("hello-world", new PdfDevice(), options).Run();
```

## Langkah 5: Selesaikan Arsip ZIP Keluaran

```csharp
((OutputZipDirectory)options.OutputWorkingDirectory).Finish();
```

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara mengganti nama pekerjaan dan menulis output terminal ke file ZIP menggunakan Aspose.TeX untuk .NET. Teknik ini bisa sangat berguna ketika menangani dokumen TeX di aplikasi C# Anda.

## FAQ

### Q1: Bisakah saya menggunakan Aspose.TeX untuk .NET dengan bahasa .NET lain seperti VB.NET?

A1: Ya, Aspose.TeX untuk .NET kompatibel dengan semua bahasa .NET.

### Q2: Di mana saya dapat menemukan dokumentasi lebih lanjut untuk Aspose.TeX untuk .NET?

 A2: Kunjungi[dokumentasi](https://reference.aspose.com/tex/net/) untuk informasi rinci.

### Q3: Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.TeX?

 A3: Dapatkan a[izin sementara](https://purchase.aspose.com/temporary-license/) untuk tujuan pengujian.

### Q4: Apakah ada forum komunitas untuk dukungan Aspose.TeX?

 A4: Ya, bergabunglah[Forum Aspose.TeX](https://forum.aspose.com/c/tex/47) untuk dukungan masyarakat.

### Q5: Di mana saya dapat membeli Aspose.TeX untuk .NET?

 A5: Anda dapat membeli Aspose.TeX[Di Sini](https://purchase.aspose.com/buy).