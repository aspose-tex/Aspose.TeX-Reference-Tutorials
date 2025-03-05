---
title: Åsidosätt jobbnamn och skriv terminalutgång till disk (C#)
linktitle: Åsidosätt jobbnamn och skriv terminalutgång till disk (C#)
second_title: Aspose.TeX .NET API
description: Utforska hur du använder Aspose.TeX för .NET för att åsidosätta jobbnamn och fånga terminalutdata. Följ vår omfattande guide för sömlös TeX-filhantering.
type: docs
weight: 10
url: /sv/net/job-output/override-job-name-disk-output-csharp/
---
## Introduktion

Välkommen till denna steg-för-steg-guide om hur du använder Aspose.TeX för .NET för att åsidosätta jobbnamn och skriva terminalutdata till disk i programmeringsspråket C#. Aspose.TeX för .NET är ett kraftfullt bibliotek som låter dig arbeta sömlöst med TeX-filer, och i den här handledningen kommer vi att fokusera på en specifik uppgift: åsidosätta jobbnamn och fånga terminalutdata.

## Förutsättningar

Innan vi dyker in i handledningen, se till att du har följande förutsättningar på plats:

-  Aspose.TeX for .NET Library: Se till att du har Aspose.TeX for .NET-biblioteket installerat. Du kan ladda ner den från[Aspose.TeX webbplats](https://releases.aspose.com/tex/net/).

- .NET-utvecklingsmiljö: Ha en fungerande .NET-utvecklingsmiljö, inklusive en integrerad utvecklingsmiljö (IDE) som Visual Studio.

- Grundläggande C#-kunskaper: Bekanta dig med grunderna i programmeringsspråket C#.

- Inmatnings- och utdatakataloger: Förbered in- och utmatningskatalogerna för dina TeX-filer.

## Importera namnområden

I din C#-kod, se till att inkludera de nödvändiga namnrymden för att komma åt Aspose.TeX-funktionerna:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

## Steg 1: Skapa konverteringsalternativ

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

Skapa TeXOptions med ConsoleAppOptions, ange ObjectTeX som TeXConfig.

## Steg 2: Ange jobbnamn

```csharp
options.JobName = "overridden-job-name";
```

Ange jobbnamnet för att åsidosätta standardnamnet.

## Steg 3: Ange Input Working Directory

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

Ställ in arbetskatalogen för dina TeX-filer.

## Steg 4: Ange Output Working Directory

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Definiera utdataarbetskatalogen för att spara de bearbetade TeX-filerna.

## Steg 5: Skriv terminalutgång till disk

```csharp
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

Konfigurera terminalutgången för att skrivas till en fil i utgångskatalogen.

## Steg 6: Kör jobbet

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

Skapa en TeXJob, ange ett jobbnamn, utdataenhet (XpsDevice) och alternativ. Slutligen, kör jobbet.

## Slutsats

Grattis! Du har framgångsrikt lärt dig hur man åsidosätter jobbnamn och skriver terminalutdata till disk med Aspose.TeX för .NET i C#. Denna förmåga är värdefull för att effektivt hantera dina TeX-bearbetningsuppgifter.

## FAQ's

### F1: Kan jag använda Aspose.TeX för .NET med andra .NET-bibliotek?

S1: Ja, Aspose.TeX för .NET kan integreras med andra .NET-bibliotek sömlöst.

### F2: Finns det en gratis testversion tillgänglig för Aspose.TeX för .NET?

 A2: Ja, du kan ladda ner en gratis testversion[här](https://releases.aspose.com/).

### F3: Hur kan jag få support för Aspose.TeX för .NET?

 A3: Besök[Aspose.TeX-forum](https://forum.aspose.com/c/tex/47) för att få gemenskap och stöd.

### F4: Finns tillfälliga licenser tillgängliga för Aspose.TeX för .NET?

 A4: Ja, du kan få en tillfällig licens[här](https://purchase.aspose.com/temporary-license/).

### F5: Var kan jag hitta dokumentationen för Aspose.TeX för .NET?

 S5: Dokumentationen finns tillgänglig[här](https://reference.aspose.com/tex/net/).