---
date: 2026-03-26
description: Naučte se, jak vytvořit XPS z TeXu pomocí Aspose.TeX pro .NET, spravovat
  vstup/výstup souborového systému a generovat vysoce kvalitní XPS dokumenty.
linktitle: Create XPS from TeX with Filesystems – Aspose.TeX for .NET
second_title: Aspose.TeX .NET API
title: Vytvořte XPS z TeXu pomocí souborových systémů – Aspose.TeX pro .NET
url: /cs/net/file-input-output/filesystem-input-xps-output/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření XPS z TeX pomocí souborových systémů – Aspose.TeX pro .NET

## Úvod

Vítejte! V tomto tutoriálu se naučíte **jak vytvořit XPS z TeX** při práci se vstupem a výstupem souborového systému pomocí Aspose.TeX pro .NET. Ať už vytváříte dávkový procesor, webovou službu nebo desktopový nástroj, níže uvedené kroky vás provedou konfigurací enginu, nasměrováním na vaše soubory a vytvořením XPS dokumentů, které vypadají přesně jako původní LaTeX zdroj.

Rozdělíme proces do přehledných číslovaných kroků, vysvětlíme „proč“ za každým řádkem kódu a poskytneme vám praktické tipy, které můžete okamžitě použít.

## Rychlé odpovědi
- **Co znamená „vytvořit XPS z TeX“?** Jedná se o konfiguraci úlohy Aspose.TeX, která čte soubory TeX a zapisuje výsledek jako XPS dokument.  
- **Potřebuji licenci?** Dočasná licence je k dispozici pro testování; plná licence je vyžadována pro produkci.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Mohu změnit výstupní formát?** Ano – nahraďte `XpsDevice` jiným zařízením (PDF, PNG, atd.).  
- **Je vyžadován výstup do konzole?** Ne – můžete použít paměťový terminál pro tichý běh.

## Jak vytvořit XPS z TeX pomocí Aspose.TeX

Vytvoření úlohy TeX, která výstupuje XPS, znamená inicializaci enginu Aspose.TeX, určení, kde má číst zdrojové soubory, a směrování vykreslených stránek do XPS balíčku. XPS (XML Paper Specification) je formát s pevnou rozvržením, který zachovává typografii a vektorovou grafiku, což jej činí ideálním pro tisk nebo další konverzi.

## Co je „create tex job xps“?

Vytvoření úlohy TeX, která výstupuje XPS, znamená inicializaci enginu Aspose.TeX, určení, kde má číst zdrojové soubory, a směrování vykreslených stránek do XPS balíčku. XPS (XML Paper Specification) je formát s pevnou rozvržením, který zachovává typografii a vektorovou grafiku, což jej činí ideálním pro tisk nebo další konverzi.

## Proč použít Aspose.TeX pro výstup XPS?

- **Vysoká věrnost:** Engine reprodukuje rozvržení LaTeX přesně v XPS.  
- **Žádné externí závislosti:** Čistá .NET knihovna, není potřeba nativní instalace LaTeX.  
- **Flexibilní I/O:** Funguje s adresáři souborového systému, paměťovými proudy nebo vlastními poskytovateli.  
- **Škálovatelné:** Vhodné pro konverze jedné souboru i hromadné zpracování.

## Předpoklady

Než se pustíme dál, ujistěte se, že máte následující:

- **Aspose.TeX pro .NET** – stáhněte nejnovější verzi z [Aspose website](https://releases.aspose.com/tex/net/).  
- **Vývojové prostředí .NET** – Visual Studio, Rider nebo VS Code s .NET SDK.  
- **Vstupní a výstupní složky** – vytvořte dva adresáře ve svém počítači (např. `C:\TeX\Input` a `C:\TeX\Output`).  
- **Licence (volitelná pro testování)** – můžete získat dočasnou licenci z Aspose portálu.

## Importování jmenných prostorů

Nejprve načtěte požadované jmenné prostory, abyste mohli přistupovat k pomocníkům souborového systému a XPS zařízení.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

Tyto jmenné prostory poskytují `InputFileSystemDirectory`, `OutputFileSystemDirectory` a `XpsDevice`, které jsou nezbytné pro workflow **create XPS from TeX**.

## Krok 1: Vytvoření možností konverze

Začínáme vytvořením objektu `TeXOptions`, který říká engine použít konfiguraci ObjectTeX (výchozí pro většinu LaTeX zdrojů).

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

> **Tip:** `ConsoleAppOptions` nastavuje rozumné výchozí hodnoty pro aplikace typu console, ale můžete možnosti později upravit podle potřeby.

## Krok 2: Specifikace vstupních a výstupních adresářů

Nasmerujte engine na složky, které jste připravili dříve. Nahraďte zástupné řetězce skutečnými cestami ve vašem počítači.

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Nyní úloha TeX ví, kde najít soubory `.tex` a kam uložit vygenerované XPS soubory.

## Krok 3: Výběr výstupního terminálu

Terminál určuje, kam se zapisují stavové zprávy. Pro rychlé ladění zůstaneme u konzole, ale můžete přepnout na paměťový terminál pro tiché spuštění.

```csharp
options.TerminalOut = new OutputConsoleTerminal(); // Default value. Arbitrary assignment.
```

> **Proč je to důležité:** Použití konzolového terminálu vám poskytne okamžitou zpětnou vazbu o varováních nebo chybách kompilace, což urychluje řešení problémů.

## Krok 4: Spuštění úlohy TeX

Vytvořte instanci `TeXJob`, dejte jí přátelský název, připojte `XpsDevice` a spusťte ji.

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

Po dokončení `Run()` najdete soubor `hello-world.xps` ve výstupním adresáři.

## Krok 5: Doladění výstupu do konzole

Přidání prázdného řádku po dokončení úlohy usnadní čtení konzolového logu, zejména když spouštíte více úloh najednou.

```csharp
options.TerminalOut.Writer.WriteLine();
```

## Běžné případy použití

| Scénář | Proč XPS? | Jak úryvek pomáhá |
|----------|----------|-----------------------|
| **Dávková konverze akademických prací** | Zachovat přesné rozvržení pro archivní tisk. | Přístup založený na souborovém systému vám umožní nasměrovat na složku s `.tex` soubory a vytvořit odpovídající sadu XPS souborů. |
| **Webová služba, která renderuje LaTeX za běhu** | XPS lze streamovat přímo do prohlížečů, které jej podporují. | Výměnou `XpsDevice` za paměťový proud můžete dokument vrátit bez zápisu na disk. |
| **Desktop publishing nástroj** | Potřebujete náhled s pevnou rozvržením před konverzí do PDF. | Stejnou úlohu lze později propojit s PDF zařízením pro finální distribuci. |

## Běžné problémy a řešení

| Problém | Příčina | Řešení |
|-------|-------|-----|
| **XPS soubor je prázdný** | Cesta k výstupnímu adresáři je nesprávná nebo není zapisovatelná. | Ověřte cestu předanou `OutputFileSystemDirectory` a zajistěte, aby proces měl oprávnění k zápisu. |
| **Chyby kompilace** | LaTeX zdroj používá balíčky, které nejsou součástí ObjectTeX. | Přepněte na konfiguraci plného TeX enginu (`TeXConfig.FullTeX()`) nebo přidejte chybějící soubory balíčků do vstupního adresáře. |
| **Konzole se zasekne** | Terminál čeká na vstup kvůli interaktivním výzvám. | Použijte `OutputMemoryTerminal` k potlačení interaktivních výzev v automatizovaných skriptech. |

## Často kladené otázky

**Q1: Mohu použít jiný výstupní formát místo XPS?**  
A1: Ano, Aspose.TeX podporuje PDF, PNG, SVG a další formáty. Nahraďte `new XpsDevice()` odpovídající třídou zařízení (např. `new PdfDevice()`).

**Q2: Je k dispozici dočasná licence pro testovací účely?**  
A2: Ano, můžete získat dočasnou licenci pro testování z [tohoto odkazu](https://purchase.aspose.com/temporary-license/).

**Q3: Kde mohu najít další dokumentaci?**  
A3: Odkazujte se na [dokumentaci Aspose.TeX pro .NET](https://reference.aspose.com/tex/net/) pro podrobné informace.

**Q4: Jak mohu získat podporu komunity nebo klást otázky?**  
A4: Navštivte [forum Aspose.TeX](https://forum.aspose.com/c/tex/47) pro podporu komunity a diskuze.

**Q5: Existují nějaké ukázkové projekty?**  
A5: Prozkoumejte repozitář Aspose.TeX na GitHubu pro ukázkové projekty a úryvky kódu.

## Závěr

Po provedení výše uvedených kroků nyní víte, jak **vytvořit XPS z TeX** pomocí Aspose.TeX pro .NET, spravovat vstupní a výstupní složky a doladit proces pro vývojové i produkční scénáře. Klidně experimentujte s dalšími výstupními zařízeními, integrujte tuto logiku do větších pracovních postupů nebo automatizujte dávkové konverze.

---

**Poslední aktualizace:** 2026-03-26  
**Testováno s:** Aspose.TeX 24.11 for .NET (latest at time of writing)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}