---
title: Render Angka LaTeX ke SVG dengan Aspose.TeX (C#)
linktitle: Render Angka LaTeX ke SVG dengan Aspose.TeX (C#)
second_title: Aspose.TeX .NET API
description: Tingkatkan rendering dokumen di .NET dengan Aspose.TeX. Pelajari cara merender angka LaTeX ke SVG di C# untuk integrasi ekspresi matematika yang lancar.
type: docs
weight: 11
url: /id/net/render-latex-figures/svg-latex-figure-renderer-csharp/
---
## Perkenalan

Jika Anda ingin meningkatkan kemampuan rendering dokumen Anda di .NET menggunakan angka LaTeX, Aspose.TeX adalah solusi tepat Anda. Dalam panduan langkah demi langkah ini, kami akan memandu Anda dalam merender angka LaTeX ke SVG menggunakan Aspose.TeX di C#. Di akhir tutorial ini, Anda akan memiliki pemahaman yang jelas tentang prosesnya, memberdayakan Anda untuk menggabungkan ekspresi dan angka matematika berkualitas tinggi dengan lancar ke dalam dokumen Anda.

## Prasyarat

Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:

- Pengetahuan dasar bahasa pemrograman C#.
-  Aspose.TeX untuk perpustakaan .NET diinstal. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/tex/net/).

## Impor Namespace

Dalam kode C# Anda, pastikan untuk mengimpor namespace yang diperlukan:

```csharp
using Aspose.TeX.Features;
```

Sekarang, mari kita bagi tutorialnya menjadi beberapa langkah:

## Langkah 1: Buat Opsi Rendering

```csharp
FigureRendererOptions options = new SvgFigureRendererOptions();
options.Preamble = "\\usepackage{pict2e}";
options.Scale = 3000;
options.BackgroundColor = Color.White;
options.LogStream = new System.IO.MemoryStream();
options.ShowTerminal = true;
```

Di sini, kami menyiapkan opsi rendering, menentukan pembukaan, faktor penskalaan, warna latar belakang, aliran log, dan apakah akan menampilkan keluaran terminal.

## Langkah 2: Tentukan Dimensi dan Aliran Keluaran

```csharp
SizeF size = new SizeF();
using (Stream stream = File.Open(Path.Combine("Your Output Directory", "text-and-formula.svg"), FileMode.Create))
{
    // Jalankan rendering.
    new SvgFigureRenderer().Render("Your LaTeX Code", stream, options, out size);
}
```

Ganti "Direktori Output Anda" dengan direktori yang Anda inginkan dan berikan kode LaTeX Anda sebagai string.

## Langkah 3: Tampilkan Hasil

```csharp
Console.Out.WriteLine(options.ErrorReport);
Console.Out.WriteLine();
Console.Out.WriteLine("Size: " + size);
```

Langkah ini menampilkan laporan kesalahan dan ukuran gambar yang dihasilkan.

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara merender angka LaTeX ke SVG menggunakan Aspose.TeX di C#. Sekarang, Anda dapat dengan mudah mengintegrasikan ekspresi dan angka matematika ke dalam aplikasi .NET Anda.

## FAQ

### Q1: Apakah Aspose.TeX gratis untuk digunakan?

 A1: Aspose.TeX menawarkan uji coba gratis. Anda dapat mengaksesnya[Di Sini](https://releases.aspose.com/).

### Q2: Di mana saya dapat menemukan dokumentasi Aspose.TeX?

 A2: Lihat dokumentasi[Di Sini](https://reference.aspose.com/tex/net/).

### Q3: Bagaimana cara mendapatkan dukungan untuk Aspose.TeX?

 A3: Kunjungi forum dukungan[Di Sini](https://forum.aspose.com/c/tex/47).

### Q4: Bisakah saya membeli Aspose.TeX?

 A4: Ya, Anda dapat membeli Aspose.TeX[Di Sini](https://purchase.aspose.com/buy).

### Q5: Apakah saya memerlukan lisensi sementara?

 A5: Jika diperlukan, Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).