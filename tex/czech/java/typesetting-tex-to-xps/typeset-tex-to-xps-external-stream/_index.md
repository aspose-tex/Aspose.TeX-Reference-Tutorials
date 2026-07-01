---
date: 2026-02-20
description: Naučte se, jak převést TeX na XPS v Javě pomocí Aspose.TeX. Tento krok‑za‑krokem
  průvodce vám ukáže, jak efektivně převádět soubory TeX a generovat XPS dokumentové
  proudy.
linktitle: How to Convert TeX to XPS in Java with External Stream
second_title: Aspose.TeX Java API
title: Jak převést TeX na XPS v Javě s externím proudem
url: /cs/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak převést TeX na XPS v Javě s externím proudem

## Úvod

Pokud potřebujete **převést TeX** soubory do vysoce kvalitního XPS výstupu z Java aplikace, Aspose.TeX for Java to udělá jednoduchým. V tomto tutoriálu uvidíte přesně **jak převést TeX** na XPS dokument pomocí externího výstupního proudu, což je ideální, když chcete výsledek přímo přenést do odpovědi, cloudové úložiště nebo jakéhokoli vlastního cíle. Projdeme celý proces, od nastavení prostředí až po zápis finálního XPS souboru.

## Rychlé odpovědi
- **Co tento tutoriál pokrývá?** Převod TeX na XPS pomocí Aspose.TeX s externím proudem.  
- **Která hlavní knihovna je vyžadována?** Aspose.TeX for Java.  
- **Potřebuji licenci?** Pro produkční použití je vyžadována dočasná nebo plná licence.  
- **Mohu generovat proudy XPS dokumentů?** Ano – příklad zapisuje XPS přímo do `OutputStream`.  
- **Jaká verze Javy je podporována?** Jakýkoli JDK 8+ (tutoriál používá JDK 11 jako referenci).

## Jak převést TeX na XPS pomocí externího proudu

## Předpoklady

Než se ponoříte do kódu, ujistěte se, že máte následující:

- Java Development Kit (JDK): Ujistěte se, že máte Javu nainstalovanou ve vašem systému. Můžete si ji stáhnout [zde](https://www.oracle.com/java/technologies/javase-downloads.html).

- Aspose.TeX for Java: Stáhněte a nainstalujte Aspose.TeX for Java. Odkaz ke stažení najdete [zde](https://releases.aspose.com/tex/java/).

## Import balíčků

Začněte importováním potřebných balíčků, abyste mohli spustit svůj proces převodu TeX‑na‑XPS. Přidejte následující úryvek kódu do svého Java projektu:

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

Vytvořte možnosti převodu pro výchozí formát ObjectTeX pomocí následujícího kódu:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

Tím nastavíte základ pro proces sazby.

## Krok 2: Specifikace názvu úlohy a adresářů

Definujte název úlohy a nastavte vstupní a výstupní pracovní adresáře:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Ujistěte se, že nahradíte zástupné texty jako „Your Input Directory“ skutečnými cestami k vašim adresářům.

## Krok 3: Nastavení výstupu terminálu

Určete, že výstup terminálu má být zapsán do souboru ve výstupním pracovním adresáři:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

Tento krok zajistí podrobné logy pro ladění.

## Krok 4: Otevření výstupního proudu

Otevřete proud pro zápis sazebního XPS dokumentu:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

Nahraďte „Your Output Directory“ odpovídající cestou.

## Krok 5: Spuštění úlohy

Spusťte úlohu převodu TeX na XPS:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

Tím je proces dokončen a v určeném výstupním adresáři najdete vygenerovaný XPS dokument.

## Proč je to důležité

Použití externího `OutputStream` vám dává plnou kontrolu nad tím, kam XPS data směřují — ať už je posíláte přímo webovému klientovi, ukládáte do cloudového úložiště nebo je řetězíte do dalšího zpracovatelského potrubí. Eliminujete tak potřebu mezisouborů a snižujete I/O zátěž, což je zvláště cenné v prostředích s vysokou propustností nebo bez serveru.

## Časté problémy a řešení

| Problém | Proč se vyskytuje | Jak opravit |
|---------|-------------------|-------------|
| **FileNotFoundException** při otevírání proudu | Cesta k výstupnímu adresáři je nesprávná nebo neexistuje. | Ověřte cestu, vytvořte adresář předem nebo použijte `Files.createDirectories`. |
| **NullPointerException** na `options.getOutputWorkingDirectory()` | `setOutputWorkingDirectory` nebyla zavolána nebo vrátila `null`. | Ujistěte se, že zavoláte `options.setOutputWorkingDirectory` před jejím použitím. |
| **LicenseException** za běhu | Spuštění bez platné licence Aspose.TeX. | Použijte dočasnou nebo trvalou licenci pomocí `License license = new License(); license.setLicense("Aspose.TeX.lic");`. |

## Často kladené otázky

**Q: Mohu použít Aspose.TeX pro Javu s jinými formáty dokumentů?**  
A: Aspose.TeX se primárně zaměřuje na zpracování dokumentů souvisejících s TeX. Pro jiné formáty prozkoumejte širokou produktovou řadu Aspose.

**Q: Je k dispozici zkušební verze?**  
A: Ano, můžete vyzkoušet Aspose.TeX stažením bezplatné zkušební verze [zde](https://releases.aspose.com/).

**Q: Kde najdu komplexní dokumentaci?**  
A: Odkaz na dokumentaci [zde](https://reference.aspose.com/tex/java/) obsahuje podrobné informace a příklady.

**Q: Jak získám podporu nebo pomoc?**  
A: Navštivte fórum Aspose.TeX [zde](https://forum.aspose.com/c/tex/47) pro komunitní podporu a diskuse.

**Q: Mohu získat dočasnou licenci pro testovací účely?**  
A: Ano, dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).

## Závěr

Gratulujeme! Právě jste se naučili **jak převést TeX** na XPS dokument v Javě pomocí Aspose.TeX a externího proudu. Tato technika vám dává plnou kontrolu nad tím, kam XPS výstup směřuje — ať už do souborového systému, webové odpovědi nebo cloudového koše. Nebojte se experimentovat s různými TeX zdroji, upravit `TeXOptions` pro vlastní písma nebo připojit proud do většího pipeline generování dokumentů.

---

**Last Updated:** 2026-02-20  
**Tested With:** Aspose.TeX for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}