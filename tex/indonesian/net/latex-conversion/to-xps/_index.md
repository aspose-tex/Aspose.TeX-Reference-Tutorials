---
title: LaTeX ke XPS di .NET - Konversi Mudah dengan Aspose.TeX
linktitle: LaTeX ke XPS di .NET - Konversi Mudah dengan Aspose.TeX
second_title: Aspose.TeX .NET API
description: Konversi LaTeX ke XPS dengan mudah di .NET dengan Aspose.TeX. Berkualitas tinggi, dapat disesuaikan, dan efisien.
type: docs
weight: 13
url: /id/net/latex-conversion/to-xps/
---
## Perkenalan

Apakah Anda mencari cara mudah untuk mengonversi dokumen LaTeX ke format XPS di aplikasi .NET Anda? Aspose.TeX untuk .NET memberikan solusi ampuh untuk tugas ini, membuat proses konversi menjadi sederhana dan efisien. Panduan langkah demi langkah ini akan memandu Anda melalui proses konversi LaTeX ke XPS menggunakan Aspose.TeX, memastikan Anda mencapai hasil yang akurat dan berkualitas tinggi.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

- Pengetahuan tentang pengembangan C# dan .NET.
-  Aspose.TeX untuk perpustakaan .NET diinstal. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/tex/net/).
- Pemahaman tentang sintaks dan struktur LaTeX.

## Impor Namespace

Mari kita mulai dengan mengimpor namespace yang diperlukan untuk aplikasi .NET kita. Namespace ini sangat penting untuk berinteraksi dengan fungsionalitas Aspose.TeX.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
using System.Text;
```

## Langkah 1: Siapkan Opsi Konversi

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectLaTeX);
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

Di sini, kami menginisialisasi opsi konversi dan mengatur direktori kerja input untuk file LaTeX Anda.

## Langkah 2: Atur Mode Interaksi

```csharp
options.Interaction = Interaction.NonstopMode;
```

Tentukan mode interaksi, di mana kami mengaturnya ke mode non-stop untuk konversi tanpa gangguan.

## Langkah 3: Tetapkan Nama Pekerjaan (Opsional)

```csharp
// options.JobName = "nama-pekerjaan saya";
```

Anda dapat menetapkan nama pekerjaan khusus jika diperlukan.

## Langkah 4: Tetapkan Tanggal di Judul (Opsional)

```csharp
// opsi.DateTime = Sistem baru.DateTime(2022, 12, 18);
```

Paksa mesin TeX untuk menampilkan tanggal tertentu di judul.

## Langkah 5: Abaikan Paket yang Hilang

```csharp
options.IgnoreMissingPackages = true;
```

Setel ke true jika Anda ingin mesin melewati paket yang hilang tanpa kesalahan.

## Langkah 6: Nonaktifkan Ligatur

```csharp
options.NoLigatures = true;
```

Setel ke true untuk mencegah mesin membuat ikatan.

## Langkah 7: Ulangi Pekerjaan (Opsional)

```csharp
// pilihan.Ulangi = benar;
```

Minta mesin untuk mengulangi pekerjaan tersebut jika diperlukan.

## Langkah 8: Tentukan Direktori Kerja Output

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Atur direktori kerja keluaran untuk file XPS yang dikonversi.

## Langkah 9: Inisialisasi Opsi Penyimpanan untuk XPS

```csharp
options.SaveOptions = new XpsSaveOptions(); // Nilai bawaan. Penugasan sewenang-wenang.
```

Inisialisasi opsi untuk menyimpan dalam format XPS.

## Langkah 10: Rasterisasi Rumus (Opsional)

```csharp
options.SaveOptions.RasterizeFormulas = true;
```

Setel ke true jika Anda ingin rumus matematika diubah menjadi gambar raster.

## Langkah 11: Rasterisasi Grafik yang Disertakan (Opsional)

```csharp
options.SaveOptions.RasterizeIncludedGraphics = true;
```

Setel ke true jika Anda ingin menyertakan grafik dengan elemen vektor untuk dikonversi menjadi gambar raster.

## Langkah 12: Subset Font

```csharp
options.SaveOptions.SubsetFonts = true;
```

Setel ke true untuk membuat font subset perangkat digunakan dalam dokumen.

## Langkah 13: Jalankan Konversi LaTeX ke XPS

```csharp
new TeXJob(Path.Combine("Your Input Directory", "sample.ltx"), new XpsDevice(), options).Run();
```

Memulai proses konversi LaTeX ke XPS.

## Langkah 14: Jalankan Konversi LaTeX ke XPS dengan MemoryStream (Alternatif)

```csharp
// TeXJob baru(New MemoryStream(Encoding.ASCII.GetBytes(@"\documentclass{article} \begin{document} Halo Dunia! \end{document}")),
// XpsDevice() baru, opsi).Run();
```

Anda juga dapat menjalankan konversi menggunakan MemoryStream untuk memasukkan konten LaTeX.

## Langkah 15: Jalankan Konversi LaTeX ke XPS dengan Terminal Input Utama (Alternatif)

```csharp
// TeXJob baru(XpsDevice() baru, opsi).Run();
```

Jalankan konversi langsung dari terminal input utama.

## Kesimpulan

Dengan mengikuti langkah-langkah sederhana ini, Anda dapat dengan mudah mengonversi dokumen LaTeX ke format XPS menggunakan Aspose.TeX untuk .NET. Pustaka canggih ini memberikan fleksibilitas dan opsi penyesuaian untuk memenuhi kebutuhan spesifik Anda.

## FAQ

### Q1: Apakah Aspose.TeX kompatibel dengan kerangka .NET terbaru?

A1: Ya, Aspose.TeX diperbarui secara berkala untuk memastikan kompatibilitas dengan kerangka .NET terbaru.

### Q2: Dapatkah saya menyesuaikan format output selain XPS?

 A2: Aspose.TeX mendukung berbagai format keluaran. Lihat dokumentasi[Di Sini](https://reference.aspose.com/tex/net/) untuk detailnya.

### Q3: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.TeX?

 A3: Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).

### Q4: Di mana saya dapat mencari bantuan atau berbagi pengalaman saya dengan Aspose.TeX?

 A4: Kunjungi forum Aspose.TeX[Di Sini](https://forum.aspose.com/c/tex/47) untuk dukungan masyarakat.

### Q5: Apakah ada contoh dokumen yang tersedia untuk pengujian?

 A5: Jelajahi contoh Aspose.TeX[Di Sini](https://github.com/aspose-tex/Aspose.TeX-for-.NET).