---
title: Spisz TeX na XPS w Javie za pomocą strumienia zewnętrznego
linktitle: Spisz TeX na XPS w Javie za pomocą strumienia zewnętrznego
second_title: Aspose.TeX API Java
description: Dowiedz się, jak złożyć TeX na XPS w Javie przy użyciu Aspose.TeX. Zapoznaj się ze wskazówkami krok po kroku dotyczącymi bezproblemowego przetwarzania dokumentów.
type: docs
weight: 10
url: /pl/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
---
## Wstęp

W świecie programowania w języku Java Aspose.TeX wyróżnia się jako potężne narzędzie do składu dokumentów TeX-owych w różnych formatach, w tym XPS. Jeśli chcesz ulepszyć możliwości przetwarzania dokumentów w aplikacji Java, ten samouczek jest stworzony dla Ciebie. W tym przewodniku krok po kroku przeprowadzimy Cię przez proces składowania TeX-a na XPS przy użyciu Aspose.TeX dla Java z zewnętrznym strumieniem.

## Warunki wstępne

Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

-  Zestaw Java Development Kit (JDK): Upewnij się, że w systemie jest zainstalowana Java. Można go pobrać z[Tutaj](https://www.oracle.com/java/technologies/javase-downloads.html).

-  Aspose.TeX dla Java: Pobierz i zainstaluj Aspose.TeX dla Java. Możesz znaleźć link do pobrania[Tutaj](https://releases.aspose.com/tex/java/).

## Importuj pakiety

Zacznij od zaimportowania niezbędnych pakietów, aby rozpocząć konwersję TeX-a na XPS. Dołącz następujący fragment kodu do swojego projektu Java:

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

## Krok 1: Skonfiguruj opcje konwersji

Rozpocznij od utworzenia opcji konwersji dla domyślnego formatu ObjectTeX przy użyciu następującego kodu:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

Stanowi to podstawę procesu składu.

## Krok 2: Określ nazwę zadania i katalogi

Zdefiniuj nazwę zadania i ustaw wejściowe i wyjściowe katalogi robocze:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Upewnij się, że zastąpiłeś symbole zastępcze, takie jak „Twój katalog wejściowy”, rzeczywistymi ścieżkami katalogów.

## Krok 3: Skonfiguruj wyjście terminala

Określ, że dane wyjściowe terminala powinny zostać zapisane do pliku w wyjściowym katalogu roboczym:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

Ten krok zapewnia przechwycenie szczegółowych dzienników na potrzeby debugowania.

## Krok 4: Otwórz strumień wyjściowy

Otwórz strumień, aby napisać złożony dokument XPS:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

Zastąp „Twój katalog wyjściowy” odpowiednią ścieżką.

## Krok 5: Uruchom zadanie

Wykonaj zadanie konwersji TeX-a na XPS:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

To kończy proces, a złożony dokument XPS znajdziesz w określonym katalogu wyjściowym.

## Wniosek

Gratulacje! Pomyślnie przepisałeś TeX na XPS w Javie przy użyciu Aspose.TeX. Otwiera to świat możliwości przetwarzania dokumentów w aplikacjach Java. Eksperymentuj z różnymi plikami TeX i poznaj różnorodne funkcje oferowane przez Aspose.TeX.

## Często zadawane pytania

### P1: Czy mogę używać Aspose.TeX dla Java z innymi formatami dokumentów?

Odpowiedź 1: Aspose.TeX koncentruje się przede wszystkim na przetwarzaniu dokumentów związanych z TeX-em. W przypadku innych formatów zapoznaj się z szeroką gamą produktów Aspose.

### P2: Czy dostępna jest wersja próbna?

 Odpowiedź 2: Tak, możesz korzystać z Aspose.TeX, pobierając bezpłatną wersję próbną[Tutaj](https://releases.aspose.com/).

### P3: Gdzie mogę znaleźć obszerną dokumentację?

 Odpowiedź 3: Zapoznaj się z dokumentacją[Tutaj](https://reference.aspose.com/tex/java/) szczegółowe informacje i przykłady.

### P4: Jak uzyskać wsparcie lub szukać pomocy?

 A4: Odwiedź forum Aspose.TeX[Tutaj](https://forum.aspose.com/c/tex/47)za wsparcie społeczności i dyskusje.

### P5: Czy mogę uzyskać tymczasową licencję do celów testowych?

 Odpowiedź 5: Tak, możesz nabyć licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).