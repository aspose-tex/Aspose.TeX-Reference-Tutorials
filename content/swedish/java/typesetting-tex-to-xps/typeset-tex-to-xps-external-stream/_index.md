---
title: Ange TeX till XPS i Java med extern ström
linktitle: Ange TeX till XPS i Java med extern ström
second_title: Aspose.TeX Java API
description: Lär dig hur du ställer in TeX till XPS i Java med Aspose.TeX. Utforska steg-för-steg-vägledning för sömlös dokumentbehandling.
type: docs
weight: 10
url: /sv/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
---
## Introduktion

I en värld av Java-utveckling framstår Aspose.TeX som ett kraftfullt verktyg för att sätta TeX-dokument i olika format, inklusive XPS. Om du vill förbättra din Java-applikations dokumentbearbetningsmöjligheter är den här handledningen skräddarsydd för dig. I den här steg-för-steg-guiden går vi igenom processen att sätta TeX till XPS med Aspose.TeX för Java med en extern ström.

## Förutsättningar

Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:

-  Java Development Kit (JDK): Se till att du har Java installerat på ditt system. Du kan ladda ner den från[här](https://www.oracle.com/java/technologies/javase-downloads.html).

-  Aspose.TeX för Java: Ladda ner och installera Aspose.TeX för Java. Du hittar nedladdningslänken[här](https://releases.aspose.com/tex/java/).

## Importera paket

Börja med att importera de nödvändiga paketen för att starta din TeX till XPS-konverteringsresa. Inkludera följande kodavsnitt i ditt Java-projekt:

```java
package com.aspose.tex.TypesetXpsWrittenToExternalStream;

import java.io.FileOutputStream;
import java.io.IOException;
import java.io.OutputStream;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

## Steg 1: Konfigurera konverteringsalternativ

Börja med att skapa konverteringsalternativ för standard ObjectTeX-format med följande kod:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

Detta lägger grunden för sättningsprocessen.

## Steg 2: Ange jobbnamn och kataloger

Definiera ett jobbnamn och ställ in arbetskatalogerna för in- och utdata:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Se till att du ersätter platshållare som "Din indatakatalog" med dina faktiska katalogsökvägar.

## Steg 3: Konfigurera terminalutgång

Ange att terminalutgången ska skrivas till en fil i utgångens arbetskatalog:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

Detta steg säkerställer att detaljerade loggar samlas in för felsökning.

## Steg 4: Öppna Output Stream

Öppna en ström för att skriva XPS-dokumentet:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

Ersätt "Din utdatakatalog" med rätt sökväg.

## Steg 5: Kör jobbet

Kör konverteringsjobbet TeX till XPS:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

Detta slutför processen och du hittar ditt XPS-dokument i den angivna utdatakatalogen.

## Slutsats

Grattis! Du har framgångsrikt skrivit in TeX till XPS i Java med Aspose.TeX. Detta öppnar upp en värld av möjligheter för dokumentbehandling i dina Java-applikationer. Experimentera med olika TeX-filer och utforska de olika funktionerna som erbjuds av Aspose.TeX.

## FAQ's

### F1: Kan jag använda Aspose.TeX för Java med andra dokumentformat?

S1: Aspose.TeX fokuserar främst på TeX-relaterad dokumentbehandling. För andra format, utforska Asposes omfattande produktsortiment.

### F2: Finns det en testversion tillgänglig?

 S2: Ja, du kan uppleva Aspose.TeX genom att ladda ner den kostnadsfria testversionen[här](https://releases.aspose.com/).

### F3: Var kan jag hitta omfattande dokumentation?

 A3: Se dokumentationen[här](https://reference.aspose.com/tex/java/) för detaljerad information och exempel.

### F4: Hur får jag stöd eller söker hjälp?

 S4: Besök Aspose.TeX-forumet[här](https://forum.aspose.com/c/tex/47)för samhällsstöd och diskussioner.

### F5: Kan jag få en tillfällig licens för teständamål?

 S5: Ja, du kan skaffa en tillfällig licens[här](https://purchase.aspose.com/temporary-license/).