---
date: 2025-12-21
description: Leer hoe je console‑uitvoer in C# kunt vastleggen met Aspose.TeX, de
  taaknaam kunt overschrijven, de TeX‑invoermap kunt instellen en terminaluitvoer
  naar een bestand kunt schrijven.
linktitle: Capture Console Output C# – Override Job Name & Write Output to Disk
second_title: Aspose.TeX .NET API
title: Console-uitvoer vastleggen C# – Jobnaam overschrijven & uitvoer naar schijf
  schrijven
url: /nl/net/job-output/override-job-name-disk-output-csharp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Console-uitvoer vastleggen C# – Jobnaam overschrijven en terminaluitvoer naar schijf schrijven (C#)

## Inleiding

In deze stap‑voor‑stap‑gids leer je **hoe je console‑uitvoer C# kunt vastleggen** bij het werken met Aspose.TeX voor .NET. Door de jobnaam te overschrijven en de terminaluitvoer naar een bestand te leiden, krijg je volledige controle over TeX‑verwerkingspijplijnen—perfect voor geautomatiseerde builds, CI/CD‑scenario's, of elke situatie waarin je de console‑stroom wilt loggen voor latere analyse.

## Snelle antwoorden
- **Wat betekent “capture console output C#”?** Het leidt de standaard terminalstroom die door Aspose.TeX wordt gegenereerd om naar een bestand dat u opgeeft.  
- **Waarom de jobnaam overschrijven?** Overschrijven zorgt voor voorspelbare bestandsnamen en voorkomt conflicten bij het uitvoeren van meerdere jobs.  
- **Welke Aspose.TeX‑klasse schrijft de output?** `OutputFileTerminal` (gebruikt via `options.TerminalOut`).  
- **Kan ik een aangepaste TeX‑invoermap instellen?** Ja—gebruik `options.InputWorkingDirectory` om de **TeX‑inputdirectory** in te stellen.  
- **Is deze aanpak compatibel met .NET Core?** Absoluut; dezelfde API werkt op .NET Framework en .NET Core.

## Wat is “capture console output C#” in de context van Aspose.TeX?
Console‑uitvoer vastleggen betekent dat alles wat normaal gesproken in het terminalvenster zou verschijnen (log‑berichten, waarschuwingen, compilatiedetails) wordt weggeschreven naar een persistent bestand. Dit is bijzonder nuttig voor het debuggen van grote TeX‑projecten of het integreren van TeX‑verwerking in geautomatiseerde workflows.

## Waarom de jobnaam overschrijven en terminaluitvoer naar een bestand schrijven?
- **Voorspelbare bestandsnamen:** Door de jobnaam te overschrijven kunt u de basisnaam voor gegenereerde bestanden bepalen, waardoor post‑processing‑scripts makkelijker te schrijven zijn.  
- **Auditbaarheid:** Het opslaan van het terminallogboek geeft u een volledige audittrail van het TeX‑compilatieproces.  
- **Parallelle uitvoering:** Bij het gelijktijdig uitvoeren van meerdere jobs voorkomen unieke jobnamen bestandsconflicten.  

## Vereisten

Voor we beginnen, zorg dat je het volgende hebt:

