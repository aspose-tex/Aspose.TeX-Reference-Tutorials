---
title: Zastąp nazwę zadania i zapisz dane wyjściowe terminala w formacie Zip w Javie
linktitle: Zastąp nazwę zadania i zapisz dane wyjściowe terminala w formacie Zip w Javie
second_title: Aspose.TeX API Java
description: Dowiedz się, jak zastąpić nazwy zadań i zapisać dane wyjściowe terminala w formacie ZIP w Javie za pomocą Aspose.TeX. Kompleksowy poradnik dla programistów Java.
weight: 11
url: /pl/java/customizing-output/override-job-name-zip/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zastąp nazwę zadania i zapisz dane wyjściowe terminala w formacie Zip w Javie

## Wstęp

W świecie programowania Java Aspose.TeX wyróżnia się jako potężne narzędzie do obsługi formatów plików TeX. W tym samouczku zajmiemy się konkretnym scenariuszem — nadpisywaniem nazw zadań i zapisywaniem danych wyjściowych terminala w pliku zip. Ten przewodnik krok po kroku przeprowadzi Cię przez proces korzystania z Aspose.TeX dla Java.

## Warunki wstępne

Zanim przejdziemy do tego samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Podstawowa znajomość programowania w języku Java.
-  Zainstalowano Aspose.TeX dla Javy. Jeśli nie, możesz pobrać go ze strony[Strona Aspose](https://releases.aspose.com/tex/java/).
- Zrozumienie sposobu konfigurowania środowiska programistycznego Java.

## Importuj pakiety

Rozpocznij od zaimportowania niezbędnych pakietów do projektu Java. Dzięki temu masz dostęp do funkcjonalności Aspose.TeX wymaganych do wykonania zadania.

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

## Krok 1: Otwórz archiwa ZIP

Najpierw otwórz strumień w archiwum ZIP, który będzie służył jako wejściowy katalog roboczy. To jest archiwum, z którego będą przetwarzane Twoje dane.

```java
// Otwórz strumień w wejściowym archiwum ZIP
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
```

## Krok 2: Otwórz wyjściowe archiwum ZIP

Następnie otwórz strumień w archiwum ZIP, który będzie służył jako wyjściowy katalog roboczy. W tym miejscu zostaną zapisane dane wyjściowe terminala.

```java
// Otwórz strumień w wyjściowym archiwum ZIP
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "terminal-out-to-zip.zip");
```

## Krok 3: Ustaw opcje konwersji

Utwórz opcje konwersji dla domyślnego formatu ObjectTeX po rozszerzeniu silnika ObjectTeX. Określ nazwę zadania i katalogi robocze archiwum ZIP zarówno dla wejścia, jak i wyjścia.

```java
// Utwórz opcje TeX dla formatu ObjectTeX
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("terminal-output-to-zip");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
```

## Krok 4: Określ wyjście terminala

 Określ, że dane wyjściowe terminala muszą zostać zapisane w pliku w wyjściowym katalogu roboczym. Nazwa pliku będzie taka`<job_name>.trm`.

```java
// Określ ustawienia wyjścia terminala
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

## Krok 5: Zdefiniuj opcje zapisywania i uruchom zadanie

Zdefiniuj opcje zapisywania, takie jak w tym przypadku opcje zapisywania pliku PDF. Uruchom zadanie TeX, aby wykonać konwersję.

```java
// Zdefiniuj opcje zapisywania i uruchom zadanie
options.setSaveOptions(new PdfSaveOptions());
new TeXJob("hello-world", new PdfDevice(), options).run();
```

## Krok 6: Sfinalizuj wyjściowe archiwum ZIP

Po zakończeniu zadania sfinalizuj wyjściowe archiwum ZIP, aby zapewnić jego prawidłowe zakończenie.

```java
// Sfinalizuj wyjściowe archiwum ZIP
((OutputZipDirectory) options.getOutputWorkingDirectory()).finish();
```

## Wniosek

Gratulacje! Pomyślnie nauczyłeś się, jak zastępować nazwy zadań i zapisywać dane wyjściowe terminala w pliku ZIP w Javie przy użyciu Aspose.TeX. Ta potężna funkcjonalność zwiększa elastyczność i wydajność projektów programistycznych Java.

## Często zadawane pytania

### P1: Co to jest Aspose.TeX?

O1: Aspose.TeX to biblioteka Java, która umożliwia programistom pracę z formatami plików TeX, zapewniając zaawansowane funkcje przetwarzania dokumentów.

### P2: Jak mogę uzyskać tymczasową licencję na Aspose.TeX?

 A2: Możesz uzyskać tymczasową licencję od[ten link](https://purchase.aspose.com/temporary-license/).

### P3: Gdzie mogę znaleźć dokumentację Aspose.TeX?

 A3: Dokumentacja jest dostępna[Tutaj](https://reference.aspose.com/tex/java/).

### P4: Czy dostępna jest bezpłatna wersja próbna Aspose.TeX?

 Odpowiedź 4: Tak, możesz znaleźć bezpłatną wersję próbną[Tutaj](https://releases.aspose.com/).

### P5: Gdzie mogę szukać pomocy lub zadać pytania dotyczące Aspose.TeX?

 A5: Odwiedź[Forum Aspose.TeX](https://forum.aspose.com/c/tex/47) za wsparcie i dyskusję.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
