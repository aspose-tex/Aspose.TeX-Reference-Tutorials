---
date: 2026-03-26
description: Dowiedz się, jak tworzyć obrazy PNG z LaTeX, konwertując TeX na PNG przy
  użyciu Aspose.TeX dla C#. Ten przewodnik pokazuje, jak generować PNG z TeX, obsługiwać
  strumienie i przechwytywać dane wejściowe z terminala.
linktitle: Create latex png – Convert TeX to PNG with Aspose.TeX C#
second_title: Aspose.TeX .NET API
title: Utwórz PNG LaTeX – konwertuj TeX na PNG za pomocą Aspose.TeX C#
url: /pl/net/advanced-io/stream-input-image-output-terminal-input-csharp/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz obraz PNG LaTeX – Konwertuj TeX na PNG przy użyciu Aspose.TeX C#

W tym obszernej tutorialu **utworzysz obraz PNG LaTeX** z ciągu źródłowego TeX przy użyciu Aspose.TeX dla C#. Niezależnie od tego, czy potrzebujesz osadzić formuły matematyczne na stronie internetowej, generować obrazy podglądu w usłudze chmurowej, czy automatyzować tworzenie raportów, przeprowadzimy Cię przez obsługę strumieni, konfigurowanie wyjścia obrazu i przechwytywanie wejścia terminala — wszystko bez dotykania systemu plików.

## Szybkie odpowiedzi
- **Co robi Aspose.TeX?** Analizuje źródło TeX i renderuje je do różnych formatów, w tym PNG.  
- **Czy mogę konwertować TeX na PNG bez zapisywania plików na dysku?** Tak – możesz podać TeX za pomocą `MemoryStream` i bezpośrednio przechwycić bajty PNG.  
- **Jakie wersje .NET są obsługiwane?** Wszystkie współczesne wersje .NET (Framework 4.6+, .NET Core 3.1+, .NET 5/6).  
- **Czy potrzebna jest licencja do użytku produkcyjnego?** Licencja komercyjna jest wymagana w produkcji; dostępna jest darmowa wersja próbna.  
- **Jaką rozdzielczość obrazu mogę ustawić?** Właściwość `PngSaveOptions.Resolution` pozwala określić DPI (np. 300 dpi).

## Jak utworzyć obraz PNG LaTeX z TeX przy użyciu Aspose.TeX?
Poniżej zobaczysz przykład krok po kroku, który odczytuje fragment TeX ze strumienia pamięci, uruchamia zadanie renderowania i zwraca bajty PNG. Ten sam wzorzec działa dla dowolnego dokumentu TeX, który musisz **przekonwertować tex na png**.

## Co to jest „convert tex to png”?
Konwersja TeX na PNG oznacza wzięcie ciągu znaków w formacie TeX (język używany w dokumentach naukowych) i wyrenderowanie go jako obrazu rastrowego. Jest to przydatne, gdy chcesz osadzić formuły matematyczne lub całe strony TeX w stronach internetowych, aplikacjach mobilnych lub w dowolnym środowisku, które nie potrafi natywnie renderować TeX.

## Dlaczego generować PNG z TeX przy użyciu Aspose.TeX?
- **Brak zewnętrznych zależności** – Aspose.TeX jest czystą biblioteką .NET, więc nie potrzebujesz dystrybucji TeX na serwerze.  
- **API przyjazne strumieniom** – Działa bezpośrednio z `MemoryStream`, co czyni je idealnym dla usług chmurowych i mikro‑serwisów.  
- **Precyzyjna kontrola** – Możesz ustawić rozdzielczość obrazu, katalogi wyjściowe, a nawet przechwycić interaktywne wejście terminala.  

## Wymagania wstępne
- Podstawowa znajomość C#.  
- Aspose.TeX dla .NET zainstalowany – możesz go pobrać **[tutaj](https://releases.aspose.com/tex/net/)**.  
- Środowisko programistyczne C# (Visual Studio, VS Code, Rider itp.).  

## Importowanie przestrzeni nazw
Dodaj wymagane dyrektywy `using` na początku pliku C#, aby uzyskać dostęp do klas Aspose.TeX:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Image;
using System.IO;
using System.Text;
```

## Krok 1: Konfiguracja opcji konwersji
Skonfiguruj potok konwersji. Tutaj informujemy Aspose.TeX, aby traktował aplikację jako aplikację konsolową, określamy foldery wejścia/wyjścia, kierujemy I/O terminala i żądamy wyjścia PNG w 300 dpi.

```csharp
// ExStart:TakeMainInputFromStream-AuxFromFileSystem-TakeTerminalInputFromConsole-AlternativeImagesStorage
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
options.JobName = "stream-in-image-out";
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
options.TerminalIn = new InputConsoleTerminal();
options.TerminalOut = new OutputConsoleTerminal();
options.SaveOptions = new PngSaveOptions() { Resolution = 300 };
```

## Krok 2: Utworzenie urządzenia obrazu i uruchomienie zadania
`ImageDevice` przechwytuje wyrenderowane dane PNG. Dostarczamy prosty fragment TeX za pomocą `MemoryStream`, uruchamiamy zadanie i pozwalamy Aspose.TeX wykonać ciężką pracę.

```csharp
ImageDevice device = new ImageDevice();
TeXJob job = new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
    "\\hrule height 10pt width 95pt\\vskip10pt\\hrule height 5pt")),
    device, options);
