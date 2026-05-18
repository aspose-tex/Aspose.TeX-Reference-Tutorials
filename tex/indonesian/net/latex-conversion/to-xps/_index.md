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

## Perkenalan

Jika Anda bertanya-tanya **cara mengonversi lateks** dokumen ke format XPS dalam aplikasi .NET Anda, Anda berada di tempat yang tepat. Aspose.TeX untuk .NET menyediakan solusi yang kuat dan sederhana yang menangani pekerjaan berat untuk Anda. Dalam panduan ini kami akan menjelaskan setiap langkah, menjelaskan mengapa setiap pengaturan penting, dan menunjukkan cara mendapatkan output XPS berkualitas tinggi dan dapat disesuaikan hanya dengan beberapa baris kode.

## Jawaban Cepat
- **Perpustakaan apa yang menangani konversi?** Aspose.TeX untuk .NET
- **Format output yang didukung?** XPS (juga PDF, PNG, dll.)
- **Waktu implementasi tipikal?** 10–15 menit untuk konversi dasar
- **Apakah saya memerlukan lisensi?** Lisensi sementara diperlukan untuk produksi; percobaan gratis tersedia.
- ** Membiarkan saya menjalankan konversi dari memori?** Ya, menggunakan `MemoryStream` seperti yang ditunjukkan nanti.

## Cara Mengonversi LaTeX ke XPS di .NET
Berikut adalah panduan langkah‑demi‑langkah singkat yang mencakup semua yang Anda butuhkan—dari prasyarat hingga penyesuaian opsional—sehingga Anda dapat fokus pada logika bisnis aplikasi Anda.

## Prasyarat

Sebelum menyelam ke tutorial, pastikan Anda memiliki prasyarat berikut:

- Pengetahuan dasar tentang C# dan pengembangan .NET.
- Perpustakaan Aspose.TeX untuk .NET terpasang. Anda dapat mengunduhnya **[di sini](https://releases.aspose.com/tex/net/)**.
- Pemahaman tentang sintaks dan struktur LaTeX.

## Impor Namespace

Mari kita mulai dengan mengimpor namespace yang diperlukan untuk aplikasi .NET kami. Namespace ini penting untuk berinteraksi dengan fungsionalitas Aspose.TeX.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
using System.Text;
```

## Langkah 1: Atur Opsi Konversi

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectLaTeX);
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

Di sini, kami menginisialisasi opsi konversi dan menunjuk mesin ke folder yang berisi file sumber `.ltx` Anda.

## Langkah 2: Atur Mode Interaksi

```csharp
options.Interaction = Interaction.NonstopMode;
```

Mode non‑stop memberi tahu mesin untuk terus memproses meskipun menemukan peringatan kecil, yang ideal untuk pipeline otomatis.

## Langkah 3: Atur Nama Pekerjaan (Opsional)

```csharp
// options.JobName = "my-job-name";
```

Anda dapat menetapkan nama pekerjaan khusus untuk membantu mengidentifikasi log saat memproses banyak dokumen.

## Langkah 4: Atur Tanggal di Judul (Opsional)

```csharp
// options.DateTime = new System.DateTime(2022, 12, 18);
```

Memaksa tanggal tertentu muncul di halaman judul yang dihasilkan, berguna untuk laporan yang dapat direproduksi.

## Langkah 5: Abaikan Paket yang Hilang

```csharp
options.IgnoreMissingPackages = true;
```

Ketika disetel ke `true`, mesin melewati paket LaTeX yang hilang alih‑alih melempar error, yang dapat mempercepat konversi batch.

## Langkah 6: Nonaktifkan Ligatur

```csharp
options.NoLigatures = true;
```

Menonaktifkan ligatur memastikan kombinasi karakter ditampilkan persis seperti yang diketik, yang diperlukan oleh beberapa dokumen teknis.

## Langkah 7: Ulangi Pekerjaan (Opsional)

```csharp
// options.Repeat = true;
```

Mengaktifkan flag ini memberi tahu mesin untuk menjalankan pekerjaan yang sama lagi—berguna untuk debugging iteratif.

## Langkah 8: Tentukan Direktori Kerja Output

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Tentukan di mana file XPS yang dihasilkan akan ditulis.

## Langkah 9: Inisialisasi Opsi Simpan untuk XPS

```csharp
options.SaveOptions = new XpsSaveOptions(); // Default value. Arbitrary assignment.
```

Buat instance `XpsSaveOptions` untuk menyetel detail output XPS.

## Langkah 10: Rasterisasi Rumus (Opsional)

```csharp
options.SaveOptions.RasterizeFormulas = true;
```

Ketika `true`, rumus matematika dirender sebagai gambar raster, yang dapat meningkatkan kompatibilitas dengan penampil XPS lama.

## Langkah 11: Rasterisasi Grafik yang Disertakan (Opsional)

```csharp
options.SaveOptions.RasterizeIncludedGraphics = true;
```

Konversi grafik vektor yang disematkan dalam sumber LaTeX menjadi gambar raster untuk rendering konsisten di semua platform.

## Langkah 12: Subset Font

```csharp
options.SaveOptions.SubsetFonts = true;
```

Subset hanya menyertakan glif yang benar‑benar digunakan dalam dokumen, sehingga ukuran file berkurang.

## Langkah 13: Jalankan Konversi LaTeX ke XPS

```csharp
new TeXJob(Path.Combine("Your Input Directory", "sample.ltx"), new XpsDevice(), options).Run();
```

Baris tunggal ini meluncurkan proses konversi, membaca `sample.ltx` dan menghasilkan file XPS di direktori output.

## Langkah 14: Jalankan Konversi LaTeX ke XPS dengan MemoryStream (Alternatif)

```csharp
// new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(@"\documentclass{article} \begin{document} Hello, World! \end{document}")),
//     new XpsDevice(), options).Run();
```

Jika Anda lebih suka memberi sumber LaTeX langsung dari memori—misalnya yang dihasilkan secara dinamis—gunakan `MemoryStream` seperti yang ditunjukkan.

## Langkah 15: Jalankan Konversi LaTeX ke XPS dengan Terminal Input Utama (Alternatif)

```csharp
// new TeXJob(new XpsDevice(), options).Run();
```

Overload ini memungkinkan Anda meluncurkan konversi dari terminal input default, berguna untuk skenario baris perintah.

## Masalah & Tip Umum

- **Paket Hilang:** Bahkan dengan `IgnoreMissingPackages` disetel ke `true`, beberapa paket tetap penting. Pastikan paket inti (mis., `amsmath`) tersedia dalam distribusi TeX Anda.
- **Font Subsetting Errors:** Jika output XPS terlihat berantakan, coba aktifkan `SubsetFonts` untuk memasukkan font lengkap.
- **Dokumen Besar:** Untuk proyek LaTeX yang sangat besar, tingkatkan ukuran heap JVM (jika menggunakan mesin TeX di bawah) atau proses dokumen dalam potongan yang lebih kecil.

## Pertanyaan yang Sering Diajukan

**Q1: ​​Apakah Aspose.TeX kompatibel dengan kerangka kerja .NET terbaru?**
A: Ya, Aspose.TeX secara rutin diperbarui untuk mendukung .NET6, .NET7, dan rilis yang lebih baru.

**Q2: Bisakah saya menyesuaikan format output selain XPS?**
A: Aspose.TeX mendukung banyak format output. Lihat referensi API lengkap **[di sini](https://reference.aspose.com/tex/net/)** untuk detailnya.

**Q3: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.TeX?**
A: Anda dapat memperoleh lisensi sementara **[di sini](https://purchase.aspose.com/temporary-license/)**.

**Q4: Di mana saya dapat mencari bantuan atau berbagi pengalaman dengan Aspose.TeX?**
A: bermitra dengan forum komunitas **[di sini](https://forum.aspose.com/c/tex/47)** untuk tips dan dukungan.

**Q5: Apakah ada contoh dokumen LaTeX untuk menguji konversi?**
A: Ya, jelajahi contoh Aspose.TeX **[di sini](https://github.com/aspose-tex/Aspose.TeX-for-.NET)**.

## Kesimpulan

Dengan mengikuti langkah‑langkah ini, Anda kini memiliki alur kerja lengkap yang siap produksi untuk **cara mengonversi lateks** dokumen ke XPS menggunakan Aspose.TeX untuk .NET. Opsi‑opsi luas dalam perpustakaan memungkinkan Anda menyesuaikan konversi sesuai kebutuhan tepat—baik Anda membuat faktur, manual teknis, atau dokumen akademik.

---

**Terakhir Diperbarui:** 23-12-2025
**Diuji Dengan:** Aspose.TeX 24.11 untuk .NET
**Penulis:** Beranggapan  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}