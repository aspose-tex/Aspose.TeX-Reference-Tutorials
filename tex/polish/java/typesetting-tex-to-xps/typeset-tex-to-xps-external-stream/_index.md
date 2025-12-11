---
date: 2025-12-11
description: Dowiedz się, jak konwertować TeX na XPS w Javie przy użyciu Aspose.TeX.
  Ten przewodnik krok po kroku pokazuje, jak efektywnie generować strumienie dokumentów
  XPS.
linktitle: How to Convert TeX to XPS in Java with External Stream
second_title: Aspose.TeX Java API
title: Jak przekonwertować TeX na XPS w Javie przy użyciu zewnętrznego strumienia
url: /pl/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak konwertować TeX na XPS w Javie przy użyciu zewnętrznego strumienia

## Wprowadzenie

Jeśli potrzebujesz **konwertować pliki TeX** do wysokiej jakości wyjścia XPS z aplikacji Java, Aspose.TeX for Java upraszcza to zadanie. W tym samouczku zobaczysz dokładnie **jak konwertować TeX** na dokument XPS przy użyciu zewnętrznego strumienia wyjściowego, co jest idealne, gdy chcesz bezpośrednio przekierować wynik do odpowiedzi HTTP, usługi przechowywania w chmurze lub dowolnego niestandardowego miejsca docelowego. Przejdźmy przez cały proces, od konfiguracji środowiska po zapisanie finalnego pliku XPS.

## Szybkie odpowiedzi
- **Co obejmuje ten samouczek?** Konwersję TeX na XPS przy użyciu Aspose.TeX z zewnętrznym strumieniem.  
- **Jakiej biblioteki głównej potrzebujesz?** Aspose.TeX for Java.  
- **Czy potrzebna jest licencja?** Wymagana jest tymczasowa lub pełna licencja do użytku produkcyjnego.  
- **Czy mogę generować strumienie dokumentów XPS?** Tak – przykład zapisuje XPS bezpośrednio do `OutputStream`.  
- **Jaką wersję Javy obsługuje?** Dowolną JDK 8+ (w samouczku użyto JDK 11 jako odniesienia).

## Wymagania wstępne

Zanim przejdziesz do kodu, upewnij się, że masz następujące elementy:

- Java Development Kit (JDK): Upewnij się, że Java jest zainstalowana w Twoim systemie. Możesz ją pobrać [tutaj](https://www.oracle.com/java/technologies/javase-downloads.html).

- Aspose.TeX for Java: Pobierz i zainstaluj Aspose.TeX for Java. Link do pobrania znajdziesz [tutaj](https://releases.aspose.com/tex/java/).

## Importowanie pakietów

Rozpocznij od zaimportowania niezbędnych pakietów, aby rozpocząć konwersję TeX‑na‑XPS. Dołącz następujący fragment kodu do swojego projektu Java:

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

## Krok 1: Konfiguracja opcji konwersji

Utwórz opcje konwersji dla domyślnego formatu ObjectTeX, używając poniższego kodu:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

To ustawia podstawy procesu składu.

## Krok 2: Określenie nazwy zadania i katalogów

Zdefiniuj nazwę zadania oraz ustaw katalogi wejściowy i wyjściowy:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Upewnij się, że zamienisz takie miejsca jak „Your Input Directory” na rzeczywiste ścieżki katalogów.

## Krok 3: Konfiguracja wyjścia terminala

Określ, że wyjście terminala ma być zapisywane do pliku w katalogu roboczym wyjścia:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

Ten krok zapewnia szczegółowe logi przydatne do debugowania.

## Krok 4: Otwarcie strumienia wyjściowego

Otwórz strumień, aby zapisać składany dokument XPS:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

Zastąp „Your Output Directory” odpowiednią ścieżką.

## Krok 5: Uruchomienie zadania

Wykonaj konwersję TeX na XPS:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

To kończy proces, a wygenerowany dokument XPS znajdziesz w określonym katalogu wyjściowym.

## Typowe problemy i rozwiązania

| Problem | Dlaczego się pojawia | Jak naprawić |
|---------|----------------------|--------------|
| **FileNotFoundException** przy otwieraniu strumienia | Ścieżka katalogu wyjściowego jest niepoprawna lub nie istnieje. | Sprawdź ścieżkę, utwórz katalog wcześniej lub użyj `Files.createDirectories`. |
| **NullPointerException** przy `options.getOutputWorkingDirectory()` | `setOutputWorkingDirectory` nie został wywołany lub zwrócił `null`. | Upewnij się, że wywołujesz `options.setOutputWorkingDirectory` przed użyciem. |
| **LicenseException** w czasie wykonywania | Uruchomienie bez ważnej licencji Aspose.TeX. | Zastosuj tymczasową lub stałą licencję używając `License license = new License(); license.setLicense("Aspose.TeX.lic");`. |

## Najczęściej zadawane pytania

**P: Czy mogę używać Aspose.TeX for Java z innymi formatami dokumentów?**  
O: Aspose.TeX koncentruje się głównie na przetwarzaniu dokumentów związanych z TeX. Dla innych formatów zapoznaj się z szeroką gamą produktów Aspose.

**P: Czy dostępna jest wersja próbna?**  
O: Tak, możesz wypróbować Aspose.TeX, pobierając darmową wersję próbną [tutaj](https://releases.aspose.com/).

**P: Gdzie znajdę pełną dokumentację?**  
O: Dokumentację znajdziesz [tutaj](https://reference.aspose.com/tex/java/) – zawiera szczegółowe informacje i przykłady.

**P: Jak uzyskać wsparcie lub pomoc?**  
O: Odwiedź forum Aspose.TeX [tutaj](https://forum.aspose.com/c/tex/47), gdzie znajdziesz wsparcie społeczności i dyskusje.

**P: Czy mogę uzyskać tymczasową licencję do testów?**  
O: Tak, tymczasową licencję można nabyć [tutaj](https://purchase.aspose.com/temporary-license/).

## Zakończenie

Gratulacje! Właśnie nauczyłeś się **jak konwertować TeX** na dokument XPS w Javie przy użyciu Aspose.TeX i zewnętrznego strumienia. Ta technika daje pełną kontrolę nad miejscem docelowym wyjścia XPS – czy to system plików, odpowiedź sieciowa, czy koszyk w chmurze. Śmiało eksperymentuj z różnymi źródłami TeX, dostosowuj `TeXOptions` pod kątem własnych czcionek lub podłącz strumień do większego potoku generowania dokumentów.

---

**Ostatnia aktualizacja:** 2025-12-11  
**Testowano z:** Aspose.TeX for Java 24.11 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}