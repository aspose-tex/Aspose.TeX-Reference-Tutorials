---
date: 2026-02-10
description: Naučte se, jak vytvořit vlastní formát TeX a jak typograficky zpracovat
  TeX v Javě pomocí Aspose.TeX pro Java, včetně krok‑za‑krokem nastavení, zpracování
  vlastního formátu a získání dočasné licence.
linktitle: How to Typeset TeX with Custom Formats in Java
second_title: Aspose.TeX Java API
title: Jak vytvořit vlastní formát TeX a sazbu TeX v Javě
url: /cs/java/custom-tex-formats/typesetting-custom-tex-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit vlastní formát TeX a sazbu TeX v Javě

## Úvod

Pokud potřebujete **vytvořit vlastní formát tex** a sázet TeX uvnitř Java aplikace, Aspose.TeX poskytuje čistý, výkonný způsob práce s vlastními soubory formátu TeX. V tomto tutoriálu projdeme vše, co potřebujete – od nastavení prostředí až po spuštění TeX úlohy, která používá váš vlastní formát. Ať už budujete nástroj pro vědecké publikování nebo generátor vlastních zpráv, níže uvedené kroky vás rychle uvedou do chodu.

## Rychlé odpovědi
- **Jaká knihovna je potřeba?** Aspose.TeX pro Java  
- **Mohu použít vlastní formát TeX?** Ano – stačí nasměrovat `FormatProvider` na váš soubor.  
- **Potřebuji licenci pro vývoj?** Dočasná licence aspose stačí pro testování; pro produkci je vyžadována plná licence.  
- **Jaká verze Javy je podporována?** JDK 8 nebo vyšší.  
- **Jaký výstupní formát příklad generuje?** XPS (můžete přepnout na PDF, PNG atd.).

## Co je vlastní formát TeX?
Vlastní formát TeX je předkompilovaná sada maker a primitiv, která přizpůsobí TeX engine vašemu konkrétnímu stylu dokumentu. Poskytnutím vlastního souboru `.fmt` můžete řídit písma, pravidla rozvržení a definice příkazů, aniž byste při každém spuštění museli měnit zdrojový TeX.

## Proč použít Aspose.TeX pro Java?
- **Pure Java** – Žádné nativní binárky, snadno vložitelné do libovolného JVM‑projektu.  
- **Vysoká věrnost** – Generuje výstup, který odpovídá renderování ve stylu LaTeX.  
- **Rozšiřitelnost** – Podporuje vlastní formáty, více výstupních zařízení a dávkové zpracování.  
- **Flexibilita licence** – Začněte s dočasnou licencí aspose a později přejděte na plnou licenci při nasazení.

## Předpoklady

Než začnete, ujistěte se, že máte:

