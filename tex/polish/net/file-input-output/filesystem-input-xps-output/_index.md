---
date: 2026-03-26
description: Dowiedz się, jak tworzyć XPS z TeX przy użyciu Aspose.TeX dla .NET, zarządzać
  wejściem/wyjściem systemu plików oraz generować wysokiej jakości dokumenty XPS.
linktitle: Create XPS from TeX with Filesystems – Aspose.TeX for .NET
second_title: Aspose.TeX .NET API
title: Tworzenie XPS z TeX przy użyciu systemów plików – Aspose.TeX dla .NET
url: /pl/net/file-input-output/filesystem-input-xps-output/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz XPS z TeX przy użyciu systemów plików – Aspose.TeX dla .NET

## Wprowadzenie

Witaj! W tym samouczku nauczysz się **jak utworzyć XPS z TeX** pracując z wejściem i wyjściem w systemie plików przy użyciu Aspose.TeX dla .NET. Niezależnie od tego, czy tworzysz przetwarzacz wsadowy, usługę internetową, czy narzędzie desktopowe, poniższe kroki poprowadzą Cię przez konfigurowanie silnika, wskazywanie na Twoje pliki i generowanie dokumentów XPS, które wyglądają dokładnie tak jak oryginalne źródło LaTeX.  
Podzielimy proces na przejrzyste, numerowane kroki, wyjaśnimy „dlaczego” za każdą linią kodu i podamy praktyczne wskazówki, które możesz od razu zastosować.

## Szybkie odpowiedzi
- **Co oznacza „utworzyć XPS z TeX”?** Odnosi się do konfigurowania zadania Aspose.TeX, które odczytuje pliki TeX i zapisuje wynik jako dokument XPS.  
- **Czy potrzebna jest licencja?** Dostępna jest tymczasowa licencja do testów; pełna licencja jest wymagana w środowisku produkcyjnym.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Czy mogę zmienić format wyjściowy?** Tak – zamień `XpsDevice` na inne urządzenie (PDF, PNG, itp.).  
- **Czy wymagane jest wyjście konsoli?** Nie – możesz użyć terminala pamięciowego do cichego wykonania.

## Jak utworzyć XPS z TeX przy użyciu Aspose.TeX

Utworzenie zadania TeX, które generuje XPS, oznacza zainicjowanie silnika Aspose.TeX, wskazanie, skąd ma czytać pliki źródłowe, oraz skierowanie renderowanych stron do pakietu XPS. XPS (XML Paper Specification) jest formatem o stałym układzie, który zachowuje typografię i grafikę wektorową, co czyni go idealnym do drukowania lub dalszej konwersji.

## Co to jest „create tex job xps”?

Utworzenie zadania TeX, które generuje XPS, oznacza zainicjowanie silnika Aspose.TeX, wskazanie, skąd ma czytać pliki źródłowe, oraz skierowanie renderowanych stron do pakietu XPS. XPS (XML Paper Specification) jest formatem o stałym układzie, który zachowuje typografię i grafikę wektorową, co czyni go idealnym do drukowania lub dalszej konwersji.

## Dlaczego używać Aspose.TeX do wyjścia XPS?

- **Wysoka wierność:** Silnik odtwarza układ LaTeX dokładnie w XPS.  
- **Brak zewnętrznych zależności:** Czysta biblioteka .NET, nie wymaga natywnych instalacji LaTeX.  
- **Elastyczne I/O:** Działa z katalogami systemu plików, strumieniami pamięci lub dostawcami niestandardowymi.  
- **Skalowalny:** Odpowiedni do konwersji pojedynczych plików lub przetwarzania wsadowego.

## Wymagania wstępne

