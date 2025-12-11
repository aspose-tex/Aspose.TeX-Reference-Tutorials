---
date: 2025-12-11
description: Leer hoe je TeX naar XPS kunt converteren in Java met Aspose.TeX. Deze
  stapsgewijze handleiding laat je zien hoe je efficiënt XPS‑documentstreams kunt
  genereren.
linktitle: How to Convert TeX to XPS in Java with External Stream
second_title: Aspose.TeX Java API
title: Hoe TeX naar XPS converteren in Java met een externe stream
url: /nl/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe TeX naar XPS te converteren in Java met een externe stream

## Introductie

Als u **TeX**‑bestanden moet **converteren** naar XPS‑output van hoge kwaliteit vanuit een Java‑applicatie, maakt Aspose.TeX for Java het werk eenvoudig. In deze tutorial ziet u precies **hoe u TeX** naar een XPS‑document converteert met behulp van een externe output‑stream, wat ideaal is wanneer u het resultaat direct wilt doorsturen naar een respons, een cloud‑opslagservice of een andere aangepaste bestemming. Laten we het hele proces doorlopen, van het opzetten van de omgeving tot het schrijven van het uiteindelijke XPS‑bestand.

## Snelle antwoorden
- **Waar gaat deze tutorial over?** TeX naar XPS converteren met Aspose.TeX en een externe stream.  
- **Welke primaire bibliotheek is vereist?** Aspose.TeX for Java.  
- **Heb ik een licentie nodig?** Een tijdelijke of volledige licentie is vereist voor productiegebruik.  
- **Kan ik XPS‑documentstreams genereren?** Ja – het voorbeeld schrijft de XPS direct naar een `OutputStream`.  
- **Welke Java‑versie wordt ondersteund?** Elke JDK 8+ (de tutorial gebruikt JDK 11 als referentie).

## Voorvereisten

Voordat u in de code duikt, zorg ervoor dat u het volgende heeft:

- Java Development Kit (JDK): Zorg ervoor dat Java op uw systeem is geïnstalleerd. U kunt het downloaden via [here](https://www.oracle.com/java/technologies/javase-downloads.html).

- Aspose.TeX for Java: Download en installeer Aspose.TeX for Java. U kunt de downloadlink vinden [here](https://releases.aspose.com/tex/java/).

## Importeer pakketten

Begin met het importeren van de benodigde pakketten om uw TeX‑naar‑XPS‑conversiereis te starten. Voeg de volgende code‑fragment toe aan uw Java‑project:

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

## Stap 1: Conversie‑opties configureren

Maak conversie‑opties voor het standaard ObjectTeX‑formaat met de volgende code:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

Dit legt de basis voor het typesettingsproces.

## Stap 2: Jobnaam en mappen opgeven

Definieer een jobnaam en stel de invoer‑ en uitvoerwerkmappen in:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Vervang placeholders zoals "Your Input Directory" door uw werkelijke map‑paden.

## Stap 3: Terminaloutput configureren

Geef aan dat de terminaloutput moet worden weggeschreven naar een bestand in de uitvoerwerkmap:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

Deze stap zorgt ervoor dat gedetailleerde logboeken worden vastgelegd voor foutopsporing.

## Stap 4: Output‑stream openen

Open een stream om het getypeerde XPS‑document te schrijven:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

Vervang "Your Output Directory" door het juiste pad.

## Stap 5: Voer de job uit

Voer de TeX‑naar‑XPS‑conversie‑job uit:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

Dit voltooit het proces, en u vindt uw gegenereerde XPS‑document in de opgegeven uitvoermap.

## Veelvoorkomende problemen en oplossingen

| Probleem | Waarom het gebeurt | Hoe op te lossen |
|----------|--------------------|------------------|
| **FileNotFoundException** bij het openen van de stream | Het pad van de output‑map is onjuist of bestaat niet. | Controleer het pad, maak de map vooraf aan, of gebruik `Files.createDirectories`. |
| **NullPointerException** op `options.getOutputWorkingDirectory()` | `setOutputWorkingDirectory` is niet aangeroepen of retourneert `null`. | Zorg ervoor dat u `options.setOutputWorkingDirectory` aanroept voordat u het gebruikt. |
| **LicenseException** tijdens runtime | Uitvoeren zonder een geldige Aspose.TeX‑licentie. | Pas een tijdelijke of permanente licentie toe met `License license = new License(); license.setLicense("Aspose.TeX.lic");`. |

## Veelgestelde vragen

**V: Kan ik Aspose.TeX for Java gebruiken met andere documentformaten?**  
A: Aspose.TeX richt zich voornamelijk op TeX‑gerelateerde documentverwerking. Voor andere formaten kunt u het uitgebreide productaanbod van Aspose verkennen.

**V: Is er een proefversie beschikbaar?**  
A: Ja, u kunt Aspose.TeX uitproberen door de gratis proefversie te downloaden [here](https://releases.aspose.com/).

**V: Waar kan ik uitgebreide documentatie vinden?**  
A: Raadpleeg de documentatie [here](https://reference.aspose.com/tex/java/) voor gedetailleerde informatie en voorbeelden.

**V: Hoe krijg ik ondersteuning of hulp?**  
A: Bezoek het Aspose.TeX‑forum [here](https://forum.aspose.com/c/tex/47) voor community‑ondersteuning en discussies.

**V: Kan ik een tijdelijke licentie verkrijgen voor testdoeleinden?**  
A: Ja, u kunt een tijdelijke licentie verkrijgen [here](https://purchase.aspose.com/temporary-license/).

## Conclusie

Gefeliciteerd! U heeft zojuist geleerd **hoe u TeX** naar een XPS‑document in Java kunt converteren met Aspose.TeX en een externe stream. Deze techniek geeft u volledige controle over waar de XPS‑output naartoe gaat — of het nu een bestandssysteem, een web‑respons of een cloud‑bucket is. Voel u vrij om te experimenteren met verschillende TeX‑bronnen, de `TeXOptions` aan te passen voor aangepaste lettertypen, of de stream in te pluggen in een grotere document‑generatie‑pipeline.

---

**Laatst bijgewerkt:** 2025-12-11  
**Getest met:** Aspose.TeX for Java 24.11 (latest at time of writing)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}