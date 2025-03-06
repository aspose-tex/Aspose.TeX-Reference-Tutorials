---
title: TeX naar XPS zetten in .NET
linktitle: TeX naar XPS zetten in .NET
second_title: Aspose.TeX .NET-API
description: Converteer Moeiteloos TeX-documenten naar XPS in .NET met Aspose.TeX. Ontdek onze stapsgewijze handleiding voor een naadloze integratie-ervaring.
weight: 10
url: /nl/net/xps-output/typeset-tex-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# TeX naar XPS zetten in .NET

## Invoering

Welkom bij onze stapsgewijze handleiding voor het zetten van TeX naar XPS in .NET met behulp van de krachtige Aspose.TeX-bibliotheek. Als u TeX-documenten naadloos naar XPS-indeling wilt converteren in uw .NET-toepassingen, bent u hier aan het juiste adres. In deze zelfstudie leiden we u door het hele proces, waarbij we elke stap opsplitsen om een soepele implementatie te garanderen.

## Vereisten

Voordat we ingaan op de tutorial, zorg ervoor dat je aan de volgende vereisten voldoet:

-  Aspose.TeX voor .NET: Zorg ervoor dat de Aspose.TeX-bibliotheek is geïnstalleerd. Je kunt het downloaden[hier](https://releases.aspose.com/tex/net/).

- Documentatie: Maak uzelf vertrouwd met de bibliotheek door de documentatie te raadplegen[hier](https://reference.aspose.com/tex/net/).

- Invoer- en uitvoermappen: Stel uw invoer- en uitvoermappen in zoals gespecificeerd in de voorbeeldcode.

Nu je alles hebt ingesteld, gaan we verder met de stapsgewijze handleiding.

## Naamruimten importeren

Begin in uw .NET-toepassing met het importeren van de benodigde naamruimten. Dit zorgt ervoor dat u toegang heeft tot de Aspose.TeX-functionaliteiten die nodig zijn voor het zetten van TeX naar XPS.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
```

## Stap 1: Conversieopties instellen

Definieer de conversieopties en specificeer het ObjectTeX-formaat op de ObjectTeX-engineextensie. Stel ook de taaknaam, invoer- en uitvoermappen en terminaluitvoerdetails in.

```csharp
// Creëer conversieopties voor het standaard ObjectTeX-formaat bij de ObjectTeX-engine-extensie.
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
// Geef een taaknaam op.
options.JobName = "external-file-stream";
// Geef een bestandssysteemwerkmap op voor invoer.
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
// Geef een bestandssysteemwerkmap op voor uitvoer.
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
// Geef op dat de terminaluitvoer naar een bestand in de uitvoerwerkmap moet worden geschreven.
// De bestandsnaam is <jobnaam>.trm.
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## Stap 2: Maak een XPS-documentstroom

Open een stream om het getypte XPS-document te schrijven. De bestandsnaam is niet noodzakelijkerwijs hetzelfde als de taaknaam.

```csharp
using (Stream stream = File.Open(Path.Combine("Your Output Directory", options.JobName + ".xps"), FileMode.Create))
```

## Stap 3: Voer de TeX-taak uit

Start de TeX-taak en voer deze uit, waarbij u de documentnaam, XpsDevice en conversieopties opgeeft.

```csharp
new TeXJob("hello-world", new XpsDevice(stream), options).Run();
```

Gefeliciteerd! U hebt TeX met succes naar XPS gezet in .NET met behulp van Aspose.TeX. Ontdek gerust meer functies en opties op basis van uw specifieke vereisten.

## Conclusie

In deze zelfstudie hebben we de essentiële stappen besproken om TeX-documenten naadloos naar XPS-indeling in .NET te converteren met behulp van Aspose.TeX. Door deze handleiding te volgen heeft u waardevolle inzichten gekregen in de mogelijkheden van de bibliotheek en hoe u deze voor uw projecten kunt inzetten.

## Veelgestelde vragen

### Vraag 1: Is Aspose.TeX compatibel met .NET Core?

A1: Ja, Aspose.TeX is volledig compatibel met .NET Core.

### V2: Kan ik Aspose.TeX gebruiken voor commerciële projecten?

A2: Absoluut! Aspose.TeX is beschikbaar voor zowel commercieel als persoonlijk gebruik.

### Vraag 3: Waar kan ik aanvullende voorbeelden en bronnen vinden?

 A3: Verken de Aspose.TeX-documentatie[hier](https://reference.aspose.com/tex/net/)voor meer voorbeelden en gedetailleerde bronnen.

### V4: Hoe kan ik ondersteuning krijgen voor Aspose.TeX?

 A4: Bezoek het Aspose.TeX-ondersteuningsforum[hier](https://forum.aspose.com/c/tex/47) om hulp te krijgen van de gemeenschap.

### Vraag 5: Is er een gratis proefversie beschikbaar?

 A5: Ja, u heeft toegang tot een gratis proefperiode[hier](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
