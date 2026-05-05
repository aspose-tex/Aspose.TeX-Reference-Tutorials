---
date: 2025-12-30
description: Dowiedz się, jak konwertować TeX na XPS w .NET przy użyciu Aspose.TeX.
  Postępuj zgodnie z tym przewodnikiem krok po kroku, aby uzyskać płynną integrację
  i niezawodny wynik.
linktitle: How to Convert TeX to XPS in .NET
second_title: Aspose.TeX .NET API
title: Jak przekonwertować TeX na XPS w .NET
url: /pl/net/xps-output/typeset-tex-to-xps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak przekonwertować TeX na XPS w .NET

## Jak przekonwertować TeX na XPS – Wprowadzenie

Witamy w naszym kompleksowym, krok po kroku przewodniku, jak **przekonwertować TeX** na format XPS w środowisku .NET. Korzystając z potężnej biblioteki Aspose.TeX, będziesz mógł zintegrować konwersję TeX‑do‑XPS w dowolnej aplikacji .NET — niezależnie od tego, czy jest to narzędzie desktopowe, usługa internetowa, czy zautomatyzowany potok raportowania. W kolejnych sekcjach przeprowadzimy Cię przez wszystkie niezbędne ustawienia, pokażemy dokładny kod oraz wyjaśnimy, dlaczego każdy element ma znaczenie, abyś mógł wdrożyć rozwiązanie z pełnym przekonaniem.

## Szybkie odpowiedzi
- **Co obejmuje ten samouczek?** Konwertowanie plików TeX na XPS przy użyciu Aspose.TeX dla .NET.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna działa do testów; licencja komercyjna jest wymagana w produkcji.  
- **Jak długo trwa implementacja?** Zazwyczaj mniej niż 15 minut dla podstawowej konwersji.  
- **Gdzie mogę pobrać bibliotekę?** Pobierz ze strony oficjalnej wersji Aspose.TeX.

## Wymagania wstępne

Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania:

- Aspose.TeX dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.TeX. Możesz ją pobrać [tutaj](https://releases.aspose.com/tex/net/).

- Dokumentacja: Zapoznaj się z biblioteką, odwołując się do dokumentacji [tutaj](https://reference.aspose.com/tex/net/).

- Katalogi wejściowy i wyjściowy: Skonfiguruj katalogi wejściowy i wyjściowy zgodnie z przykładowym kodem.

Teraz, gdy wszystko jest skonfigurowane, przejdźmy do przewodnika krok po kroku.

## Importowanie przestrzeni nazw

W swojej aplikacji .NET rozpocznij od zaimportowania niezbędnych przestrzeni nazw. Zapewni to dostęp do funkcjonalności Aspose.TeX wymaganych do składu TeX na XPS.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
```

## Krok 1: Ustaw opcje konwersji

Zdefiniuj opcje konwersji, określając format ObjectTeX przy użyciu rozszerzenia silnika ObjectTeX. Ustaw także nazwę zadania, katalogi wejściowy i wyjściowy oraz szczegóły wyjścia terminala.

```csharp
// Create conversion options for default ObjectTeX format upon ObjectTeX engine extension.
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
// Specify a job name.
options.JobName = "external-file-stream";
// Specify a file system working directory for input.
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
// Specify a file system working directory for output.
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
// Specify that the terminal output must be written to a file in the output working directory.
// The file name is <job_name>.trm.
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## Krok 2: Utwórz strumień dokumentu XPS

Otwórz strumień do zapisu składanego dokumentu XPS. Nazwa pliku nie musi być identyczna z nazwą zadania.

```csharp
using (Stream stream = File.Open(Path.Combine("Your Output Directory", options.JobName + ".xps"), FileMode.Create))
```

## Krok 3: Uruchom zadanie TeX

Zainicjuj i uruchom zadanie TeX, określając nazwę dokumentu, XpsDevice oraz opcje konwersji.

```csharp
new TeXJob("hello-world", new XpsDevice(stream), options).Run();
```

Gratulacje! Pomyślnie przetworzyłeś TeX na XPS w .NET przy użyciu Aspose.TeX. Śmiało eksploruj dalsze funkcje i opcje zgodnie ze swoimi wymaganiami.

## Zakończenie

W tym samouczku omówiliśmy kluczowe kroki, które umożliwiają płynną konwersję dokumentów TeX do formatu XPS w .NET przy użyciu Aspose.TeX. Postępując zgodnie z tym przewodnikiem, zyskałeś cenną wiedzę o możliwościach biblioteki i sposobach ich wykorzystania w swoich projektach.

## FAQ

### P1: Czy Aspose.TeX jest kompatybilny z .NET Core?

A1: Tak, Aspose.TeX jest w pełni kompatybilny z .NET Core.

### P2: Czy mogę używać Aspose.TeX w projektach komercyjnych?

A2: Oczywiście! Aspose.TeX jest dostępny zarówno do użytku komercyjnego, jak i prywatnego.

### P3: Gdzie mogę znaleźć dodatkowe przykłady i zasoby?

A3: Przeglądaj dokumentację Aspose.TeX [tutaj](https://reference.aspose.com/tex/net/) aby zobaczyć więcej przykładów i szczegółowe zasoby.

### P4: Jak mogę uzyskać wsparcie dla Aspose.TeX?

A4: Odwiedź forum wsparcia Aspose.TeX [tutaj](https://forum.aspose.com/c/tex/47), aby uzyskać pomoc od społeczności.

### P5: Czy dostępna jest darmowa wersja próbna?

A5: Tak, możesz uzyskać dostęp do darmowej wersji próbnej [tutaj](https://releases.aspose.com/).

## Najczęściej zadawane pytania

**Q: Czy mogę dostosować wyjście XPS (np. rozmiar strony lub marginesy)?**  
A: Tak. Możesz zmienić ustawienia XpsDevice lub zmodyfikować źródło TeX, aby kontrolować układ strony przed konwersją.

**Q: Co się stanie, jeśli plik wejściowy TeX zawiera błędy?**  
A: Proces konwersji zapisuje szczegóły błędów do pliku wyjścia terminala (`*.trm`). Przejrzyj ten plik, aby zdiagnozować i naprawić problemy.

**Q: Czy można konwertować wiele plików TeX w jednym uruchomieniu?**  
A: Możesz iterować po kolekcji plików źródłowych TeX, tworząc osobny TeXJob dla każdego, jednocześnie używając tej samej instancji `TeXOptions`.

**Q: Czy Aspose.TeX obsługuje pakiety LaTeX takie jak `amsmath` lub `graphicx`?**  
A: Większość standardowych pakietów LaTeX jest obsługiwana. Sprawdź oficjalną dokumentację, aby uzyskać pełną listę kompatybilnych pakietów.

**Q: Jak osadzić czcionki w wygenerowanym pliku XPS?**  
A: Aspose.TeX automatycznie osadza czcionki używane przez silnik TeX. Upewnij się, że wymagane czcionki są zainstalowane na maszynie wykonującej konwersję.

---

**Ostatnia aktualizacja:** 2025-12-30  
**Testowano z:** Aspose.TeX for .NET 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}