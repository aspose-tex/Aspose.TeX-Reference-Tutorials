---
date: 2025-12-05
description: Leer hoe u TeX kunt opmaken met Aspose.TeX voor Java, inclusief stappen
  voor aangepaste formaten en hoe u een tijdelijke Aspose-licentie kunt verkrijgen.
linktitle: How to Typeset TeX with Custom Formats in Java
second_title: Aspose.TeX Java API
title: Hoe TeX te typesetten met aangepaste formaten in Java
url: /nl/java/custom-tex-formats/typesetting-custom-tex-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe TeX opmaken met aangepaste formaten in Java

## Inleiding

Als je **hoe je TeX moet opmaken** binnen een Java‑applicatie, biedt Aspose.TeX een nette, hoog‑presterende manier om met aangepaste TeX‑formaatbestanden te werken. In deze tutorial lopen we alles door wat je nodig hebt – van het opzetten van de omgeving tot het uitvoeren van een TeX‑taak die jouw eigen formaat gebruikt. Of je nu een wetenschappelijk publicatietool bouwt of een aangepaste rapportgenerator, de onderstaande stappen krijgen je snel aan de slag.

## Snelle antwoorden
- **Welke bibliotheek heb ik nodig?** Aspose.TeX for Java  
- **Kan ik een aangepast TeX‑formaat gebruiken?** Ja – wijs de `FormatProvider` gewoon naar je bestand.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een tijdelijke licentie aspose werkt voor testen; een volledige licentie is vereist voor productie.  
- **Welke Java‑versie wordt ondersteund?** JDK 8 of hoger.  
- **Welk uitvoerformaat genereert het voorbeeld?** XPS (je kunt overschakelen naar PDF, PNG, enz.).

## Wat is een aangepast TeX‑formaat?
Een aangepast TeX‑formaat is een vooraf gecompileerde set macro’s en primitieve commando’s die de TeX‑engine afstemt op jouw specifieke documentstijl. Door je eigen `.fmt`‑bestand te leveren, kun je lettertypen, lay‑outrichtlijnen en opdrachtdefinities regelen zonder elke keer de bron‑TeX aan te passen.

## Waarom Aspose.TeX for Java gebruiken?
- **Pure Java** – Geen native binaries, eenvoudig in te sluiten in elk JVM‑gebaseerd project.  
- **Hoge getrouwheid** – Genereert output die overeenkomt met LaTeX‑stijl rendering.  
- **Uitbreidbaar** – Ondersteunt aangepaste formaten, meerdere uitvoerapparaten en batchverwerking.  
- **Licentie‑flexibiliteit** – Begin met een tijdelijke licentie aspose, upgrade later wanneer je live gaat.

## Voorvereisten

Voordat je begint, zorg dat je het volgende hebt:

