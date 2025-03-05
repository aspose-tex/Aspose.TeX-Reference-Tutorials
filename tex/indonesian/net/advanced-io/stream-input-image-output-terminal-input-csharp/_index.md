---
title: Aliran Master, Gambar, & Input Terminal di Aspose.TeX untuk C#
linktitle: Aliran Master, Gambar, & Input Terminal di Aspose.TeX untuk C#
second_title: Aspose.TeX .NET API
description: Jelajahi kekuatan Aspose.TeX untuk aliran master C#, gambar, dan input terminal dengan mudah. Unduh sekarang untuk pemrosesan dokumen yang lancar.
type: docs
weight: 11
url: /id/net/advanced-io/stream-input-image-output-terminal-input-csharp/
---
## Perkenalan

Selamat datang di tutorial komprehensif tentang menguasai aliran, gambar, dan input terminal di Aspose.TeX untuk C#. Aspose.TeX adalah perpustakaan canggih yang memungkinkan pengembang bekerja dengan file TeX, menyediakan berbagai fitur untuk manipulasi dan konversi dokumen. Dalam panduan ini, kita akan mempelajari cara menangani aliran, mengelola gambar, dan menangkap input terminal menggunakan Aspose.TeX untuk C#. Di akhir tutorial ini, Anda akan dibekali dengan pengetahuan untuk bekerja secara efisien dengan aspek-aspek penting dalam pemrosesan dokumen.

## Prasyarat

Sebelum kita mendalami contohnya, pastikan Anda memiliki prasyarat berikut:

- Pengetahuan dasar bahasa pemrograman C#.
-  Aspose.TeX untuk perpustakaan .NET diinstal. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/tex/net/).
- Lingkungan pengembangan yang disiapkan untuk C#.

## Impor Namespace

Dalam proyek C# Anda, pastikan untuk menyertakan namespace yang diperlukan untuk mengakses fungsionalitas Aspose.TeX. Tambahkan baris berikut di awal kode Anda:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Image;
using System.IO;
using System.Text;
```

## Langkah 1: Siapkan Opsi Konversi

```csharp
// ExStart:TakeMainInputFromStream-AuxFromFileSystem-TakeTerminalInputFromConsole-AlternativeImagesStorage
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
options.JobName = "stream-in-image-out";
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
options.TerminalIn = new InputConsoleTerminal();
options.TerminalOut = new OutputConsoleTerminal();
options.SaveOptions = new PngSaveOptions() { Resolution = 300 };
```

## Langkah 2: Buat Perangkat Gambar dan Jalankan Pekerjaan

```csharp
ImageDevice device = new ImageDevice();
TeXJob job = new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
    "\\hrule height 10pt width 95pt\\vskip10pt\\hrule height 5pt")),
    device, options);
job.Run();
```

## Langkah 3: Berikan Masukan di Konsol

Saat diminta di konsol, ketik "ABC", tekan Enter, lalu ketik "\end", lalu tekan Enter lagi.

## Langkah 4: Sempurnakan Output

```csharp
options.TerminalOut.Writer.WriteLine();
byte[][] result = device.Result;
// ExEnd:TakeMainInputFromStream-AuxFromFileSystem-TakeTerminalInputFromConsole-AlternativeImagesStorage
```

Selamat! Anda telah berhasil memproses input TeX dari aliran, gambar terkelola, dan menangkap input terminal menggunakan Aspose.TeX untuk C#. Keterampilan ini sangat berharga untuk berbagai skenario pemrosesan dokumen.

## Kesimpulan

Dalam tutorial ini, kami membahas aspek penting dalam bekerja dengan stream, gambar, dan input terminal di Aspose.TeX untuk C#. Anda mempelajari cara menyiapkan opsi konversi, membuat perangkat gambar, menjalankan tugas, dan menyempurnakan keluaran. Dengan pengetahuan ini, Anda diperlengkapi untuk menangani beragam tugas pemrosesan dokumen secara efisien.

## FAQ

### Q1: Dapatkah saya menggunakan Aspose.TeX untuk .NET dalam aplikasi non-konsol?

A1: Tentu saja! Aspose.TeX dapat diintegrasikan dengan mulus ke dalam berbagai jenis aplikasi, termasuk aplikasi desktop dan web.

### Q2: Bagaimana cara menyesuaikan resolusi gambar keluaran?

 A2: Dalam contoh yang diberikan, resolusi diatur di`PngSaveOptions` obyek. Anda dapat menyesuaikannya`Resolution` properti berdasarkan kebutuhan Anda.

### Q3: Apakah ada versi uji coba yang tersedia?

 A3: Ya, Anda dapat menjelajahi Aspose.TeX dengan uji coba gratis yang tersedia[Di Sini](https://releases.aspose.com/).

### Q4: Di mana saya bisa mendapatkan dukungan dan bantuan tambahan?

 A4: Kunjungi forum Aspose.TeX[Di Sini](https://forum.aspose.com/c/tex/47)untuk dukungan dan diskusi komunitas.

### Q5: Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.TeX?

 A5: Anda dapat memperoleh lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).