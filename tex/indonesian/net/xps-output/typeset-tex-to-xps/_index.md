---
date: 2025-12-30
description: Pelajari cara mengonversi TeX ke XPS di .NET menggunakan Aspose.TeX.
  Ikuti panduan langkah demi langkah ini untuk integrasi yang mulus dan output yang
  dapat diandalkan.
linktitle: How to Convert TeX to XPS in .NET
second_title: Aspose.TeX .NET API
title: Cara Mengonversi TeX ke XPS di .NET
url: /id/net/xps-output/typeset-tex-to-xps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengonversi TeX ke XPS di .NET

## Cara Mengonversi TeX ke XPS – Pendahuluan

Selamat datang di panduan komprehensif langkah‑demi‑langkah kami tentang **cara mengonversi TeX** menjadi format XPS dalam lingkungan .NET. Dengan menggunakan library Aspose.TeX yang kuat, Anda dapat mengintegrasikan konversi TeX‑ke‑XPS ke dalam aplikasi .NET apa pun—baik itu alat desktop, layanan web, atau pipeline pelaporan otomatis. Pada bagian‑bagian berikut kami akan menelusuri setiap pengaturan yang diperlukan, menampilkan kode yang tepat, dan menjelaskan mengapa setiap bagian penting, sehingga Anda dapat mengimplementasikan solusi dengan percaya diri.

## Jawaban Cepat
- **Apa yang dibahas dalam tutorial ini?** Converting TeX files to XPS using Aspose.TeX for .NET.  
- **Versi .NET mana yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi komersial diperlukan untuk produksi.  
- **Berapa lama implementasinya?** Biasanya kurang dari 15 menit untuk konversi dasar.  
- **Di mana saya dapat mendapatkan library?** Download from the official Aspose.TeX release page.

## Prasyarat

Sebelum kita masuk ke tutorial, pastikan Anda telah menyiapkan prasyarat berikut:

- Aspose.TeX untuk .NET: Pastikan Anda telah menginstal library Aspose.TeX. Anda dapat mengunduhnya [di sini](https://releases.aspose.com/tex/net/).

- Dokumentasi: Biasakan diri Anda dengan library dengan merujuk ke dokumentasi [di sini](https://reference.aspose.com/tex/net/).

- Direktori Input dan Output: Siapkan direktori input dan output Anda sesuai dengan contoh kode.

Sekarang semua sudah siap, mari lanjutkan dengan panduan langkah‑demi‑langkah.

## Impor Namespace

Dalam aplikasi .NET Anda, mulailah dengan mengimpor namespace yang diperlukan. Ini memastikan Anda memiliki akses ke fungsionalitas Aspose.TeX yang dibutuhkan untuk typesetting TeX ke XPS.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
```

## Langkah 1: Atur Opsi Konversi

Definisikan opsi konversi, menentukan format ObjectTeX pada ekstensi mesin ObjectTeX. Juga, atur nama pekerjaan, direktori input dan output, serta detail output terminal.

```csharp
// Create conversion options for default ObjectTeX format upon ObjectTeX engine extension.
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
// Specify a job name.
options.JobName = "external-file-stream";
// Specify a file system working directory for input.
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
// Specify a file system working directory for output.
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
// Specify that the terminal output must be written to a file in the output working directory.
// The file name is <job_name>.trm.
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## Langkah 2: Buat Stream Dokumen XPS

Buka stream untuk menulis dokumen XPS yang telah typeset. Nama file tidak harus sama dengan nama pekerjaan.

```csharp
using (Stream stream = File.Open(Path.Combine("Your Output Directory", options.JobName + ".xps"), FileMode.Create))
```

## Langkah 3: Jalankan Pekerjaan TeX

Inisiasi dan jalankan pekerjaan TeX, menentukan nama dokumen, XpsDevice, dan opsi konversi.

```csharp
new TeXJob("hello-world", new XpsDevice(stream), options).Run();
```

Selamat! Anda telah berhasil typeset TeX ke XPS di .NET menggunakan Aspose.TeX. Silakan jelajahi lebih banyak fitur dan opsi sesuai kebutuhan spesifik Anda.

## Kesimpulan

Dalam tutorial ini, kami membahas langkah‑langkah penting untuk mengonversi dokumen TeX ke format XPS secara mulus di .NET menggunakan Aspose.TeX. Dengan mengikuti panduan ini, Anda telah memperoleh wawasan berharga tentang kemampuan library dan cara memanfaatkannya untuk proyek Anda.

## FAQ

### Q1: Apakah Aspose.TeX kompatibel dengan .NET Core?
A1: Ya, Aspose.TeX sepenuhnya kompatibel dengan .NET Core.

### Q2: Bisakah saya menggunakan Aspose.TeX untuk proyek komersial?
A2: Tentu saja! Aspose.TeX tersedia untuk penggunaan komersial maupun pribadi.

### Q3: Di mana saya dapat menemukan contoh dan sumber daya tambahan?
A3: Jelajahi dokumentasi Aspose.TeX [di sini](https://reference.aspose.com/tex/net/) untuk contoh lebih banyak dan sumber daya detail.

### Q4: Bagaimana cara mendapatkan dukungan untuk Aspose.TeX?
A4: Kunjungi forum dukungan Aspose.TeX [di sini](https://forum.aspose.com/c/tex/47) untuk mendapatkan bantuan dari komunitas.

### Q5: Apakah ada versi percobaan gratis yang tersedia?
A5: Ya, Anda dapat mengakses versi percobaan gratis [di sini](https://releases.aspose.com/).

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menyesuaikan output XPS (misalnya ukuran halaman atau margin)?**  
A: Ya. Anda dapat menyesuaikan pengaturan XpsDevice atau memodifikasi sumber TeX untuk mengontrol tata letak halaman sebelum konversi.

**Q: Apa yang terjadi jika file TeX input mengandung kesalahan?**  
A: Proses konversi menulis detail kesalahan ke file output terminal (`*.trm`). Tinjau file ini untuk mendiagnosis dan memperbaiki masalah.

**Q: Apakah memungkinkan mengonversi beberapa file TeX dalam satu kali jalankan?**  
A: Anda dapat melakukan loop pada koleksi file sumber TeX, membuat TeXJob terpisah untuk masing‑masing sambil menggunakan kembali instance `TeXOptions` yang sama.

**Q: Apakah Aspose.TeX mendukung paket LaTeX seperti `amsmath` atau `graphicx`?**  
A: Sebagian besar paket LaTeX standar didukung. Periksa dokumentasi resmi untuk daftar lengkap paket yang kompatibel.

**Q: Bagaimana cara menyematkan font dalam file XPS yang dihasilkan?**  
A: Aspose.TeX secara otomatis menyematkan font yang digunakan oleh mesin TeX. Pastikan font yang diperlukan terinstal pada mesin yang menjalankan konversi.

---

**Terakhir Diperbarui:** 2025-12-30  
**Diuji Dengan:** Aspose.TeX for .NET 24.11  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}