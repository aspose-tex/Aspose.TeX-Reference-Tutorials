---
title: Zastąp nazwę zadania i zapisz dane wyjściowe terminala w formacie Zip (C#)
linktitle: Zastąp nazwę zadania i zapisz dane wyjściowe terminala w formacie Zip (C#)
second_title: Aspose.TeX API .NET
description: Dowiedz się, jak zastąpić nazwy zadań i zapisać dane wyjściowe terminala w pliku ZIP przy użyciu Aspose.TeX dla .NET. Przewodnik krok po kroku z przykładami C#.
weight: 11
url: /pl/net/job-output/override-job-name-zip-output-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zastąp nazwę zadania i zapisz dane wyjściowe terminala w formacie Zip (C#)

## Wstęp

tym samouczku przyjrzymy się, jak zastąpić nazwę zadania i zapisać dane wyjściowe terminala w pliku ZIP przy użyciu Aspose.TeX dla .NET. Aspose.TeX to potężna biblioteka, która umożliwia programistom pracę z dokumentami TeX w aplikacjach .NET. W tym konkretnym przykładzie skupimy się na typowym zadaniu – zapisaniu danych wyjściowych terminala do pliku ZIP z możliwością nadpisania nazwy zadania.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:

- Praktyczna znajomość języka C#
- Zainstalowany Aspose.TeX dla .NET
- Wprowadź archiwum ZIP dla katalogu roboczego
- Wyjściowe archiwum ZIP dla danych wyjściowych terminala

## Importuj przestrzenie nazw

Zanim zagłębisz się w kod, pamiętaj o uwzględnieniu niezbędnych przestrzeni nazw w projekcie C#:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Pdf;
using System.IO;
```

Podzielmy teraz przykład na wiele kroków, które poprowadzą Cię przez cały proces.

## Krok 1: Otwórz wejściowe i wyjściowe strumienie ZIP

```csharp
using (Stream inZipStream = File.Open(Path.Combine("Your Input Directory", "zip-in.zip"), FileMode.Open))
using (Stream outZipStream = File.Open(Path.Combine("Your Output Directory", "terminal-out-to-zip.zip"), FileMode.Create))
{
    // Kod kroku 1 znajduje się tutaj
}
```

## Krok 2: Ustaw opcje konwersji

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
options.JobName = "terminal-output-to-zip";
options.InputWorkingDirectory = new InputZipDirectory(inZipStream, "in");
options.OutputWorkingDirectory = new OutputZipDirectory(outZipStream);
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## Krok 3: Zdefiniuj opcje zapisywania

```csharp
options.SaveOptions = new PdfSaveOptions();
```

## Krok 4: Uruchom zadanie TeX

```csharp
new TeXJob("hello-world", new PdfDevice(), options).Run();
```

## Krok 5: Sfinalizuj wyjściowe archiwum ZIP

```csharp
((OutputZipDirectory)options.OutputWorkingDirectory).Finish();
```

## Wniosek

Gratulacje! Pomyślnie nauczyłeś się, jak zastąpić nazwę zadania i zapisać dane wyjściowe terminala do pliku ZIP przy użyciu Aspose.TeX dla .NET. Ta technika może być niezwykle przydatna podczas pracy z dokumentami TeX w aplikacjach C#.

## Często zadawane pytania

### P1: Czy mogę używać Aspose.TeX dla .NET z innymi językami .NET, takimi jak VB.NET?

O1: Tak, Aspose.TeX dla .NET jest kompatybilny ze wszystkimi językami .NET.

### P2: Gdzie mogę znaleźć więcej dokumentacji dla Aspose.TeX dla .NET?

 A2: Odwiedź[dokumentacja](https://reference.aspose.com/tex/net/) aby uzyskać szczegółowe informacje.

### P3: Jak mogę uzyskać tymczasową licencję na Aspose.TeX?

 A3: Uzyskaj[licencja tymczasowa](https://purchase.aspose.com/temporary-license/) do celów testowych.

### P4: Czy istnieje forum społecznościowe dotyczące wsparcia Aspose.TeX?

 A4: Tak, dołącz do[Forum Aspose.TeX](https://forum.aspose.com/c/tex/47) za wsparcie społeczności.

### P5: Gdzie mogę kupić Aspose.TeX dla .NET?

 Odpowiedź 5: Możesz kupić Aspose.TeX[Tutaj](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
