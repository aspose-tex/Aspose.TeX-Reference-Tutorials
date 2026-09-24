---
date: 2026-09-24
description: Pelajari cara mengonfigurasi direktori input TeX, aliran, gambar, dan
  input terminal menggunakan Aspose.TeX untuk .NET dalam C#.
keywords:
- configure tex input directory
- add image stream tex
- add images from stream
lastmod: 2026-09-24
linktitle: Input dan Output Aspose.TeX Lanjutan
og_description: Konfigurasikan direktori input TeX, tambahkan aliran gambar, dan tangani
  input terminal dengan Aspose.TeX untuk .NET dalam C#. Pelajari langkah demi langkah.
og_image_alt: Guide showing how to configure TeX input directory and streams in Aspose.TeX
  for .NET
og_title: Konfigurasikan direktori input TeX – Panduan Aspose.TeX Lanjutan
schemas:
- author: Aspose
  dateModified: '2026-09-24'
  description: Learn how to configure TeX input directory, streams, images, and terminal
    input using Aspose.TeX for .NET in C#.
  headline: Configure TeX input directory – Advanced Aspose.TeX Input and Output
  type: TechArticle
- description: Learn how to configure TeX input directory, streams, images, and terminal
    input using Aspose.TeX for .NET in C#.
  name: Configure TeX input directory – Advanced Aspose.TeX Input and Output
  steps:
  - name: instantiate TeXInputOptions
    text: Assign the base folder that holds the primary TeX source.
  - name: add extra search paths
    text: If your project stores figures in a separate folder (e.g., *Images*), call
      `AddSearchPath` to include it.
  - name: hand the options to the processor
    text: Create a `TeXProcessor`, provide the configured options, and invoke `Process`
      or `Render`.
  type: HowTo
- questions:
  - answer: Yes—you can create a new `TeXInputOptions` instance with a different `BaseFolder`
      and pass it to a fresh `TeXProcessor` whenever you need to reconfigure.
    question: Can I change the input directory at runtime?
  - answer: Retrieve the image as a `byte[]`, wrap it in a `MemoryStream`, and call
      `TeXInputOptions.AddImage("image.png", stream)`. The name must match the reference
      in your `.tex` file.
    question: How do I add images that are stored in a database?
  - answer: Absolutely. Convert the incoming string to a `MemoryStream`, set it as
      the source for `TeXProcessor`, and render directly to your desired output format.
    question: Is it possible to process LaTeX code received from a web API without
      saving a file?
  - answer: Dispose of any streams you create, and for large workloads invoke `TeXProcessor.Cleanup()`
      to free native resources.
    question: Do I need to call any cleanup methods after processing?
  - answer: The two tutorial links above contain full code samples that demonstrate
      each scenario in detail, including error handling and performance tips.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.TeX .NET API
tags:
- Aspose.TeX
- input directory
- C# document processing
title: Konfigurasikan direktori input TeX – Input dan Output Aspose.TeX Lanjutan
url: /id/net/advanced-io/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konfigurasikan Direktori Input TeX di Aspose.TeX untuk .NET

Aspose.TeX untuk .NET memungkinkan Anda menyematkan pemrosesan TeX lengkap langsung ke dalam aplikasi C# Anda. Dalam tutorial ini Anda akan belajar cara **mengonfigurasi direktori input TeX**, memberi umpan konten LaTeX dari aliran, dan menambahkan gambar tanpa menyentuh sistem file. Jika Anda memerlukan kontrol yang tepat tentang di mana mesin mencari file `.tex` dan sumber daya, Anda berada di tempat yang tepat.

## Jawaban Cepat
- **Apa arti “configure tex input directory”?**  
  Itu memberi tahu Aspose.TeX di mana menemukan file `.tex` utama, file tambahan, dan grafik.
- **Kelas mana yang mendefinisikan jalur input?**  
  `TeXInputOptions` menyimpan folder dasar dan lokasi pencarian tambahan.
- **Bisakah saya memuat gambar dari aliran memori?**  
  Ya—gunakan `TeXInputOptions.AddImage` dengan instance `Stream`.
