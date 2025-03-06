---
title: Ganti Nama Pekerjaan dan Tulis Output Terminal ke Disk (C#)
linktitle: Ganti Nama Pekerjaan dan Tulis Output Terminal ke Disk (C#)
second_title: Aspose.TeX .NET API
description: Jelajahi cara menggunakan Aspose.TeX untuk .NET untuk mengganti nama pekerjaan dan menangkap output terminal. Ikuti panduan komprehensif kami untuk pengelolaan file TeX yang lancar.
weight: 10
url: /id/net/job-output/override-job-name-disk-output-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ganti Nama Pekerjaan dan Tulis Output Terminal ke Disk (C#)

## Perkenalan

Selamat datang di panduan langkah demi langkah tentang penggunaan Aspose.TeX untuk .NET untuk mengganti nama pekerjaan dan menulis keluaran terminal ke disk dalam bahasa pemrograman C#. Aspose.TeX untuk .NET adalah perpustakaan canggih yang memungkinkan Anda bekerja dengan lancar dengan file TeX, dan dalam tutorial ini, kita akan fokus pada tugas tertentu: mengganti nama pekerjaan dan menangkap keluaran terminal.

## Prasyarat

Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:

-  Aspose.TeX untuk .NET Library: Pastikan Anda telah menginstal perpustakaan Aspose.TeX untuk .NET. Anda dapat mengunduhnya dari[Situs web Aspose.TeX](https://releases.aspose.com/tex/net/).

- Lingkungan Pengembangan .NET: Memiliki lingkungan pengembangan .NET yang berfungsi, termasuk lingkungan pengembangan terintegrasi (IDE) seperti Visual Studio.

- Pengetahuan Dasar C#: Biasakan diri Anda dengan dasar-dasar bahasa pemrograman C#.

- Direktori Input dan Output: Siapkan direktori input dan output untuk file TeX Anda.

## Impor Namespace

Dalam kode C# Anda, pastikan untuk menyertakan namespace yang diperlukan untuk mengakses fungsionalitas Aspose.TeX:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

## Langkah 1: Buat Opsi Konversi

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

Buat TeXOptions dengan ConsoleAppOptions, tentukan ObjectTeX sebagai TeXConfig.

## Langkah 2: Tentukan Nama Pekerjaan

```csharp
options.JobName = "overridden-job-name";
```

Tentukan nama pekerjaan untuk mengganti nama default.

## Langkah 3: Tentukan Direktori Kerja Input

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

Atur direktori kerja input untuk file TeX Anda.

## Langkah 4: Tentukan Direktori Kerja Output

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Tentukan direktori kerja keluaran untuk menyimpan file TeX yang diproses.

## Langkah 5: Tulis Output Terminal ke Disk

```csharp
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

Konfigurasikan keluaran terminal untuk ditulis ke file di direktori keluaran.

## Langkah 6: Jalankan Pekerjaan

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

Buat TeXJob, tentukan nama pekerjaan, perangkat keluaran (XpsDevice), dan opsi. Terakhir, jalankan pekerjaan.

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara mengganti nama pekerjaan dan menulis output terminal ke disk menggunakan Aspose.TeX untuk .NET di C#. Kemampuan ini berharga untuk mengelola tugas pemrosesan TeX Anda secara efisien.

## FAQ

### Q1: Bisakah saya menggunakan Aspose.TeX untuk .NET dengan perpustakaan .NET lainnya?

A1: Ya, Aspose.TeX untuk .NET dapat diintegrasikan dengan perpustakaan .NET lainnya dengan lancar.

### Q2: Apakah ada uji coba gratis yang tersedia untuk Aspose.TeX untuk .NET?

 A2: Ya, Anda dapat mengunduh versi uji coba gratis[Di Sini](https://releases.aspose.com/).

### Q3: Bagaimana saya bisa mendapatkan dukungan untuk Aspose.TeX untuk .NET?

 A3: Kunjungi[Forum Aspose.TeX](https://forum.aspose.com/c/tex/47) untuk mendapatkan komunitas dan dukungan.

### Q4: Apakah lisensi sementara tersedia untuk Aspose.TeX untuk .NET?

 A4: Ya, Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).

### Q5: Di mana saya dapat menemukan dokumentasi Aspose.TeX untuk .NET?

 A5: Dokumentasi tersedia[Di Sini](https://reference.aspose.com/tex/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
