---
title: Zastąp nazwę zadania i zapisz dane wyjściowe terminala w Javie
linktitle: Zastąp nazwę zadania i zapisz dane wyjściowe terminala w Javie
second_title: Aspose.TeX API Java
description: Zapoznaj się z przewodnikiem krok po kroku dotyczącym zastępowania nazw zadań i zapisywania danych wyjściowych terminala przy użyciu Aspose.TeX dla języka Java. Usprawnij przetwarzanie dokumentów dzięki zaawansowanym opcjom dostosowywania.
weight: 10
url: /pl/java/customizing-output/override-job-name-disk/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zastąp nazwę zadania i zapisz dane wyjściowe terminala w Javie

## Wstęp

Aspose.TeX dla Java zapewnia zaawansowane funkcje do pracy z plikami TeX, umożliwiając programistom manipulowanie i dostosowywanie przetwarzania dokumentów TeX. W tym samouczku przeprowadzimy Cię przez proces zastępowania nazwy zadania i zapisywania danych wyjściowych terminala w systemie plików przy użyciu Aspose.TeX w Javie.

## Warunki wstępne

Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

- Praktyczna znajomość programowania w języku Java.
-  Zainstalowany Aspose.TeX dla Java. Można go pobrać z[Dokumentacja Aspose.TeX Java](https://reference.aspose.com/tex/java/).

## Importuj pakiety

Aby rozpocząć, zaimportuj niezbędne pakiety do swojego projektu Java. W pliku Java uwzględnij następujące importy:

```java
package com.aspose.tex.OverridenJobNameAndTerminalOutputWrittenToDisk;

import java.io.IOException;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

## Zastąp nazwę zadania i zapisz dane wyjściowe terminala

### Krok 1: Utwórz opcje konwersji

Rozpocznij od utworzenia opcji konwersji dla domyślnego formatu ObjectTeX po rozszerzeniu silnika ObjectTeX. Użyj następującego fragmentu kodu:

```java
//ExStart: OverrideJobName-WriteTerminalOutputToFileSystem
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

### Krok 2: Określ nazwę zadania i katalogi robocze

Określ nazwę zadania, wejściowy katalog roboczy i wyjściowy katalog roboczy. Jeżeli nazwa zadania nie zostanie podana, za nazwę zadania zostanie przyjęty pierwszy argument konstruktora TeXJob. Użyj następującego fragmentu kodu:

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### Krok 3: Zapisz dane wyjściowe terminala do systemu plików

 Określ, że dane wyjściowe terminala muszą zostać zapisane w pliku w wyjściowym katalogu roboczym. Nazwa pliku będzie taka`<job_name>.trm`. Dodaj następujący kod:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### Krok 4: Uruchom zadanie

Uruchom zadanie TeX, używając określonych opcji i nazwy zadania. Oto jak możesz to zrobić:

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
// ExEnd: OverrideJobName-WriteTerminalOutputToFileSystem
```

Gratulacje! Pomyślnie zastąpiłeś nazwę zadania i zapisane dane wyjściowe terminala w systemie plików przy użyciu Aspose.TeX w Javie.

## Wniosek

tym samouczku omówiliśmy, jak wykorzystać Aspose.TeX dla Java do zastąpienia nazwy zadania i przechwytywania danych wyjściowych terminala. Funkcje te umożliwiają programistom precyzyjną kontrolę nad przetwarzaniem dokumentów TeX, zwiększając dostosowywanie i elastyczność.

## Często zadawane pytania

### P1: Czy mogę używać Aspose.TeX dla Java z innymi bibliotekami Java?

Odpowiedź 1: Tak, Aspose.TeX dla Java został zaprojektowany tak, aby bezproblemowo integrować się z innymi bibliotekami Java w celu zwiększenia możliwości przetwarzania dokumentów.

### P2: Gdzie mogę znaleźć wsparcie dla Aspose.TeX dla Java?

 A2: Odwiedź[Forum Aspose.TeX](https://forum.aspose.com/c/tex/47) w celu uzyskania wsparcia społeczności i pomocy w przypadku jakichkolwiek problemów, jakie możesz napotkać.

### P3: Czy dostępna jest bezpłatna wersja próbna Aspose.TeX dla Java?

 O3: Tak, możesz uzyskać dostęp do bezpłatnej wersji próbnej Aspose.TeX dla Java[Tutaj](https://releases.aspose.com/).

### P4: Jak mogę uzyskać tymczasową licencję na Aspose.TeX dla Java?

 A4: Postępuj zgodnie z tym[połączyć](https://purchase.aspose.com/temporary-license/) w celu uzyskania tymczasowej licencji do celów testowania i oceny.

### P5: Gdzie mogę kupić Aspose.TeX dla Java?

 A5: Odwiedź[strona zakupu](https://purchase.aspose.com/buy) nabycie licencji na Aspose.TeX dla Java.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
