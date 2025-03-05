---
title: Renderuj figury LaTeX do formatu PNG za pomocą Aspose.TeX (C#)
linktitle: Renderuj figury LaTeX do formatu PNG za pomocą Aspose.TeX (C#)
second_title: Aspose.TeX API .NET
description: Zapoznaj się z obszernym przewodnikiem na temat renderowania figur LaTeX do formatu PNG przy użyciu Aspose.TeX w języku C#. Ucz się krok po kroku na przykładach kodu.
type: docs
weight: 10
url: /pl/net/render-latex-figures/png-latex-figure-renderer-csharp/
---
## Wstęp

Jeśli zagłębiasz się w świat składu i tworzenia dokumentów w .NET, prawdopodobnie znasz wyzwania związane z renderowaniem figur LaTeX. W tym przewodniku krok po kroku odkryjemy, jak używać Aspose.TeX dla .NET do renderowania figur LaTeX do formatu PNG przy użyciu C#. Aspose.TeX zapewnia wydajne i elastyczne rozwiązanie do obsługi dokumentów LaTeX, co czyni go nieocenionym narzędziem dla programistów pracujących nad generowaniem i formatowaniem dokumentów.

## Warunki wstępne

Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

-  Biblioteka Aspose.TeX dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.TeX dla .NET. Możesz go pobrać[Tutaj](https://releases.aspose.com/tex/net/).

## Importuj przestrzenie nazw

W kodzie C# rozpocznij od zaimportowania niezbędnych przestrzeni nazw. Ten krok gwarantuje, że będziesz mieć dostęp do wymaganych klas i funkcjonalności.

```csharp
using Aspose.TeX.Features;
```

## Renderuj figury LaTeX do formatu PNG

### Krok 1: Skonfiguruj opcje renderowania

Zacznij od utworzenia opcji renderowania i ustawienia parametrów, takich jak rozdzielczość obrazu, preambuła, współczynnik skalowania, kolor tła i inne.

```csharp
FigureRendererOptions options = new PngFigureRendererOptions() { Resolution = 150 };
options.Preamble = "\\usepackage{pict2e}";
options.Scale = 3000;
options.BackgroundColor = System.Drawing.Color.White;
options.LogStream = new System.IO.MemoryStream();
options.ShowTerminal = true;
```

### Krok 2: Zdefiniuj strumień wyjściowy i wymiary

Utwórz strumień wyjściowy dla obrazu PNG i zmiennych do przechowywania wymiarów wynikowego obrazu.

```csharp
System.Drawing.SizeF size = new System.Drawing.SizeF();
using (System.IO.Stream stream = System.IO.File.Open(
   System.IO.Path.Combine("Your Output Directory", "text-and-formula.png"), System.IO.FileMode.Create))
{
    // Kod do renderowania znajduje się tutaj
}
```

### Krok 3: Uruchom renderowanie

Zaimplementuj proces renderowania przy użyciu biblioteki Aspose.TeX. Podaj kod LaTeX, strumień wyjściowy, opcje renderowania i zmienną rozmiaru.

```csharp
new PngFigureRenderer().Render(@"\setlength{\unitlength}{0.8cm}
\begin{picture}(6,5)
    % LaTeX figure code goes here
\end{picture}", stream, options, out size);
```

### Krok 4: Wyświetl wyniki

Na koniec wyświetl wyniki, łącznie z raportami o błędach i rozmiarem wyrenderowanego obrazu.

```csharp
System.Console.Out.WriteLine(options.ErrorReport);
System.Console.Out.WriteLine();
System.Console.Out.WriteLine("Size: " + size);
```

## Wniosek

Dzięki Aspose.TeX dla .NET renderowanie figur LaTeX do formatu PNG staje się procesem płynnym. Ten samouczek przeprowadził Cię przez najważniejsze kroki, od skonfigurowania opcji renderowania po wyświetlenie końcowych wyników.

## Często zadawane pytania

### P1: Czy Aspose.TeX jest kompatybilny ze wszystkimi poleceniami LaTeX?

 O1: Aspose.TeX obsługuje szeroką gamę poleceń LaTeX, ale zaleca się zapoznanie z[dokumentacja](https://reference.aspose.com/tex/net/) aby uzyskać szczegółowe informacje.

### P2: Czy mogę wypróbować Aspose.TeX przed zakupem?

 Odpowiedź 2: Tak, możesz skorzystać z bezpłatnej wersji próbnej[Tutaj](https://releases.aspose.com/).

### P3: Jak uzyskać wsparcie dla Aspose.TeX?

 A3: Odwiedź[Forum Aspose.TeX](https://forum.aspose.com/c/tex/47)za wsparcie społeczności i dyskusje.

### P4: Gdzie mogę znaleźć tymczasowe licencje dla Aspose.TeX?

 A4: Dostępne są licencje tymczasowe[Tutaj](https://purchase.aspose.com/temporary-license/).

### P5: Jaka jest struktura cenowa Aspose.TeX?

Odpowiedź 5: Zapoznaj się ze szczegółami cenowymi i dokonaj zakupu[Tutaj](https://purchase.aspose.com/buy).