---
date: 2026-03-24
description: Pelajari cara mendapatkan aliran file C# sambil menentukan input yang
  diperlukan untuk Aspose.TeX .NET. Ikuti panduan langkah demi langkah kami.
linktitle: Get File Stream C# in Aspose.TeX Required Input Directory
second_title: Aspose.TeX .NET API
title: Mendapatkan Stream File C# di Aspose.TeX Direktori Input yang Diperlukan
url: /id/net/advanced-io/required-input-directory-csharp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dapatkan File Stream C# di Aspose.TeX Direktori Input yang Diperlukan

## Pendahuluan

Jika Anda perlu **get file stream C#** saat bekerja dengan Aspose.TeX, langkah pertama adalah memberi tahu perpustakaan di mana file sumber TeX Anda berada. Tutorial ini memandu Anda melalui kode tepat yang diperlukan untuk **specify required input** bagi mesin Aspose.TeX, mengubah folder berisi file `.tex` menjadi stream yang dapat dikonsumsi oleh API. Pada akhir panduan ini Anda akan memiliki kelas `RequiredInputDirectory` yang dapat digunakan kembali dan menghubungkan sistem file Anda dengan Aspose.TeX secara bersih.

## Jawaban Cepat
- **Apa arti “get file stream C#”?** Artinya mengembalikan objek `System.IO.Stream` untuk nama file yang diminta.  
- **Mengapa saya harus specify required input?** Aspose.TeX mencari file TeX di direktori input; tanpa itu mesin tidak dapat menyelesaikan perintah `\include{}` atau `\input{}`.  
- **Namespace mana yang wajib?** `Aspose.TeX.IO`, `System.Collections.Generic`, dan `System.IO`.  
- **Apakah diperlukan lisensi khusus?** Lisensi pengembangan atau percobaan Aspose.TeX diperlukan untuk penggunaan produksi.  
- **Bisakah saya menggunakan kembali kelas ini di proyek lain?** Ya—setelah dikompilasi, kelas ini bekerja dengan proyek .NET apa pun yang merujuk ke Aspose.TeX.

## Apa itu get file stream C#?

Di .NET, *file stream* adalah objek yang diturunkan dari `System.IO.Stream` yang menyediakan akses baca/tulis ke byte mentah sebuah file. Ketika Aspose.TeX meminta sebuah file, ia mengharapkan Anda mengembalikan stream semacam itu sehingga mesin dapat membaca sumber TeX langsung dari memori atau disk.

## Mengapa menentukan input yang diperlukan untuk Aspose.TeX?

Aspose.TeX memproses dokumen TeX dengan menemukan file tambahan (gambar, file gaya, file TeX yang di‑include) relatif terhadap **direktori input yang diperlukan**. Dengan secara eksplisit mendefinisikan direktori ini Anda:

1. Menghindari kesalahan “file not found” selama kompilasi.  
2. Memisahkan logika akses file proyek Anda dari kode lainnya.  
3. Memungkinkan pengujian unit yang lebih mudah dengan mem‑mock direktori input.

## Prasyarat

