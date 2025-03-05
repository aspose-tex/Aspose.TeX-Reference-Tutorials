---
title: Vysázet TeX do PDF v Javě pomocí externího streamu
linktitle: Vysázet TeX do PDF v Javě pomocí externího streamu
second_title: Aspose.TeX Java API
description: Naučte se vysázet TeX do PDF v Javě pomocí externích streamů s Aspose.TeX. Postupujte podle našeho podrobného průvodce pro bezproblémovou integraci.
type: docs
weight: 10
url: /cs/java/typesetting-tex-to-pdf/typeset-tex-to-pdf-external-stream/
---
## Úvod

Ve světě vývoje v Javě je vytváření PDF ze souborů TeX běžným požadavkem. Aspose.TeX pro Javu tento proces zjednodušuje a poskytuje efektivní řešení pro sazbu TeXu do PDF. V tomto tutoriálu vás provedeme kroky sazby TeX do PDF pomocí externích streamů. Na konci budete mít jasno v tom, jak tento proces bezproblémově implementovat do vašich aplikací Java.

## Předpoklady

Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:

- Aspose.TeX for Java: Ujistěte se, že máte nainstalovanou knihovnu Aspose.TeX pro Java. Můžete si jej stáhnout z[Aspose.TeX pro dokumentaci Java](https://reference.aspose.com/tex/java/).

- Vstupní a výstupní adresáře: Připravte vstupní a výstupní adresáře. K získání potřebných souborů můžete použít poskytnutý odkaz ke stažení.

## Importujte balíčky

Začněte importováním požadovaných balíčků do vašeho projektu Java:

```java
package com.aspose.tex.TypesetPdfWrittenToExternalStream;

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

## Krok 1: Otevřete vstupní a výstupní proudy

Začněte otevřením proudů pro vstupní archiv ZIP (fungující jako vstupní pracovní adresář) a výstupní archiv ZIP (sloužící jako výstupní pracovní adresář). Ujistěte se, že jste nahradili "Váš vstupní adresář" a "Váš výstupní adresář" svými skutečnými cestami k adresáři.

```java
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "typeset-pdf-to-external-stream.zip");
```

## Krok 2: Nakonfigurujte TeXOptions

Vytvořte objekt TeXOptions a nakonfigurujte jej podle svých požadavků. Nastavte název úlohy, vstupní pracovní adresář, výstupní pracovní adresář a další možnosti.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("typeset-pdf-to-external-stream");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
options.setSaveOptions(new PdfSaveOptions());
```

## Krok 3: Sazba TeXu na PDF

Nyní otevřete stream a zapište výstupní PDF na požadované místo. Můžete si vybrat, zda jej chcete zapsat do místního souboru nebo přímo do výstupního archivu ZIP.

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + "file-name.pdf");
try {
    new TeXJob("hello-world", new PdfDevice(stream), options).run();
} finally {
    stream.close();
}
```

## Krok 4: Dokončete výstupní archiv ZIP

Dokončete výstupní archiv ZIP a dokončete proces sazby.

```java
((OutputZipDirectory)options.getOutputWorkingDirectory()).finish();
```

## Závěr

Gratulujeme! Úspěšně jste vysázeli TeX do PDF v Javě pomocí externích streamů s Aspose.TeX. Tento tutoriál poskytuje robustní základ pro bezproblémové začlenění převodu TeX do PDF do vašich aplikací Java.

## FAQ

### Q1: Mohu přizpůsobit název výstupního souboru PDF?

 A1: Ano, můžete upravit`options.setJobName("typeset-pdf-to-external-stream")` pro nastavení požadovaného názvu úlohy.

### Q2: Jak mohu vyřešit běžné problémy během sazby?

 A2: Navštivte[Fórum Aspose.TeX](https://forum.aspose.com/c/tex/47) za podporu a pomoc komunity.

### Q3: Je k dispozici bezplatná zkušební verze pro Aspose.TeX pro Javu?

 A3: Ano, máte přístup k bezplatné zkušební verzi[tady](https://releases.aspose.com/).

### Q4: Kde najdu další dokumentaci a příklady?

 A4: Prozkoumejte komplexní[Dokumentace Aspose.TeX](https://reference.aspose.com/tex/java/) pro podrobné informace.

### Q5: Mohu získat dočasnou licenci pro Aspose.TeX?

 A5: Ano, můžete požádat o dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).