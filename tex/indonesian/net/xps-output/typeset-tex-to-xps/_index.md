---
title: Mengetik TeX ke XPS di .NET
linktitle: Mengetik TeX ke XPS di .NET
second_title: Aspose.TeX .NET API
description: Konversikan dokumen TeX ke XPS dengan mudah di .NET dengan Aspose.TeX. Jelajahi panduan langkah demi langkah kami untuk pengalaman integrasi yang lancar.
weight: 10
url: /id/net/xps-output/typeset-tex-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mengetik TeX ke XPS di .NET

## Perkenalan

Selamat datang di panduan langkah demi langkah kami tentang penyusunan huruf TeX ke XPS di .NET menggunakan pustaka Aspose.TeX yang canggih. Jika Anda ingin mengonversi dokumen TeX ke format XPS dengan lancar di aplikasi .NET, Anda datang ke tempat yang tepat. Dalam tutorial ini, kami akan memandu Anda melalui seluruh proses, menguraikan setiap langkah untuk memastikan implementasi yang lancar.

## Prasyarat

Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:

-  Aspose.TeX untuk .NET: Pastikan Anda telah menginstal perpustakaan Aspose.TeX. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/tex/net/).

- Dokumentasi: Biasakan diri Anda dengan perpustakaan dengan mengacu pada dokumentasi[Di Sini](https://reference.aspose.com/tex/net/).

- Direktori Input dan Output: Siapkan direktori input dan output Anda seperti yang ditentukan dalam kode contoh.

Sekarang Anda sudah menyiapkan semuanya, mari lanjutkan dengan panduan langkah demi langkah.

## Impor Namespace

Di aplikasi .NET Anda, mulailah dengan mengimpor namespace yang diperlukan. Hal ini memastikan bahwa Anda memiliki akses ke fungsionalitas Aspose.TeX yang diperlukan untuk penyusunan huruf TeX ke XPS.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
```

## Langkah 1: Tetapkan Opsi Konversi

Tentukan opsi konversi, tentukan format ObjectTeX pada ekstensi mesin ObjectTeX. Juga, atur nama pekerjaan, direktori input dan output, dan detail output terminal.

```csharp
// Buat opsi konversi untuk format ObjectTeX default pada ekstensi mesin ObjectTeX.
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
// Tentukan nama pekerjaan.
options.JobName = "external-file-stream";
// Tentukan direktori kerja sistem file untuk input.
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
// Tentukan direktori kerja sistem file untuk keluaran.
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
// Tentukan bahwa keluaran terminal harus ditulis ke file di direktori kerja keluaran.
// Nama filenya adalah <nama_pekerjaan>.trm.
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## Langkah 2: Buat Aliran Dokumen XPS

Buka aliran untuk menulis dokumen XPS yang dikeset. Nama file belum tentu sama dengan nama pekerjaan.

```csharp
using (Stream stream = File.Open(Path.Combine("Your Output Directory", options.JobName + ".xps"), FileMode.Create))
```

## Langkah 3: Jalankan Pekerjaan TeX

Memulai dan menjalankan pekerjaan TeX, menentukan nama dokumen, XpsDevice, dan opsi konversi.

```csharp
new TeXJob("hello-world", new XpsDevice(stream), options).Run();
```

Selamat! Anda telah berhasil mengeset TeX ke XPS di .NET menggunakan Aspose.TeX. Jangan ragu untuk menjelajahi lebih banyak fitur dan opsi berdasarkan kebutuhan spesifik Anda.

## Kesimpulan

Dalam tutorial ini, kami membahas langkah-langkah penting untuk mengonversi dokumen TeX ke format XPS dengan lancar di .NET menggunakan Aspose.TeX. Dengan mengikuti panduan ini, Anda mendapatkan wawasan berharga tentang kemampuan perpustakaan dan cara memanfaatkannya untuk proyek Anda.

## FAQ

### Q1: Apakah Aspose.TeX kompatibel dengan .NET Core?

A1: Ya, Aspose.TeX sepenuhnya kompatibel dengan .NET Core.

### Q2: Dapatkah saya menggunakan Aspose.TeX untuk proyek komersial?

A2: Tentu saja! Aspose.TeX tersedia untuk penggunaan komersial dan pribadi.

### Q3: Di mana saya dapat menemukan contoh dan sumber tambahan?

 A3: Jelajahi dokumentasi Aspose.TeX[Di Sini](https://reference.aspose.com/tex/net/)untuk lebih banyak contoh dan sumber daya terperinci.

### Q4: Bagaimana saya bisa mendapatkan dukungan untuk Aspose.TeX?

 A4: Kunjungi forum dukungan Aspose.TeX[Di Sini](https://forum.aspose.com/c/tex/47) untuk mendapatkan bantuan dari masyarakat.

### Q5: Apakah tersedia uji coba gratis?

 A5: Ya, Anda dapat mengakses uji coba gratis[Di Sini](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
