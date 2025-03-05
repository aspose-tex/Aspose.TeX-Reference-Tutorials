---
title: Wejście strumieniowe, wyjście obrazu i wejście terminala w Javie
linktitle: Wejście strumieniowe, wyjście obrazu i wejście terminala w Javie
second_title: Aspose.TeX API Java
description: Naucz się wprowadzania strumieniowego, wyjściowego obrazu i terminala w Javie przy użyciu Aspose.TeX. Kompleksowy samouczek dotyczący bezproblemowej integracji.
type: docs
weight: 11
url: /pl/java/advanced-io/stream-input-image-output/
---
## Wstęp

Aspose.TeX dla Java to potężna biblioteka, która umożliwia programistom pracę z plikami TeX, ułatwiając tworzenie i manipulowanie dokumentami wysokiej jakości. W tym samouczku omówimy proces pobierania danych wejściowych ze strumienia, generowania obrazu wyjściowego i obsługi danych wejściowych terminala w Javie przy użyciu Aspose.TeX.

## Warunki wstępne

Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

- Podstawowa znajomość programowania w języku Java.
- Zestaw Java Development Kit (JDK) zainstalowany na komputerze.
- Znajomość biblioteki Aspose.TeX.
-  Zainstalowany Aspose.TeX dla Java. Możesz go pobrać[Tutaj](https://releases.aspose.com/tex/java/).

## Importuj pakiety

Upewnij się, że zaimportowano pakiety wymagane do tego samouczka. Poniższy fragment kodu demonstruje niezbędne importy:

```java
package com.aspose.tex.StreamInputImageOutputAndTerminalInput;

import java.io.ByteArrayInputStream;
import java.io.IOException;

import com.aspose.tex.InputConsoleTerminal;
import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputConsoleTerminal;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.ImageDevice;
import com.aspose.tex.rendering.PngSaveOptions;
```

## Krok 1: Skonfiguruj opcje konwersji

Utwórz opcje konwersji TeX-a z domyślnym formatem ObjectTeX po rozszerzeniu silnika ObjectTeX. Określ nazwę zadania, wejściowy katalog roboczy i wyjściowy katalog roboczy.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("stream-in-image-out");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

## Krok 2: Określ zaciski wejściowe i wyjściowe

Określ konsolę jako terminal wejściowy i wyjściowy.

```java
options.setTerminalIn(new InputConsoleTerminal());
options.setTerminalOut(new OutputConsoleTerminal());
```

## Krok 3: Zdefiniuj opcje zapisywania

Zdefiniuj opcje zapisywania obrazu wyjściowego. W tym przykładzie używamy formatu PNG o rozdzielczości 300 DPI.

```java
PngSaveOptions pngOptions = new PngSaveOptions();
pngOptions.setResolution(300);
options.setSaveOptions(pngOptions);
```

## Krok 4: Utwórz urządzenie obrazu

Utwórz urządzenie obrazu, aby wygenerować obraz wyjściowy.

```java
ImageDevice device = new ImageDevice();
```

## Krok 5: Uruchom zadanie

Uruchom zadanie TeX z określonymi danymi wejściowymi, urządzeniem i opcjami.

```java
TeXJob job = new TeXJob(new ByteArrayInputStream(
        "\\hrule height 10pt width 95pt\\vskip10pt\\hrule height 5pt".getBytes("ASCII")),
        device, options);
job.run();
```

## Krok 6: Obsługuj wejście terminala

Gdy konsola poprosi o wprowadzenie danych, wpisz „ABC”, naciśnij Enter, następnie wpisz „\end” i ponownie naciśnij Enter.

```java
// Aby dalsze dane wyjściowe wyglądały dobrze.
options.getTerminalOut().getWriter().newLine();
```

## Krok 7: Pobierz wynik obrazu

Obrazy można uzyskać w postaci tablicy tablic bajtów.

```java
byte[][] result = device.getResult();
```

To kończy przewodnik krok po kroku dotyczący wprowadzania strumienia, wyjściowego obrazu i wprowadzania danych terminalowych w Javie przy użyciu Aspose.TeX.

## Wniosek

Aspose.TeX dla Java upraszcza proces obsługi dokumentów TeX, oferując solidne funkcje wprowadzania strumieniowego, wyjściowego obrazu i interakcji z terminalem. Wykonując ten samouczek, nauczyłeś się, jak bezproblemowo integrować te funkcje z aplikacjami Java.

## Często zadawane pytania

### P1: Czy Aspose.TeX jest kompatybilny z innymi bibliotekami Java?

Odpowiedź 1: Tak, Aspose.TeX można bezproblemowo zintegrować z innymi bibliotekami Java w celu zwiększenia funkcjonalności.

### P2: Czy mogę dostosować format obrazu wyjściowego?

A2: Absolutnie! Aspose.TeX zapewnia różne opcje zapisywania obrazów wyjściowych, umożliwiając dostosowanie w oparciu o Twoje preferencje.

### P3: Czy istnieje forum społecznościowe dotyczące wsparcia Aspose.TeX?

 Odpowiedź 3: Tak, możesz znaleźć wsparcie i kontaktować się ze społecznością na stronie[Forum Aspose.TeX](https://forum.aspose.com/c/tex/47).

### P4: Jak mogę uzyskać tymczasową licencję na Aspose.TeX?

 A4: Możesz uzyskać tymczasową licencję od[Tutaj](https://purchase.aspose.com/temporary-license/).

### P5: Czy są jakieś dodatkowe źródła dokumentacji Aspose.TeX?

 A5: Poznaj kompleksowość[dokumentacja](https://reference.aspose.com/tex/java/) szczegółowe informacje i przykłady.