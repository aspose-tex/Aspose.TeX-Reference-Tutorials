---
title: Zet TeX naar PDF in Java met externe stream
linktitle: Zet TeX naar PDF in Java met externe stream
second_title: Aspose.TeX Java-API
description: Leer hoe u TeX naar PDF kunt zetten in Java met behulp van externe streams met Aspose.TeX. Volg onze stapsgewijze handleiding voor een naadloze integratie.
type: docs
weight: 10
url: /nl/java/typesetting-tex-to-pdf/typeset-tex-to-pdf-external-stream/
---
## Invoering

In de wereld van Java-ontwikkeling is het maken van PDF's van TeX-bestanden een veel voorkomende vereiste. Aspose.TeX voor Java vereenvoudigt dit proces en biedt een efficiënte oplossing voor het omzetten van TeX naar PDF. In deze zelfstudie leiden we u door de stappen voor het zetten van TeX naar PDF met behulp van externe streams. Aan het einde heeft u een duidelijk inzicht in de manier waarop u dit proces naadloos in uw Java-applicaties kunt implementeren.

## Vereisten

Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

- Aspose.TeX voor Java: Zorg ervoor dat de Aspose.TeX-bibliotheek voor Java is geïnstalleerd. Je kunt het downloaden van de[Aspose.TeX voor Java-documentatie](https://reference.aspose.com/tex/java/).

- Invoer- en uitvoermappen: Bereid de invoer- en uitvoermappen voor. U kunt de meegeleverde downloadlink gebruiken om de benodigde bestanden te verkrijgen.

## Pakketten importeren

Begin met het importeren van de vereiste pakketten in uw Java-project:

```java
package com.aspose.tex.TypesetPdfWrittenToExternalStream;

import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.io.OutputStream;

import com.aspose.tex.InputZipDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.OutputZipDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.PdfDevice;
import com.aspose.tex.rendering.PdfSaveOptions;

import util.Utils;
```

## Stap 1: Open invoer- en uitvoerstromen

Begin met het openen van streams voor het invoer-ZIP-archief (dat fungeert als de invoerwerkmap) en het uitvoer-ZIP-archief (dat fungeert als de uitvoerwerkmap). Zorg ervoor dat u "Uw invoermap" en "Uw uitvoermap" vervangt door uw daadwerkelijke mappaden.

```java
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "typeset-pdf-to-external-stream.zip");
```

## Stap 2: Configureer TeXOptions

Maak het TeXOptions-object en configureer het volgens uw vereisten. Stel de taaknaam, de invoerwerkmap, de uitvoerwerkmap en andere opties in.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("typeset-pdf-to-external-stream");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
options.setSaveOptions(new PdfSaveOptions());
```

## Stap 3: Zet TeX naar PDF

Open nu een stream om de uitvoer-PDF naar de gewenste locatie te schrijven. U kunt ervoor kiezen om het naar een lokaal bestand te schrijven of rechtstreeks naar het uitvoer-ZIP-archief.

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + "file-name.pdf");
try {
    new TeXJob("hello-world", new PdfDevice(stream), options).run();
} finally {
    stream.close();
}
```

## Stap 4: Voltooi het uitvoer-ZIP-archief

Voltooi het uitvoer-ZIP-archief om het zetproces te voltooien.

```java
((OutputZipDirectory)options.getOutputWorkingDirectory()).finish();
```

## Conclusie

Gefeliciteerd! U hebt TeX met succes naar PDF gezet in Java met behulp van externe streams met Aspose.TeX. Deze tutorial biedt een robuuste basis voor het naadloos integreren van TeX naar PDF-conversie in uw Java-applicaties.

## Veelgestelde vragen

### Vraag 1: Kan ik de bestandsnaam van de uitvoer-PDF aanpassen?

 A1: Ja, u kunt de`options.setJobName("typeset-pdf-to-external-stream")` om de gewenste taaknaam in te stellen.

### Vraag 2: Hoe los ik veelvoorkomende problemen tijdens het zetwerk op?

 A2: Bezoek de[Aspose.TeX-forum](https://forum.aspose.com/c/tex/47) voor steun en hulp van de gemeenschap.

### V3: Is er een gratis proefversie beschikbaar voor Aspose.TeX voor Java?

 A3: Ja, u heeft toegang tot de gratis proefperiode[hier](https://releases.aspose.com/).

### V4: Waar kan ik aanvullende documentatie en voorbeelden vinden?

 A4: Ontdek het uitgebreide[Aspose.TeX-documentatie](https://reference.aspose.com/tex/java/) voor gedetailleerde informatie.

### V5: Kan ik een tijdelijke licentie verkrijgen voor Aspose.TeX?

 A5: Ja, u kunt een tijdelijke licentie aanvragen[hier](https://purchase.aspose.com/temporary-license/).