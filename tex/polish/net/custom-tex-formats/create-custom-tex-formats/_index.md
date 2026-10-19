---
date: 2026-10-19
description: Dowiedz się, jak przeprowadzić generowanie dokumentów tex, utworzyć własny
  format tex i ustawić katalog wejściowy tex przy użyciu Aspose.TeX dla .NET. Przewodnik
  krok po kroku z fragmentami kodu i wskazówkami rozwiązywania problemów.
keywords:
- tex document generation
- create custom tex format
- set tex input directory
- custom tex macros
lastmod: 2026-10-19
linktitle: Tworzenie własnych formatów TeX w .NET
og_description: Generowanie dokumentów tex przy użyciu Aspose.TeX pozwala utworzyć
  własny format tex i ustawić katalog wejściowy tex w .NET. Skorzystaj z tego przewodnika,
  aby uzyskać wyjście w formacie XPS, PDF lub PNG.
og_image_alt: Developer guide showing tex document generation using Aspose.TeX in
  .NET
og_title: Jak generować dokumenty tex z formatem w .NET
schemas:
- author: Aspose
  dateModified: '2026-10-19'
  description: Learn how to perform tex document generation, create custom tex format
    and set tex input directory using Aspose.TeX for .NET. Step‑by‑step guide with
    code snippets and troubleshooting tips.
  headline: How to do tex document generation with format in .NET
  type: TechArticle
- description: Learn how to perform tex document generation, create custom tex format
    and set tex input directory using Aspose.TeX for .NET. Step‑by‑step guide with
    code snippets and troubleshooting tips.
  name: How to do tex document generation with format in .NET
  steps:
  - name: '**Aspose.TeX for .NET** – download it from the [Aspose.TeX website](https://releases.aspose.com/tex/net/).'
    text: '**Aspose.TeX for .NET** – download it from the [Aspose.TeX website](https://releases.aspose.com/tex/net/).'
  - name: A **.NET development environment** (Visual Studio, VS Code, or the .NET
      CLI).
    text: A **.NET development environment** (Visual Studio, VS Code, or the .NET
      CLI).
  - name: (Optional) A valid **Aspose.TeX license** for production use.
    text: (Optional) A valid **Aspose.TeX license** for production use.
  type: HowTo
- questions:
  - answer: Absolutely. Replace `new XpsDevice()` with `new PdfDevice()` and adjust
      the output path accordingly.
    question: Can I output PDF instead of XPS?
  - answer: Yes. Any modification to macros or engine settings requires re‑running
      `tex -ini` to generate a fresh `.fmt` file.
    question: Do I need to re‑compile the format file after every change?
  type: FAQPage
second_title: Aspose.TeX .NET API
tags:
- tex document generation
- Aspose.TeX
- .NET document processing
- custom tex format
title: Jak generować dokumenty tex z formatem w .NET
url: /pl/net/custom-tex-formats/create-custom-tex-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generować dokumenty tex z formatem w .NET

W nowoczesnym rozwoju .NET, **generowanie dokumentów tex** jest potężnym sposobem na tworzenie wysokiej jakości wyjścia typograficznego bez polegania na zewnętrznych instalacjach LaTeX. Aspose.TeX for .NET daje pełną kontrolę: możesz **tworzyć własny format tex**, wskazać silnik na dedykowany folder wejściowy i eksportować do XPS, PDF, PNG lub innych urządzeń — wszystko z prostego kodu C#.

## Szybkie odpowiedzi
- **Co oznacza „create custom tex format”?** Oznacza to definiowanie własnej konfiguracji silnika TeX oraz skompilowanego pliku formatu, tak aby procesor stosował Twoje makra i ustawienia.  
- **Jakiej biblioteki potrzebuję?** Aspose.TeX for .NET, która obsługuje ponad 30 formatów wejścia i wyjścia.  
- **Czy muszę ustawić katalog wejściowy tex?** Tak – użyj `InputWorkingDirectory`, aby poinformować silnik, gdzie znajdują się pliki pomocnicze.  
- **Jakie wyjścia mogę generować?** XPS, PDF, PNG, TIFF i wiele innych formatów urządzeń.  
- **Czy wymagana jest licencja do produkcji?** Ważna licencja Aspose.TeX jest obowiązkowa przy wdrożeniach komercyjnych.

