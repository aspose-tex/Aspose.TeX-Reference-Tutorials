---
title: Převeďte LaTeX do formátu XPS v Javě s lehkostí
linktitle: Převeďte LaTeX do formátu XPS v Javě s lehkostí
second_title: Aspose.TeX Java API
description: Převeďte LaTeX na XPS bez námahy v Javě pomocí Aspose.TeX. Postupujte podle našeho podrobného průvodce pro bezproblémovou integraci.
type: docs
weight: 10
url: /cs/java/converting-lato-xps/simple-xps-conversion/
---
## Úvod

Hledáte bezproblémový převod dokumentů LaTeX do formátu XPS ve vašich aplikacích Java? Aspose.TeX pro Javu poskytuje výkonné řešení, které vám umožní tohoto snadno dosáhnout. V tomto podrobném průvodci vás provedeme procesem převodu LaTeXu na XPS pomocí Aspose.TeX.

## Předpoklady

Než se pustíte do procesu převodu, ujistěte se, že máte splněny následující předpoklady:

- Java Development Kit (JDK) nainstalovaný ve vašem systému.
-  Knihovna Aspose.TeX pro Java stažena. Odkaz ke stažení najdete[tady](https://releases.aspose.com/tex/java/).

## Importujte balíčky

Chcete-li začít, importujte potřebné balíčky pro váš projekt Java. Ujistěte se, že jste do závislostí projektu zahrnuli knihovnu Aspose.TeX.

```java
package com.aspose.tex.LaTeXXpsConversionSimplest;

import java.io.ByteArrayInputStream;
import java.io.IOException;
import java.util.Calendar;
import java.util.GregorianCalendar;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.Interaction;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;
import com.aspose.tex.rendering.XpsSaveOptions;

import util.Utils;
```

Nyní rozdělíme proces převodu do několika kroků pomocí poskytnutých příkladů kódu.

## Krok 1: Nastavte vstupní a výstupní adresáře

```java
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Zadejte adresáře, kde se nachází váš vstupní soubor LaTeX a kam chcete uložit převedený soubor XPS.

## Krok 2: Nakonfigurujte možnosti TeXu

Nakonfigurujte různé možnosti pro přizpůsobení procesu převodu podle vašich potřeb.

```java
options.setInteraction(Interaction.NonstopMode);
options.setDateTime(new GregorianCalendar(2022, Calendar.DECEMBER, 18).getTime());
options.ignoreMissingPackages(true);
options.noLigatures(true);
options.repeat(true);
```

Podle potřeby upravte režim interakce, datum v názvu, manipulaci s chybějícími balíčky, ligatury a opakování.

## Krok 3: Inicializujte možnosti uložení XPS

```java
options.setSaveOptions(new XpsSaveOptions());
```

Inicializujte možnosti ukládání ve formátu XPS.

## Krok 4: Přizpůsobte možnosti ukládání XPS

```java
options.getSaveOptions().rasterizeFormulas(true);
options.getSaveOptions().rasterizeIncludedGraphics(true);
options.getSaveOptions().subsetFonts(true);
```

Přizpůsobte si možnosti ukládání XPS pro řízení převodu vzorců, zahrnuté grafiky a podmnožiny písem.

## Krok 5: Spusťte převod LaTeX na XPS

```java
new TeXJob("Your Input Directory" + "sample.ltx", new XpsDevice(), options).run();
```

Spusťte proces převodu spuštěním úlohy TeX se zadaným vstupním souborem, výstupním zařízením (XpsDevice) a volbami.

## Další příklady

Prozkoumejte další metody převodu pomocí různých vstupních zdrojů:

### Použijte InputStream

```java
new TeXJob(new ByteArrayInputStream(
    "\\documentclass{article} \\begin{document} Hello, World! \\end{document}".getBytes("ASCII")),
    new XpsDevice(), options).run();
```

### Použijte hlavní vstupní terminál

```java
new TeXJob(new XpsDevice(), options).run();
```

## Závěr

S Aspose.TeX pro Javu je převod LaTeXu na XPS hračkou. Postupujte podle těchto kroků, přizpůsobte možnosti a bezproblémově integrujte tuto funkci do svých aplikací Java.

## FAQ

### Q1: Mohu pomocí Aspose.TeX převádět dokumenty LaTeXu se složitými vzorci?

A1: Rozhodně! Aspose.TeX bez problémů zpracovává složité vzorce během procesu převodu.

### Q2: Je k dispozici zkušební verze pro Aspose.TeX pro Javu?

 A2: Ano, můžete najít bezplatnou zkušební verzi[tady](https://releases.aspose.com/).

### Q3: Jak mohu získat podporu pro Aspose.TeX?

 A3: Navštivte[Fórum Aspose.TeX](https://forum.aspose.com/c/tex/47) za pomoc a podporu komunity.

### Q4: Jsou k dispozici dočasné licence pro Aspose.TeX?

 A4: Ano, můžete získat dočasné licence[tady](https://purchase.aspose.com/temporary-license/).

### Q5: Kde najdu dokumentaci k Aspose.TeX?

 A5: Viz[dokumentace](https://reference.aspose.com/tex/java/) za komplexní návod.