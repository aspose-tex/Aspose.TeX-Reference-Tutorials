---
date: 2025-12-20
description: Dowiedz się, jak tworzyć wyjście XPS z zadań TeX przy użyciu Aspose.TeX
  dla .NET, zarządzać wejściem/wyjściem systemu plików oraz generować wysokiej jakości
  dokumenty XPS.
linktitle: Create TeX Job XPS Output with Filesystems – Aspose.TeX for .NET
second_title: Aspose.TeX .NET API
title: Utwórz wyjście XPS zadania TeX przy użyciu systemów plików – Aspose.TeX dla
  .NET
url: /pl/net/file-input-output/filesystem-input-xps-output/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz zadanie TeX z wyjściem XPS przy użyciu systemów plików – Aspose.TeX dla .NET

## Wstęp

Witamy! W tym samouczku nauczsz się **jak uruchomić zadanie TeX z wyjścia XPS** pracując z wyjściem i wyjściem w systemie plików przy użyciu Aspose.TeX dla .NET. oprogramowanie od tego, czy tworzywo sztuczne wsadowy, obsługa oprogramowania, czy narzędzie desktopowe, kolejne kroki po uruchomieniu Cię przez konfigurowanie silnika, wspisywanie plików oraz generowanie dokumentów XPS, które wyglądają jak prawdziwe kody LaTeX.

Podzielimy proces na przejrzyste, numerowane kroki, wyjaśnimy „dlaczego” każdego kodu liniowego i podamy praktyczne, które można natychmiast sprawdzić.

## Szybkie odpowiedzi
- **Co oznacza „create tex job xps”?** Odnosi się do konfigurowania zadań Aspose.TeX, które odczytuje pliki TeX i zapisuje wynik jako dokument XPS.
- **Czy jest to licencjat?** Dostępna jest tymczasowa licencja do egzaminów; pełny licencjat jest wymagany w środowisku produkcyjnym.
- **Jakie wersje .NET są pobierane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Czy można zmienić format wyjściowy?** Tak – zamień `XpsDevice` na inne urządzenie (PDF, PNG, itp.).
- **Czy wymagane jest wyjście konsoli?** Nie można użyć terminala pamięciowego do cichego wykonania.

## Co to jest „utwórz xps pracy w Teksasie”?

Utworzenie zadań TeX, które oznacza XPS, oznacza nie silnik Aspose.TeX, wskazanie, skąd pochodzą pliki źródłowe, oraz wskazanenie renderowanych stron do źródła XPS. XPS (Specyfikacja papieru XML) do formatu okablowania, który wyznacza typografię i grafikę wektorową, co stanowi idealne rozwiązanie do urządzeń lub urządzeń.

## Po co używać Aspose.TeX do tworzenia plików XPS?

- **Wysoka wierność:** Silnik uruchamia układ LaTeX w XPS.
- **Brak zewnętrznych zależności:** Czysta biblioteka .NET, nie wymaga natywnych instalacji LaTeX.
- **Elastyczne I/O:** Działa z katalogami systemów plików, strumieniami pamięci lub dostawcami.
- **Skalowalność:** Równie często używane pliki, jak i przetwarzanie wsadowego.

## Warunki wstępne

