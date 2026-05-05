---
date: 2025-12-30
description: Naučte se, jak převést TeX na XPS v .NET pomocí Aspose.TeX. Postupujte
  podle tohoto krok‑za‑krokem průvodce pro bezproblémovou integraci a spolehlivý výstup.
linktitle: How to Convert TeX to XPS in .NET
second_title: Aspose.TeX .NET API
title: Jak převést TeX na XPS v .NET
url: /cs/net/xps-output/typeset-tex-to-xps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak převést TeX na XPS v .NET

## Jak převést TeX na XPS – Úvod

Vítejte v našem komplexním, krok‑za‑krokem průvodci, jak **převést TeX** dokumenty do formátu XPS v prostředí .NET. S využitím výkonné knihovny Aspose.TeX budete moci integrovat převod TeX‑na‑XPS do jakékoli .NET aplikace — ať už jde o desktopový nástroj, webovou službu nebo automatizovaný reportingový kanál. V následujících sekcích projdeme všechna potřebná nastavení, ukážeme vám přesný kód, který potřebujete, a vysvětlíme, proč je každá část důležitá, abyste mohli řešení implementovat s jistotou.

## Rychlé odpovědi
- **Co tento tutoriál pokrývá?** Převod souborů TeX na XPS pomocí Aspose.TeX pro .NET.  
- **Které verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro testování; pro produkční nasazení je vyžadována komerční licence.  
- **Jak dlouho trvá implementace?** Obvykle méně než 15 minut pro základní převod.  
- **Kde mohu získat knihovnu?** Stáhněte ji z oficiální stránky vydání Aspose.TeX.

## Předpoklady

Než se pustíme do tutoriálu, ujistěte se, že máte následující předpoklady připravené:

- Aspose.TeX pro .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.TeX. Můžete si ji stáhnout [zde](https://releases.aspose.com/tex/net/).

- Dokumentace: Seznamte se s knihovnou pomocí dokumentace [zde](https://reference.aspose.com/tex/net/).

- Vstupní a výstupní adresáře: Nastavte své vstupní a výstupní adresáře podle příkladu v kódu.

Nyní, když máte vše nastaveno, přejděme k průvodci krok za krokem.

## Importování jmenných prostorů

Ve vaší .NET aplikaci začněte importováním potřebných jmenných prostorů. Tím zajistíte přístup k funkcím Aspose.TeX potřebným pro sazbu TeX do XPS.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
```

## Krok 1: Nastavení možností převodu

Definujte možnosti převodu, specifikujte formát ObjectTeX na rozšíření engine ObjectTeX. Také nastavte název úlohy, vstupní a výstupní adresáře a podrobnosti výstupu terminálu.

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

## Krok 2: Vytvoření proudu XPS dokumentu

Otevřete proud pro zápis sazby XPS dokumentu. Název souboru nemusí být nutně stejný jako název úlohy.

```csharp
using (Stream stream = File.Open(Path.Combine("Your Output Directory", options.JobName + ".xps"), FileMode.Create))
```

## Krok 3: Spuštění TeX úlohy

Inicializujte a spusťte TeX úlohu, přičemž specifikujete název dokumentu, XpsDevice a možnosti převodu.

```csharp
new TeXJob("hello-world", new XpsDevice(stream), options).Run();
```

Gratulujeme! Úspěšně jste sazbu TeX do XPS v .NET pomocí Aspose.TeX dokončili. Neváhejte prozkoumat další funkce a možnosti podle vašich konkrétních požadavků.

## Závěr

V tomto tutoriálu jsme prošli nezbytné kroky pro bezproblémový převod TeX dokumentů do formátu XPS v .NET pomocí Aspose.TeX. Dodržením tohoto průvodce jste získali cenné poznatky o schopnostech knihovny a o tom, jak je využít ve svých projektech.

## Často kladené otázky

### Q1: Je Aspose.TeX kompatibilní s .NET Core?

A1: Ano, Aspose.TeX je plně kompatibilní s .NET Core.

### Q2: Mohu použít Aspose.TeX pro komerční projekty?

A2: Rozhodně! Aspose.TeX je k dispozici jak pro komerční, tak i osobní použití.

### Q3: Kde najdu další příklady a zdroje?

A3: Prozkoumejte dokumentaci Aspose.TeX [zde](https://reference.aspose.com/tex/net/) pro více příkladů a podrobné zdroje.

### Q4: Jak mohu získat podporu pro Aspose.TeX?

A4: Navštivte fórum podpory Aspose.TeX [zde](https://forum.aspose.com/c/tex/47) a získejte pomoc od komunity.

### Q5: Je k dispozici bezplatná zkušební verze?

A5: Ano, bezplatnou zkušební verzi můžete získat [zde](https://releases.aspose.com/).

## Často kladené otázky

**Q: Mohu přizpůsobit výstup XPS (např. velikost stránky nebo okraje)?**  
**A:** Ano. Můžete upravit nastavení XpsDevice nebo změnit zdrojový TeX kód, abyste před převodem ovládali rozvržení stránky.

**Q: Co se stane, pokud vstupní soubor TeX obsahuje chyby?**  
**A:** Proces převodu zapíše podrobnosti o chybách do souboru výstupu terminálu (`*.trm`). Prohlédněte tento soubor a diagnostikujte a opravte problémy.

**Q: Je možné převést více souborů TeX najednou?**  
**A:** Můžete iterovat přes kolekci zdrojových souborů TeX, vytvořit pro každý samostatný TeXJob a přitom znovu použít stejnou instanci `TeXOptions`.

**Q: Podporuje Aspose.TeX LaTeX balíčky jako `amsmath` nebo `graphicx`?**  
**A:** Většina standardních LaTeX balíčků je podporována. Pro úplný seznam kompatibilních balíčků si prohlédněte oficiální dokumentaci.

**Q: Jak vložit fonty do vygenerovaného XPS souboru?**  
**A:** Aspose.TeX automaticky vkládá fonty použité TeX engine. Ujistěte se, že požadované fonty jsou nainstalovány na počítači, který převod provádí.

---

**Last Updated:** 2025-12-30  
**Tested With:** Aspose.TeX for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}