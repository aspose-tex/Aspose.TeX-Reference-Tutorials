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

## Introduction

Witamy! W tym samouczku nauczysz się **jak utworzyć zadanie TeX z wyjściem XPS** pracując z wejściem i wyjściem w systemie plików przy użyciu Aspose.TeX dla .NET. Niezależnie od tego, czy tworzysz przetwarzacz wsadowy, usługę internetową, czy narzędzie desktopowe, poniższe kroki poprowadzą Cię przez konfigurowanie silnika, wskazywanie plików oraz generowanie dokumentów XPS, które wyglądają dokładnie tak jak oryginalny kod LaTeX.

Podzielimy proces na przejrzyste, numerowane kroki, wyjaśnimy „dlaczego” każdej linii kodu i podamy praktyczne wskazówki, które możesz od razu zastosować.

## Quick Answers
- **Co oznacza „create tex job xps”?** Odnosi się do konfigurowania zadania Aspose.TeX, które odczytuje pliki TeX i zapisuje wynik jako dokument XPS.  
- **Czy potrzebna jest licencja?** Dostępna jest tymczasowa licencja do testów; pełna licencja jest wymagana w środowisku produkcyjnym.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Czy mogę zmienić format wyjściowy?** Tak – zamień `XpsDevice` na inny urządzenie (PDF, PNG, itp.).  
- **Czy wymagane jest wyjście konsoli?** Nie – możesz użyć terminala pamięciowego do cichego wykonania.

## What is “create tex job xps”?

Utworzenie zadania TeX, które generuje XPS, oznacza zainicjowanie silnika Aspose.TeX, wskazanie, skąd ma czytać pliki źródłowe, oraz skierowanie renderowanych stron do pakietu XPS. XPS (XML Paper Specification) to format o stałym układzie, który zachowuje typografię i grafikę wektorową, co czyni go idealnym do drukowania lub dalszej konwersji.

## Why use Aspose.TeX for XPS output?

- **Wysoka wierność:** Silnik dokładnie odtwarza układ LaTeX w XPS.  
- **Brak zewnętrznych zależności:** Czysta biblioteka .NET, nie wymaga natywnych instalacji LaTeX.  
- **Elastyczne I/O:** Działa z katalogami systemu plików, strumieniami pamięci lub własnymi dostawcami.  
- **Skalowalność:** Odpowiedni zarówno do konwersji pojedynczych plików, jak i przetwarzania wsadowego.

## Prerequisites