## Co to jest własny format tex?
Własny format tex to prekompilowana kolekcja makr i ustawień silnika, którą procesor TeX ładuje przy uruchomieniu. Tworząc go, możesz osadzić branding korporacyjny, wymusić standardy układu i skrócić czas kompilacji powtarzalnych dokumentów. Umożliwia to spójne stylowanie wszystkich generowanych dokumentów oraz upraszcza utrzymanie złożonych przepływów typograficznych.

## Dlaczego ustawiać katalog wejściowy tex?
Ustawienie **katalogu wejściowego tex** informuje silnik, gdzie ma szukać plików pomocniczych, takich jak pliki stylów, własne czcionki czy dodatkowe pakiety makr. Eliminuje to błędy „plik nie znaleziony” i utrzymuje porządek w folderze projektu. Poprawia także powtarzalność budowania, zapewniając, że wszystkie zasoby są rozwiązywane z określonej lokalizacji.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

1. **Aspose.TeX for .NET** – pobierz go ze [strony Aspose.TeX](https://releases.aspose.com/tex/net/).  
2. **Środowisko programistyczne .NET** (Visual Studio, VS Code lub .NET CLI).  
3. (Opcjonalnie) Ważna **licencja Aspose.TeX** do użytku produkcyjnego.

## Importowanie przestrzeni nazw

Poniższe przestrzenie nazw zapewniają dostęp do podstawowych klas Aspose.TeX.  
Klasy związane z `Document` znajdują się w `Aspose.TeX`, natomiast opcje i urządzenia w `Aspose.TeX.Rendering`.

Klasa `Document` jest obiektem najwyższego poziomu, który reprezentuje pojedynczy dokument TeX w pamięci.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using Aspose.TeX.ResourceProviders;
using System.IO;
using System.Text;
```

## Krok 1: utwórz dostawcę formatu

`FormatProvider` informuje silnik, gdzie znajduje się skompilowany plik formatu (`customtex.fmt`). Zastąp `"Your Output Directory"` absolutną ścieżką, która zawiera Twój własny format.

`FormatProvider` jest lekkim wrapperem, który ładuje plik `.fmt` raz i ponownie używa go przy każdej konwersji, znacząco zwiększając wydajność zadań wsadowych.

```csharp
using (FormatProvider formatProvider =
    new FormatProvider(new InputFileSystemDirectory("Your Output Directory"), "customtex"))
{
```

## Krok 2: skonfiguruj opcje konwersji (i ustaw katalog wejściowy tex)

Tutaj tworzymy instancję `TeXOptions`. Właściwość `InputWorkingDirectory` **ustawia katalog wejściowy tex**, aby silnik mógł znaleźć wszystkie pliki pomocnicze, takie jak własne pakiety lub czcionki.

`TeXOptions` pozwala także określić urządzenie wyjściowe, rozmiar strony i jakość renderowania. Przy generowaniu na dużą skalę możesz włączyć `EnableParallelProcessing`, aby przyspieszyć renderowanie na serwerach wielordzeniowych.

```csharp
    TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX(formatProvider));
    options.JobName = "typeset-with-custom-format";
    options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
    options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

## Krok 3: uruchom zadanie

Teraz przekaż prosty ciąg TeX do silnika, wybierz urządzenie wyjściowe (XPS w tym przykładzie) i wykonaj zadanie. `TeXEngine` odczytuje własny format, przetwarza źródło i zapisuje wynik na wybranym urządzeniu.

`TeXEngine` jest podstawowym procesorem Aspose.TeX, który parsuje źródło TeX, stosuje własny format i przesyła renderowane strony do wskazanego urządzenia.

```csharp
    new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
        "Congratulations! You have successfully typeset this text with your own TeX format!\\end")),
        new XpsDevice(), options).Run();
```

## Krok 4: dopracuj wyjście w terminalu

Dodanie pustej linii po zakończeniu zadania ułatwia czytanie logów konsoli, szczególnie gdy łańczysz wiele konwersji w skrypcie.

`Console.WriteLine()` zapisuje linię tekstu do standardowego strumienia wyjścia. Jest używany tutaj wyłącznie do wizualnego oddzielenia; nie wpływa na wygenerowany dokument.

```csharp
    options.TerminalOut.Writer.WriteLine();
}
// ExEnd:TypesetWithCustomTeXFormat
```

Gratulacje! Utworzyłeś **własny format tex** i użyłeś go do **generowania dokumentów tex** w .NET. Możesz zamienić `XpsDevice` na `PdfDevice`, `PngDevice` lub dowolne inne obsługiwane urządzenie, aby dopasować je do swoich potrzeb.

## Typowe problemy i rozwiązania

| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| *„Format file not found”* | Nieprawidłowa ścieżka w `FormatProvider` | Zweryfikuj, że `"Your Output Directory"` zawiera `customtex.fmt` oraz że ścieżka jest absolutna lub poprawnie względna względem pliku wykonywalnego. |
| *„Cannot find input file”* | `InputWorkingDirectory` wskazuje niewłaściwy folder | Upewnij się, że `"Your Input Directory"` zawiera plik źródłowy TeX lub że przekazujesz źródło jako strumień (tak jak w przykładzie). |
| *Terminal output garbled* | Niepasujące kodowanie | Użyj `Encoding.UTF8`, jeśli Twoje źródło TeX zawiera znaki nie‑ASCII. |
| *XPS file is empty* | Zadanie nie zostało wykonane z powodu wcześniejszego wyjątku | Sprawdź konsolę pod kątem komunikatów o błędach; często wskazują one brakujące pakiety lub błędy składni w ciągu TeX. |

## Najczęściej zadawane pytania

**Q1: Czy mogę używać Aspose.TeX for .NET z innymi bibliotekami Aspose?**  
A: Tak, Aspose.TeX integruje się płynnie z Aspose.PDF, Aspose.Words i innymi produktami Aspose w pełnych łańcuchach przetwarzania dokumentów.

**Q2: Czy dostępna jest darmowa wersja próbna Aspose.TeX for .NET?**  
A: Tak, możesz pobrać wersję próbną ze **strony pobierania darmowej wersji próbnej Aspose.TeX** (https://releases.aspose.com/tex/net/).

**Q3: Jak mogę uzyskać wsparcie dla Aspose.TeX for .NET?**  
A: Odwiedź [forum Aspose.TeX](https://forum.aspose.com/c/tex/47) po pomoc społeczności lub zapoznaj się z opcjami premium na **stronie zakupu wsparcia premium** (https://purchase.aspose.com/buy).

**Q4: Czy dostępne są tymczasowe licencje dla Aspose.TeX for .NET?**  
A: Tak, możesz poprosić o taką na **stronie wnioskowania o tymczasową licencję** (https://purchase.aspose.com/temporary-license/).

**Q5: Gdzie mogę znaleźć oficjalną dokumentację API?**  
A: Kompleksowa dokumentacja jest dostępna w **dokumentacji referencyjnej API** (https://reference.aspose.com/tex/net/).

### Dodatkowe Pytania i Odpowiedzi

**Q: Czy mogę wyjść w formacie PDF zamiast XPS?**  
A: Oczywiście. Zamień `new XpsDevice()` na `new PdfDevice()` i odpowiednio dostosuj ścieżkę wyjścia.

**Q: Czy muszę ponownie kompilować plik formatu po każdej zmianie?**  
A: Tak. Każda modyfikacja makr lub ustawień silnika wymaga ponownego uruchomienia `tex -ini`, aby wygenerować nowy plik `.fmt`.

## Podsumowanie

Aspose.TeX for .NET zapewnia **solidne, wysokowydajne rozwiązanie do generowania dokumentów tex**, umożliwiając **tworzenie własnego formatu tex**, ustawienie **katalogu wejściowego tex** oraz wyjście na dowolne obsługiwane urządzenie. Włącz powyższe kroki do swojego potoku CI/CD, zautomatyzuj generowanie raportów na dużą skalę lub zbuduj własny silnik publikacji spełniający standardy brandingu Twojej organizacji.

---

**Last Updated:** 2026-10-19  
**Tested With:** Aspose.TeX 24.11 for .NET  
**Author:** Aspose

## Powiązane samouczki

- [Pobierz strumień pliku TeX (C#) przy użyciu Aspose.TeX API Wymagany katalog wejściowy](/tex/net/advanced-io/required-input-directory-csharp/)
- [Jak utworzyć PDF przy użyciu Aspose.TeX for .NET – krok po kroku](/tex/net/pdf-output/)
- [Jak utworzyć dokument XPS w .NET – konwersja TeX do wyjścia XPS przy użyciu Aspose.TeX for .NET](/tex/net/xps-output/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}