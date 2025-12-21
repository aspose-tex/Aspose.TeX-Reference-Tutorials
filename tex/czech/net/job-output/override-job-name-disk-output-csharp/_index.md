---
date: 2025-12-21
description: Naučte se zachytit výstup konzole v C# pomocí Aspose.TeX, přepsat název
  úlohy, nastavit vstupní adresář TeX a zapsat výstup terminálu do souboru.
linktitle: Capture Console Output C# – Override Job Name & Write Output to Disk
second_title: Aspose.TeX .NET API
title: Zachycení výstupu konzole v C# – Přepsání názvu úlohy a zápis výstupu na disk
url: /cs/net/job-output/override-job-name-disk-output-csharp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zachycení výstupu konzole C# – Přepsání názvu úlohy a zápis výstupu terminálu na disk (C#)

## Introduction

V tomto krok‑za‑krokem průvodci se naučíte **jak zachytit výstup konzole C#** při práci s Aspose.TeX pro .NET. Přepsáním názvu úlohy a nasměrováním výstupu terminálu do souboru získáte plnou kontrolu nad pipeline zpracování TeX—ideální pro automatizované sestavení, scénáře CI/CD nebo jakoukoli situaci, kdy potřebujete zaznamenat proud konzole pro pozdější analýzu.

## Quick Answers
- **Co znamená „capture console output C#“?** Přesměrovává standardní proud terminálu generovaný Aspose.TeX do souboru, který určíte.  
- **Proč přepsat název úlohy?** Přepsání zajišťuje předvídatelná jména souborů a zabraňuje kolizím při spuštění více úloh.  
- **Která třída Aspose.TeX zapisuje výstup?** `OutputFileTerminal` (používá se přes `options.TerminalOut`).  
- **Mohu nastavit vlastní vstupní složku TeX?** Ano — použijte `options.InputWorkingDirectory` k **nastavení vstupního adresáře TeX**.  
- **Je tento přístup kompatibilní s .NET Core?** Naprosto; stejné API funguje jak na .NET Framework, tak na .NET Core.

## What is “capture console output C#” in the context of Aspose.TeX?
Zachycení výstupu konzole znamená převzít vše, co by se normálně zobrazilo v okně terminálu (logovací zprávy, varování, podrobnosti o kompilaci) a zapsat to do trvalého souboru. To je zvláště užitečné při ladění rozsáhlých projektů TeX nebo při integraci zpracování TeX do automatizovaných pracovních postupů.

## Why override the job name and write terminal output to a file?
- **Předvídatelná jména souborů:** Přepsání názvu úlohy vám umožní rozhodnout o základním jménu všech generovaných souborů, což usnadňuje psaní skriptů pro následné zpracování.  
- **Auditovatelnost:** Uložení logu terminálu vám poskytuje kompletní auditní stopu procesu kompilace TeX.  
- **Paralelní provádění:** Při současném spouštění několika úloh unikátní názvy úloh zabraňují kolizím souborů.  

## Prerequisites