- **Aspose.TeX dla .NET** – pobierz najnowszą wersję ze [strony Aspose](https://releases.aspose.com/tex/net/).
- **Środowisko programistyczne .NET** – Visual Studio, Rider lub VS Code z zestawem .NET SDK.
- **Folder dostarczany i wyjściowy** – utwórz dwa katalogi na swoim komputerze (np. `C:\TeX\Input` i `C:\TeX\Output`).
- **Licencja (opcjonalnie do testów)** – umożliwia uzyskanie tymczasowego dostępu w portalu Aspose.

## Importuj przestrzenie nazw

Najpierw wprowadź wymagane przestrzenie nazw, aby mieć dostęp do plików pomocniczych oraz urządzeń XPS.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

Te przestrzenie nazw udostępniają `InputFileSystemDirectory`, `OutputFileSystemDirectory` oraz `XpsDevice`, które są niezbędne dla przepływu pracy **create tex job xps**.

## Krok 1: Utwórz opcje konwersji

Zaczynamy od utworzenia obiektu `TeXOptions`, który instruuje silnik, aby używał konfiguracji ObjectTeX (domyślnej dla większości źródeł LaTeX).

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

> **Wskazówka:** `ConsoleAppOptions` ustawia rozsądne domyślne wartości dla aplikacji konsolowych, ale w razie potrzeby możesz później dostosować opcje.

## Krok 2: Określ katalogi wejściowe i wyjściowe

Wskaż silnikowi katalogi, które przygotowałeś wcześniej. Zastąp ciągi zastępcze rzeczywistymi ścieżkami na swoim komputerze.

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Teraz zadanie TeX wie, gdzie szukać plików `.tex` i gdzie umieścić wygenerowane pliki XPS.

## Krok 3: Wybierz terminal wyjściowy

Terminal kontroluje, gdzie zapisywane są komunikaty statusu. Do szybkiego debugowania pozostaniemy przy konsoli, ale możesz przełączyć się na terminal pamięciowy, aby uruchamiać procesy w trybie cichym.

```csharp
options.TerminalOut = new OutputConsoleTerminal(); // Default value. Arbitrary assignment.
```

> **Dlaczego to ważne:** Użycie terminala konsolowego daje natychmiastową informację zwrotną o ostrzeżeniach lub błędach kompilacji, co przyspiesza rozwiązywanie problemów.

## Krok 4: Uruchom zadanie TeX

Utwórz instancję `TeXJob`, nadaj jej przyjazną nazwę, podłącz `XpsDevice` i uruchom ją.

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

Po zakończeniu `Run()` znajdziesz plik `hello-world.xps` w katalogu wyjściowym.

## Krok 5: Dostrój wyjście konsoli

Dodanie pustej linii po zakończeniu zadania ułatwia czytanie logu konsoli, szczególnie gdy uruchamiasz wiele zadań w partii.

```csharp
options.TerminalOut.Writer.WriteLine();
```

## Typowe problemy i rozwiązania

| Problem | Przyczyna | Rozwiązanie |
|--------|-----------|------------|
| **Plik XPS jest pusty** | Ścieżka wyjściowa jest nieprawidłowa lub nie ma uprawnień do zapisu. | Zweryfikuj przekazaną do `OutputFileSystemDirectory` i kontroluj, że proces ma dostęp do zapisu. |
| **Błędy odpadi** | Źródło LaTeX używa pakietów nie podłączanych do ObjectTeX. | przełączył się na pełne gniazdo silnika TeX („TeXConfig.FullTeX()”) lub dodaj brakujące pliki pakietów do katalogu źródłowego. |
| **Konsola się zawiesza** | Terminal dostępny na dane pochodzące z zapytania interaktywnego. | Użyj `OutputMemoryTerminal`, aby wyciszyć zapytanie w skryptach automatycznych. |

## Często zadawane pytania

**Q1: ​​Czy mogę używać innego formatu wyjściowego zamiast XPS?**
A1: Tak, Aspose.TeX obsługuje PDF, PNG, SVG i inne formaty. Zamień `new XpsDevice()` na tworzenie klasę urządzeń (np. `new PdfDevice()`).

**Q2: Czy dostępna jest tymczasowa licencjat do celów testowych?**
A2: Tak, tymczasową szkodę, jaką można uzyskać pod [tym linkiem](https://purchase.aspose.com/temporary-license/).

**Q3: Gdzie mogę znaleźć dodatkowe uzupełnienie?**
A3: Odwołaj się do [dokumentacji Aspose.TeX dla .NET](https://reference.aspose.com/tex/net/) po szczegółowe informacje.

**Pytanie 4: Jak mogę uzyskać wsparcie społeczności lub pytania?**
A4: Odwiedź [forum Aspose.TeX](https://forum.aspose.com/c/tex/47) w celu uzyskania wsparcia społeczności i debaty.

**Pyt. 5: Czy dostępne są przykładowe projekty?**
A5: Przeglądaj repozytorium Aspose.TeX na GitHub pod kątem przykładów użycia i fragmentów kodu.

## Wniosek

Po połączeniu z krokami, teraz wiesz, jak **utworzyć zadanie TeX z wyjścia XPS** przy użyciu Aspose.TeX dla .NET, udostępnić folderami dystrybucjimi i wyjściami oraz przebieg procesu zarówno do scenariuszy deweloperskich, jak i dystrybucji. Śmiało eksperymentuj z innymi wyjściami wyjściowymi, integruj tę logikę w głównych przepływach pracy lub automatyzuj konwersje wsadowe.

---

**Ostatnia aktualizacja:** 2025-12-20
**Testowano z:** Aspose.TeX 24.11 dla .NET (najnowsza wersja w momencie pisania)
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}