- **Apakah memungkinkan untuk mengompilasi kode LaTeX yang diberikan pada waktu berjalan?**  
  Tentu—lewatkan `MemoryStream` yang berisi teks sumber ke processor.
- **Apakah saya memerlukan lisensi untuk penggunaan produksi?**  
  Lisensi Aspose.TeX yang valid diperlukan untuk penyebaran non‑evaluasi.

## Apa itu TeXInputOptions?
`TeXInputOptions` adalah objek konfigurasi yang mendefinisikan folder dasar dan jalur pencarian tambahan untuk sumber daya TeX. Menyiapkannya dengan benar menghilangkan kesalahan “file not found” dan memungkinkan Anda menjaga aset terorganisir.

## Cara mengonfigurasi direktori input TeX?
`TeXInputOptions` adalah objek konfigurasi yang menentukan folder dasar dan jalur pencarian tambahan untuk sumber daya TeX. Muat dokumen utama Anda dan beri tahu processor di mana mencari semua hal dalam beberapa baris saja. Jawaban langsung ini menjelaskan langkah-langkah penting sebelum detail tambahan apa pun.

Buat instance `TeXInputOptions`, set `BaseFolder` ke folder yang berisi file `.tex` utama Anda, tambahkan sub‑folder apa pun yang menyimpan gambar atau file tambahan, dan berikan opsi tersebut ke `TeXProcessor`. Mesin kemudian akan menyelesaikan semua referensi relatif secara otomatis.

### Langkah 1: buat instance TeXInputOptions
Tetapkan folder dasar yang menyimpan sumber TeX utama.

### Langkah 2: tambahkan jalur pencarian tambahan
Jika proyek Anda menyimpan gambar dalam folder terpisah (mis., *Images*), panggil `AddSearchPath` untuk menyertakannya.

### Langkah 3: serahkan opsi ke processor
Buat `TeXProcessor`, berikan opsi yang telah dikonfigurasi, dan panggil `Process` atau `Render`.

## Cara menambahkan gambar dengan Aspose.TeX
Gambar yang direferensikan dalam file TeX dapat disediakan baik melalui folder maupun langsung dari aliran. Menyediakan aliran berguna ketika gambar disimpan dalam basis data atau dihasilkan secara dinamis. `AddImage(string name, Stream data)` mendaftarkan aliran gambar dengan nama file yang diberikan untuk digunakan dalam dokumen TeX. Metode ini memungkinkan Anda menghindari file sementara dan mempercepat pemrosesan.

## Cara memproses aliran dalam Aspose.TeX
Ketika sumber LaTeX Anda dihasilkan secara dinamis—mungkin dari masukan pengguna atau layanan web—Anda dapat memberi makan langsung ke processor tanpa menulis file. `TeXProcessor` memproses konten TeX dan dapat menerima `MemoryStream` yang berisi kode LaTeX sumber. Bungkus string LaTeX dalam `MemoryStream`, setel sebagai aliran sumber di `TeXProcessor`, dan jalankan konversi. Teknik ini bekerja sama baiknya untuk layanan cloud‑native di mana I/O disk mahal.

## Mengapa menggunakan Aspose.TeX untuk I/O lanjutan?
Aspose.TeX mendukung **lebih dari 30 format input dan output** (termasuk PDF, PNG, SVG) dan dapat merender dokumen ratusan halaman tanpa memuat seluruh file ke memori. Desain berbasis aliran pertama mengurangi overhead I/O hingga 40 % dibandingkan alur kerja berbasis file, menjadikannya ideal untuk aplikasi server dengan throughput tinggi.

## Prasyarat
- .NET 6.0 atau lebih baru (perpustakaan juga berfungsi dengan .NET Core 3.1+ dan .NET Framework 4.6.1+)
- Paket NuGet Aspose.TeX untuk .NET (versi 24.11 atau lebih baru)
- Lisensi Aspose.TeX yang valid untuk penggunaan produksi

