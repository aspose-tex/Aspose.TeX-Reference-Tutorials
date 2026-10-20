---
date: 2026-10-19
description: Pelajari cara melakukan tex document generation, membuat custom tex format,
  dan mengatur tex input directory menggunakan Aspose.TeX untuk .NET. Panduan langkah
  demi langkah dengan code snippets dan troubleshooting tips.
keywords:
- tex document generation
- create custom tex format
- set tex input directory
- custom tex macros
lastmod: 2026-10-19
linktitle: Membuat Custom TeX Formats di .NET
og_description: tex document generation dengan Aspose.TeX memungkinkan Anda membuat
  custom tex format dan mengatur tex input directory di .NET. Ikuti panduan ini untuk
  output XPS, PDF, atau PNG.
og_image_alt: Developer guide showing tex document generation using Aspose.TeX in
  .NET
og_title: Cara melakukan tex document generation dengan format di .NET
schemas:
- author: Aspose
  dateModified: '2026-10-19'
  description: Learn how to perform tex document generation, create custom tex format
    and set tex input directory using Aspose.TeX for .NET. Step‑by‑step guide with
    code snippets and troubleshooting tips.
  headline: How to do tex document generation with format in .NET
  type: TechArticle
- description: Learn how to perform tex document generation, create custom tex format
    and set tex input directory using Aspose.TeX for .NET. Step‑by‑step guide with
    code snippets and troubleshooting tips.
  name: How to do tex document generation with format in .NET
  steps:
  - name: '**Aspose.TeX for .NET** – download it from the [Aspose.TeX website](https://releases.aspose.com/tex/net/).'
    text: '**Aspose.TeX for .NET** – download it from the [Aspose.TeX website](https://releases.aspose.com/tex/net/).'
  - name: A **.NET development environment** (Visual Studio, VS Code, or the .NET
      CLI).
    text: A **.NET development environment** (Visual Studio, VS Code, or the .NET
      CLI).
  - name: (Optional) A valid **Aspose.TeX license** for production use.
    text: (Optional) A valid **Aspose.TeX license** for production use.
  type: HowTo
- questions:
  - answer: Absolutely. Replace `new XpsDevice()` with `new PdfDevice()` and adjust
      the output path accordingly.
    question: Can I output PDF instead of XPS?
  - answer: Yes. Any modification to macros or engine settings requires re‑running
      `tex -ini` to generate a fresh `.fmt` file.
    question: Do I need to re‑compile the format file after every change?
  type: FAQPage
second_title: Aspose.TeX .NET API
tags:
- tex document generation
- Aspose.TeX
- .NET document processing
- custom tex format
title: Cara melakukan tex document generation dengan format di .NET
url: /id/net/custom-tex-formats/create-custom-tex-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara melakukan pembuatan dokumen tex dengan format di .NET

## Jawaban singkat
- **Apa arti “membuat format tex khusus”?** Artinya mendefinisikan konfigurasi mesin TeX Anda sendiri serta file format yang telah dikompilasi sehingga prosesor mengikuti makro dan pengaturan Anda.  
- **Perpustakaan apa yang saya perlukan?** Aspose.TeX untuk .NET, yang mendukung lebih dari 30 format input dan output.  
- **Apakah saya harus mengatur direktori input tex?** Ya – gunakan `InputWorkingDirectory` untuk memberi tahu mesin di mana file bantu berada.  
- **Output apa yang dapat saya hasilkan?** XPS, PDF, PNG, TIFF, dan banyak format perangkat lainnya.  
- **Apakah lisensi diperlukan untuk produksi?** Lisensi Aspose.TeX yang valid wajib untuk penyebaran komersial.

## Apa itu format tex khusus?
Format tex khusus adalah kumpulan makro dan pengaturan mesin yang telah dikompilasi sebelumnya dan dimuat oleh prosesor TeX saat start‑up. Dengan membuatnya, Anda dapat menyematkan branding perusahaan, menegakkan standar tata letak, dan mengurangi waktu kompilasi untuk dokumen berulang. Ini memungkinkan gaya yang konsisten di semua dokumen yang dihasilkan dan menyederhanakan pemeliharaan alur kerja typesetting yang kompleks.