- **Aspose.TeX for .NET** – pobierz najnowszą wersję ze [strony Aspose](https://releases.aspose.com/tex/net/).  
- **Środowisko programistyczne .NET** – Visual Studio, Rider lub VS Code z .NET SDK.  
- **Foldery wejściowy i wyjściowy** – utwórz dwa katalogi na swoim komputerze (np. `C:\TeX\Input` i `C:\TeX\Output`).  
- **Licencja (opcjonalnie do testów)** – możesz uzyskać tymczasową licencję z portalu Aspose.

## Importowanie przestrzeni nazw

Najpierw wprowadź wymagane przestrzenie nazw, aby mieć dostęp do pomocników systemu plików i urządzenia XPS.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

Te przestrzenie nazw udostępniają `InputFileSystemDirectory`, `OutputFileSystemDirectory` oraz `XpsDevice`, które są niezbędne w przepływie pracy **create XPS from TeX**.

## Krok 1: Utwórz opcje konwersji

Zaczynamy od zbudowania obiektu `TeXOptions`, który instruuje silnik, aby używał konfiguracji ObjectTeX (domyślnej dla większości źródeł LaTeX).

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

> **Wskazówka:** `ConsoleAppOptions` ustawia rozsądne domyślne wartości dla aplikacji konsolowych, ale w razie potrzeby możesz później dostosować opcje.

## Krok 2: Określ katalogi wejściowy i wyjściowy

Wskaż silnikowi foldery, które przygotowałeś wcześniej. Zastąp ciągi znaków zastępczych rzeczywistymi ścieżkami na swoim komputerze.

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Teraz zadanie TeX wie, gdzie znaleźć pliki `.tex` i gdzie umieścić wygenerowane pliki XPS.

## Krok 3: Wybierz terminal wyjściowy

Terminal kontroluje, gdzie zapisywane są komunikaty statusu. Do szybkiego debugowania pozostaniemy przy konsoli, ale możesz przełączyć się na terminal pamięciowy dla cichych uruchomień.

```csharp
options.TerminalOut = new OutputConsoleTerminal(); // Default value. Arbitrary assignment.
```

> **Dlaczego to ważne:** Użycie terminala konsolowego daje natychmiastową informację zwrotną o ostrzeżeniach lub błędach kompilacji, co przyspiesza rozwiązywanie problemów.

## Krok 4: Uruchom zadanie TeX

Utwórz instancję `TeXJob`, nadaj jej przyjazną nazwę, podłącz `XpsDevice` i wykonaj ją.

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

Po zakończeniu `Run()` znajdziesz plik `hello-world.xps` w katalogu wyjściowym.

## Krok 5: Dostosuj wyjście konsoli

Dodanie pustej linii po zakończeniu zadania ułatwia czytanie logu konsoli, szczególnie gdy uruchamiasz wiele zadań w trybie wsadowym.

```csharp
options.TerminalOut.Writer.WriteLine();
```

## Typowe przypadki użycia

| Scenario | Why XPS? | How the snippet helps |
|----------|----------|-----------------------|
| **Masowa konwersja prac akademickich** | Zachowanie dokładnego układu do druku archiwalnego. | Podejście oparte na systemie plików pozwala wskazać folder z plikami `.tex` i wygenerować odpowiadający zestaw plików XPS. |
| **Usługa internetowa renderująca LaTeX w locie** | XPS może być strumieniowany bezpośrednio do przeglądarek, które go obsługują. | Zamieniając `XpsDevice` na strumień pamięci, możesz zwrócić dokument bez zapisywania go na dysku. |
| **Narzędzie do publikacji desktopowej** | Potrzeba podglądu o stałym układzie przed konwersją do PDF. | To samo zadanie może później zostać połączone z urządzeniem PDF w celu ostatecznej dystrybucji. |

## Typowe problemy i rozwiązania

| Issue | Cause | Fix |
|-------|-------|-----|
| **Plik XPS jest pusty** | Ścieżka katalogu wyjściowego jest niepoprawna lub nie ma uprawnień do zapisu. | Sprawdź ścieżkę przekazaną do `OutputFileSystemDirectory` i upewnij się, że proces ma uprawnienia do zapisu. |
| **Błędy kompilacji** | Źródło LaTeX używa pakietów nie zawartych w ObjectTeX. | Przełącz się na pełną konfigurację silnika TeX (`TeXConfig.FullTeX()`) lub dodaj brakujące pliki pakietów do katalogu wejściowego. |
| **Konsola zawiesza się** | Terminal oczekuje na dane wejściowe z powodu interaktywnych zapytań. | Użyj `OutputMemoryTerminal`, aby wyciszyć interaktywne zapytania w skryptach automatycznych. |

## Najczęściej zadawane pytania

**Q1: Czy mogę użyć innego formatu wyjściowego zamiast XPS?**  
A1: Tak, Aspose.TeX obsługuje PDF, PNG, SVG i inne formaty. Zamień `new XpsDevice()` na odpowiednią klasę urządzenia (np. `new PdfDevice()`).

**Q2: Czy dostępna jest tymczasowa licencja do celów testowych?**  
A2: Tak, możesz uzyskać tymczasową licencję do testów z [tego linku](https://purchase.aspose.com/temporary-license/).

**Q3: Gdzie mogę znaleźć dodatkową dokumentację?**  
A3: Odwołaj się do [dokumentacji Aspose.TeX dla .NET](https://reference.aspose.com/tex/net/) po szczegółowe informacje.

**Q4: Jak mogę uzyskać wsparcie społeczności lub zadać pytania?**  
A4: Odwiedź [forum Aspose.TeX](https://forum.aspose.com/c/tex/47) w celu uzyskania wsparcia społeczności i dyskusji.

**Q5: Czy dostępne są przykładowe projekty?**  
A5: Przeglądaj repozytorium Aspose.TeX na GitHubie, aby znaleźć przykładowe projekty i fragmenty kodu.

## Podsumowanie

Postępując zgodnie z powyższymi krokami, teraz wiesz, jak **utworzyć XPS z TeX** przy użyciu Aspose.TeX dla .NET, zarządzać folderami wejściowymi i wyjściowymi oraz dopasować proces zarówno w scenariuszach deweloperskich, jak i produkcyjnych. Śmiało eksperymentuj z innymi urządzeniami wyjściowymi, integruj tę logikę w większych przepływach pracy lub automatyzuj konwersje wsadowe.

---

**Last Updated:** 2026-03-26  
**Tested With:** Aspose.TeX 24.11 for .NET (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}