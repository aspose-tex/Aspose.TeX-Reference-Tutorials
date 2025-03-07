---
title: Přepište název úlohy a zapište výstup terminálu do Zip v Javě
linktitle: Přepište název úlohy a zapište výstup terminálu do Zip v Javě
second_title: Aspose.TeX Java API
description: Naučte se, jak přepsat názvy úloh a zapsat výstup terminálu do ZIP v Javě pomocí Aspose.TeX. Komplexní návod pro vývojáře v Javě.
weight: 11
url: /cs/java/customizing-output/override-job-name-zip/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přepište název úlohy a zapište výstup terminálu do Zip v Javě

## Úvod

Ve světě vývoje v Javě vyniká Aspose.TeX jako výkonný nástroj pro práci s formáty souborů TeX. V tomto tutoriálu se ponoříme do konkrétního scénáře – přepsání názvů úloh a zápis výstupu terminálu do souboru zip. Tento průvodce vás krok za krokem provede procesem pomocí Aspose.TeX pro Javu.

## Předpoklady

Než se pustíme do tohoto tutoriálu, ujistěte se, že máte splněny následující předpoklady:
- Základní znalost programování v Javě.
-  Nainstalován Aspose.TeX pro Javu. Pokud ne, můžete si jej stáhnout z[Aspose webové stránky](https://releases.aspose.com/tex/java/).
- Pochopení toho, jak nastavit vývojové prostředí Java.

## Importujte balíčky

Začněte importováním potřebných balíčků do vašeho projektu Java. To zajišťuje, že máte přístup k funkcím Aspose.TeX, které jsou pro danou úlohu vyžadovány.

```java
package com.aspose.tex.OverridenJobNameAndTerminalOutputWrittenToZip;

import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.io.OutputStream;

import com.aspose.tex.InputZipDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.OutputZipDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.PdfDevice;
import com.aspose.tex.rendering.PdfSaveOptions;

import util.Utils;
```

## Krok 1: Otevřete archivy ZIP

Nejprve otevřete stream v archivu ZIP, který bude sloužit jako vstupní pracovní adresář. Toto je archiv, ze kterého budou zpracovávány vaše údaje.

```java
// Otevřete stream ve vstupním archivu ZIP
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
```

## Krok 2: Otevřete výstupní archiv ZIP

Dále otevřete stream v archivu ZIP, který bude sloužit jako výstupní pracovní adresář. Zde bude zapsán výstup terminálu.

```java
// Otevřete stream ve výstupním archivu ZIP
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "terminal-out-to-zip.zip");
```

## Krok 3: Nastavte možnosti převodu

Vytvořte možnosti převodu pro výchozí formát ObjectTeX na rozšíření enginu ObjectTeX. Zadejte název úlohy a pracovní adresáře archivu ZIP pro vstup i výstup.

```java
// Vytvořte možnosti TeXu pro formát ObjectTeX
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("terminal-output-to-zip");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
```

## Krok 4: Zadejte Terminal Output

 Určete, že výstup terminálu musí být zapsán do souboru ve výstupním pracovním adresáři. Název souboru bude`<job_name>.trm`.

```java
// Zadejte nastavení výstupu terminálu
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

## Krok 5: Definujte možnosti ukládání a spusťte úlohu

Definujte možnosti uložení, jako jsou v tomto případě možnosti uložení PDF. Spusťte úlohu TeX pro provedení převodu.

```java
// Definujte možnosti uložení a spusťte úlohu
options.setSaveOptions(new PdfSaveOptions());
new TeXJob("hello-world", new PdfDevice(), options).run();
```

## Krok 6: Dokončete výstupní archiv ZIP

Po dokončení úlohy dokončete výstupní archiv ZIP, abyste zajistili správné dokončení.

```java
// Dokončete výstupní archiv ZIP
((OutputZipDirectory) options.getOutputWorkingDirectory()).finish();
```

## Závěr

Gratulujeme! Úspěšně jste se naučili, jak přepsat názvy úloh a zapsat výstup terminálu do souboru ZIP v Javě pomocí Aspose.TeX. Tato výkonná funkce přidává flexibilitu a efektivitu vašim vývojovým projektům Java.

## FAQ

### Q1: Co je Aspose.TeX?

A1: Aspose.TeX je knihovna Java, která umožňuje vývojářům pracovat s formáty souborů TeX a poskytuje pokročilé funkce pro zpracování dokumentů.

### Q2: Jak mohu získat dočasnou licenci pro Aspose.TeX?

 A2: Můžete získat dočasnou licenci od[tento odkaz](https://purchase.aspose.com/temporary-license/).

### Q3: Kde najdu dokumentaci Aspose.TeX?

 A3: Dokumentace je k dispozici[tady](https://reference.aspose.com/tex/java/).

### Q4: Existuje bezplatná zkušební verze Aspose.TeX?

 A4: Ano, můžete najít bezplatnou zkušební verzi[tady](https://releases.aspose.com/).

### Q5: Kde mohu hledat podporu nebo se ptát na Aspose.TeX?

 A5: Navštivte[Fórum Aspose.TeX](https://forum.aspose.com/c/tex/47) za podporu a diskuze.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
