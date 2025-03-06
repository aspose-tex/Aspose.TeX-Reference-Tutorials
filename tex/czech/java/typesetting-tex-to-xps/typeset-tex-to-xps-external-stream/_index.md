---
title: Vysázet TeX na XPS v Javě s externím proudem
linktitle: Vysázet TeX na XPS v Javě s externím proudem
second_title: Aspose.TeX Java API
description: Naučte se vysázet TeX na XPS v Javě pomocí Aspose.TeX. Prozkoumejte podrobné pokyny pro bezproblémové zpracování dokumentů.
weight: 10
url: /cs/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vysázet TeX na XPS v Javě s externím proudem

## Úvod

Ve světě vývoje v Javě vyniká Aspose.TeX jako výkonný nástroj pro sazbu TeXových dokumentů do různých formátů, včetně XPS. Pokud chcete vylepšit možnosti zpracování dokumentů vaší Java aplikace, je tento výukový program vytvořen přímo pro vás. V tomto podrobném průvodci vás provedeme procesem sazby TeX na XPS pomocí Aspose.TeX for Java s externím streamem.

## Předpoklady

Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:

-  Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovanou Java. Můžete si jej stáhnout z[tady](https://www.oracle.com/java/technologies/javase-downloads.html).

-  Aspose.TeX for Java: Stáhněte si a nainstalujte Aspose.TeX for Java. Odkaz ke stažení najdete[tady](https://releases.aspose.com/tex/java/).

## Importujte balíčky

Začněte importem potřebných balíčků, abyste zahájili svou cestu konverze TeX na XPS. Zahrňte do svého projektu Java následující fragment kódu:

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

## Krok 1: Nakonfigurujte možnosti převodu

Začněte vytvořením možností převodu pro výchozí formát ObjectTeX pomocí následujícího kódu:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

Tím se vytvoří základ pro proces sazby.

## Krok 2: Zadejte název úlohy a adresáře

Definujte název úlohy a nastavte vstupní a výstupní pracovní adresář:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Ujistěte se, že jste nahradili zástupné symboly jako "Váš vstupní adresář" svými skutečnými cestami k adresářům.

## Krok 3: Konfigurace terminálového výstupu

Určete, že výstup terminálu má být zapsán do souboru ve výstupním pracovním adresáři:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

Tento krok zajišťuje zachycení podrobných protokolů pro ladění.

## Krok 4: Otevřete Output Stream

Otevřete stream a napište vysázený dokument XPS:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

Nahraďte "Váš výstupní adresář" příslušnou cestou.

## Krok 5: Spusťte úlohu

Spusťte úlohu převodu TeX na XPS:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

Tím je proces dokončen a svůj vysázený dokument XPS najdete v určeném výstupním adresáři.

## Závěr

Gratulujeme! Úspěšně jste vysázeli TeX na XPS v Javě pomocí Aspose.TeX. To otevírá svět možností pro zpracování dokumentů ve vašich aplikacích Java. Experimentujte s různými soubory TeX a prozkoumejte rozmanité funkce, které nabízí Aspose.TeX.

## FAQ

### Q1: Mohu použít Aspose.TeX for Java s jinými formáty dokumentů?

A1: Aspose.TeX se primárně zaměřuje na zpracování dokumentů souvisejících s TeXem. Pro další formáty prozkoumejte rozsáhlý sortiment produktů Aspose.

### Q2: Je k dispozici zkušební verze?

 Odpověď 2: Ano, Aspose.TeX můžete vyzkoušet stažením bezplatné zkušební verze[tady](https://releases.aspose.com/).

### Q3: Kde najdu komplexní dokumentaci?

 A3: Viz dokumentace[tady](https://reference.aspose.com/tex/java/) pro podrobné informace a příklady.

### Q4: Jak získám podporu nebo vyhledám pomoc?

 A4: Navštivte fórum Aspose.TeX[tady](https://forum.aspose.com/c/tex/47)za podporu komunity a diskuze.

### Q5: Mohu získat dočasnou licenci pro testovací účely?

 A5: Ano, můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
