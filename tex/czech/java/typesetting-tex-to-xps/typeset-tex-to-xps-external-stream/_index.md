---
date: 2025-12-11
description: Naučte se, jak převést TeX na XPS v Javě pomocí Aspose.TeX. Tento krok‑za‑krokem
  průvodce vám ukáže, jak efektivně generovat XPS dokumentové proudy.
linktitle: How to Convert TeX to XPS in Java with External Stream
second_title: Aspose.TeX Java API
title: Jak převést TeX na XPS v Javě s externím proudem
url: /cs/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak převést TeX na XPS v Javě s externím streamem

## Úvod

Pokud potřebujete **převést TeX** soubory na vysoce kvalitní XPS výstup z Java aplikace, Aspose.TeX for Java to usnadňuje. V tomto tutoriálu uvidíte přesně **jak převést TeX** na XPS dokument pomocí externího výstupního streamu, což je ideální, když chcete výsledek přímo přesměrovat do odpovědi, cloudové úložiště nebo jakéhokoli vlastního cíle. Projděme celý proces, od nastavení prostředí až po zápis finálního XPS souboru.

## Rychlé odpovědi
- **Co tento tutoriál pokrývá?** Převod TeX na XPS pomocí Aspose.TeX s externím streamem.  
- **Která hlavní knihovna je vyžadována?** Aspose.TeX for Java.  
- **Potřebuji licenci?** Pro produkční použití je vyžadována dočasná nebo plná licence.  
- **Mohu generovat XPS dokumentové streamy?** Ano – příklad zapisuje XPS přímo do `OutputStream`.  
- **Jaká verze Javy je podporována?** Jakýkoli JDK 8+ (v tutoriálu je použito JDK 11 jako reference).

## Požadavky

Než se ponoříte do kódu, ujistěte se, že máte následující:

- Java Development Kit (JDK): Ujistěte se, že máte Javu nainstalovanou ve vašem systému. Můžete si ji stáhnout [zde](https://www.oracle.com/java/technologies/javase-downloads.html).
- Aspose.TeX for Java: Stáhněte a nainstalujte Aspose.TeX for Java. Odkaz ke stažení najdete [zde](https://releases.aspose.com/tex/java/).

## Import balíčků

Začněte importováním potřebných balíčků, abyste zahájili převod TeX‑na‑XPS. Vložte následující úryvek kódu do vašeho Java projektu:

```java
package com.aspose.tex.TypesetXpsWrittenToExternalStream;

import java.io.FileOutputStream;
import java.io.IOException;
import java.io.OutputStream;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

## Krok 1: Nastavení možností převodu

Začněte vytvořením možností převodu pro výchozí formát ObjectTeX pomocí následujícího kódu:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

Tím se nastaví základ pro proces sazby.

## Krok 2: Určení názvu úlohy a adresářů

Definujte název úlohy a nastavte vstupní a výstupní pracovní adresáře:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Ujistěte se, že nahradíte zástupné symboly jako „Your Input Directory“ skutečnými cestami k adresářům.

## Krok 3: Nastavení výstupu terminálu

Určete, že výstup terminálu má být zapsán do souboru ve výstupním pracovním adresáři:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

Tento krok zajišťuje zachycení podrobných logů pro ladění.

## Krok 4: Otevření výstupního streamu

Otevřete stream pro zápis sazebního XPS dokumentu:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

Nahraďte „Your Output Directory“ vhodnou cestou.

## Krok 5: Spuštění úlohy

Spusťte úlohu převodu TeX na XPS:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

Tím se proces dokončí a v určeném výstupním adresáři najdete vygenerovaný XPS dokument.

## Časté problémy a řešení

| Problém | Proč se stane | Jak opravit |
|---------|----------------|-------------|
| **FileNotFoundException** při otevírání streamu | Cesta k výstupnímu adresáři je nesprávná nebo neexistuje. | Ověřte cestu, vytvořte adresář předem, nebo použijte `Files.createDirectories`. |
| **NullPointerException** na `options.getOutputWorkingDirectory()` | `setOutputWorkingDirectory` nebyla zavolána nebo vrátila `null`. | Ujistěte se, že zavoláte `options.setOutputWorkingDirectory` před jejím použitím. |
| **LicenseException** za běhu | Spuštění bez platné licence Aspose.TeX. | Použijte dočasnou nebo trvalou licenci pomocí `License license = new License(); license.setLicense("Aspose.TeX.lic");`. |

## Často kladené otázky

**Q: Mohu použít Aspose.TeX for Java s jinými formáty dokumentů?**  
A: Aspose.TeX se primárně zaměřuje na zpracování dokumentů souvisejících s TeX. Pro jiné formáty prozkoumejte rozsáhlou produktovou řadu Aspose.

**Q: Je k dispozici zkušební verze?**  
A: Ano, můžete vyzkoušet Aspose.TeX stažením bezplatné zkušební verze [zde](https://releases.aspose.com/).

**Q: Kde najdu komplexní dokumentaci?**  
A: Odkaz na dokumentaci [zde](https://reference.aspose.com/tex/java/) poskytuje podrobné informace a příklady.

**Q: Jak získám podporu nebo pomoc?**  
A: Navštivte fórum Aspose.TeX [zde](https://forum.aspose.com/c/tex/47) pro komunitní podporu a diskuse.

**Q: Mohu získat dočasnou licenci pro testovací účely?**  
A: Ano, dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).

## Závěr

Gratulujeme! Právě jste se naučili **jak převést TeX** na XPS dokument v Javě pomocí Aspose.TeX a externího streamu. Tato technika vám dává plnou kontrolu nad tím, kam XPS výstup směřuje – ať už do souborového systému, webové odpovědi nebo cloudového úložiště. Klidně experimentujte s různými TeX zdroji, upravte `TeXOptions` pro vlastní fonty nebo připojte stream do většího pipeline pro generování dokumentů.

---

**Poslední aktualizace:** 2025-12-11  
**Testováno s:** Aspose.TeX for Java 24.11 (latest at time of writing)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}