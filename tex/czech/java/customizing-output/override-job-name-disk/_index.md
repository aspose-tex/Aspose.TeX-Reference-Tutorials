---
title: Přepište název úlohy a zapište výstup terminálu v jazyce Java
linktitle: Přepište název úlohy a zapište výstup terminálu v jazyce Java
second_title: Aspose.TeX Java API
description: Prozkoumejte podrobného průvodce přepisováním názvů úloh a psaním terminálového výstupu pomocí Aspose.TeX for Java. Vylepšete zpracování dokumentů pomocí výkonných možností přizpůsobení.
type: docs
weight: 10
url: /cs/java/customizing-output/override-job-name-disk/
---
## Úvod

Aspose.TeX for Java poskytuje výkonné funkce pro práci se soubory TeX a umožňuje vývojářům manipulovat a přizpůsobovat zpracování dokumentů TeX. V tomto tutoriálu vás provedeme procesem přepsání názvu úlohy a zápisu terminálového výstupu do souborového systému pomocí Aspose.TeX v Javě.

## Předpoklady

Než se pustíme do výukového programu, ujistěte se, že máte splněny následující předpoklady:

- Pracovní znalost programování v Javě.
-  Aspose.TeX pro Javu nainstalován. Můžete si jej stáhnout z[Aspose.TeX Java dokumentace](https://reference.aspose.com/tex/java/).

## Importujte balíčky

Chcete-li začít, importujte potřebné balíčky do svého projektu Java. Do souboru Java zahrňte následující importy:

```java
package com.aspose.tex.OverridenJobNameAndTerminalOutputWrittenToDisk;

import java.io.IOException;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

## Přepsat název úlohy a zapsat výstup terminálu

### Krok 1: Vytvořte možnosti převodu

Začněte vytvořením možností převodu pro výchozí formát ObjectTeX na rozšíření enginu ObjectTeX. Použijte následující fragment kódu:

```java
//ExStart:OverrideJobName-WriteTerminalOutputToFileSystem
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

### Krok 2: Zadejte název úlohy a pracovní adresáře

Zadejte název úlohy, vstupní pracovní adresář a výstupní pracovní adresář. Pokud není zadán název úlohy, bude jako název úlohy použit první argument konstruktoru TeXJob. Použijte následující fragment kódu:

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### Krok 3: Zapište výstup terminálu do systému souborů

 Určete, že výstup terminálu musí být zapsán do souboru ve výstupním pracovním adresáři. Název souboru bude`<job_name>.trm`. Přidejte následující kód:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### Krok 4: Spusťte úlohu

Spusťte úlohu TeX pomocí zadaných možností a názvu úlohy. Můžete to udělat takto:

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
// ExEnd:OverrideJobName-WriteTerminalOutputToFileSystem
```

Gratulujeme! Úspěšně jste přepsali název úlohy a zapsali výstup terminálu do systému souborů pomocí Aspose.TeX v Javě.

## Závěr

tomto tutoriálu jsme prozkoumali, jak využít Aspose.TeX pro Javu k přepsání názvu úlohy a zachycení výstupu terminálu. Tyto funkce umožňují vývojářům mít jemnou kontrolu nad zpracováním dokumentů TeX, což zvyšuje přizpůsobení a flexibilitu.

## FAQ

### Q1: Mohu použít Aspose.TeX pro Javu s jinými Java knihovnami?

Odpověď 1: Ano, Aspose.TeX for Java je navržen tak, aby se hladce integroval s jinými knihovnami Java a zlepšil tak možnosti zpracování dokumentů.

### Q2: Kde najdu podporu pro Aspose.TeX pro Javu?

 A2: Navštivte[Fórum Aspose.TeX](https://forum.aspose.com/c/tex/47) za podporu komunity a pomoc s jakýmikoli problémy, se kterými se můžete setkat.

### Q3: Je k dispozici bezplatná zkušební verze pro Aspose.TeX pro Javu?

 A3: Ano, máte přístup k bezplatné zkušební verzi Aspose.TeX pro Javu[tady](https://releases.aspose.com/).

### Q4: Jak mohu získat dočasnou licenci pro Aspose.TeX for Java?

 A4: Postupujte podle tohoto[odkaz](https://purchase.aspose.com/temporary-license/) získat dočasnou licenci pro účely testování a hodnocení.

### Q5: Kde mohu zakoupit Aspose.TeX pro Javu?

 A5: Navštivte[nákupní stránku](https://purchase.aspose.com/buy) získat licenci na Aspose.TeX for Java.