job.Run();
```

## Krok 3: Dostarczenie wejścia w konsoli
Gdy konsola wyświetli zapytanie, wpisz **ABC**, naciśnij **Enter**, następnie wpisz **\end** i ponownie naciśnij **Enter**. To pokazuje, jak można przechwycić wejście terminala podczas działania silnika TeX.

## Krok 4: Dostosowanie wyjścia
Po zakończeniu zadania możesz wypisać znak nowej linii w konsoli i pobrać surowe bajty PNG z urządzenia. Tablica `result` zawiera jeden obraz PNG na każdą stronę.

```csharp
options.TerminalOut.Writer.WriteLine();
byte[][] result = device.Result;
// ExEnd:TakeMainInputFromStream-AuxFromFileSystem-TakeTerminalInputFromConsole-AlternativeImagesStorage
```

Możesz teraz zapisać `result[0]` do pliku, wysłać go przez sieć lub osadzić bezpośrednio w komponencie UI.

## Typowe problemy i rozwiązania

| Problem | Dlaczego się pojawia | Rozwiązanie |
|-------|----------------|-----|
| **Brak wyjścia PNG** | `SaveOptions` nie ustawione lub rozdzielczość wynosi zero. | Upewnij się, że `options.SaveOptions = new PngSaveOptions() { Resolution = 300 };` |
| **Konsola zawiesza się** | Wejście TeX nigdy nie otrzymuje `\end`. | Zawsze zakończ strumień TeX przy pomocy `\end` (lub `\stop`). |
| **Nieprawidłowy rozmiar obrazu** | Domyślna DPI wynosi 96. | Zwiększ `Resolution` w `PngSaveOptions`. |
| **Ścieżki systemu plików nie znaleziono** | Nieprawidłowe ciągi katalogu roboczego. | Użyj ścieżek bezwzględnych lub sprawdź, czy katalogi istnieją przed uruchomieniem. |

## Najczęściej zadawane pytania

### P1: Czy mogę używać Aspose.TeX dla .NET w aplikacji nie‑konsolowej?
A1: Oczywiście! Aspose.TeX działa w aplikacjach desktopowych, webowych i usługowych. Wystarczy zamienić terminale konsoli na własne strumienie lub kontrolki UI.

### P2: Jak mogę dostosować rozdzielczość wyjściowego obrazu?
A2: W przykładzie rozdzielczość jest ustawiana przez `PngSaveOptions.Resolution`. Zmień wartość całkowitą (np. `Resolution = 600`), aby uzyskać PNG wyższej jakości.

### P3: Czy dostępna jest wersja próbna?
A3: Tak, możesz wypróbować Aspose.TeX w darmowej wersji próbnej dostępnej **[tutaj](https://releases.aspose.com/)**.

### P4: Gdzie mogę znaleźć dodatkowe wsparcie i pomoc?
A4: Odwiedź forum Aspose.TeX **[tutaj](https://forum.aspose.com/c/tex/47)**, aby uzyskać wsparcie społeczności i dyskusje.

### P5: Jak mogę uzyskać tymczasową licencję dla Aspose.TeX?
A5: Możesz uzyskać tymczasową licencję **[tutaj](https://purchase.aspose.com/temporary-license/)**.

## Podsumowanie
Teraz widzisz, jak **utworzyć obraz PNG LaTeX** przy użyciu Aspose.TeX dla C#. Konfigurując strumienie, ustawiając `ImageDevice` i obsługując wejście terminala, możesz generować obrazy wysokiej rozdzielczości z dowolnego źródła TeX — idealne do raportów, podglądów webowych lub zautomatyzowanych pipeline’ów. Eksperymentuj z różnymi fragmentami TeX, dostosowuj DPI lub integruj otrzymaną tablicę bajtów w własnym UI, aby uzyskać płynne doświadczenie.

---

**Ostatnia aktualizacja:** 2026-03-26  
**Testowano z:** Aspose.TeX 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}