- **Aspose.TeX for .NET Library** – unduh dari [release page](https://releases.aspose.com/tex/net/).  
- **Lingkungan Pengembangan .NET** – Visual Studio 2022, Rider, atau IDE apa pun yang mendukung .NET 6+.

Sekarang, mari impor namespace yang Anda perlukan.

## Impor Namespace

Tambahkan pernyataan `using` berikut di bagian atas file C# Anda agar kompiler dapat menemukan tipe yang diperlukan:

```csharp
using Aspose.TeX.IO;
using System.Collections.Generic;
using System.IO;
```

## Cara Mendapatkan File Stream C# dengan Direktori Input yang Diperlukan

Berikut adalah penjelasan langkah‑demi‑langkah kelas `RequiredInputDirectory`. Setiap langkah menyertakan penjelasan singkat diikuti oleh blok kode yang harus Anda salin ke proyek Anda.

### Langkah 1: Buat Kelas `RequiredInputDirectory`

Kelas ini mengimplementasikan dua antarmuka—`IInputWorkingDirectory` (digunakan Aspose.TeX untuk menemukan file) dan `IFileCollector` (digunakan untuk mengumpulkan nama file saat ditambahkan).

```csharp
public class RequiredInputDirectory : IInputWorkingDirectory, IFileCollector
{
    private Dictionary<string, Dictionary<string, string>> _fileNames =
        new Dictionary<string, Dictionary<string, string>>();

    public RequiredInputDirectory()
    {
    }
```

### Langkah 2: Implementasikan Metode `StoreFileName`

Metode ini mencatat setiap nama file yang Anda berikan ke kolektor, mengelompokkannya berdasarkan ekstensi untuk pencarian cepat.

```csharp
public void StoreFileName(string fileName)
{
    string extension = Path.GetExtension(fileName);
    string name = Path.GetFileNameWithoutExtension(fileName);

    Dictionary<string, string> files;
    if (!_fileNames.TryGetValue(extension, out files))
        _fileNames.Add(extension, files = new Dictionary<string, string>());

    files[name] = fileName;
}
```

### Langkah 3: Implementasikan Antarmuka IInputWorkingDirectory – GetFile

Ketika Aspose.TeX meminta sebuah file, metode ini mengembalikan **file stream** (atau `null` jika Anda menangani stream di tempat lain). Output `fullName` memberi tahu mesin jalur tepat yang telah diselesaikan.

```csharp
public Stream GetFile(string fileName, out string fullName, bool searchSubdirectories = false)
{
    fullName = fileName;
    return null; // Here we actually return a stream for the file requested by its name.
}
```

### Langkah 4: Kumpulkan Koleksi File berdasarkan Ekstensi

Mesin mungkin meminta semua file dengan ekstensi tertentu (misalnya “.tex”). Metode ini mengembalikan nama‑nama tersebut sebagai array string.

```csharp
public string[] GetFileNamesByExtension(string extension, string path = null)
{
    Dictionary<string, string> files;
    if (!_fileNames.TryGetValue(extension, out files))
        return new string[0];

    return new List<string>(files.Values).ToArray();
}
```

### Langkah 5: Buang Sumber Daya

Membersihkan kamus internal mencegah kebocoran memori, terutama ketika kelas ini digunakan dalam layanan yang berjalan lama.

```csharp
public void Dispose()
{
    _fileNames.Clear();
}
```

Dengan lima potongan kode ini Anda kini memiliki kelas `RequiredInputDirectory` yang berfungsi penuh dan **gets file stream C#**‑style serta **specifies required input** untuk prosesor Aspose.TeX.

## Masalah Umum dan Solusinya

| Masalah | Mengapa Terjadi | Perbaikan Cepat |
|-------|----------------|-----------|
| `GetFile` mengembalikan `null` dan kompilasi gagal | Metode ini hanya placeholder; Anda perlu membuka `FileStream` nyata jika mesin harus membaca file. | Ganti `return null;` dengan `return File.OpenRead(fullName);` (pastikan jalur sudah benar). |
| File tidak ditemukan meskipun ada | Kolektor tidak menerima nama file atau ekstensi yang tepat. | Panggil `StoreFileName` untuk setiap file **sebelum** mengirimkan direktori ke Aspose.TeX. |
| Penggunaan memori melonjak dengan banyak file `.tex` besar | Kamus menyimpan semua nama file di memori. | Buang `RequiredInputDirectory` segera setelah pemrosesan selesai, atau gunakan pendekatan streaming. |

## Pertanyaan yang Sering Diajukan

**T: Di mana saya dapat menemukan dokumentasi Aspose.TeX untuk .NET?**  
J: Dokumentasi tersedia [di sini](https://reference.aspose.com/tex/net/).

**T: Bagaimana cara mengunduh library Aspose.TeX untuk .NET?**  
J: Anda dapat mengunduh library dari [halaman rilis](https://releases.aspose.com/tex/net/).

**T: Di mana saya dapat mendapatkan dukungan untuk Aspose.TeX untuk .NET?**  
J: Kunjungi [forum Aspose.TeX](https://forum.aspose.com/c/tex/47) untuk dukungan komunitas.

**T: Apakah ada versi percobaan gratis?**  
J: Ya, Anda dapat menjelajahi versi percobaan gratis [di sini](https://releases.aspose.com/).

**T: Bagaimana cara memperoleh lisensi sementara untuk Aspose.TeX untuk .NET?**  
J: Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

## Pertanyaan Tambahan yang Sering Diajukan

**T: Bisakah saya menggunakan kelas ini dalam proyek .NET Core?**  
J: Tentu—`IInputWorkingDirectory` dan `IFileCollector` bersifat platform‑agnostik.

**T: Apakah saya harus mendaftarkan direktori secara manual ke Aspose.TeX?**  
J: Ya, berikan instance `RequiredInputDirectory` ke konstruktor `TeXDocument` atau panggilan API yang relevan.

**T: Versi .NET apa saja yang didukung?**  
J: Aspose.TeX bekerja dengan .NET 5, .NET 6, dan yang lebih baru, serta .NET Framework 4.6.2+.

---

**Last Updated:** 2026-03-24  
**Tested With:** Aspose.TeX 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}