---
title: Renderuj figury LaTeX do SVG za pomocą Aspose.TeX (C#)
linktitle: Renderuj figury LaTeX do SVG za pomocą Aspose.TeX (C#)
second_title: Aspose.TeX API .NET
description: Ulepsz renderowanie dokumentów w .NET dzięki Aspose.TeX. Dowiedz się, jak renderować figury LaTeX do formatu SVG w języku C#, aby zapewnić płynną integrację wyrażeń matematycznych.
weight: 11
url: /pl/net/render-latex-figures/svg-latex-figure-renderer-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Renderuj figury LaTeX do SVG za pomocą Aspose.TeX (C#)

## Wstęp

Jeśli chcesz ulepszyć swoje możliwości renderowania dokumentów w .NET przy użyciu figur LaTeX, Aspose.TeX jest rozwiązaniem dla Ciebie. W tym przewodniku krok po kroku przeprowadzimy Cię przez proces renderowania figur LaTeX do formatu SVG przy użyciu Aspose.TeX w języku C#. Pod koniec tego samouczka będziesz w pełni rozumieć proces, co umożliwi Ci bezproblemowe włączanie wysokiej jakości wyrażeń i liczb matematycznych do swoich dokumentów.

## Warunki wstępne

Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

- Podstawowa znajomość języka programowania C#.
-  Zainstalowana biblioteka Aspose.TeX dla .NET. Możesz go pobrać[Tutaj](https://releases.aspose.com/tex/net/).

## Importuj przestrzenie nazw

W kodzie C# pamiętaj o zaimportowaniu niezbędnych przestrzeni nazw:

```csharp
using Aspose.TeX.Features;
```

Podzielmy teraz samouczek na kilka kroków:

## Krok 1: Utwórz opcje renderowania

```csharp
FigureRendererOptions options = new SvgFigureRendererOptions();
options.Preamble = "\\usepackage{pict2e}";
options.Scale = 3000;
options.BackgroundColor = Color.White;
options.LogStream = new System.IO.MemoryStream();
options.ShowTerminal = true;
```

Tutaj konfigurujemy opcje renderowania, określając preambułę, współczynnik skalowania, kolor tła, strumień dziennika i to, czy wyświetlać dane wyjściowe terminala.

## Krok 2: Zdefiniuj wymiary i strumień wyjściowy

```csharp
SizeF size = new SizeF();
using (Stream stream = File.Open(Path.Combine("Your Output Directory", "text-and-formula.svg"), FileMode.Create))
{
    // Uruchom renderowanie.
    new SvgFigureRenderer().Render("Your LaTeX Code", stream, options, out size);
}
```

Zamień „Twój katalog wyjściowy” na żądany katalog i podaj swój kod LaTeX w postaci ciągu znaków.

## Krok 3: Wyświetl wyniki

```csharp
Console.Out.WriteLine(options.ErrorReport);
Console.Out.WriteLine();
Console.Out.WriteLine("Size: " + size);
```

W tym kroku zostaną wyświetlone raporty o błędach i rozmiar wynikowego obrazu.

## Wniosek

Gratulacje! Pomyślnie nauczyłeś się renderować figury LaTeX do SVG przy użyciu Aspose.TeX w C#. Teraz możesz bezproblemowo integrować wyrażenia i liczby matematyczne z aplikacjami .NET.

## Często zadawane pytania

### P1: Czy korzystanie z Aspose.TeX jest darmowe?

 Odpowiedź 1: Aspose.TeX oferuje bezpłatną wersję próbną. Możesz uzyskać do niego dostęp[Tutaj](https://releases.aspose.com/).

### P2: Gdzie mogę znaleźć dokumentację Aspose.TeX?

 Odpowiedź 2: Zapoznaj się z dokumentacją[Tutaj](https://reference.aspose.com/tex/net/).

### P3: Jak uzyskać wsparcie dla Aspose.TeX?

 Odpowiedź 3: Odwiedź forum pomocy technicznej[Tutaj](https://forum.aspose.com/c/tex/47).

### P4: Czy mogę kupić Aspose.TeX?

 Odpowiedź 4: Tak, możesz kupić Aspose.TeX[Tutaj](https://purchase.aspose.com/buy).

### P5: Czy potrzebuję licencji tymczasowej?

 Odpowiedź 5: W razie potrzeby możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
