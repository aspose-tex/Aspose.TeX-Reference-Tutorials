---
date: 2025-12-05
description: Naučte se, jak sazovat TeX pomocí Aspose.TeX pro Javu, včetně kroků pro
  vlastní formáty a jak získat dočasnou licenci Aspose.
linktitle: How to Typeset TeX with Custom Formats in Java
second_title: Aspose.TeX Java API
title: Jak sázet TeX s vlastními formáty v Javě
url: /cs/java/custom-tex-formats/typesetting-custom-tex-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak typografovat TeX s vlastními formáty v Javě

## Úvod

Pokud potřebujete **jak typografovat tex** uvnitř Java aplikace, Aspose.TeX poskytuje čistý, výkonný způsob práce s vlastními soubory formátu TeX. V tomto tutoriálu vás provedeme vším, co potřebujete – od nastavení prostředí až po spuštění TeX úlohy, která používá váš vlastní formát. Ať už vytváříte nástroj pro vědecké publikování nebo vlastní generátor zpráv, níže uvedené kroky vás rychle uvedou do provozu.

## Rychlé odpovědi
- **Jaká knihovna je potřeba?** Aspose.TeX for Java  
- **Mohu použít vlastní formát TeX?** Ano – stačí nasměrovat `FormatProvider` na váš soubor.  
- **Potřebuji licenci pro vývoj?** Dočasná licence aspose funguje pro testování; pro produkci je vyžadována plná licence.  
- **Která verze Javy je podporována?** JDK 8 nebo vyšší.  
- **Jaký výstupní formát příklad generuje?** XPS (můžete přepnout na PDF, PNG atd.).

## Co je vlastní formát TeX?
Vlastní formát TeX je předkompilovaná sada maker a primitiv, která přizpůsobuje TeX engine vašemu konkrétnímu stylu dokumentu. Poskytnutím vlastního souboru `.fmt` můžete řídit písma, pravidla rozvržení a definice příkazů, aniž byste pokaždé upravovali zdrojový TeX.

## Proč používat Aspose.TeX pro Java?
- **Čistá Java** – Žádné nativní binární soubory, snadné vložení do jakéhokoli projektu založeného na JVM.  
- **Vysoká věrnost** – Generuje výstup, který odpovídá vykreslování ve stylu LaTeX.  
- **Rozšiřitelný** – Podporuje vlastní formáty, více výstupních zařízení a dávkové zpracování.  
- **Flexibilita licence** – Začněte s dočasnou licencí aspose, poté upgradujte při nasazení.

## Požadavky