## Mengapa mengatur direktori input tex?
Mengatur **direktori input tex** memberi tahu mesin di mana menemukan file bantu seperti file gaya, font khusus, atau paket makro tambahan. Hal ini menghilangkan kesalahan “file tidak ditemukan” dan menjaga folder proyek tetap rapi. Selain itu, meningkatkan reproduktifitas build dengan memastikan semua sumber daya diambil dari lokasi yang diketahui.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

1. **Aspose.TeX untuk .NET** – unduh dari [situs Aspose.TeX](https://releases.aspose.com/tex/net/).  
2. Lingkungan pengembangan **.NET** (Visual Studio, VS Code, atau .NET CLI).  
3. (Opsional) Lisensi **Aspose.TeX** yang valid untuk penggunaan produksi.

## Impor namespace

Namespace berikut memberi Anda akses ke kelas inti Aspose.TeX.  
Kelas terkait `Document` berada di bawah `Aspose.TeX`, sementara opsi dan perangkat berada di `Aspose.TeX.Rendering`.

Kelas `Document` adalah objek tingkat atas yang merepresentasikan satu dokumen TeX dalam memori.  

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using Aspose.TeX.ResourceProviders;
using System.IO;
using System.Text;
```

## Langkah 1: buat penyedia format

`FormatProvider` memberi tahu mesin di mana file format yang telah dikompilasi (`customtex.fmt`) berada. Ganti `"Your Output Directory"` dengan jalur absolut yang berisi format khusus Anda.

`FormatProvider` adalah pembungkus ringan yang memuat file `.fmt` sekali dan menggunakannya kembali untuk setiap konversi, secara dramatis meningkatkan kinerja untuk pekerjaan batch.

```csharp
using (FormatProvider formatProvider =
    new FormatProvider(new InputFileSystemDirectory("Your Output Directory"), "customtex"))
{
```

## Langkah 2: konfigurasikan opsi konversi (dan atur direktori input tex)

Di sini kita membuat instance `TeXOptions`. Properti `InputWorkingDirectory` **mengatur direktori input tex** sehingga mesin dapat menemukan file pendukung apa pun seperti paket khusus atau font.

`TeXOptions` juga memungkinkan Anda menentukan perangkat output, ukuran halaman, dan kualitas rendering. Untuk generasi skala besar, Anda dapat mengaktifkan `EnableParallelProcessing` untuk mempercepat rendering pada server multi‑core.

```csharp
    TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX(formatProvider));
    options.JobName = "typeset-with-custom-format";
    options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
    options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

## Langkah 3: jalankan pekerjaan

Sekarang berikan string TeX sederhana ke mesin, pilih perangkat output (XPS pada contoh ini), dan eksekusi pekerjaan. `TeXEngine` membaca format khusus, memproses sumber, dan menulis hasil ke perangkat yang dipilih.

`TeXEngine` adalah prosesor inti Aspose.TeX yang mem-parsing sumber TeX, menerapkan format khusus, dan menyalurkan halaman yang dirender ke perangkat yang Anda tentukan.

```csharp
    new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
        "Congratulations! You have successfully typeset this text with your own TeX format!\\end")),
        new XpsDevice(), options).Run();
```

## Langkah 4: poles output terminal

Menambahkan baris kosong setelah pekerjaan selesai membuat log konsol lebih mudah dibaca, terutama ketika Anda menumpuk beberapa konversi dalam skrip.

`Console.WriteLine()` menulis satu baris teks ke aliran output standar. Ini hanya digunakan untuk pemisahan visual; tidak memengaruhi dokumen yang dihasilkan.

```csharp
    options.TerminalOut.Writer.WriteLine();
}
// ExEnd:TypesetWithCustomTeXFormat
```

Selamat! Anda kini **telah membuat format tex khusus** dan menggunakannya untuk **pembuatan dokumen tex** di .NET. Anda dapat mengganti `XpsDevice` dengan `PdfDevice`, `PngDevice`, atau perangkat lain yang didukung sesuai kebutuhan penyampaian Anda.

## Masalah umum dan solusi

| Masalah | Penyebab | Solusi |
|-------|--------|-----|
| *“File format tidak ditemukan”* | Jalur `FormatProvider` salah | Pastikan `"Your Output Directory"` berisi `customtex.fmt` dan jalurnya absolut atau relatif dengan benar terhadap executable. |
| *“Tidak dapat menemukan file input”* | `InputWorkingDirectory` mengarah ke folder yang salah | Pastikan `"Your Input Directory"` berisi file sumber TeX atau Anda mengirimkan sumber sebagai stream (seperti pada contoh). |
| *Output terminal berantakan* | Ketidaksesuaian encoding | Gunakan `Encoding.UTF8` jika sumber TeX Anda mengandung karakter non‑ASCII. |
| *File XPS kosong* | Pekerjaan tidak dijalankan karena pengecualian sebelumnya | Periksa konsol untuk pesan error; biasanya menunjukkan paket yang hilang atau kesalahan sintaks dalam string TeX. |

## Pertanyaan yang sering diajukan

**T1: Bisakah saya menggunakan Aspose.TeX untuk .NET bersama perpustakaan Aspose lainnya?**  
J: Ya, Aspose.TeX terintegrasi mulus dengan Aspose.PDF, Aspose.Words, dan produk Aspose lainnya untuk pipeline dokumen end‑to‑end.

**T2: Apakah ada percobaan gratis untuk Aspose.TeX untuk .NET?**  
J: Ya, Anda dapat mengunduh percobaan dari **halaman unduhan percobaan Aspose.TeX** (https://releases.aspose.com/tex/net/).

**T3: Bagaimana cara mendapatkan dukungan untuk Aspose.TeX untuk .NET?**  
J: Kunjungi [forum Aspose.TeX](https://forum.aspose.com/c/tex/47) untuk bantuan komunitas atau jelajahi opsi premium pada **halaman pembelian dukungan premium** (https://purchase.aspose.com/buy).

**T4: Apakah lisensi sementara tersedia untuk Aspose.TeX untuk .NET?**  
J: Ya, ajukan permintaan pada **halaman permintaan lisensi sementara** (https://purchase.aspose.com/temporary-license/).

**T5: Di mana saya dapat menemukan referensi API resmi?**  
J: Dokumentasi lengkap tersedia di **dokumentasi referensi API** (https://reference.aspose.com/tex/net/).

### Tambahan Q&A

**T: Bisakah saya menghasilkan PDF alih-alih XPS?**  
J: Tentu saja. Ganti `new XpsDevice()` dengan `new PdfDevice()` dan sesuaikan jalur outputnya.

**T: Apakah saya harus meng‑kompilasi ulang file format setelah setiap perubahan?**  
J: Ya. Setiap modifikasi makro atau pengaturan mesin memerlukan menjalankan kembali `tex -ini` untuk menghasilkan file `.fmt` yang baru.

## Kesimpulan

Aspose.TeX untuk .NET menyediakan solusi **kuat dan berperforma tinggi untuk pembuatan dokumen tex**, memungkinkan Anda **membuat format tex khusus**, mengatur **direktori input tex**, dan mengekspor ke perangkat apa pun yang didukung. Integrasikan langkah‑langkah di atas ke dalam pipeline CI/CD Anda, otomatisasi pembuatan laporan skala besar, atau bangun mesin publikasi khusus yang memenuhi standar branding organisasi Anda.

---

**Terakhir diperbarui:** 2026-10-19  
**Diuji dengan:** Aspose.TeX 24.11 untuk .NET  
**Penulis:** Aspose

## Tutorial Terkait

- [Dapatkan Stream File TeX (C#) Menggunakan Aspose.TeX API Direktori Input yang Diperlukan](/tex/net/advanced-io/required-input-directory-csharp/)
- [Cara Membuat PDF dengan Aspose.TeX untuk .NET – Langkah demi Langkah](/tex/net/pdf-output/)
- [Cara membuat dokumen XPS .NET – Konversi TeX ke Output XPS dengan Aspose.TeX untuk .NET](/tex/net/xps-output/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}