---
date: 2025-12-23
description: Pelajari cara mengonversi LaTeX ke XPS di .NET dengan Aspose.TeX dengan
  mudah. Konversi berkualitas tinggi, dapat disesuaikan, dan efisien.
linktitle: How to Convert LaTeX to XPS in .NET – Easy Conversion with Aspose.TeX
second_title: Aspose.TeX .NET API
title: Cara Mengonversi LaTeX ke XPS di .NET – Konversi Mudah dengan Aspose.TeX
url: /id/net/latex-conversion/to-xps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# LaTeX ke XPS di .NET - Konversi Mudah dengan Aspose.TeX

## Introduction

Jika Anda bertanya-tanya **cara mengonversi latex** dokumen ke format XPS dalam aplikasi .NET Anda, Anda berada di tempat yang tepat. Aspose.TeX untuk .NET menyediakan solusi yang kuat dan sederhana yang menangani pekerjaan berat untuk Anda. Dalam panduan ini kami akan menjelaskan setiap langkah, menjelaskan mengapa setiap pengaturan penting, dan menunjukkan cara mendapatkan output XPS berkualitas tinggi dan dapat disesuaikan dengan hanya beberapa baris kode.

## Quick Answers
- **Perpustakaan apa yang menangani konversi?** Aspose.TeX for .NET  
- **Format output yang didukung?** XPS (also PDF, PNG, etc.)  
- **Waktu implementasi tipikal?** 10–15 menit untuk konversi dasar  
- **Apakah saya memerlukan lisensi?** Lisensi sementara diperlukan untuk produksi; percobaan gratis tersedia.  
- **Bisakah saya menjalankan konversi dari memori?** Ya, menggunakan `MemoryStream` seperti yang ditunjukkan nanti.

## How to Convert LaTeX to XPS in .NET
Berikut adalah panduan singkat langkah‑demi‑langkah yang mencakup semua yang Anda butuhkan—dari prasyarat hingga penyesuaian opsional—sehingga Anda dapat fokus pada logika bisnis aplikasi Anda.

## Prerequisites

Sebelum menyelam ke tutorial, pastikan Anda memiliki prasyarat berikut:

