---
title: Zastąp nazwę zadania i zapisz dane wyjściowe terminala na dysku (C#)
linktitle: Zastąp nazwę zadania i zapisz dane wyjściowe terminala na dysku (C#)
second_title: Aspose.TeX API .NET
description: Dowiedz się, jak używać Aspose.TeX dla .NET do zastępowania nazw zadań i przechwytywania danych wyjściowych terminala. Postępuj zgodnie z naszym obszernym przewodnikiem po bezproblemowym zarządzaniu plikami TeX.
type: docs
weight: 10
url: /pl/net/job-output/override-job-name-disk-output-csharp/
---
## Wstęp

Witamy w tym przewodniku krok po kroku dotyczącym używania Aspose.TeX dla .NET do zastępowania nazw zadań i zapisywania danych wyjściowych terminala na dysku w języku programowania C#. Aspose.TeX dla .NET to potężna biblioteka, która pozwala bezproblemowo pracować z plikami TeX, a w tym samouczku skupimy się na konkretnym zadaniu: nadpisywaniu nazw zadań i przechwytywaniu danych wyjściowych terminala.

## Warunki wstępne

Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

-  Biblioteka Aspose.TeX dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.TeX dla .NET. Można go pobrać z[Witryna Aspose.TeX](https://releases.aspose.com/tex/net/).

- Środowisko programistyczne .NET: Posiadaj działające środowisko programistyczne .NET, w tym zintegrowane środowisko programistyczne (IDE), takie jak Visual Studio.

- Podstawowa znajomość języka C#: Zapoznaj się z podstawami języka programowania C#.

- Katalogi wejściowe i wyjściowe: Przygotuj katalogi wejściowe i wyjściowe dla plików TeX.

## Importuj przestrzenie nazw

W kodzie C# pamiętaj o uwzględnieniu niezbędnych przestrzeni nazw, aby uzyskać dostęp do funkcjonalności Aspose.TeX:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

## Krok 1: Utwórz opcje konwersji

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

Utwórz TeXOptions za pomocą ConsoleAppOptions, określając ObjectTeX jako TeXConfig.

## Krok 2: Określ nazwę zadania

```csharp
options.JobName = "overridden-job-name";
```

Określ nazwę zadania, aby zastąpić nazwę domyślną.

## Krok 3: Określ wejściowy katalog roboczy

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

Ustaw wejściowy katalog roboczy dla plików TeX.

## Krok 4: Określ wyjściowy katalog roboczy

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Zdefiniuj wyjściowy katalog roboczy, w którym będą zapisywane przetworzone pliki TeX.

## Krok 5: Zapisz dane wyjściowe terminala na dysku

```csharp
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

Skonfiguruj zapis wyjścia terminala do pliku w katalogu wyjściowym.

## Krok 6: Uruchom zadanie

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

Utwórz TeXJob, określając nazwę zadania, urządzenie wyjściowe (XpsDevice) i opcje. Na koniec uruchom zadanie.

## Wniosek

Gratulacje! Pomyślnie nauczyłeś się, jak zastępować nazwy zadań i zapisywać dane wyjściowe terminala na dysku przy użyciu Aspose.TeX dla .NET w języku C#. Ta funkcja jest cenna dla wydajnego zarządzania zadaniami przetwarzania TeX-a.

## Często zadawane pytania

### P1: Czy mogę używać Aspose.TeX dla .NET z innymi bibliotekami .NET?

Odpowiedź 1: Tak, Aspose.TeX dla .NET można bezproblemowo zintegrować z innymi bibliotekami .NET.

### P2: Czy dostępna jest bezpłatna wersja próbna Aspose.TeX dla .NET?

 Odpowiedź 2: Tak, możesz pobrać bezpłatną wersję próbną[Tutaj](https://releases.aspose.com/).

### P3: Jak mogę uzyskać wsparcie dla Aspose.TeX dla .NET?

 A3: Odwiedź[Forum Aspose.TeX](https://forum.aspose.com/c/tex/47) aby uzyskać społeczność i wsparcie.

### P4: Czy dostępne są licencje tymczasowe dla Aspose.TeX dla .NET?

 Odpowiedź 4: Tak, możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).

### P5: Gdzie mogę znaleźć dokumentację Aspose.TeX dla .NET?

 Odpowiedź 5: Dokumentacja jest dostępna[Tutaj](https://reference.aspose.com/tex/net/).