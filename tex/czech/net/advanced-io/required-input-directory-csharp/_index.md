---
date: 2026-03-24
description: Naučte se, jak v C# získat stream souboru při zadávání požadovaného vstupu
  pro Aspose.TeX .NET. Postupujte podle našeho krok‑za‑krokem průvodce.
linktitle: Get File Stream C# in Aspose.TeX Required Input Directory
second_title: Aspose.TeX .NET API
title: Získat souborový stream C# v Aspose.TeX požadovaný vstupní adresář
url: /cs/net/advanced-io/required-input-directory-csharp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Získání souborového proudu C# v Aspose.TeX – Požadovaný vstupní adresář

## Úvod

Pokud potřebujete **získat souborový proud C#** při práci s Aspose.TeX, prvním krokem je informovat knihovnu, kde se nacházejí vaše zdrojové soubory TeX. Tento tutoriál vás provede přesný kód, který potřebujete k **specifikaci požadovaného vstupu** pro engine Aspose.TeX, převádějící složku s `.tex` soubory na proud, který API může konzumovat. Na konci tohoto průvodce budete mít znovupoužitelnou třídu `RequiredInputDirectory`, která čistě propojuje váš souborový systém s Aspose.TeX.

## Rychlé odpovědi
- **Co znamená “get file stream C#”?** Znamená to vrácení objektu `System.IO.Stream` pro požadovaný název souboru.  
- **Proč musím specifikovat požadovaný vstup?** Aspose.TeX prohledává vstupní adresář pro soubory TeX; bez něj engine nemůže rozpoznat příkazy `\include{}` nebo `\input{}`.  
- **Které jmenné prostory jsou povinné?** `Aspose.TeX.IO`, `System.Collections.Generic` a `System.IO`.  
- **Je potřeba nějaká speciální licence?** Pro produkční použití je vyžadována vývojová nebo zkušební licence Aspose.TeX.  
- **Mohu třídu znovu použít v různých projektech?** Ano — po zkompilování funguje s jakýmkoli .NET projektem, který odkazuje na Aspose.TeX.

## Co je get file stream C#?

V .NET je *souborový proud* objekt odvozený od `System.IO.Stream`, který poskytuje čtení/zápis k surovým bajtům souboru. Když Aspose.TeX požaduje soubor, očekává, že vrátíte takový proud, aby engine mohl číst zdroj TeX přímo z paměti nebo disku.

## Proč specifikovat požadovaný vstup pro Aspose.TeX?

Aspose.TeX zpracovává TeX dokumenty tím, že vyhledává pomocné soubory (obrázky, soubory stylů, zahrnuté TeX soubory) relativně k **požadovanému vstupnímu adresáři**. Tím, že tento adresář explicitně definujete, můžete:
1. Předejít chybám „soubor nenalezen“ během kompilace.  
2. Udržet logiku přístupu k souborům ve vašem projektu oddělenou od zbytku kódu.  
3. Usnadnit jednotkové testování pomocí mockování vstupního adresáře.

## Požadavky

