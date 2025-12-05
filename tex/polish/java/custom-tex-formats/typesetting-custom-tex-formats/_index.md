---
date: 2025-12-05
description: Dowiedz się, jak składać TeX przy użyciu Aspose.TeX dla Javy, w tym kroki
  dotyczące własnych formatów oraz jak uzyskać tymczasową licencję Aspose.
language: pl
linktitle: How to Typeset TeX with Custom Formats in Java
second_title: Aspose.TeX Java API
title: Jak składać TeX przy użyciu własnych formatów w Javie
url: /java/custom-tex-formats/typesetting-custom-tex-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak składać TeX przy użyciu własnych formatów w Javie

## Wprowadzenie

Jeśli potrzebujesz **jak składać tex** w aplikacji Java, Aspose.TeX zapewnia czysty, wysokowydajny sposób pracy z własnymi plikami formatów TeX. W tym samouczku przeprowadzimy Cię przez wszystko, co potrzebne — od konfiguracji środowiska po uruchomienie zadania TeX używającego Twojego własnego formatu. Niezależnie od tego, czy tworzysz narzędzie do publikacji naukowych, czy własny generator raportów, poniższe kroki szybko uruchomią Cię w działaniu.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebuję?** Aspose.TeX for Java  
- **Czy mogę używać własnego formatu TeX?** Tak – wystarczy wskazać `FormatProvider` na swój plik.  
- **Czy potrzebuję licencji do rozwoju?** Tymczasowa licencja aspose działa w testach; pełna licencja jest wymagana w produkcji.  
- **Która wersja Javy jest wspierana?** JDK 8 lub wyższa.  
- **Jaki format wyjściowy generuje przykład?** XPS (można przełączyć na PDF, PNG, itp.).

## Co to jest własny format TeX?
Własny format TeX to prekompilowany zestaw makr i prymitywów, które dostosowują silnik TeX do Twojego konkretnego stylu dokumentu. Dostarczając własny plik `.fmt`, możesz kontrolować czcionki, zasady układu i definicje poleceń bez konieczności modyfikowania źródłowego TeX za każdym razem.

## Dlaczego używać Aspose.TeX dla Javy?
- **Czysta Java** – Brak natywnych binarek, łatwe osadzenie w każdym projekcie opartym na JVM.  
- **Wysoka wierność** – Generuje wyjście, które odpowiada renderowaniu w stylu LaTeX.  
- **Rozszerzalny** – Obsługuje własne formaty, wiele urządzeń wyjściowych i przetwarzanie wsadowe.  
- **Elastyczność licencji** – Zacznij od tymczasowej licencji aspose, a następnie przejdź na pełną, gdy przejdziesz do produkcji.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że masz:

1. **Java Development Kit (JDK)** – Zainstalowany JDK 8 lub nowszy. Pobierz go z oficjalnej [strony Java](https://www.oracle.com/java/technologies/javase-downloads.html), jeśli jeszcze tego nie zrobiłeś.  
2. **Biblioteka Aspose.TeX dla Javy** – Pobierz najnowszy plik JAR ze [strony pobierania Aspose.TeX dla Javy](https://releases.aspose.com/tex/java/).  
3. **Twój własny plik formatu TeX** – Umieść skompilowany plik `.fmt` (np. `customtex.fmt`) w folderze, który będzie służył jako katalog wyjściowy.  

> **Wskazówka:** Jeśli testujesz produkt, poproś o *tymczasową licencję aspose* w portalu Aspose; usuwa ona znak wodny oceny na ograniczony czas.

## Importowanie pakietów

Najpierw dodaj wymagane importy do swojego projektu Java. Te klasy dają dostęp do dostawcy formatu, konfiguracji zadania i urządzenia renderującego.

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

## Przewodnik krok po kroku

### Krok 1: Utwórz dostawcę formatu

`FormatProvider` wskazuje katalog zawierający Twój własny plik formatu TeX. Zastąp `"Your Output Directory"` rzeczywistą ścieżką, w której znajduje się `customtex.fmt`.

```java
final FormatProvider formatProvider = new FormatProvider(
        new InputFileSystemDirectory("Your Output Directory"), "customtex");
```

### Krok 2: Ustaw opcje konwersji

Skonfiguruj zadanie, aby używało silnika ObjectTeX (silnika rozumiejącego własne formaty). Tutaj również ustawiamy nazwę zadania oraz określamy katalogi robocze wejścia/wyjścia.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX(formatProvider));
options.setJobName("typeset-with-custom-format");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### Krok 3: Uruchom zadanie TeX

Utwórz instancję `TeXJob`, podaj jej prosty fragment TeX i nakaz renderowanie wyniku przy użyciu `XpsDevice`. Fragment kończy się `\end`, aby zamknąć dokument.

```java
new TeXJob(new ByteArrayInputStream(
        "Congratulations! You have successfully typeset this text with your own TeX format!\\end".getBytes("ASCII")),
        new XpsDevice(), options).run();
```

### Krok 4: Zakończ wyjście

Po zakończeniu zadania dodaj znak nowej linii do wyjścia terminala, aby konsola pozostała czytelna.

```java
options.getTerminalOut().getWriter().newLine();
```

### Krok 5: Zamknij dostawcę formatu

Po zakończeniu zamknij dostawcę, aby zwolnić uchwyty plików i zasoby.

```java
formatProvider.close();
```

## Częste problemy i rozwiązania

| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| **„Plik formatu nie znaleziony”** | Nieprawidłowa ścieżka w `FormatProvider` | Sprawdź, czy katalog i nazwa pliku (`customtex.fmt`) są poprawne i dostępne. |
| **Błędy kodowania** | Znaki nie‑ASCII w ciągu TeX | Użyj kodowania UTF‑8 (`"UTF-8"` zamiast `"ASCII"`). |
| **Brak wygenerowanego wyjścia** | Katalog wyjściowy nie ma uprawnień do zapisu | Upewnij się, że proces Java ma dostęp do zapisu w `"Your Output Directory"`. |
| **Znak wodny licencji** | Używanie wyłącznie licencji ewaluacyjnej | Zastosuj *tymczasową licencję aspose* do testów lub zakup pełną licencję do produkcji. |

## Najczęściej zadawane pytania

**P: Czy mogę używać Aspose.TeX razem z innymi bibliotekami Java?**  
O: Zdecydowanie. API jest czystą Javą i działa obok bibliotek takich jak Apache PDFBox, iText czy Spring Boot.

**P: Gdzie mogę uzyskać tymczasową licencję aspose do oceny?**  
O: Zamów ją na [stronie tymczasowej licencji Aspose](https://purchase.aspose.com/temporary-license/). Usuwa znak wodny oceny na maksymalnie 30 dni.

**P: Czy Aspose.TeX obsługuje formaty wyjściowe inne niż XPS?**  
O: Tak. Możesz zamienić `new XpsDevice()` na `new PdfDevice()`, `new PngDevice()` itd., w zależności od potrzeb.

**P: Jak debugować niepowodzenie zadania TeX?**  
O: Włącz szczegółowe logowanie, wywołując `options.setLogLevel(LogLevel.DEBUG);` i sprawdź wyjście konsoli pod kątem szczegółowych komunikatów o błędach.

**P: Czy dostępna jest darmowa wersja próbna?**  
O: Tak – pobierz pliki próbne ze [strony pobierania Aspose.TeX](https://releases.aspose.com/tex/java/).

## Zakończenie

Teraz wiesz **jak składać tex** w aplikacji Java przy użyciu własnego formatu TeX z Aspose.TeX. Postępując zgodnie z powyższymi krokami, możesz zintegrować wysokiej jakości składanie tekstu z dowolnym procesem opartym na Javie, eksperymentować z własnymi plikami formatów i przejść od prototypu do produkcji z odpowiednią licencją.

---

**Last Updated:** 2025-12-05  
**Tested With:** Aspose.TeX for Java 24.10  
**Author:** Aspose  
**Powiązane zasoby:** [Aspose.TeX API Reference](https://docs.aspose.com/tex/java/) | [Download Free Trial](https://releases.aspose.com/tex/java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}