## Jelajahi Aspose.TeX: gerbang ke pemrosesan dokumen lanjutan
Untuk melihat konfigurasi dalam aksi, ikuti panduan langkah‑demi‑langkah kami **[Tentukan Direktori Input yang Diperlukan untuk Aspose.TeX (C#)](./required-input-directory-csharp/)**. Tutorial itu memandu Anda membuat objek `TeXInputOptions` dan merender output PDF.  
**[Tentukan Direktori Input yang Diperlukan untuk Aspose.TeX (C#)](./required-input-directory-csharp/)**

## Menguasai aliran, gambar, dan input terminal dalam Aspose.TeX untuk C#
Untuk pendalaman lebih lanjut tentang memberi umpan LaTeX dari memori, menambahkan gambar via aliran, dan menggunakan input bergaya terminal, lihat **[Kuasai Aliran, Gambar, & Input Terminal dalam Aspose.TeX untuk C#](./stream-input-image-output-terminal-input-csharp/)**. Itu menunjukkan cara mengintegrasikan Aspose.TeX ke dalam API web, layanan latar belakang, dan alat konsol.  
**[Kuasai Aliran, Gambar, & Input Terminal dalam Aspose.TeX untuk C#](./stream-input-image-output-terminal-input-csharp/)**

## Masalah umum dan solusi
- **Kesalahan “File not found”** – Pastikan `BaseFolder` mengarah ke direktori yang benar dan semua jalur pencarian tambahan ditambahkan sebelum rendering.
- **Gambar tidak dimuat** – Pastikan nama gambar di `AddImage` persis sama dengan nama yang digunakan dalam sumber TeX, termasuk ekstensi file.
- **Lonjakan penggunaan memori** – Saat memproses dokumen sangat besar, panggil `TeXProcessor.Cleanup()` setelah rendering untuk melepaskan sumber daya yang tidak dikelola.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya mengubah direktori input saat runtime?**  
A: Ya—Anda dapat membuat instance `TeXInputOptions` baru dengan `BaseFolder` yang berbeda dan memberikannya ke `TeXProcessor` baru setiap kali Anda perlu mengkonfigurasi ulang.

**Q: Bagaimana cara menambahkan gambar yang disimpan dalam basis data?**  
A: Ambil gambar sebagai `byte[]`, bungkus dalam `MemoryStream`, dan panggil `TeXInputOptions.AddImage("image.png", stream)`. Nama harus cocok dengan referensi di file `.tex` Anda.

**Q: Apakah memungkinkan memproses kode LaTeX yang diterima dari API web tanpa menyimpan file?**  
A: Tentu saja. Konversi string yang masuk ke `MemoryStream`, setel sebagai sumber untuk `TeXProcessor`, dan render langsung ke format output yang diinginkan.

**Q: Apakah saya perlu memanggil metode pembersihan apa pun setelah pemrosesan?**  
A: Hapus (dispose) semua aliran yang Anda buat, dan untuk beban kerja besar panggil `TeXProcessor.Cleanup()` untuk membebaskan sumber daya native.

**Q: Di mana saya dapat menemukan contoh yang lebih lanjutan?**  
A: Dua tautan tutorial di atas berisi contoh kode lengkap yang menunjukkan setiap skenario secara detail, termasuk penanganan kesalahan dan tips kinerja.

---

**Terakhir Diperbarui:** 2026-09-24  
**Diuji Dengan:** Aspose.TeX 24.11 untuk .NET  
**Penulis:** Aspose

## Tutorial Terkait

- [Dapatkan Aliran File TeX (C#) Menggunakan API Aspose.TeX (Direktori Input yang Diperlukan)](/tex/net/advanced-io/required-input-directory-csharp/)
- [Buat XPS dari TeX dengan Sistem File – Aspose.TeX untuk .NET](/tex/net/file-input-output/filesystem-input-xps-output/)
- [Konversi LaTeX ke PNG Menggunakan Aspose.TeX untuk .NET – Proses Input Sistem File & ZIP](/tex/net/file-input-output/required-inputs-from-filesystem-and-zip/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}