- **Aspose.TeX for .NET Library** – stáhněte ji ze [stránky vydání](https://releases.aspose.com/tex/net/).  
- **.NET Development Environment** – Visual Studio 2022, Rider nebo jakékoli IDE, které podporuje .NET 6+.

Nyní importujeme jmenné prostory, které budete potřebovat.

## Import jmenných prostor

Přidejte tyto `using` příkazy na začátek vašeho C# souboru, aby kompilátor mohl najít požadované typy:

```csharp
using Aspose.TeX.IO;
using System.Collections.Generic;
using System.IO;
```

## Jak získat souborový proud C# s požadovaným vstupním adresářem

Níže je podrobný krok‑za‑krokem rozpis třídy `RequiredInputDirectory`. Každý krok obsahuje krátké vysvětlení následované přesným blokem kódu, který byste měli zkopírovat do svého projektu.

### Krok 1: Vytvořte třídu `RequiredInputDirectory`

Třída implementuje dvě rozhraní — `IInputWorkingDirectory` (používáno Aspose.TeX k vyhledávání souborů) a `IFileCollector` (používáno k shromažďování názvů souborů při jejich přidávání).

```csharp
public class RequiredInputDirectory : IInputWorkingDirectory, IFileCollector
{
    private Dictionary<string, Dictionary<string, string>> _fileNames =
        new Dictionary<string, Dictionary<string, string>>();

    public RequiredInputDirectory()
    {
    }
```

### Krok 2: Implementujte metodu `StoreFileName`

Tato metoda zaznamenává každý název souboru, který předáte kolektoru, a seskupuje je podle jejich přípony pro rychlé vyhledávání.

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

### Krok 3: Implementujte rozhraní `IInputWorkingDirectory` — GetFile

Když Aspose.TeX požaduje soubor, tato metoda vrací **souborový proud** (nebo `null`, pokud proud zpracováváte jinde). Výstup `fullName` informuje engine o přesné cestě, kterou vyřešil.

```csharp
public Stream GetFile(string fileName, out string fullName, bool searchSubdirectories = false)
{
    fullName = fileName;
    return null; // Here we actually return a stream for the file requested by its name.
}
```

### Krok 4: Shromážděte kolekce souborů podle přípony

Engine může požádat o všechny soubory s určitou příponou (např. „.tex“). Tato metoda vrací tyto názvy jako pole řetězců.

```csharp
public string[] GetFileNamesByExtension(string extension, string path = null)
{
    Dictionary<string, string> files;
    if (!_fileNames.TryGetValue(extension, out files))
        return new string[0];

    return new List<string>(files.Values).ToArray();
}
```

### Krok 5: Uvolnění prostředků

Vyčištění vnitřního slovníku zabraňuje únikům paměti, zejména když je třída používána v dlouhodobých službách.

```csharp
public void Dispose()
{
    _fileNames.Clear();
}
```

S těmito pěti úryvky nyní máte plně funkční třídu `RequiredInputDirectory`, která **získává souborový proud C#**‑styl a **specifikuje požadovaný vstup** pro procesor Aspose.TeX.

## Časté problémy a řešení

| Problém | Proč se to děje | Rychlé řešení |
|---------|----------------|---------------|
| `GetFile` vrací `null` a kompilace selže | Metoda je zástupná; musíte otevřít skutečný `FileStream`, pokud chcete, aby engine četl soubor. | Nahraďte `return null;` za `return File.OpenRead(fullName);` (ujistěte se, že cesta je správná). |
| Soubory nejsou nalezeny, i když existují | Kolektor nedostal správné názvy souborů nebo přípony. | Zavolejte `StoreFileName` pro každý soubor **před** předáním adresáře Aspose.TeX. |
| Spotřeba paměti stoupá při mnoha velkých `.tex` souborech | Slovník uchovává všechny názvy souborů v paměti. | Uvolněte `RequiredInputDirectory` hned po dokončení zpracování, nebo použijte streamingový přístup. |

## Často kladené otázky

**Q: Kde mohu najít dokumentaci k Aspose.TeX pro .NET?**  
A: Dokumentace je dostupná [zde](https://reference.aspose.com/tex/net/).

**Q: Jak si mohu stáhnout knihovnu Aspose.TeX pro .NET?**  
A: Knihovnu můžete stáhnout ze [stránky vydání](https://releases.aspose.com/tex/net/).

**Q: Kde mohu získat podporu pro Aspose.TeX pro .NET?**  
A: Navštivte [forum Aspose.TeX](https://forum.aspose.com/c/tex/47) pro komunitní podporu.

**Q: Je k dispozici bezplatná zkušební verze?**  
A: Ano, bezplatnou zkušební verzi můžete prozkoumat [zde](https://releases.aspose.com/).

**Q: Jak mohu získat dočasnou licenci pro Aspose.TeX pro .NET?**  
A: Dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).

## Další často kladené otázky

**Q: Mohu tuto třídu použít v .NET Core projektu?**  
A: Rozhodně — `IInputWorkingDirectory` a `IFileCollector` jsou platformově agnostické.

**Q: Musím adresář s Aspose.TeX registrovat ručně?**  
A: Ano, předáte instanci `RequiredInputDirectory` do konstruktoru `TeXDocument` nebo příslušného API volání.

**Q: Jaké verze .NET jsou podporovány?**  
A: Aspose.TeX funguje s .NET 5, .NET 6 a novějšími, stejně jako s .NET Framework 4.6.2+.

---

**Poslední aktualizace:** 2026-03-24  
**Testováno s:** Aspose.TeX 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}