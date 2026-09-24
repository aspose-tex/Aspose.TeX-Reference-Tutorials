---
date: 2026-09-24
description: Dowiedz się, jak skonfigurować katalog wejściowy TeX, strumienie, obrazy
  i wejście terminala przy użyciu Aspose.TeX dla .NET w C#.
keywords:
- configure tex input directory
- add image stream tex
- add images from stream
lastmod: 2026-09-24
linktitle: Zaawansowane wejście i wyjście Aspose.TeX
og_description: Skonfiguruj katalog wejściowy TeX, dodaj strumienie obrazów i obsłuż
  wejście terminala przy użyciu Aspose.TeX dla .NET w C#. Dowiedz się krok po kroku.
og_image_alt: Guide showing how to configure TeX input directory and streams in Aspose.TeX
  for .NET
og_title: Skonfiguruj katalog wejściowy TeX – Przewodnik zaawansowany Aspose.TeX
schemas:
- author: Aspose
  dateModified: '2026-09-24'
  description: Learn how to configure TeX input directory, streams, images, and terminal
    input using Aspose.TeX for .NET in C#.
  headline: Configure TeX input directory – Advanced Aspose.TeX Input and Output
  type: TechArticle
- description: Learn how to configure TeX input directory, streams, images, and terminal
    input using Aspose.TeX for .NET in C#.
  name: Configure TeX input directory – Advanced Aspose.TeX Input and Output
  steps:
  - name: instantiate TeXInputOptions
    text: Assign the base folder that holds the primary TeX source.
  - name: add extra search paths
    text: If your project stores figures in a separate folder (e.g., *Images*), call
      `AddSearchPath` to include it.
  - name: hand the options to the processor
    text: Create a `TeXProcessor`, provide the configured options, and invoke `Process`
      or `Render`.
  type: HowTo
- questions:
  - answer: Yes—you can create a new `TeXInputOptions` instance with a different `BaseFolder`
      and pass it to a fresh `TeXProcessor` whenever you need to reconfigure.
    question: Can I change the input directory at runtime?
  - answer: Retrieve the image as a `byte[]`, wrap it in a `MemoryStream`, and call
      `TeXInputOptions.AddImage("image.png", stream)`. The name must match the reference
      in your `.tex` file.
    question: How do I add images that are stored in a database?
  - answer: Absolutely. Convert the incoming string to a `MemoryStream`, set it as
      the source for `TeXProcessor`, and render directly to your desired output format.
    question: Is it possible to process LaTeX code received from a web API without
      saving a file?
  - answer: Dispose of any streams you create, and for large workloads invoke `TeXProcessor.Cleanup()`
      to free native resources.
    question: Do I need to call any cleanup methods after processing?
  - answer: The two tutorial links above contain full code samples that demonstrate
      each scenario in detail, including error handling and performance tips.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.TeX .NET API
tags:
- Aspose.TeX
- input directory
- C# document processing
title: Skonfiguruj katalog wejściowy TeX – Zaawansowane wejście i wyjście Aspose.TeX
url: /pl/net/advanced-io/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skonfiguruj katalog wejściowy TeX w Aspose.TeX dla .NET

Aspose.TeX dla .NET pozwala osadzić w pełni funkcjonalne przetwarzanie TeX bezpośrednio w aplikacjach C#. W tym samouczku dowiesz się, jak **skonfigurować katalog wejściowy TeX**, dostarczać zawartość LaTeX ze strumieni oraz dodawać obrazy bez ingerencji w system plików. Jeśli potrzebujesz precyzyjnej kontroli nad tym, gdzie silnik szuka plików `.tex` i zasobów, jesteś we właściwym miejscu.

## Szybkie odpowiedzi
- **Co oznacza „skonfigurować katalog wejściowy tex”?**  
  Informuje Aspose.TeX, gdzie znaleźć główny plik `.tex`, pliki pomocnicze i grafiki.
- **Która klasa definiuje ścieżki wejściowe?**  
  `TeXInputOptions` przechowuje folder bazowy oraz dodatkowe lokalizacje wyszukiwania.
- **Czy mogę załadować obraz ze strumienia pamięci?**  
  Tak — użyj `TeXInputOptions.AddImage` z instancją `Stream`.
