---
title: Přepsat název úlohy a zapsat výstup terminálu na disk (C#)
linktitle: Přepsat název úlohy a zapsat výstup terminálu na disk (C#)
second_title: Aspose.TeX .NET API
description: Prozkoumejte, jak používat Aspose.TeX pro .NET k přepsání názvů úloh a zachycení výstupu z terminálu. Postupujte podle našeho komplexního průvodce pro bezproblémovou správu souborů TeX.
weight: 10
url: /cs/net/job-output/override-job-name-disk-output-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přepsat název úlohy a zapsat výstup terminálu na disk (C#)

## Úvod

Vítejte v tomto podrobném návodu k použití Aspose.TeX pro .NET k přepsání názvů úloh a zápisu terminálového výstupu na disk v programovacím jazyce C#. Aspose.TeX for .NET je výkonná knihovna, která vám umožňuje bezproblémově pracovat se soubory TeX, a v tomto tutoriálu se zaměříme na konkrétní úkol: přepsání názvů úloh a zachycení výstupu z terminálu.

## Předpoklady

Než se pustíme do výukového programu, ujistěte se, že máte splněny následující předpoklady:

-  Knihovna Aspose.TeX for .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.TeX for .NET. Můžete si jej stáhnout z[Web Aspose.TeX](https://releases.aspose.com/tex/net/).

- Vývojové prostředí .NET: Mějte funkční vývojové prostředí .NET, včetně integrovaného vývojového prostředí (IDE), jako je Visual Studio.

- Základní znalost C#: Seznamte se se základy programovacího jazyka C#.

- Vstupní a výstupní adresáře: Připravte vstupní a výstupní adresáře pro vaše soubory TeX.

## Importovat jmenné prostory

Ujistěte se, že ve svém kódu C# obsahuje potřebné jmenné prostory pro přístup k funkcím Aspose.TeX:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

## Krok 1: Vytvořte možnosti převodu

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

Vytvořte TeXOptions pomocí ConsoleAppOptions, specifikujte ObjectTeX jako TeXConfig.

## Krok 2: Zadejte název úlohy

```csharp
options.JobName = "overridden-job-name";
```

Zadejte název úlohy, který má přepsat výchozí název.

## Krok 3: Zadejte pracovní adresář vstupu

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

Nastavte vstupní pracovní adresář pro vaše soubory TeX.

## Krok 4: Zadejte výstupní pracovní adresář

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Definujte výstupní pracovní adresář pro uložení zpracovaných souborů TeX.

## Krok 5: Zapište výstup terminálu na disk

```csharp
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

Nakonfigurujte výstup terminálu tak, aby byl zapsán do souboru ve výstupním adresáři.

## Krok 6: Spusťte úlohu

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

Vytvořte TeXJob, zadejte název úlohy, výstupní zařízení (XpsDevice) a možnosti. Nakonec spusťte úlohu.

## Závěr

Gratulujeme! Úspěšně jste se naučili, jak přepsat názvy úloh a zapsat výstup terminálu na disk pomocí Aspose.TeX for .NET v C#. Tato schopnost je cenná pro efektivní správu úloh zpracování TeXu.

## FAQ

### Q1: Mohu používat Aspose.TeX pro .NET s jinými knihovnami .NET?

Odpověď 1: Ano, Aspose.TeX pro .NET lze bez problémů integrovat s jinými knihovnami .NET.

### Q2: Je k dispozici bezplatná zkušební verze pro Aspose.TeX pro .NET?

 A2: Ano, můžete si stáhnout bezplatnou zkušební verzi[tady](https://releases.aspose.com/).

### Q3: Jak mohu získat podporu pro Aspose.TeX pro .NET?

 A3: Navštivte[Fórum Aspose.TeX](https://forum.aspose.com/c/tex/47) získat komunitu a podporu.

### Q4: Jsou dostupné dočasné licence pro Aspose.TeX pro .NET?

 A4: Ano, můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).

### Q5: Kde najdu dokumentaci k Aspose.TeX pro .NET?

 A5: Dokumentace je k dispozici[tady](https://reference.aspose.com/tex/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