- Pengetahuan dasar tentang C# dan pengembangan .NET.  
- Perpustakaan Aspose.TeX untuk .NET terpasang. Anda dapat mengunduhnya **[here](https://releases.aspose.com/tex/net/)**.  
- Pemahaman tentang sintaks dan struktur LaTeX.

## Import Namespaces

Mari kita mulai dengan mengimpor namespace yang diperlukan untuk aplikasi .NET kami. Namespace ini penting untuk berinteraksi dengan fungsionalitas Aspose.TeX.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
using System.Text;
```

## Step 1: Set Up Conversion Options

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectLaTeX);
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

Di sini, kami menginisialisasi opsi konversi dan menunjuk mesin ke folder yang berisi file sumber `.ltx` Anda.

## Step 2: Set Interaction Mode

```csharp
options.Interaction = Interaction.NonstopMode;
```

Mode non‑stop memberi tahu mesin untuk terus memproses meskipun menemukan peringatan kecil, yang ideal untuk pipeline otomatis.

## Step 3: Set Job Name (Optional)

```csharp
// options.JobName = "my-job-name";
```

Anda dapat menetapkan nama pekerjaan khusus untuk membantu mengidentifikasi log saat memproses banyak dokumen.

## Step 4: Set Date in Title (Optional)

```csharp
// options.DateTime = new System.DateTime(2022, 12, 18);
```

Memaksa tanggal tertentu muncul di halaman judul yang dihasilkan, berguna untuk laporan yang dapat direproduksi.

## Step 5: Ignore Missing Packages

```csharp
options.IgnoreMissingPackages = true;
```

Ketika disetel ke `true`, mesin melewati paket LaTeX yang hilang alih‑alih melempar error, yang dapat mempercepat konversi batch.

## Step 6: Disable Ligatures

```csharp
options.NoLigatures = true;
```

Menonaktifkan ligatur memastikan kombinasi karakter ditampilkan persis seperti yang diketik, yang diperlukan oleh beberapa dokumen teknis.

## Step 7: Repeat the Job (Optional)

```csharp
// options.Repeat = true;
```

Mengaktifkan flag ini memberi tahu mesin untuk menjalankan pekerjaan yang sama lagi—berguna untuk debugging iteratif.

## Step 8: Specify Output Working Directory

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Tentukan di mana file XPS yang dihasilkan akan ditulis.

## Step 9: Initialize Save Options for XPS

```csharp
options.SaveOptions = new XpsSaveOptions(); // Default value. Arbitrary assignment.
```

Buat instance `XpsSaveOptions` untuk menyetel detail output XPS.

## Step 10: Rasterize Formulas (Optional)

```csharp
options.SaveOptions.RasterizeFormulas = true;
```

Ketika `true`, rumus matematika dirender sebagai gambar raster, yang dapat meningkatkan kompatibilitas dengan penampil XPS lama.

## Step 11: Rasterize Included Graphics (Optional)

```csharp
options.SaveOptions.RasterizeIncludedGraphics = true;
```

Konversi grafik vektor yang disematkan dalam sumber LaTeX menjadi gambar raster untuk rendering konsisten di semua platform.

## Step 12: Subset Fonts

```csharp
options.SaveOptions.SubsetFonts = true;
```

Subset hanya menyertakan glif yang benar‑benar digunakan dalam dokumen, sehingga ukuran file berkurang.

## Step 13: Run LaTeX to XPS Conversion

```csharp
new TeXJob(Path.Combine("Your Input Directory", "sample.ltx"), new XpsDevice(), options).Run();
```

Baris tunggal ini meluncurkan proses konversi, membaca `sample.ltx` dan menghasilkan file XPS di direktori output.

## Step 14: Run LaTeX to XPS Conversion with MemoryStream (Alternative)

```csharp
// new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(@"\documentclass{article} \begin{document} Hello, World! \end{document}")),
//     new XpsDevice(), options).Run();
```

Jika Anda lebih suka memberi sumber LaTeX langsung dari memori—misalnya yang dihasilkan secara dinamis—gunakan `MemoryStream` seperti yang ditunjukkan.

## Step 15: Run LaTeX to XPS Conversion with Main Input Terminal (Alternative)

```csharp
// new TeXJob(new XpsDevice(), options).Run();
```

Overload ini memungkinkan Anda meluncurkan konversi dari terminal input default, berguna untuk skenario baris perintah.

## Common Issues & Tips

- **Missing Packages:** Bahkan dengan `IgnoreMissingPackages` disetel ke `true`, beberapa paket tetap penting. Pastikan paket inti (mis., `amsmath`) tersedia dalam distribusi TeX Anda.  
- **Font Subsetting Errors:** Jika output XPS terlihat berantakan, coba nonaktifkan `SubsetFonts` untuk menyertakan font lengkap.  
- **Large Documents:** Untuk proyek LaTeX yang sangat besar, tingkatkan ukuran heap JVM (jika menggunakan mesin TeX di bawah) atau proses dokumen dalam potongan yang lebih kecil.

## Frequently Asked Questions

**Q1: Apakah Aspose.TeX kompatibel dengan kerangka kerja .NET terbaru?**  
A: Ya, Aspose.TeX secara rutin diperbarui untuk mendukung .NET 6, .NET 7, dan rilis yang lebih baru.

**Q2: Bisakah saya menyesuaikan format output selain XPS?**  
A: Aspose.TeX mendukung banyak format output. Lihat referensi API lengkap **[here](https://reference.aspose.com/tex/net/)** untuk detailnya.

**Q3: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.TeX?**  
A: Anda dapat memperoleh lisensi sementara **[here](https://purchase.aspose.com/temporary-license/)**.

**Q4: Di mana saya dapat mencari bantuan atau berbagi pengalaman dengan Aspose.TeX?**  
A: Bergabunglah dengan forum komunitas **[here](https://forum.aspose.com/c/tex/47)** untuk tips dan dukungan.

**Q5: Apakah ada contoh dokumen LaTeX untuk menguji konversi?**  
A: Ya, jelajahi contoh Aspose.TeX **[here](https://github.com/aspose-tex/Aspose.TeX-for-.NET)**.

## Conclusion

Dengan mengikuti langkah‑langkah ini, Anda kini memiliki alur kerja lengkap yang siap produksi untuk **cara mengonversi latex** dokumen ke XPS menggunakan Aspose.TeX untuk .NET. Opsi‑opsi luas dalam perpustakaan memungkinkan Anda menyesuaikan konversi sesuai kebutuhan tepat—baik Anda membuat faktur, manual teknis, atau makalah akademik.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.TeX 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}