---
title: Zet TeX naar XPS in Java met externe stream
linktitle: Zet TeX naar XPS in Java met externe stream
second_title: Aspose.TeX Java-API
description: Leer hoe u TeX naar XPS kunt zetten in Java met behulp van Aspose.TeX. Ontdek stapsgewijze begeleiding voor een naadloze documentverwerking.
type: docs
weight: 10
url: /nl/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
---
## Invoering

In de wereld van Java-ontwikkeling onderscheidt Aspose.TeX zich als een krachtig hulpmiddel voor het zetten van TeX-documenten in verschillende formaten, waaronder XPS. Als u de documentverwerkingsmogelijkheden van uw Java-toepassing wilt verbeteren, is deze tutorial op maat voor u gemaakt. In deze stapsgewijze handleiding leiden we u door het proces van het zetten van TeX naar XPS met behulp van Aspose.TeX voor Java met een externe stream.

## Vereisten

Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

-  Java Development Kit (JDK): Zorg ervoor dat Java op uw systeem is geïnstalleerd. Je kunt het downloaden van[hier](https://www.oracle.com/java/technologies/javase-downloads.html).

-  Aspose.TeX voor Java: Download en installeer Aspose.TeX voor Java. Je kunt de downloadlink vinden[hier](https://releases.aspose.com/tex/java/).

## Pakketten importeren

Begin met het importeren van de benodigde pakketten om uw conversietraject van TeX naar XPS te starten. Neem het volgende codefragment op in uw Java-project:

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

## Stap 1: Conversieopties configureren

Begin met het maken van conversieopties voor het standaard ObjectTeX-formaat met behulp van de volgende code:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

Hiermee wordt de basis gelegd voor het zetproces.

## Stap 2: Geef de taaknaam en mappen op

Definieer een taaknaam en stel de invoer- en uitvoerwerkmappen in:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Zorg ervoor dat u tijdelijke aanduidingen zoals 'Uw invoermap' vervangt door uw daadwerkelijke mappaden.

## Stap 3: Terminaluitgang configureren

Geef op dat de terminaluitvoer naar een bestand in de uitvoerwerkmap moet worden geschreven:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

Deze stap zorgt ervoor dat er gedetailleerde logboeken worden vastgelegd voor foutopsporing.

## Stap 4: Open uitvoerstroom

Open een stream om het getypte XPS-document te schrijven:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

Vervang "Uw uitvoermap" door het juiste pad.

## Stap 5: Voer de taak uit

Voer de conversietaak TeX naar XPS uit:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

Hiermee is het proces voltooid en vindt u uw gezet XPS-document in de opgegeven uitvoermap.

## Conclusie

Gefeliciteerd! U hebt TeX met succes naar XPS gezet in Java met behulp van Aspose.TeX. Dit opent een wereld aan mogelijkheden voor documentverwerking in uw Java-applicaties. Experimenteer met verschillende TeX-bestanden en ontdek de diverse functies van Aspose.TeX.

## Veelgestelde vragen

### V1: Kan ik Aspose.TeX voor Java gebruiken met andere documentformaten?

A1: Aspose.TeX richt zich primair op TeX-gerelateerde documentverwerking. Voor andere formaten kunt u het uitgebreide productassortiment van Aspose verkennen.

### Vraag 2: Is er een proefversie beschikbaar?

 A2: Ja, u kunt Aspose.TeX ervaren door de gratis proefversie te downloaden[hier](https://releases.aspose.com/).

### Vraag 3: Waar kan ik uitgebreide documentatie vinden?

 A3: Raadpleeg de documentatie[hier](https://reference.aspose.com/tex/java/) voor gedetailleerde informatie en voorbeelden.

### Vraag 4: Hoe krijg ik ondersteuning of zoek ik hulp?

 A4: Bezoek het Aspose.TeX-forum[hier](https://forum.aspose.com/c/tex/47)voor gemeenschapsondersteuning en discussies.

### Vraag 5: Kan ik een tijdelijke licentie verkrijgen voor testdoeleinden?

 A5: Ja, u kunt een tijdelijke licentie aanschaffen[hier](https://purchase.aspose.com/temporary-license/).