- **Czy można kompilować kod LaTeX dostarczany w czasie wykonywania?**  
  Oczywiście — przekaż `MemoryStream` zawierający tekst źródłowy do procesora.
- **Czy potrzebna jest licencja do użytku produkcyjnego?**  
  Wymagana jest ważna licencja Aspose.TeX dla wdrożeń nie‑ewaluacyjnych.

## Co to jest TeXInputOptions?
`TeXInputOptions` jest obiektem konfiguracyjnym definiującym folder bazowy oraz dodatkowe ścieżki wyszukiwania zasobów TeX. Poprawne jego ustawienie eliminuje błędy „plik nie znaleziony” i pozwala utrzymać zasoby w porządku.

## Jak skonfigurować katalog wejściowy tex?
`TeXInputOptions` jest obiektem konfiguracyjnym określającym folder bazowy oraz dodatkowe ścieżki wyszukiwania zasobów TeX. Załaduj swój główny dokument i poinformuj procesor, gdzie ma szukać wszystkiego, w kilku prostych linijkach. Ta bezpośrednia odpowiedź wyjaśnia niezbędne kroki przed dodatkowymi szczegółami.

Utwórz instancję `TeXInputOptions`, ustaw `BaseFolder` na folder zawierający Twój główny plik `.tex`, dodaj wszelkie podfoldery przechowujące obrazy lub pliki pomocnicze i przekaż opcje do `TeXProcessor`. Silnik automatycznie rozwiąże wszystkie odwołania względne.

### Krok 1: utwórz instancję TeXInputOptions
Przypisz folder bazowy, w którym znajduje się główne źródło TeX.

### Krok 2: dodaj dodatkowe ścieżki wyszukiwania
Jeśli Twój projekt przechowuje rysunki w osobnym folderze (np. *Images*), wywołaj `AddSearchPath`, aby go uwzględnić.

### Krok 3: przekaż opcje do procesora
Utwórz `TeXProcessor`, przekaż skonfigurowane opcje i wywołaj `Process` lub `Render`.

## Jak dodać obrazy przy użyciu Aspose.TeX
Obrazy odwoływane w pliku TeX mogą być dostarczane albo przez folder, albo bezpośrednio ze strumienia. Dostarczanie ze strumienia jest przydatne, gdy obrazy są przechowywane w bazie danych lub generowane w locie. `AddImage(string name, Stream data)` rejestruje strumień obrazu pod podaną nazwą pliku do użycia w dokumencie TeX. Ta metoda pozwala uniknąć plików tymczasowych i przyspiesza przetwarzanie.

## Jak przetwarzać strumienie w Aspose.TeX
Gdy źródło LaTeX jest generowane dynamicznie — być może z danych użytkownika lub usługi sieciowej — możesz przekazać je bezpośrednio do procesora, bez zapisywania pliku. `TeXProcessor` przetwarza zawartość TeX i może przyjąć `MemoryStream` zawierający kod źródłowy LaTeX. Umieść ciąg LaTeX w `MemoryStream`, ustaw go jako strumień źródłowy w `TeXProcessor` i uruchom konwersję. Ta technika sprawdza się równie dobrze w usługach chmurowych, gdzie operacje dyskowe są kosztowne.

## Dlaczego używać Aspose.TeX do zaawansowanego I/O?
Aspose.TeX obsługuje **ponad 30 formatów wejścia i wyjścia** (w tym PDF, PNG, SVG) i może renderować dokumenty liczące setki stron bez ładowania całego pliku do pamięci. Projekt oparty na strumieniach zmniejsza obciążenie I/O nawet o 40 % w porównaniu z przepływami opartymi na plikach, co czyni go idealnym dla aplikacji serwerowych o wysokiej przepustowości.

## Wymagania wstępne
- .NET 6.0 lub nowszy (biblioteka działa również z .NET Core 3.1+ i .NET Framework 4.6.1+)
- Pakiet NuGet Aspose.TeX dla .NET (wersja 24.11 lub nowsza)
- Ważna licencja Aspose.TeX do użytku produkcyjnego