1. **Java Development Kit (JDK)** – JDK 8 nebo novější nainstalované. Stáhněte jej z oficiálního [Java website](https://www.oracle.com/java/technologies/javase-downloads.html), pokud jej ještě nemáte.  
2. **Aspose.TeX library for Java** – Stáhněte nejnovější JAR ze [Aspose.TeX for Java download page](https://releases.aspose.com/tex/java/).  
3. **Váš vlastní soubor formátu TeX** – Umístěte zkompilovaný `.fmt` (např. `customtex.fmt`) do složky, která bude sloužit jako výstupní adresář.  

> **Tip:** Pokud produkt hodnotíte, požádejte o *dočasnou licenci aspose* na portálu Aspose; odstraní vodotisk evaluace na omezenou dobu.

## Importovat balíčky

Nejprve přidejte požadované importy do svého Java projektu. Tyto třídy vám poskytují přístup k poskytovateli formátu, konfiguraci úlohy a vykreslovacímu zařízení.

```java
package com.aspose.tex.TypesetWithCustomTeXFormat;

import java.io.ByteArrayInputStream;
import java.io.IOException;

import com.aspose.tex.FormatProvider;
import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

## Postupný průvodce

### Krok 1: Vytvořit poskytovatele formátu

`FormatProvider` ukazuje na adresář, který obsahuje váš vlastní soubor formátu TeX. Nahraďte `"Your Output Directory"` skutečnou cestou, kde se nachází `customtex.fmt`.

```java
final FormatProvider formatProvider = new FormatProvider(
        new InputFileSystemDirectory("Your Output Directory"), "customtex");
```

### Krok 2: Nastavit možnosti konverze

Nastavte úlohu tak, aby používala engine ObjectTeX (engine, který rozumí vlastním formátům). Zde také nastavíme název úlohy a specifikujeme vstupní/výstupní pracovní adresáře.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX(formatProvider));
options.setJobName("typeset-with-custom-format");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### Krok 3: Spustit TeX úlohu

Vytvořte instanci `TeXJob`, předáte jí jednoduchý TeX úryvek a řekněte jí, aby výsledek vykreslila pomocí `XpsDevice`. Úryvek končí `\end`, aby uzavřel dokument.

```java
new TeXJob(new ByteArrayInputStream(
        "Congratulations! You have successfully typeset this text with your own TeX format!\\end".getBytes("ASCII")),
        new XpsDevice(), options).run();
```

### Krok 4: Dokončit výstup

Po dokončení úlohy přidejte zalomení řádku do výstupu terminálu, aby konzole zůstala přehledná.

```java
options.getTerminalOut().getWriter().newLine();
```

### Krok 5: Zavřít poskytovatele formátu

Když skončíte, zavřete poskytovatele, aby se uvolnily souborové handly a zdroje.

```java
formatProvider.close();
```

## Časté problémy a řešení

| Problém | Příčina | Řešení |
|-------|-------|-----|
| **„Format file not found“** | Špatná cesta v `FormatProvider` | Ověřte, že adresář a název souboru (`customtex.fmt`) jsou správné a přístupné. |
| **Encoding errors** | Ne‑ASCII znaky v TeX řetězci | Použijte kódování UTF‑8 (`"UTF-8"` místo `"ASCII"`). |
| **Output not generated** | Výstupní adresář nemá oprávnění k zápisu | Zajistěte, aby Java proces měl zápis do `"Your Output Directory"`. |
| **License watermark** | Používáte pouze evaluační licenci | Aplikujte *dočasnou licenci aspose* pro testování nebo zakupte plnou licenci pro produkci. |

**Související zdroje:** [Aspose.TeX API Reference](https://docs.aspose.com/tex/java/) | [Download Free Trial](https://releases.aspose.com/tex/java/)

## Často kladené otázky

**Q: Mohu použít Aspose.TeX spolu s jinými Java knihovnami?**  
A: Rozhodně. API je čistá Java a funguje vedle knihoven jako Apache PDFBox, iText nebo Spring Boot.

**Q: Kde získám dočasnou licenci aspose pro evaluaci?**  
A: Požádejte o ni na [Aspose temporary license page](https://purchase.aspose.com/temporary-license/). Odstraní evaluační vodotisk až na 30 dní.

**Q: Podporuje Aspose.TeX výstupní formáty kromě XPS?**  
A: Ano. Můžete nahradit `new XpsDevice()` za `new PdfDevice()`, `new PngDevice()` atd., podle vašich potřeb.

**Q: Jak ladím selhávající TeX úlohu?**  
A: Zapněte podrobný log voláním `options.setLogLevel(LogLevel.DEBUG);` a prozkoumejte výstup konzole pro detailní chybové zprávy.

**Q: Je k dispozici bezplatná zkušební verze?**  
A: Ano – stáhněte si zkušební binárky ze [Aspose.TeX download page](https://releases.aspose.com/tex/java/).

## Závěr

Nyní víte **jak typografovat tex** v Java aplikaci pomocí vlastního formátu TeX s Aspose.TeX. Dodržením výše uvedených kroků můžete integrovat vysoce kvalitní sazbu do jakéhokoli Java‑založeného workflow, experimentovat s vlastními soubory formátu a přejít z prototypu do produkce s odpovídající licencí.

---

**Poslední aktualizace:** 2025-12-05  
**Testováno s:** Aspose.TeX for Java 24.10  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}