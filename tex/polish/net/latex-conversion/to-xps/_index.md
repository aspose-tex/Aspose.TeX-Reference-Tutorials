---
title: LaTeX do XPS w .NET - Łatwa konwersja z Aspose.TeX
linktitle: LaTeX do XPS w .NET - Łatwa konwersja z Aspose.TeX
second_title: Aspose.TeX API .NET
description: Bez wysiłku konwertuj LaTeX na XPS w .NET za pomocą Aspose.TeX. Wysoka jakość, możliwość dostosowania i wydajność.
type: docs
weight: 13
url: /pl/net/latex-conversion/to-xps/
---
## Wstęp

Szukasz bezproblemowego sposobu na konwersję dokumentów LaTeX do formatu XPS w aplikacjach .NET? Aspose.TeX dla .NET zapewnia potężne rozwiązanie do tego zadania, dzięki czemu proces konwersji jest prosty i wydajny. Ten przewodnik krok po kroku przeprowadzi Cię przez proces konwersji LaTeX-a na XPS przy użyciu Aspose.TeX, zapewniając osiągnięcie dokładnych i wysokiej jakości wyników.

## Warunki wstępne

Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

- Praktyczna znajomość programowania w C# i .NET.
-  Zainstalowana biblioteka Aspose.TeX dla .NET. Możesz go pobrać[Tutaj](https://releases.aspose.com/tex/net/).
- Znajomość składni i struktury LaTeX-a.

## Importuj przestrzenie nazw

Zacznijmy od zaimportowania niezbędnych przestrzeni nazw dla naszej aplikacji .NET. Te przestrzenie nazw są kluczowe dla interakcji z funkcjonalnościami Aspose.TeX.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
using System.Text;
```

## Krok 1: Skonfiguruj opcje konwersji

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectLaTeX);
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

Tutaj inicjujemy opcje konwersji i ustawiamy wejściowy katalog roboczy dla plików LaTeX.

## Krok 2: Ustaw tryb interakcji

```csharp
options.Interaction = Interaction.NonstopMode;
```

Określ tryb interakcji, gdzie ustawimy go na tryb ciągły, aby zapewnić nieprzerwaną konwersję.

## Krok 3: Ustaw nazwę zadania (opcjonalnie)

```csharp
// options.JobName = "nazwa-mojego-zadania";
```

W razie potrzeby możesz ustawić niestandardową nazwę zadania.

## Krok 4: Ustaw datę w tytule (opcjonalnie)

```csharp
// opcje.DateTime = nowy System.DateTime(2022, 12, 18);
```

Zmuś silnik TeX do wypisywania określonej daty w tytule.

## Krok 5: Zignoruj brakujące pakiety

```csharp
options.IgnoreMissingPackages = true;
```

Ustaw na true, jeśli chcesz, aby silnik pomijał brakujące pakiety bez błędów.

## Krok 6: Wyłącz ligatury

```csharp
options.NoLigatures = true;
```

Ustaw na true, aby uniemożliwić silnikowi tworzenie ligatur.

## Krok 7: Powtórz zadanie (opcjonalnie)

```csharp
// opcje.Powtórz = prawda;
```

W razie potrzeby poproś silnik o powtórzenie zadania.

## Krok 8: Określ wyjściowy katalog roboczy

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Ustaw wyjściowy katalog roboczy dla przekonwertowanych plików XPS.

## Krok 9: Zainicjuj opcje zapisu dla XPS

```csharp
options.SaveOptions = new XpsSaveOptions(); // Domyślna wartość. Przypisanie arbitralne.
```

Zainicjuj opcje zapisywania w formacie XPS.

## Krok 10: Rasteryzacja formuł (opcjonalnie)

```csharp
options.SaveOptions.RasterizeFormulas = true;
```

Ustaw na true, jeśli chcesz, aby formuły matematyczne były konwertowane na obrazy rastrowe.

## Krok 11: Rasteryzuj dołączoną grafikę (opcjonalnie)

```csharp
options.SaveOptions.RasterizeIncludedGraphics = true;
```

Ustaw na true, jeśli chcesz, aby dołączona grafika z elementami wektorowymi była konwertowana na obrazy rastrowe.

## Krok 12: Podstaw czcionki

```csharp
options.SaveOptions.SubsetFonts = true;
```

Ustaw na true, aby ustawić podzbiór czcionek urządzenia używanych w dokumencie.

## Krok 13: Uruchom konwersję LaTeX-a na XPS

```csharp
new TeXJob(Path.Combine("Your Input Directory", "sample.ltx"), new XpsDevice(), options).Run();
```

Rozpocznij proces konwersji LaTeX na XPS.

## Krok 14: Uruchom konwersję LaTeX-a na XPS za pomocą MemoryStream (alternatywa)

```csharp
// nowy TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(@"\documentclass{article} \begin{document} Witaj, świecie! \end{document}")),
// nowe XpsDevice(), opcje).Run();
```

Konwersję można także uruchomić przy użyciu strumienia MemoryStream dla wejściowej zawartości LaTeX.

## Krok 15: Uruchom konwersję LaTeX-a na XPS za pomocą głównego terminala wejściowego (alternatywa)

```csharp
// nowy TeXJob(nowe XpsDevice(), opcje).Run();
```

Uruchom konwersję bezpośrednio z głównego terminala wejściowego.

## Wniosek

Wykonując te proste kroki, możesz bez wysiłku konwertować dokumenty LaTeX do formatu XPS przy użyciu Aspose.TeX dla .NET. Ta potężna biblioteka zapewnia elastyczność i opcje dostosowywania do konkretnych wymagań.

## Często zadawane pytania

### P1: Czy Aspose.TeX jest kompatybilny z najnowszymi frameworkami .NET?

O1: Tak, Aspose.TeX jest regularnie aktualizowany, aby zapewnić kompatybilność z najnowszymi frameworkami .NET.

### P2: Czy mogę dostosować format wyjściowy inny niż XPS?

 Odpowiedź 2: Aspose.TeX obsługuje różne formaty wyjściowe. Zapoznaj się z dokumentacją[Tutaj](https://reference.aspose.com/tex/net/) dla szczegółów.

### P3: Jak uzyskać tymczasową licencję na Aspose.TeX?

 A3: Możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).

### P4: Gdzie mogę szukać pomocy lub podzielić się swoimi doświadczeniami z Aspose.TeX?

 A4: Odwiedź forum Aspose.TeX[Tutaj](https://forum.aspose.com/c/tex/47) za wsparcie społeczności.

### P5: Czy dostępne są przykładowe dokumenty do przetestowania?

 A5: Zapoznaj się z przykładami Aspose.TeX[Tutaj](https://github.com/aspose-tex/Aspose.TeX-for-.NET).