- Aspose.TeX voor .NET Bibliotheek: Zorg ervoor dat u de Aspose.TeX voor .NET bibliotheek geïnstalleerd heeft. U kunt deze downloaden van de [Aspose.TeX website](https://releases.aspose.com/tex/net/).
- .NET-ontwikkelomgeving: Zorg voor een werkende .NET‑ontwikkelomgeving, inclusief een geïntegreerde ontwikkelomgeving (IDE) zoals Visual Studio.
- Basiskennis C#: Vertrouwd met de basisprincipes van de programmeertaal C#.
- Invoer‑ en uitvoermappen: Bereid de invoer‑ en uitvoermappen voor uw TeX‑bestanden voor.

## Namespaces importeren

In uw C#‑code moet u de benodigde namespaces opnemen om toegang te krijgen tot de Aspose.TeX‑functionaliteiten:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

## Stap 1: Conversie‑opties maken

Eerst maken we een `TeXOptions`‑instantie die Aspose.TeX vertelt dat we in een console‑applicatiescenario draaien.

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

Maak `TeXOptions` met `ConsoleAppOptions`, waarbij `ObjectTeX` als de `TeXConfig` wordt opgegeven.

## Stap 2: Jobnaam opgeven (standaard overschrijven)

Door de jobnaam te overschrijven krijgen we controle over de basisnaam van alle gegenereerde artefacten.

```csharp
options.JobName = "overridden-job-name";
```

Geef de jobnaam op om de standaardnaam te overschrijven.

## Stap 3: TeX‑invoermap instellen

Vertel Aspose.TeX waar uw bron‑`.tex`‑bestanden zich bevinden. Dit is de **set tex input directory** stap.

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

Stel de invoerwerkmap in voor uw TeX‑bestanden.

## Stap 4: Uitvoermap opgeven

Definieer waar de verwerkte bestanden en het vastgelegde console‑logboek worden opgeslagen.

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Definieer de uitvoerwerkmap om de verwerkte TeX‑bestanden op te slaan.

## Stap 5: Terminaluitvoer naar bestand schrijven

Nu leiden we de console‑stroom naar een fysiek bestand in de uitvoermap. Dit implementeert de **write terminal output to file** eis.

```csharp
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

Configureer de terminaluitvoer zodat deze naar een bestand in de uitvoermap wordt geschreven.

## Stap 6: Job uitvoeren

Tot slot maken we een `TeXJob` met de overschreven jobnaam, het XPS‑outputapparaat, en de opties die we hebben geconfigureerd. Het uitvoeren van de job genereert het XPS‑bestand en legt het console‑logboek vast.

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

Maak een `TeXJob`, met een jobnaam, output‑apparaat (`XpsDevice`) en opties. Voer vervolgens de job uit.

## Veelvoorkomende problemen & probleemoplossing

| Symptoom | Waarschijnlijke oorzaak | Oplossing |
|----------|--------------------------|-----------|
| Geen uitvoerbestand aangemaakt | Pad van de uitvoermap is onjuist of er ontbreken schrijfrechten | Controleer of `options.OutputWorkingDirectory` naar een geldige map wijst en dat het proces schrijfrechten heeft. |
| Terminallogboek is leeg | `TerminalOut` niet ingesteld of later overschreven | Zorg ervoor dat `options.TerminalOut = new OutputFileTerminal(...);` wordt uitgevoerd vóór `job.Run();`. |
| Job mislukt met “bestand niet gevonden” | Invoermap niet correct ingesteld | Controleer het pad dat aan `InputFileSystemDirectory` wordt doorgegeven en of de `.tex`‑bestanden daar aanwezig zijn. |

## Veelgestelde vragen

### V1: Kan ik Aspose.TeX voor .NET gebruiken met andere .NET‑bibliotheken?

Ja, Aspose.TeX voor .NET kan naadloos worden geïntegreerd met andere .NET‑bibliotheken.

### V2: Is er een gratis proefversie beschikbaar voor Aspose.TeX voor .NET?

Ja, u kunt een gratis proefversie downloaden [hier](https://releases.aspose.com/).

### V3: Hoe kan ik ondersteuning krijgen voor Aspose.TeX voor .NET?

Bezoek het [Aspose.TeX forum](https://forum.aspose.com/c/tex/47) voor community‑ondersteuning en hulp.

### V4: Zijn tijdelijke licenties beschikbaar voor Aspose.TeX voor .NET?

Ja, u kunt een tijdelijke licentie verkrijgen [hier](https://purchase.aspose.com/temporary-license/).

### V5: Waar kan ik de documentatie vinden voor Aspose.TeX voor .NET?

De documentatie is beschikbaar [hier](https://reference.aspose.com/tex/net/).

## Conclusie

Gefeliciteerd! Je hebt met succes geleerd hoe je **console‑uitvoer vastlegt C#** door de jobnaam te overschrijven, de TeX‑invoermap in te stellen, en de terminaluitvoer naar een bestand te schrijven met behulp van Aspose.TeX voor .NET. Deze techniek stroomlijnt het loggen, verbetert de traceerbaarheid en maakt geautomatiseerde TeX‑verwerkingspijplijnen robuuster.

---

**Laatst bijgewerkt:** 2025-12-21  
**Getest met:** Aspose.TeX 24.11 voor .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}