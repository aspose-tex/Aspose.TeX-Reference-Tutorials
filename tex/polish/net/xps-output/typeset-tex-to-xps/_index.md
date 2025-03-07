---
title: Skład TeX-a na XPS w .NET
linktitle: Skład TeX-a na XPS w .NET
second_title: Aspose.TeX API .NET
description: Bez wysiłku konwertuj dokumenty TeX na XPS w .NET za pomocą Aspose.TeX. Zapoznaj się z naszym przewodnikiem krok po kroku, aby zapewnić bezproblemową integrację.
weight: 10
url: /pl/net/xps-output/typeset-tex-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skład TeX-a na XPS w .NET

## Wstęp

Witamy w naszym przewodniku krok po kroku dotyczącym składu TeX-a na XPS w .NET przy użyciu potężnej biblioteki Aspose.TeX. Jeśli chcesz bezproblemowo konwertować dokumenty TeX do formatu XPS w aplikacjach .NET, jesteś we właściwym miejscu. W tym samouczku przeprowadzimy Cię przez cały proces, dzieląc każdy krok, aby zapewnić płynne wdrożenie.

## Warunki wstępne

Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

-  Aspose.TeX dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.TeX. Możesz go pobrać[Tutaj](https://releases.aspose.com/tex/net/).

- Dokumentacja: Zapoznaj się z biblioteką, korzystając z dokumentacji[Tutaj](https://reference.aspose.com/tex/net/).

- Katalogi wejściowe i wyjściowe: skonfiguruj katalogi wejściowe i wyjściowe zgodnie z przykładowym kodem.

Teraz, gdy już wszystko skonfigurowałeś, przejdźmy do przewodnika krok po kroku.

## Importuj przestrzenie nazw

W aplikacji .NET rozpocznij od zaimportowania niezbędnych przestrzeni nazw. Dzięki temu masz dostęp do funkcjonalności Aspose.TeX wymaganych do składu TeX-a na XPS.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
```

## Krok 1: Ustaw opcje konwersji

Zdefiniuj opcje konwersji, określając format ObjectTeX w rozszerzeniu silnika ObjectTeX. Ustaw także nazwę zadania, katalogi wejściowe i wyjściowe oraz szczegóły wyjściowe terminala.

```csharp
// Utwórz opcje konwersji dla domyślnego formatu ObjectTeX po rozszerzeniu silnika ObjectTeX.
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
// Podaj nazwę zadania.
options.JobName = "external-file-stream";
// Określ katalog roboczy systemu plików dla danych wejściowych.
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
// Określ katalog roboczy systemu plików dla danych wyjściowych.
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
// Określ, że dane wyjściowe terminala muszą zostać zapisane w pliku w wyjściowym katalogu roboczym.
// Nazwa pliku to <nazwa_zadania>.trm.
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## Krok 2: Utwórz strumień dokumentów XPS

Otwórz strumień, aby napisać złożony dokument XPS. Nazwa pliku nie musi być taka sama jak nazwa zadania.

```csharp
using (Stream stream = File.Open(Path.Combine("Your Output Directory", options.JobName + ".xps"), FileMode.Create))
```

## Krok 3: Uruchom zadanie TeX

Zainicjuj i uruchom zadanie TeX, określając nazwę dokumentu, XpsDevice i opcje konwersji.

```csharp
new TeXJob("hello-world", new XpsDevice(stream), options).Run();
```

Gratulacje! Pomyślnie przepisałeś TeX na XPS w .NET przy użyciu Aspose.TeX. Zachęcamy do zapoznania się z większą liczbą funkcji i opcji w zależności od konkretnych wymagań.

## Wniosek

W tym samouczku omówiliśmy podstawowe kroki, aby bezproblemowo przekonwertować dokumenty TeX do formatu XPS w .NET przy użyciu Aspose.TeX. Postępując zgodnie z tym przewodnikiem, uzyskałeś cenny wgląd w możliwości biblioteki i sposoby wykorzystania ich w swoich projektach.

## Często zadawane pytania

### P1: Czy Aspose.TeX jest kompatybilny z .NET Core?

O1: Tak, Aspose.TeX jest w pełni kompatybilny z .NET Core.

### P2: Czy mogę używać Aspose.TeX w projektach komercyjnych?

A2: Absolutnie! Aspose.TeX jest dostępny zarówno do użytku komercyjnego, jak i osobistego.

### P3: Gdzie mogę znaleźć dodatkowe przykłady i zasoby?

 A3: Zapoznaj się z dokumentacją Aspose.TeX[Tutaj](https://reference.aspose.com/tex/net/)aby uzyskać więcej przykładów i szczegółowych zasobów.

### P4: Jak mogę uzyskać wsparcie dla Aspose.TeX?

 A4: Odwiedź forum wsparcia Aspose.TeX[Tutaj](https://forum.aspose.com/c/tex/47) aby uzyskać pomoc od społeczności.

### P5: Czy dostępny jest bezpłatny okres próbny?

 Odpowiedź 5: Tak, możesz uzyskać dostęp do bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
