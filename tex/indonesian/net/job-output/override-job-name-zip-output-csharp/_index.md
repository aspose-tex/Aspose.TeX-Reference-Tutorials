---
date: 2025-12-21
description: Pelajari cara mengonversi TeX ke PDF, mengganti nama pekerjaan, dan menulis
  output terminal ke file ZIP menggunakan Aspose.TeX untuk .NET. Hasilkan PDF dari
  TeX dengan C#.
linktitle: Convert TeX to PDF and Override Job Name – Write Output to ZIP (C#)
second_title: Aspose.TeX .NET API
title: Konversi TeX ke PDF dan Ganti Nama Pekerjaan – Tulis Output ke ZIP (C#)
url: /id/net/job-output/override-job-name-zip-output-csharp/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mengonversi TeX ke PDF dan Menimpa Nama Pekerjaan – Menulis Output ke ZIP (C#)

## Pendahuluan

Dalam tutorial ini Anda akan belajar **cara mengonversi TeX ke PDF** sekaligus menimpa nama pekerjaan dan menangkap output terminal di dalam arsip ZIP. Aspose.TeX untuk .NET memudahkan pembuatan PDF dari TeX, memberi Anda kontrol penuh atas konfigurasi pekerjaan dan penanganan output. Baik Anda mengotomatisasi pembuatan laporan maupun membangun pipeline penerbitan berbasis TeX, langkah‑langkah di bawah ini akan membawa Anda dari sumber TeX biasa ke file PDF siap pakai yang disimpan dalam kontainer ZIP.

## Jawaban Cepat
- **Apa yang dibahas dalam tutorial ini?** Mengonversi TeX ke PDF, menimpa nama pekerjaan TeX, dan menulis output terminal ke file ZIP menggunakan C#.
- **Pustaka mana yang diperlukan?** Aspose.TeX untuk .NET (solusi “membuat PDF menggunakan Aspose”).
- **Apakah saya memerlukan lisensi?** Lisensi sementara dapat digunakan untuk pengujian; lisensi penuh diperlukan untuk produksi.
- **Apa saja prasyarat utama?** Lingkungan pengembangan .NET, Aspose.TeX terpasang, serta file ZIP input/output.
- **Berapa lama implementasinya?** Sekitar 10–15 menit setelah lingkungan disiapkan.

## Apa itu “convert tex to pdf”?
Mengonversi TeX ke PDF berarti mengambil dokumen sumber TeX dan memprosesnya dengan mesin TeX untuk menghasilkan tampilan PDF. Aspose.TeX menyediakan API .NET terkelola yang melakukan konversi ini tanpa memerlukan distribusi TeX eksternal.

## Mengapa Menimpa Nama Pekerjaan?
Menimpa nama pekerjaan memungkinkan Anda mengontrol nama dasar yang digunakan untuk file bantu (mis., *.log, *.aux) dan untuk aliran output apa pun yang Anda alihkan. Hal ini sangat berguna ketika Anda menjalankan beberapa pekerjaan di direktori kerja yang sama atau ketika Anda memerlukan skema penamaan file yang dapat diprediksi untuk proses lanjutan.

## Prasyarat

- Familiaritas dengan C# dan pengembangan .NET.
- Aspose.TeX untuk .NET terpasang (melalui NuGet atau paket manual).
- Arsip ZIP input yang berisi file sumber TeX.
- Arsip ZIP kosong yang akan menerima output terminal.

## Impor Namespace

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Pdf;
using System.IO;
```

## Cara Mengonversi TeX ke PDF dan Menimpa Nama Pekerjaan

Berikut adalah panduan langkah demi langkah yang memandu Anda membuka aliran ZIP, mengkonfigurasi opsi konversi, menjalankan pekerjaan TeX, dan menyelesaikan ZIP output.

### Langkah 1: Buka Aliran ZIP Input dan Output

```csharp
using (Stream inZipStream = File.Open(Path.Combine("Your Input Directory", "zip-in.zip"), FileMode.Open))
using (Stream outZipStream = File.Open(Path.Combine("Your Output Directory", "terminal-out-to-zip.zip"), FileMode.Create))
{
    // Code for step 1 goes here
}
```

*Penjelasan*: Pernyataan `using` memastikan kedua aliran dibuang dengan benar. ZIP input (`zip-in.zip`) berisi sumber TeX, sementara ZIP output (`terminal-out-to-zip.zip`) akan menyimpan log terminal yang dihasilkan selama konversi.

### Langkah 2: Atur Opsi Konversi (termasuk **menimpa nama pekerjaan**)

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
options.JobName = "terminal-output-to-zip";
options.InputWorkingDirectory = new InputZipDirectory(inZipStream, "in");
options.OutputWorkingDirectory = new OutputZipDirectory(outZipStream);
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

*Penjelasan*:  
- `JobName` diatur ke `"terminal-output-to-zip"` – ini menimpa nama pekerjaan default.  
- `InputWorkingDirectory` dan `OutputWorkingDirectory` menunjuk ke aliran ZIP, memungkinkan Aspose.TeX membaca/menulis langsung dari arsip.  
- `TerminalOut` mengalihkan output konsol mesin TeX ke file di dalam ZIP output.

### Langkah 3: Tentukan Opsi Penyimpanan (menghasilkan PDF dari TeX)

```csharp
options.SaveOptions = new PdfSaveOptions();
```

*Penjelasan*: `PdfSaveOptions` memberi tahu Aspose.TeX untuk menghasilkan file PDF sebagai output akhir.

### Langkah 4: Jalankan Pekerjaan TeX

```csharp
new TeXJob("hello-world", new PdfDevice(), options).Run();
```

*Penjelasan*: Konstruktor `TeXJob` menerima nama file TeX utama (`hello-world.tex`), perangkat target (`PdfDevice`), dan `options` yang telah dikonfigurasi sebelumnya. Memanggil `.Run()` memulai proses konversi.

### Langkah 5: Selesaikan Arsip ZIP Output

```csharp
((OutputZipDirectory)options.OutputWorkingDirectory).Finish();
```

*Penjelasan*: Panggilan ini mengosongkan data yang tertunda dan menutup ZIP output dengan benar, memastikan log terminal dan PDF yang dihasilkan tersimpan dengan tepat.

## Masalah Umum & Pemecahan Masalah

| Gejala | Penyebab Kemungkinan | Solusi |
|---------|----------------------|--------|
| PDF tidak dibuat | `options.SaveOptions` tidak disetel | Verifikasi Langkah 3 telah dijalankan. |
| Log terminal kosong | `options.TerminalOut` tidak ditetapkan | Pastikan Langkah 2 menyertakan baris `TerminalOut`. |
| Kesalahan “File tidak ditemukan” | Jalur ke ZIP input tidak benar | Periksa kembali jalur file pada Langkah 1. |
| Nama pekerjaan tidak tercermin di file bantu | Kesalahan penulisan `options.JobName` | Pastikan nama properti tepat `JobName`. |

## Pertanyaan yang Sering Diajukan

### Q1: Apakah saya dapat menggunakan Aspose.TeX untuk .NET dengan bahasa .NET lain seperti VB.NET?
**A:** Ya, Aspose.TeX untuk .NET kompatibel dengan semua bahasa .NET, termasuk VB.NET, F#, dan C#.

### Q2: Di mana saya dapat menemukan dokumentasi lebih lanjut untuk Aspose.TeX untuk .NET?
**A:** Visit the [documentation](https://reference.aspose.com/tex/net/) for detailed information.

### Q3: Bagaimana saya dapat memperoleh lisensi sementara untuk Aspose.TeX?
**A:** Obtain a [temporary license](https://purchase.aspose.com/temporary-license/) for testing purposes.

### Q4: Apakah ada forum komunitas untuk dukungan Aspose.TeX?
**A:** Yes, join the [Aspose.TeX forum](https://forum.aspose.com/c/tex/47) for community support.

### Q5: Di mana saya dapat membeli Aspose.TeX untuk .NET?
**A:** You can buy Aspose.TeX [here](https://purchase.aspose.com/buy).

### Q6: Apakah pendekatan ini bekerja pada .NET Core / .NET 5+?
**A:** Absolutely. Aspose.TeX supports .NET Framework, .NET Core, and .NET 5/6+. Just reference the appropriate NuGet package.

### Q7: Bisakah saya menyesuaikan output PDF (mis., menambahkan metadata)?
**A:** Yes. After conversion, you can use Aspose.PDF or the `PdfSaveOptions` properties to embed metadata, set compression levels, or modify page settings.

## Kesimpulan

Anda sekarang memiliki contoh lengkap yang siap produksi yang **mengonversi TeX ke PDF**, **menimpa nama pekerjaan**, dan **menulis output terminal ke dalam arsip ZIP** menggunakan Aspose.TeX untuk .NET. Silakan sesuaikan jalur, nama pekerjaan, atau format output sesuai alur kerja Anda.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Terakhir Diperbarui:** 2025-12-21  
**Diuji Dengan:** Aspose.TeX 24.12 untuk .NET  
**Penulis:** Aspose