## Odkryj Aspose.TeX: bramę do zaawansowanego przetwarzania dokumentów
Aby zobaczyć konfigurację w praktyce, postępuj zgodnie z naszym przewodnikiem krok po kroku **[Określ wymagany katalog wejściowy dla Aspose.TeX (C#)](./required-input-directory-csharp/)**. Ten samouczek prowadzi Cię przez tworzenie obiektu `TeXInputOptions` i renderowanie wyjścia PDF.  
**[Określ wymagany katalog wejściowy dla Aspose.TeX (C#)](./required-input-directory-csharp/)**

## Opanowanie strumieni, obrazów i wejścia terminalowego w Aspose.TeX dla C#
Aby głębiej zagłębić się w dostarczanie LaTeX z pamięci, dodawanie obrazów za pomocą strumieni i używanie wejścia w stylu terminala, sprawdź **[Opanuj strumienie, obrazy i wejście terminalowe w Aspose.TeX dla C#](./stream-input-image-output-terminal-input-csharp/)**. Pokazuje, jak zintegrować Aspose.TeX z API webowymi, usługami w tle i narzędziami konsolowymi.  
**[Opanuj strumienie, obrazy i wejście terminalowe w Aspose.TeX dla C#](./stream-input-image-output-terminal-input-csharp/)**

## Typowe problemy i rozwiązania
- **Błędy „plik nie znaleziony”** – Sprawdź, czy `BaseFolder` wskazuje prawidłowy katalog oraz czy dodatkowe ścieżki wyszukiwania zostały dodane przed renderowaniem.
- **Obrazy się nie ładują** – Upewnij się, że nazwa obrazu w `AddImage` dokładnie odpowiada nazwie użytej w źródle TeX, łącznie z rozszerzeniem pliku.
- **Wzrost zużycia pamięci** – Przy przetwarzaniu bardzo dużych dokumentów wywołaj `TeXProcessor.Cleanup()` po renderowaniu, aby zwolnić zasoby niezarządzane.

## Najczęściej zadawane pytania

**P: Czy mogę zmienić katalog wejściowy w czasie działania?**  
O: Tak — możesz utworzyć nową instancję `TeXInputOptions` z innym `BaseFolder` i przekazać ją do nowego `TeXProcessor`, gdy potrzebujesz ponownej konfiguracji.

**P: Jak dodać obrazy przechowywane w bazie danych?**  
O: Pobierz obraz jako `byte[]`, umieść go w `MemoryStream` i wywołaj `TeXInputOptions.AddImage("image.png", stream)`. Nazwa musi odpowiadać odwołaniu w Twoim pliku `.tex`.

**P: Czy można przetworzyć kod LaTeX otrzymany z API webowego bez zapisywania pliku?**  
O: Zdecydowanie. Przekształć otrzymany ciąg w `MemoryStream`, ustaw go jako źródło dla `TeXProcessor` i renderuj bezpośrednio do wybranego formatu wyjściowego.

**P: Czy muszę wywoływać jakiekolwiek metody czyszczenia po przetworzeniu?**  
O: Zwolnij wszystkie utworzone strumienie, a przy dużych obciążeniach wywołaj `TeXProcessor.Cleanup()`, aby zwolnić zasoby natywne.

**P: Gdzie mogę znaleźć bardziej zaawansowane przykłady?**  
O: Dwa powyższe linki do samouczków zawierają pełne przykłady kodu, które szczegółowo demonstrują każdy scenariusz, w tym obsługę błędów i wskazówki dotyczące wydajności.

---

**Last Updated:** 2026-09-24  
**Tested With:** Aspose.TeX 24.11 for .NET  
**Author:** Aspose

## Powiązane samouczki

- [Pobierz strumień pliku TeX (C#) przy użyciu Aspose.TeX API – Wymagany katalog wejściowy](/tex/net/advanced-io/required-input-directory-csharp/)
- [Utwórz XPS z TeX przy użyciu systemów plików – Aspose.TeX dla .NET](/tex/net/file-input-output/filesystem-input-xps-output/)
- [Konwertuj LaTeX do PNG przy użyciu Aspose.TeX dla .NET – Przetwarzaj wejścia z systemu plików i ZIP](/tex/net/file-input-output/required-inputs-from-filesystem-and-zip/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}