---
title: Converteer LaTeX eenvoudig naar XPS-indeling in Java
linktitle: Converteer LaTeX eenvoudig naar XPS-indeling in Java
second_title: Aspose.TeX Java-API
description: Converteer LaTeX moeiteloos naar XPS in Java met Aspose.TeX. Volg onze stapsgewijze handleiding voor een naadloze integratie.
type: docs
weight: 10
url: /nl/java/converting-lato-xps/simple-xps-conversion/
---
## Invoering

Wilt u LaTeX-documenten naadloos converteren naar XPS-indeling in uw Java-toepassingen? Aspose.TeX voor Java biedt een krachtige oplossing waarmee u dit gemakkelijk kunt bereiken. In deze stapsgewijze handleiding leiden we u door het proces van het converteren van LaTeX naar XPS met behulp van Aspose.TeX.

## Vereisten

Voordat u in het conversieproces duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

- Java Development Kit (JDK) op uw systeem geïnstalleerd.
-  Aspose.TeX voor Java-bibliotheek gedownload. Je kunt de downloadlink vinden[hier](https://releases.aspose.com/tex/java/).

## Pakketten importeren

Importeer om te beginnen de benodigde pakketten voor uw Java-project. Zorg ervoor dat u de Aspose.TeX-bibliotheek opneemt in uw projectafhankelijkheden.

```java
package com.aspose.tex.LaTeXXpsConversionSimplest;

import java.io.ByteArrayInputStream;
import java.io.IOException;
import java.util.Calendar;
import java.util.GregorianCalendar;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.Interaction;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;
import com.aspose.tex.rendering.XpsSaveOptions;

import util.Utils;
```

Laten we nu het conversieproces in meerdere stappen opsplitsen met behulp van de meegeleverde codevoorbeelden.

## Stap 1: Stel invoer- en uitvoermappen in

```java
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Geef de mappen op waar uw LaTeX-invoerbestand zich bevindt en waar u het geconverteerde XPS-bestand wilt opslaan.

## Stap 2: Configureer TeX-opties

Configureer verschillende opties om het conversieproces aan uw behoeften aan te passen.

```java
options.setInteraction(Interaction.NonstopMode);
options.setDateTime(new GregorianCalendar(2022, Calendar.DECEMBER, 18).getTime());
options.ignoreMissingPackages(true);
options.noLigatures(true);
options.repeat(true);
```

Pas indien nodig de interactiemodus, datum in de titel, afhandeling van ontbrekende pakketten, ligaturen en herhaling aan.

## Stap 3: Initialiseer de XPS-opslagopties

```java
options.setSaveOptions(new XpsSaveOptions());
```

Initialiseer de opties voor het opslaan in XPS-indeling.

## Stap 4: XPS-opslagopties aanpassen

```java
options.getSaveOptions().rasterizeFormulas(true);
options.getSaveOptions().rasterizeIncludedGraphics(true);
options.getSaveOptions().subsetFonts(true);
```

Pas de XPS-opslagopties aan om de conversie van formules, meegeleverde afbeeldingen en subinstellingen van lettertypen te beheren.

## Stap 5: Voer LaTeX naar XPS-conversie uit

```java
new TeXJob("Your Input Directory" + "sample.ltx", new XpsDevice(), options).run();
```

Start het conversieproces door een TeX-taak uit te voeren met het opgegeven invoerbestand, uitvoerapparaat (XpsDevice) en opties.

## Aanvullende voorbeelden

Ontdek aanvullende conversiemethoden met behulp van verschillende invoerbronnen:

### Gebruik InputStream

```java
new TeXJob(new ByteArrayInputStream(
    "\\documentclass{article} \\begin{document} Hello, World! \\end{document}".getBytes("ASCII")),
    new XpsDevice(), options).run();
```

### Gebruik de hoofdingang

```java
new TeXJob(new XpsDevice(), options).run();
```

## Conclusie

Met Aspose.TeX voor Java is het converteren van LaTeX naar XPS een fluitje van een cent. Volg deze stappen, pas de opties aan en integreer deze functionaliteit naadloos in uw Java-applicaties.

## Veelgestelde vragen

### V1: Kan ik LaTeX-documenten met complexe formules converteren met Aspose.TeX?

A1: Absoluut! Aspose.TeX verwerkt complexe formules naadloos tijdens het conversieproces.

### V2: Is er een proefversie beschikbaar voor Aspose.TeX voor Java?

 A2: Ja, u kunt de gratis proefversie vinden[hier](https://releases.aspose.com/).

### V3: Hoe kan ik ondersteuning krijgen voor Aspose.TeX?

 A3: Bezoek de[Aspose.TeX-forum](https://forum.aspose.com/c/tex/47) voor hulp en gemeenschapsondersteuning.

### V4: Zijn er tijdelijke licenties beschikbaar voor Aspose.TeX?

 A4: Ja, u kunt tijdelijke licenties verkrijgen[hier](https://purchase.aspose.com/temporary-license/).

### V5: Waar kan ik de documentatie voor Aspose.TeX vinden?

 A5: Raadpleeg de[documentatie](https://reference.aspose.com/tex/java/) voor uitgebreide begeleiding.