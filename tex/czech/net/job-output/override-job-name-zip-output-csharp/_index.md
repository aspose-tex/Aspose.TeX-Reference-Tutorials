---
title: Přepsat název úlohy a zapsat výstup terminálu do Zip (C#)
linktitle: Přepsat název úlohy a zapsat výstup terminálu do Zip (C#)
second_title: Aspose.TeX .NET API
description: Naučte se, jak přepsat názvy úloh a zapsat výstup terminálu do souboru ZIP pomocí Aspose.TeX for .NET. Průvodce krok za krokem s příklady C#.
weight: 11
url: /cs/net/job-output/override-job-name-zip-output-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přepsat název úlohy a zapsat výstup terminálu do Zip (C#)

## Úvod

tomto tutoriálu prozkoumáme, jak přepsat název úlohy a zapsat výstup terminálu do souboru ZIP pomocí Aspose.TeX for .NET. Aspose.TeX je výkonná knihovna, která umožňuje vývojářům pracovat s TeXovými dokumenty v jejich aplikacích .NET. V tomto konkrétním příkladu se zaměříme na běžný úkol – zápis terminálového výstupu do souboru ZIP s možností přepsat název úlohy.

## Předpoklady

Než začneme, ujistěte se, že máte splněny následující předpoklady:

- Pracovní znalost C#
- Aspose.TeX pro .NET nainstalován
- Zadejte ZIP archiv pro pracovní adresář
- Výstupní ZIP archiv pro výstup terminálu

## Importovat jmenné prostory

Než se ponoříte do kódu, nezapomeňte do svého projektu C# zahrnout potřebné jmenné prostory:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Pdf;
using System.IO;
```

Nyní si tento příklad rozdělíme do několika kroků, které vás celým procesem provedou.

## Krok 1: Otevřete vstupní a výstupní ZIP streamy

```csharp
using (Stream inZipStream = File.Open(Path.Combine("Your Input Directory", "zip-in.zip"), FileMode.Open))
using (Stream outZipStream = File.Open(Path.Combine("Your Output Directory", "terminal-out-to-zip.zip"), FileMode.Create))
{
    // Zde je kód pro krok 1
}
```

## Krok 2: Nastavte možnosti převodu

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
options.JobName = "terminal-output-to-zip";
options.InputWorkingDirectory = new InputZipDirectory(inZipStream, "in");
options.OutputWorkingDirectory = new OutputZipDirectory(outZipStream);
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## Krok 3: Definujte možnosti uložení

```csharp
options.SaveOptions = new PdfSaveOptions();
```

## Krok 4: Spusťte TeX Job

```csharp
new TeXJob("hello-world", new PdfDevice(), options).Run();
```

## Krok 5: Dokončete výstupní archiv ZIP

```csharp
((OutputZipDirectory)options.OutputWorkingDirectory).Finish();
```

## Závěr

Gratulujeme! Úspěšně jste se naučili, jak přepsat název úlohy a zapsat výstup terminálu do souboru ZIP pomocí Aspose.TeX for .NET. Tato technika může být neuvěřitelně užitečná při práci s dokumenty TeX ve vašich aplikacích C#.

## FAQ

### Q1: Mohu používat Aspose.TeX pro .NET s jinými jazyky .NET, jako je VB.NET?

Odpověď 1: Ano, Aspose.TeX for .NET je kompatibilní se všemi jazyky .NET.

### Q2: Kde najdu další dokumentaci k Aspose.TeX pro .NET?

 A2: Navštivte[dokumentace](https://reference.aspose.com/tex/net/) pro podrobné informace.

### Q3: Jak mohu získat dočasnou licenci pro Aspose.TeX?

 A3: Získejte a[dočasná licence](https://purchase.aspose.com/temporary-license/) pro testovací účely.

### Q4: Existuje komunitní fórum pro podporu Aspose.TeX?

 A4: Ano, připojte se[Fórum Aspose.TeX](https://forum.aspose.com/c/tex/47) za podporu komunity.

### Q5: Kde mohu zakoupit Aspose.TeX pro .NET?

 A5: Můžete si koupit Aspose.TeX[tady](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