1. **Java Development Kit (JDK)** – JDK 8 of nieuwer geïnstalleerd. Download het van de officiële [Java‑website](https://www.oracle.com/java/technologies/javase-downloads.html) als je dat nog niet hebt gedaan.  
2. **Aspose.TeX‑bibliotheek voor Java** – Haal de nieuwste JAR van de [Aspose.TeX for Java downloadpagina](https://releases.aspose.com/tex/java/).  
3. **Je aangepaste TeX‑formaatbestand** – Plaats het gecompileerde `.fmt` (bijv. `customtex.fmt`) in een map die dient als de uitvoermap.  

> **Pro tip:** Als je het product evalueert, vraag dan een *temporary license aspose* aan via het Aspose‑portaal; dit verwijdert het evaluatiewatermerk voor een beperkte periode.

## Importeer pakketten

Voeg eerst de benodigde imports toe aan je Java‑project. Deze klassen geven je toegang tot de format provider, taakconfiguratie en rendering‑apparaat.

```java
package com.aspose.tex.TypesetWithCustomTeXFormat;

import java.io.ByteArrayInputStream;
import java.io.IOException;

import com.aspose.tex.FormatProvider;
import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

## Stapsgewijze handleiding

### Stap 1: Maak een Format Provider

De `FormatProvider` wijst naar de directory die je aangepaste TeX‑formaatbestand bevat. Vervang `"Your Output Directory"` door het daadwerkelijke pad waar `customtex.fmt` zich bevindt.

```java
final FormatProvider formatProvider = new FormatProvider(
        new InputFileSystemDirectory("Your Output Directory"), "customtex");
```

### Stap 2: Stel conversie‑opties in

Configureer de taak om de ObjectTeX‑engine te gebruiken (de engine die aangepaste formaten begrijpt). Hier stellen we ook de taaknaam in en geven we de invoer‑/uitvoer‑werkmappen op.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX(formatProvider));
options.setJobName("typeset-with-custom-format");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### Stap 3: Voer de TeX‑taak uit

Maak een `TeXJob`‑instantie, geef deze een eenvoudige TeX‑snippet, en laat hem het resultaat renderen met een `XpsDevice`. De snippet eindigt met `\end` om het document te sluiten.

```java
new TeXJob(new ByteArrayInputStream(
        "Congratulations! You have successfully typeset this text with your own TeX format!\\end".getBytes("ASCII")),
        new XpsDevice(), options).run();
```

### Stap 4: Finaliseer de output

Nadat de taak is voltooid, voeg je een regeleinde toe aan de terminaloutput zodat de console netjes blijft.

```java
options.getTerminalOut().getWriter().newLine();
```

### Stap 5: Sluit de Format Provider

Wanneer je klaar bent, sluit je de provider om bestands­handles vrij te geven en bronnen te ontlasten.

```java
formatProvider.close();
```

## Veelvoorkomende problemen en oplossingen

| Probleem | Oorzaak | Oplossing |
|----------|---------|-----------|
| **“Format file not found”** | Verkeerd pad in `FormatProvider` | Controleer of de directory en bestandsnaam (`customtex.fmt`) correct en toegankelijk zijn. |
| **Encoding errors** | Niet‑ASCII‑tekens in de TeX‑string | Gebruik UTF‑8‑encoding (`"UTF-8"` in plaats van `"ASCII"`). |
| **Output not generated** | Uitvoermap heeft geen schrijfrechten | Zorg ervoor dat het Java‑proces schrijfrechten heeft voor `"Your Output Directory"`. |
| **License watermark** | Alleen de evaluatielicentie gebruiken | Pas een *temporary license aspose* toe voor testen of koop een volledige licentie voor productie. |

**Gerelateerde bronnen:** [Aspose.TeX API Reference](https://docs.aspose.com/tex/java/) | [Download Free Trial](https://releases.aspose.com/tex/java/)

## Veelgestelde vragen

**V: Kan ik Aspose.TeX samen met andere Java‑bibliotheken gebruiken?**  
A: Absoluut. De API is pure Java en werkt naast bibliotheken zoals Apache PDFBox, iText of Spring Boot.

**V: Waar kan ik een tijdelijke licentie aspose voor evaluatie krijgen?**  
A: Vraag er een aan via de [Aspose temporary license page](https://purchase.aspose.com/temporary-license/). Het verwijdert het evaluatiewatermerk voor maximaal 30 dagen.

**V: Ondersteunt Aspose.TeX andere uitvoerformaten dan XPS?**  
A: Ja. Je kunt `new XpsDevice()` vervangen door `new PdfDevice()`, `new PngDevice()`, enz., afhankelijk van je behoeften.

**V: Hoe debug ik een mislukte TeX‑taak?**  
A: Schakel gedetailleerde logging in door `options.setLogLevel(LogLevel.DEBUG);` aan te roepen en inspecteer de console‑output voor uitgebreide foutmeldingen.

**V: Is er een gratis proefversie beschikbaar?**  
A: Ja – download de proef‑binaries van de [Aspose.TeX downloadpagina](https://releases.aspose.com/tex/java/).

## Conclusie

Je weet nu **hoe je TeX moet opmaken** in een Java‑applicatie met een aangepast TeX‑formaat via Aspose.TeX. Door de bovenstaande stappen te volgen, kun je hoogwaardige typesetting integreren in elke Java‑gebaseerde workflow, experimenteren met je eigen formaatbestanden, en van prototype naar productie gaan met een juiste licentie.

---

**Laatst bijgewerkt:** 2025-12-05  
**Getest met:** Aspose.TeX for Java 24.10  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}