1. **Java Development Kit (JDK)** – JDK 8 nebo novější nainstalované. Stáhněte jej z oficiálního [Java webu](https://www.oracle.com/java/technologies/javase-downloads.html), pokud jej ještě nemáte.  
2. **Aspose.TeX knihovna pro Java** – Stáhněte nejnovější JAR ze [stránky ke stažení Aspose.TeX pro Java](https://releases.aspose.com/tex/java/).  
3. **Váš vlastní soubor formátu TeX** – Umístěte zkompilovaný `.fmt` (např. `customtex.fmt`) do složky, která bude sloužit jako výstupní adresář.  

> **Pro tip:** Pokud produkt hodnotíte, požádejte o *dočasnou licenci aspose* na portálu Aspose; odstraní vodotisk hodnocení na omezenou dobu.

## Import balíčků

Nejprve přidejte potřebné importy do svého Java projektu. Tyto třídy vám umožní přístup k poskytovateli formátu, konfiguraci úlohy a vykreslovacímu zařízení.

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

## Průvodce krok za krokem

### Krok 1: Vytvořte poskytovatele formátu

`FormatProvider` ukazuje na adresář, který obsahuje váš vlastní soubor formátu TeX. Nahraďte `"Your Output Directory"` skutečnou cestou, kde se nachází `customtex.fmt`.

```java
final FormatProvider formatProvider = new FormatProvider(
        new InputFileSystemDirectory("Your Output Directory"), "customtex");
```

### Krok 2: Nastavte možnosti konverze

Nakonfigurujte úlohu tak, aby používala engine ObjectTeX (engine, který rozumí vlastním formátům). Zde také nastavíme název úlohy a specifikujeme vstupní/výstupní pracovní adresáře.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX(formatProvider));
options.setJobName("typeset-with-custom-format");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### Krok 3: Spusťte TeX úlohu

Vytvořte instanci `TeXJob`, předáte jí jednoduchý úryvek TeXu a řeknete jí, aby výsledek vykreslila pomocí `XpsDevice`. Úryvek končí `\end`, aby uzavřel dokument.

```java
new TeXJob(new ByteArrayInputStream(
        "Congratulations! You have successfully typeset this text with your own TeX format!\\end".getBytes("ASCII")),
        new XpsDevice(), options).run();
```

### Krok 4: Dokončete výstup

Po dokončení úlohy přidejte zalomení řádku do terminálového výstupu, aby konzole zůstala přehledná.

```java
options.getTerminalOut().getWriter().newLine();
```

### Krok 5: Uzavřete poskytovatele formátu

Až budete hotovi, uzavřete poskytovatele, aby se uvolnily souborové handle a uvolnily se zdroje.

```java
formatProvider.close();
```

## Běžné případy použití

- **Automatizované generování vědeckých článků** – Použijte předkompilovaný formát, který obsahuje makra specifická pro časopis.  
- **Dynamické vytváření zpráv** – Generujte faktury nebo certifikáty za běhu, aniž byste pokaždé přestavovali LaTeX zdroje.  
- **Dávkové zpracování velkých kolekcí dokumentů** – Načtěte vlastní formát jednou a znovu jej použijte pro stovky souborů, čímž dramaticky snížíte dobu zpracování.

## Běžné problémy a řešení

| Problém | Příčina | Řešení |
|-------|-------|-----|
| **„Formátový soubor nebyl nalezen“** | Špatná cesta v `FormatProvider` | Ověřte, že adresář a název souboru (`customtex.fmt`) jsou správné a přístupné. |
| **Chyby kódování** | Ne‑ASCII znaky v TeX řetězci | Použijte kódování UTF‑8 (`"UTF-8"` místo `"ASCII"`). |
| **Výstup nebyl vygenerován** | Chybějící oprávnění pro zápis do výstupního adresáře | Zajistěte, aby Java proces měl právo zápisu do `"Your Output Directory"`. |
| **Vodoznak licence** | Použití pouze evaluační licence | Použijte *dočasnou licenci aspose* pro testování nebo zakupte plnou licenci pro produkci. |

**Související zdroje:** [Aspose.TeX API Reference](https://docs.aspose.com/tex/java/) | [Stáhnout bezplatnou zkušební verzi](https://releases.aspose.com/tex/java/)

## Často kladené otázky

**Q: Můžu použít Aspose.TeX spolu s jinými Java knihovnami?**  
A: Rozhodně. API je čistě Java a funguje vedle knihoven jako Apache PDFBox, iText nebo Spring Boot.

**Q: Kde získám dočasnou licenci aspose pro hodnocení?**  
A: Požádejte o ni na [stránce dočasné licence Aspose](https://purchase.aspose.com/temporary-license/). Odstraní evaluační vodoznak až na 30 dní.

**Q: Podporuje Aspose.TeX výstupní formáty kromě XPS?**  
A: Ano. Můžete nahradit `new XpsDevice()` za `new PdfDevice()`, `new PngDevice()` atd., podle vašich potřeb.

**Q: Jak ladit selhávající TeX úlohu?**  
A: Aktivujte podrobný log voláním `options.setLogLevel(LogLevel.DEBUG);` a prozkoumejte výstup v konzoli pro detailní chybové zprávy.

**Q: Je k dispozici bezplatná zkušební verze?**  
A: Ano – stáhněte si zkušební binárky ze [stránky ke stažení Aspose.TeX](https://releases.aspose.com/tex/java/).

**Q: Můžu vytvořit více vlastních formátů v jedné aplikaci?**  
A: Ano. Vytvořte samostatný `FormatProvider` pro každý `.fmt` soubor a předávejte příslušného poskytovatele do `TeXConfig.objectTeX()`.

## Závěr

Nyní víte **jak vytvořit vlastní formát tex** a **jak sázet tex v Javě** pomocí Aspose.TeX. Dodržením výše uvedených kroků můžete integrovat vysoce kvalitní sazbu do libovolného Java‑založeného workflow, experimentovat s vlastními soubory formátu a přejít z prototypu do produkce s řádnou licencí.

---

**Poslední aktualizace:** 2026-02-10  
**Testováno s:** Aspose.TeX pro Java 24.10  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}