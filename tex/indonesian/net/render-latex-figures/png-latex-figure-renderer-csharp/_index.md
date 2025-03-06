---
title: Render Angka LaTeX ke PNG dengan Aspose.TeX (C#)
linktitle: Render Angka LaTeX ke PNG dengan Aspose.TeX (C#)
second_title: Aspose.TeX .NET API
description: Jelajahi panduan komprehensif tentang merender angka LaTeX ke PNG menggunakan Aspose.TeX di C#. Pelajari langkah demi langkah dengan contoh kode.
weight: 10
url: /id/net/render-latex-figures/png-latex-figure-renderer-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Render Angka LaTeX ke PNG dengan Aspose.TeX (C#)

## Perkenalan

Jika Anda mempelajari dunia penyusunan huruf dan pembuatan dokumen di .NET, Anda mungkin sudah familiar dengan tantangan dalam merender angka LaTeX. Dalam panduan langkah demi langkah ini, kita akan mempelajari cara menggunakan Aspose.TeX untuk .NET untuk merender angka LaTeX ke format PNG menggunakan C#. Aspose.TeX memberikan solusi yang kuat dan fleksibel untuk menangani dokumen LaTeX, menjadikannya alat yang sangat berharga bagi pengembang yang bekerja dengan pembuatan dan pemformatan dokumen.

## Prasyarat

Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:

-  Aspose.TeX untuk .NET Library: Pastikan Anda telah menginstal perpustakaan Aspose.TeX untuk .NET. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/tex/net/).

## Impor Namespace

Dalam kode C# Anda, mulailah dengan mengimpor namespace yang diperlukan. Langkah ini memastikan bahwa Anda memiliki akses ke kelas dan fungsi yang diperlukan.

```csharp
using Aspose.TeX.Features;
```

## Render Angka LaTeX ke PNG

### Langkah 1: Siapkan Opsi Rendering

Mulailah dengan membuat opsi rendering dan mengatur parameter seperti resolusi gambar, pembukaan, faktor skala, warna latar belakang, dan banyak lagi.

```csharp
FigureRendererOptions options = new PngFigureRendererOptions() { Resolution = 150 };
options.Preamble = "\\usepackage{pict2e}";
options.Scale = 3000;
options.BackgroundColor = System.Drawing.Color.White;
options.LogStream = new System.IO.MemoryStream();
options.ShowTerminal = true;
```

### Langkah 2: Tentukan Aliran dan Dimensi Output

Buat aliran keluaran untuk gambar PNG dan variabel untuk menyimpan dimensi gambar yang dihasilkan.

```csharp
System.Drawing.SizeF size = new System.Drawing.SizeF();
using (System.IO.Stream stream = System.IO.File.Open(
   System.IO.Path.Combine("Your Output Directory", "text-and-formula.png"), System.IO.FileMode.Create))
{
    // Kode untuk rendering ada di sini
}
```

### Langkah 3: Jalankan Rendering

Terapkan proses rendering menggunakan perpustakaan Aspose.TeX. Berikan kode LaTeX, aliran keluaran, opsi rendering, dan variabel ukuran.

```csharp
new PngFigureRenderer().Render(@"\setlength{\unitlength}{0.8cm}
\begin{picture}(6,5)
    % LaTeX figure code goes here
\end{picture}", stream, options, out size);
```

### Langkah 4: Tampilkan Hasil

Terakhir, tampilkan hasilnya, termasuk laporan kesalahan dan ukuran gambar yang dirender.

```csharp
System.Console.Out.WriteLine(options.ErrorReport);
System.Console.Out.WriteLine();
System.Console.Out.WriteLine("Size: " + size);
```

## Kesimpulan

Dengan Aspose.TeX untuk .NET, merender angka LaTeX ke format PNG menjadi proses yang mulus. Tutorial ini telah memandu Anda melalui langkah-langkah penting, mulai dari menyiapkan opsi rendering hingga menampilkan hasil akhir.

## FAQ

### Q1: Apakah Aspose.TeX kompatibel dengan semua perintah LaTeX?

 A1: Aspose.TeX mendukung berbagai perintah LaTeX, namun disarankan untuk merujuk ke[dokumentasi](https://reference.aspose.com/tex/net/) untuk informasi rinci.

### Q2: Dapatkah saya mencoba Aspose.TeX sebelum membeli?

 A2: Ya, Anda dapat menjelajahi versi uji coba gratis[Di Sini](https://releases.aspose.com/).

### Q3: Bagaimana cara mendapatkan dukungan untuk Aspose.TeX?

 A3: Kunjungi[Forum Aspose.TeX](https://forum.aspose.com/c/tex/47)untuk dukungan dan diskusi komunitas.

### Q4: Di mana saya dapat menemukan lisensi sementara untuk Aspose.TeX?

 A4: Lisensi sementara tersedia[Di Sini](https://purchase.aspose.com/temporary-license/).

### Q5: Bagaimana struktur harga untuk Aspose.TeX?

A5: Jelajahi detail harga dan lakukan pembelian[Di Sini](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