- Aspose.TeX pro .NET knihovna: Ujistěte se, že máte nainstalovanou knihovnu Aspose.TeX pro .NET. Můžete si ji stáhnout z [webu Aspose.TeX](https://releases.aspose.com/tex/net/).
- .NET vývojové prostředí: Mějte funkční .NET vývojové prostředí, včetně integrovaného vývojového prostředí (IDE) jako je Visual Studio.
- Základní znalosti C#: Znalost základů programovacího jazyka C#.
- Vstupní a výstupní adresáře: Připravte vstupní a výstupní adresáře pro vaše soubory TeX.

## Import Namespaces

Ve vašem C# kódu se ujistěte, že zahrnujete potřebné jmenné prostory pro přístup k funkcím Aspose.TeX:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

## Step 1: Create Conversion Options

Nejprve vytvoříme instanci `TeXOptions`, která Aspose.TeX informuje, že běžíme ve scénáři konzolové aplikace.

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

Vytvořte `TeXOptions` s `ConsoleAppOptions`, přičemž jako `TeXConfig` specifikujete `ObjectTeX`.

## Step 2: Specify Job Name (Override Default)

Přepsání názvu úlohy nám dává kontrolu nad základním jménem všech generovaných artefaktů.

```csharp
options.JobName = "overridden-job-name";
```

Zadejte název úlohy, aby přepsal výchozí jméno.

## Step 3: Set TeX Input Directory

Řekněte Aspose.TeX, kde najde vaše zdrojové soubory `.tex`. Toto je krok **nastavení vstupního adresáře TeX**.

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

Nastavte pracovní vstupní adresář pro vaše soubory TeX.

## Step 4: Specify Output Working Directory

Definujte, kam budou uloženy zpracované soubory a zachycený log konzole.

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Definujte výstupní pracovní adresář pro uložení zpracovaných souborů TeX.

## Step 5: Write Terminal Output to File

Nyní nasměrujeme proud konzole do fyzického souboru ve výstupním adresáři. Tím splníme požadavek **zápisu výstupu terminálu do souboru**.

```csharp
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

Nakonfigurujte výstup terminálu tak, aby byl zapisován do souboru ve výstupním adresáři.

## Step 6: Run the Job

Nakonec vytvoříme `TeXJob` s přepsaným názvem úlohy, výstupním zařízením XPS a konfigurovanými možnostmi. Spuštěním úlohy se vygeneruje soubor XPS a zachytí log konzole.

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

Vytvořte `TeXJob`, specifikujte název úlohy, výstupní zařízení (`XpsDevice`) a možnosti. Nakonec úlohu spusťte.

## Common Issues & Troubleshooting

| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| Žádný výstupní soubor nebyl vytvořen | Cesta k výstupnímu adresáři je nesprávná nebo chybí oprávnění k zápisu | Ověřte, že `options.OutputWorkingDirectory` ukazuje na platný adresář a proces má právo zapisovat. |
| Log terminálu je prázdný | `TerminalOut` není nastaven nebo je později přepsán | Ujistěte se, že `options.TerminalOut = new OutputFileTerminal(...);` je vykonáno před `job.Run();`. |
| Úloha selhala s chybou „soubor nenalezen“ | Vstupní adresář není nastaven správně | Zkontrolujte znovu cestu předanou do `InputFileSystemDirectory` a že `.tex` soubory v tomto adresáři existují. |

## Frequently Asked Questions

### Q1: Can I use Aspose.TeX for .NET with other .NET libraries?

Ano, Aspose.TeX pro .NET lze bez problémů integrovat s dalšími .NET knihovnami.

### Q2: Is there a free trial available for Aspose.TeX for .NET?

Ano, můžete si stáhnout verzi zdarma [zde](https://releases.aspose.com/).

### Q3: How can I get support for Aspose.TeX for .NET?

Navštivte [forum Aspose.TeX](https://forum.aspose.com/c/tex/47) pro komunitní podporu.

### Q4: Are temporary licenses available for Aspose.TeX for .NET?

Ano, můžete získat dočasnou licenci [zde](https://purchase.aspose.com/temporary-license/).

### Q5: Where can I find the documentation for Aspose.TeX for .NET?

Dokumentace je k dispozici [zde](https://reference.aspose.com/tex/net/).

## Conclusion

Gratulujeme! Úspěšně jste se naučili **zachytit výstup konzole C#** přepsáním názvu úlohy, nastavením vstupního adresáře TeX a zápisem výstupu terminálu do souboru pomocí Aspose.TeX pro .NET. Tato technika zjednodušuje logování, zlepšuje sledovatelnost a činí automatizované pipeline zpracování TeX robustnějšími.

---

**Poslední aktualizace:** 2025-12-21  
**Testováno s:** Aspose.TeX 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}