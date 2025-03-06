---
title: Åsidosätt jobbnamn och skriv terminalutgång i Java
linktitle: Åsidosätt jobbnamn och skriv terminalutgång i Java
second_title: Aspose.TeX Java API
description: Utforska steg-för-steg-guiden för att åsidosätta jobbnamn och skriva terminalutdata med Aspose.TeX för Java. Förbättra din dokumentbehandling med kraftfulla anpassningsalternativ.
weight: 10
url: /sv/java/customizing-output/override-job-name-disk/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Åsidosätt jobbnamn och skriv terminalutgång i Java

## Introduktion

Aspose.TeX för Java tillhandahåller kraftfulla funktioner för att arbeta med TeX-filer, vilket gör att utvecklare kan manipulera och anpassa TeX-dokumentbehandlingen. I den här handledningen kommer vi att guida dig genom processen att åsidosätta jobbnamnet och skriva terminalutdata till filsystemet med Aspose.TeX i Java.

## Förutsättningar

Innan vi dyker in i handledningen, se till att du har följande förutsättningar på plats:

- En praktisk kunskap om Java-programmering.
-  Aspose.TeX för Java installerat. Du kan ladda ner den från[Aspose.TeX Java-dokumentation](https://reference.aspose.com/tex/java/).

## Importera paket

För att komma igång, importera nödvändiga paket till ditt Java-projekt. Inkludera följande importer i din Java-fil:

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

## Åsidosätt jobbnamn och skriv terminalutgång

### Steg 1: Skapa konverteringsalternativ

Börja med att skapa konverteringsalternativ för standard ObjectTeX-formatet på ObjectTeX-motortillägget. Använd följande kodavsnitt:

```java
//ExStart:OverrideJobName-WriteTerminalOutputToFileSystem
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

### Steg 2: Ange jobbnamn och arbetskataloger

Ange ett jobbnamn, mata in arbetskatalog och mata ut arbetskatalog. Om jobbnamnet inte anges, kommer det första argumentet i TeXJob-konstruktorn att tas som jobbnamn. Använd följande kodavsnitt:

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### Steg 3: Skriv terminalutgång till filsystemet

 Ange att terminalutgången måste skrivas till en fil i utgångens arbetskatalog. Filnamnet blir`<job_name>.trm`. Lägg till följande kod:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### Steg 4: Kör jobbet

Kör TeX-jobbet med de angivna alternativen och jobbnamnet. Så här kan du göra det:

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
// ExEnd:OverrideJobName-WriteTerminalOutputToFileSystem
```

Grattis! Du har framgångsrikt åsidosatt jobbnamnet och skrivit terminalutdata till filsystemet med Aspose.TeX i Java.

## Slutsats

den här handledningen undersökte vi hur man använder Aspose.TeX för Java för att åsidosätta jobbnamnet och fånga terminalutdata. Dessa funktioner ger utvecklare möjlighet att ha finkornig kontroll över TeX-dokumentbehandling, vilket förbättrar anpassning och flexibilitet.

## FAQ's

### F1: Kan jag använda Aspose.TeX för Java med andra Java-bibliotek?

S1: Ja, Aspose.TeX för Java är utformad för att sömlöst integreras med andra Java-bibliotek för att förbättra dina dokumentbehandlingsmöjligheter.

### F2: Var kan jag hitta support för Aspose.TeX för Java?

 A2: Besök[Aspose.TeX-forum](https://forum.aspose.com/c/tex/47) för gemenskapsstöd och hjälp med alla problem du kan stöta på.

### F3: Finns det en gratis testversion tillgänglig för Aspose.TeX för Java?

 S3: Ja, du kan komma åt den kostnadsfria testversionen av Aspose.TeX för Java[här](https://releases.aspose.com/).

### F4: Hur kan jag få en tillfällig licens för Aspose.TeX för Java?

 A4: Följ detta[länk](https://purchase.aspose.com/temporary-license/) för att få en tillfällig licens för test- och utvärderingsändamål.

### F5: Var kan jag köpa Aspose.TeX för Java?

 A5: Besök[köpsidan](https://purchase.aspose.com/buy) att skaffa en licens för Aspose.TeX för Java.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
