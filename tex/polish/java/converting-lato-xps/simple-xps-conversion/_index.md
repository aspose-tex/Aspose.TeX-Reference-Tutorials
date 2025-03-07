---
title: Z łatwością konwertuj LaTeX na format XPS w Javie
linktitle: Z łatwością konwertuj LaTeX na format XPS w Javie
second_title: Aspose.TeX API Java
description: Konwertuj LaTeX na XPS bez wysiłku w Javie za pomocą Aspose.TeX. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby zapewnić bezproblemową integrację.
weight: 10
url: /pl/java/converting-lato-xps/simple-xps-conversion/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Z łatwością konwertuj LaTeX na format XPS w Javie

## Wstęp

Czy chcesz bezproblemowo konwertować dokumenty LaTeX do formatu XPS w swoich aplikacjach Java? Aspose.TeX dla Java zapewnia potężne rozwiązanie, dzięki któremu możesz to osiągnąć z łatwością. W tym przewodniku krok po kroku przeprowadzimy Cię przez proces konwersji LaTeX-a na XPS przy użyciu Aspose.TeX.

## Warunki wstępne

Zanim przystąpisz do procesu konwersji, upewnij się, że spełnione są następujące wymagania wstępne:

- Zestaw Java Development Kit (JDK) zainstalowany w systemie.
-  Pobrano bibliotekę Aspose.TeX dla Java. Możesz znaleźć link do pobrania[Tutaj](https://releases.aspose.com/tex/java/).

## Importuj pakiety

Aby rozpocząć, zaimportuj niezbędne pakiety dla swojego projektu Java. Upewnij się, że dołączyłeś bibliotekę Aspose.TeX do zależności projektu.

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

Podzielmy teraz proces konwersji na wiele etapów, korzystając z podanych przykładów kodu.

## Krok 1: Ustaw katalogi wejściowe i wyjściowe

```java
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Określ katalogi, w których znajduje się plik wejściowy LaTeX i gdzie chcesz zapisać przekonwertowany plik XPS.

## Krok 2: Skonfiguruj opcje TeX

Skonfiguruj różne opcje, aby dostosować proces konwersji do swoich potrzeb.

```java
options.setInteraction(Interaction.NonstopMode);
options.setDateTime(new GregorianCalendar(2022, Calendar.DECEMBER, 18).getTime());
options.ignoreMissingPackages(true);
options.noLigatures(true);
options.repeat(true);
```

Dostosuj tryb interakcji, datę w tytule, obsługę brakujących pakietów, ligatury i powtórzenia, jeśli to konieczne.

## Krok 3: Zainicjuj opcje zapisywania XPS

```java
options.setSaveOptions(new XpsSaveOptions());
```

Zainicjuj opcje zapisywania w formacie XPS.

## Krok 4: Dostosuj opcje zapisywania XPS

```java
options.getSaveOptions().rasterizeFormulas(true);
options.getSaveOptions().rasterizeIncludedGraphics(true);
options.getSaveOptions().subsetFonts(true);
```

Dostosuj opcje zapisywania XPS, aby kontrolować konwersję formuł, dołączonej grafiki i podzbiorów czcionek.

## Krok 5: Uruchom konwersję LaTeX-a na XPS

```java
new TeXJob("Your Input Directory" + "sample.ltx", new XpsDevice(), options).run();
```

Zainicjuj proces konwersji, uruchamiając zadanie TeX z określonym plikiem wejściowym, urządzeniem wyjściowym (XpsDevice) i opcjami.

## Dodatkowe przykłady

Poznaj dodatkowe metody konwersji przy użyciu różnych źródeł wejściowych:

### Użyj strumienia wejściowego

```java
new TeXJob(new ByteArrayInputStream(
    "\\documentclass{article} \\begin{document} Hello, World! \\end{document}".getBytes("ASCII")),
    new XpsDevice(), options).run();
```

### Użyj głównego terminala wejściowego

```java
new TeXJob(new XpsDevice(), options).run();
```

## Wniosek

Dzięki Aspose.TeX dla Java konwersja LaTeX na XPS jest dziecinnie prosta. Wykonaj poniższe kroki, dostosuj opcje i bezproblemowo zintegruj tę funkcjonalność z aplikacjami Java.

## Często zadawane pytania

### P1: Czy mogę konwertować dokumenty LaTeX ze złożonymi formułami za pomocą Aspose.TeX?

A1: Absolutnie! Aspose.TeX bezproblemowo obsługuje złożone formuły podczas procesu konwersji.

### P2: Czy dostępna jest wersja próbna Aspose.TeX dla Java?

 Odpowiedź 2: Tak, możesz znaleźć bezpłatną wersję próbną[Tutaj](https://releases.aspose.com/).

### P3: Jak mogę uzyskać wsparcie dla Aspose.TeX?

 A3: Odwiedź[Forum Aspose.TeX](https://forum.aspose.com/c/tex/47) za pomoc i wsparcie społeczne.

### P4: Czy dostępne są licencje tymczasowe dla Aspose.TeX?

 Odpowiedź 4: Tak, możesz uzyskać licencje tymczasowe[Tutaj](https://purchase.aspose.com/temporary-license/).

### P5: Gdzie mogę znaleźć dokumentację Aspose.TeX?

 Odpowiedź 5: Patrz[dokumentacja](https://reference.aspose.com/tex/java/) w celu uzyskania kompleksowych wskazówek.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
