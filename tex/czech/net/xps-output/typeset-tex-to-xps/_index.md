---
title: Sazba TeXu na XPS v .NET
linktitle: Sazba TeXu na XPS v .NET
second_title: Aspose.TeX .NET API
description: Bez námahy převádějte TeXové dokumenty na XPS v .NET pomocí Aspose.TeX. Prozkoumejte našeho podrobného průvodce pro bezproblémovou integraci.
weight: 10
url: /cs/net/xps-output/typeset-tex-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Sazba TeXu na XPS v .NET

## Úvod

Vítejte v našem podrobném průvodci o sazbě TeXu na XPS v .NET pomocí výkonné knihovny Aspose.TeX. Pokud hledáte bezproblémový převod dokumentů TeX do formátu XPS ve vašich aplikacích .NET, jste na správném místě. V tomto tutoriálu vás provedeme celým procesem a rozebereme každý krok, abychom zajistili hladkou implementaci.

## Předpoklady

Než se pustíme do výukového programu, ujistěte se, že máte splněny následující předpoklady:

-  Aspose.TeX for .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.TeX. Můžete si jej stáhnout[tady](https://releases.aspose.com/tex/net/).

- Dokumentace: Seznamte se s knihovnou podle dokumentace[tady](https://reference.aspose.com/tex/net/).

- Vstupní a výstupní adresáře: Nastavte své vstupní a výstupní adresáře, jak je uvedeno v příkladu kódu.

Nyní, když máte vše nastaveno, pojďme pokračovat s průvodcem krok za krokem.

## Importovat jmenné prostory

Ve své aplikaci .NET začněte importováním potřebných jmenných prostorů. Tím je zajištěno, že máte přístup k funkcím Aspose.TeX potřebným pro sazbu TeXu na XPS.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
```

## Krok 1: Nastavte možnosti převodu

Definujte možnosti převodu, specifikujte formát ObjectTeX na rozšíření enginu ObjectTeX. Nastavte také název úlohy, vstupní a výstupní adresáře a podrobnosti o výstupu na terminál.

```csharp
// Vytvořte možnosti převodu pro výchozí formát ObjectTeX na rozšíření enginu ObjectTeX.
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
// Zadejte název úlohy.
options.JobName = "external-file-stream";
// Zadejte pracovní adresář systému souborů pro vstup.
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
// Zadejte pracovní adresář systému souborů pro výstup.
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
// Určete, že výstup terminálu musí být zapsán do souboru ve výstupním pracovním adresáři.
// Název souboru je <job_name>.trm.
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## Krok 2: Vytvořte stream dokumentů XPS

Otevřete stream a napište vysázený dokument XPS. Název souboru nemusí být nutně stejný jako název úlohy.

```csharp
using (Stream stream = File.Open(Path.Combine("Your Output Directory", options.JobName + ".xps"), FileMode.Create))
```

## Krok 3: Spusťte TeX Job

Spusťte a spusťte úlohu TeX, zadejte název dokumentu, XpsDevice a možnosti převodu.

```csharp
new TeXJob("hello-world", new XpsDevice(stream), options).Run();
```

Gratulujeme! Úspěšně jste vysázeli TeX na XPS v .NET pomocí Aspose.TeX. Neváhejte a prozkoumejte další funkce a možnosti na základě vašich konkrétních požadavků.

## Závěr

V tomto tutoriálu jsme se zabývali základními kroky pro bezproblémový převod TeXových dokumentů do formátu XPS v .NET pomocí Aspose.TeX. Sledováním tohoto průvodce jste získali cenné poznatky o možnostech knihovny a o tom, jak je využít pro své projekty.

## FAQ

### Q1: Je Aspose.TeX kompatibilní s .NET Core?

A1: Ano, Aspose.TeX je plně kompatibilní s .NET Core.

### Q2: Mohu použít Aspose.TeX pro komerční projekty?

A2: Rozhodně! Aspose.TeX je k dispozici pro komerční i osobní použití.

### Q3: Kde najdu další příklady a zdroje?

 A3: Prozkoumejte dokumentaci Aspose.TeX[tady](https://reference.aspose.com/tex/net/)pro další příklady a podrobné zdroje.

### Q4: Jak mohu získat podporu pro Aspose.TeX?

 A4: Navštivte fórum podpory Aspose.TeX[tady](https://forum.aspose.com/c/tex/47) získat pomoc od komunity.

### Q5: Je k dispozici bezplatná zkušební verze?

 A5: Ano, máte přístup k bezplatné zkušební verzi[tady](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
