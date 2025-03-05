---
title: Åsidosätt jobbnamn och skriv terminalutgång till zip (C#)
linktitle: Åsidosätt jobbnamn och skriv terminalutgång till zip (C#)
second_title: Aspose.TeX .NET API
description: Lär dig hur du åsidosätter jobbnamn och skriver terminalutdata till en ZIP-fil med Aspose.TeX för .NET. Steg-för-steg-guide med C#-exempel.
type: docs
weight: 11
url: /sv/net/job-output/override-job-name-zip-output-csharp/
---
## Introduktion

den här handledningen kommer vi att utforska hur man åsidosätter jobbnamnet och skriver terminalutdata till en ZIP-fil med Aspose.TeX för .NET. Aspose.TeX är ett kraftfullt bibliotek som låter utvecklare arbeta med TeX-dokument i sina .NET-applikationer. I det här specifika exemplet kommer vi att fokusera på en vanlig uppgift – att skriva terminalutdata till en ZIP-fil med möjligheten att åsidosätta jobbnamnet.

## Förutsättningar

Innan vi börjar, se till att du har följande förutsättningar på plats:

- Har praktiska kunskaper i C#
- Aspose.TeX för .NET installerat
- Mata in ZIP-arkiv för arbetskatalogen
- Output ZIP-arkiv för terminalutgång

## Importera namnområden

Innan du dyker in i koden, se till att inkludera de nödvändiga namnrymden i ditt C#-projekt:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Pdf;
using System.IO;
```

Låt oss nu dela upp exemplet i flera steg för att guida dig genom processen.

## Steg 1: Öppna Input och Output ZIP-strömmar

```csharp
using (Stream inZipStream = File.Open(Path.Combine("Your Input Directory", "zip-in.zip"), FileMode.Open))
using (Stream outZipStream = File.Open(Path.Combine("Your Output Directory", "terminal-out-to-zip.zip"), FileMode.Create))
{
    // Koden för steg 1 kommer här
}
```

## Steg 2: Ställ in konverteringsalternativ

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
options.JobName = "terminal-output-to-zip";
options.InputWorkingDirectory = new InputZipDirectory(inZipStream, "in");
options.OutputWorkingDirectory = new OutputZipDirectory(outZipStream);
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## Steg 3: Definiera sparalternativ

```csharp
options.SaveOptions = new PdfSaveOptions();
```

## Steg 4: Kör TeX Job

```csharp
new TeXJob("hello-world", new PdfDevice(), options).Run();
```

## Steg 5: Slutför utdata-zip-arkivet

```csharp
((OutputZipDirectory)options.OutputWorkingDirectory).Finish();
```

## Slutsats

Grattis! Du har framgångsrikt lärt dig hur du åsidosätter jobbnamnet och skriver terminalutdata till en ZIP-fil med Aspose.TeX för .NET. Denna teknik kan vara otroligt användbar när du hanterar TeX-dokument i dina C#-applikationer.

## FAQ's

### F1: Kan jag använda Aspose.TeX för .NET med andra .NET-språk som VB.NET?

S1: Ja, Aspose.TeX för .NET är kompatibelt med alla .NET-språk.

### F2: Var kan jag hitta mer dokumentation för Aspose.TeX för .NET?

 A2: Besök[dokumentation](https://reference.aspose.com/tex/net/) för detaljerad information.

### F3: Hur kan jag få en tillfällig licens för Aspose.TeX?

 A3: Skaffa en[tillfällig licens](https://purchase.aspose.com/temporary-license/) för teständamål.

### F4: Finns det ett communityforum för Aspose.TeX-support?

 A4: Ja, gå med i[Aspose.TeX-forum](https://forum.aspose.com/c/tex/47) för samhällsstöd.

### F5: Var kan jag köpa Aspose.TeX för .NET?

 S5: Du kan köpa Aspose.TeX[här](https://purchase.aspose.com/buy).