- **Aspose.TeX for .NET** – pobierz najnowszą wersję ze [strony Aspose](https://releases.aspose.com/tex/net/).  
- **Środowisko programistyczne .NET** – Visual Studio, Rider lub VS Code z zestawem .NET SDK.  
- **Foldery wejściowy i wyjściowy** – utwórz dwa katalogi na swoim komputerze (np. `C:\TeX\Input` i `C:\TeX\Output`).  
- **Licencja (opcjonalnie do testów)** – możesz uzyskać tymczasową licencję w portalu Aspose.

## Import Namespaces

Najpierw wprowadź wymagane przestrzenie nazw, aby mieć dostęp do pomocników systemu plików oraz urządzenia XPS.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

Te przestrzenie nazw udostępniają `InputFileSystemDirectory`, `OutputFileSystemDirectory` oraz `XpsDevice`, które są niezbędne dla przepływu pracy **create tex job xps**.

## Step 1: Create Conversion Options

Zaczynamy od utworzenia obiektu `TeXOptions`, który instruuje silnik, aby używał konfiguracji ObjectTeX (domyślnej dla większości źródeł LaTeX).

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

> **Wskazówka:** `ConsoleAppOptions` ustawia rozsądne domyślne wartości dla aplikacji konsolowych, ale w razie potrzeby możesz później dostosować opcje.

## Step 2: Specify Input and Output Directories

Wskaż silnikowi katalogi, które przygotowałeś wcześniej. Zastąp ciągi zastępcze rzeczywistymi ścieżkami na swoim komputerze.

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Teraz zadanie TeX wie, gdzie szukać plików `.tex` i gdzie umieścić wygenerowane pliki XPS.

## Step 3: Choose an Output Terminal

Terminal kontroluje, gdzie zapisywane są komunikaty statusu. Do szybkiego debugowania pozostaniemy przy konsoli, ale możesz przełączyć się na terminal pamięciowy, aby uruchamiać procesy w trybie cichym.

```csharp
options.TerminalOut = new OutputConsoleTerminal(); // Default value. Arbitrary assignment.
```

> **Dlaczego to ważne:** Użycie terminala konsolowego daje natychmiastową informację zwrotną o ostrzeżeniach lub błędach kompilacji, co przyspiesza rozwiązywanie problemów.

## Step 4: Run the TeX Job

Utwórz instancję `TeXJob`, nadaj jej przyjazną nazwę, podłącz `XpsDevice` i uruchom ją.

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

Po zakończeniu `Run()` znajdziesz plik `hello-world.xps` w katalogu wyjściowym.

## Step 5: Fine‑Tune the Console Output

Dodanie pustej linii po zakończeniu zadania ułatwia czytanie logu konsoli, szczególnie gdy uruchamiasz wiele zadań w partii.

```csharp
options.TerminalOut.Writer.WriteLine();
```

## Common Issues and Solutions

| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| **Plik XPS jest pusty** | Ścieżka katalogu wyjściowego jest nieprawidłowa lub nie ma uprawnień do zapisu. | Zweryfikuj ścieżkę przekazaną do `OutputFileSystemDirectory` i upewnij się, że proces ma uprawnienia do zapisu. |
| **Błędy kompilacji** | Źródło LaTeX używa pakietów nie dołączonych do ObjectTeX. | Przełącz się na pełną konfigurację silnika TeX (`TeXConfig.FullTeX()`) lub dodaj brakujące pliki pakietów do katalogu wejściowego. |
| **Konsola się zawiesza** | Terminal oczekuje na dane wejściowe z powodu interaktywnych zapytań. | Użyj `OutputMemoryTerminal`, aby wyciszyć interaktywne zapytania w skryptach automatycznych. |

## Frequently Asked Questions

**Q1: Czy mogę użyć innego formatu wyjściowego zamiast XPS?**  
A1: Tak, Aspose.TeX obsługuje PDF, PNG, SVG i inne formaty. Zamień `new XpsDevice()` na odpowiednią klasę urządzenia (np. `new PdfDevice()`).

**Q2: Czy dostępna jest tymczasowa licencja do celów testowych?**  
A2: Tak, tymczasową licencję do testów możesz uzyskać pod [tym linkiem](https://purchase.aspose.com/temporary-license/).

**Q3: Gdzie mogę znaleźć dodatkową dokumentację?**  
A3: Odwołaj się do [dokumentacji Aspose.TeX dla .NET](https://reference.aspose.com/tex/net/) po szczegółowe informacje.

**Q4: Jak mogę uzyskać wsparcie społeczności lub zadać pytania?**  
A4: Odwiedź [forum Aspose.TeX](https://forum.aspose.com/c/tex/47) w celu uzyskania wsparcia społeczności i dyskusji.

**Q5: Czy dostępne są przykładowe projekty?**  
A5: Przeglądaj repozytorium Aspose.TeX na GitHub pod kątem przykładowych projektów i fragmentów kodu.

## Conclusion

Postępując zgodnie z powyższymi krokami, teraz wiesz, jak **utworzyć zadanie TeX z wyjściem XPS** przy użyciu Aspose.TeX dla .NET, zarządzać folderami wejściowymi i wyjściowymi oraz dopasować proces zarówno do scenariuszy deweloperskich, jak i produkcyjnych. Śmiało eksperymentuj z innymi urządzeniami wyjściowymi, integruj tę logikę w większych przepływach pracy lub automatyzuj konwersje wsadowe.

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.TeX 24.11 for .NET (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}