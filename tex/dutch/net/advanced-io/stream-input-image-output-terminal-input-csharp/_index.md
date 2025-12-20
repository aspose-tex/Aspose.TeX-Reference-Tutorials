---
date: 2025-12-20
description: Leer hoe u TeX naar PNG kunt converteren met Aspose.TeX voor C#. Deze
  gids laat zien hoe u een afbeelding uit TeX genereert, streams verwerkt en terminalinvoer
  vastlegt.
linktitle: Convert TeX to PNG – Master Streams, Images, & Terminal Input in Aspose.TeX
  for C#
second_title: Aspose.TeX .NET API
title: Converteer TeX naar PNG – Beheers streams, afbeeldingen en terminalinvoer in
  Aspose.TeX voor C#
url: /nl/net/advanced-io/stream-input-image-output-terminal-input-csharp/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# TeX naar PNG converteren – Master Streams, Afbeeldingen en Terminalinvoer in Aspose.TeX voor C#

## Inleiding

In deze uitgebreide tutorial leer je **hoe je TeX naar PNG kunt converteren** met Aspose.TeX voor C#. Of je nu **een afbeelding uit TeX moet genereren** voor rapporten, web‑previews of geautomatiseerde document‑pipelines, deze gids leidt je door het omgaan met streams, het beheren van afbeeldingen en het vastleggen van terminalinvoer — alles in één eenvoudig te volgen voorbeeld.

## Snelle antwoorden
- **Wat doet Aspose.TeX?** Het parseert TeX‑broncode en rendert deze naar verschillende formaten, inclusief PNG.  
- **Kan ik TeX naar PNG converteren zonder bestanden naar schijf te schrijven?** Ja – je kunt TeX via een `MemoryStream` invoeren en de PNG‑bytes direct vastleggen.  
- **Welke .NET‑versies worden ondersteund?** Alle moderne .NET‑versies (Framework 4.6+, .NET Core 3.1+, .NET 5/6).  
- **Heb ik een licentie nodig voor productiegebruik?** Een commerciële licentie is vereist voor productie; een gratis proefversie is beschikbaar.  
- **Welke beeldresolutie kan ik instellen?** De eigenschap `PngSaveOptions.Resolution` laat je DPI specificeren (bijv. 300 dpi).

## Wat betekent “convert tex to png”?

TeX naar PNG converteren betekent dat je een TeX‑opmaakstring (de taal die wordt gebruikt voor wetenschappelijke documenten) omzet naar een rasterafbeelding. Dit is handig wanneer je wiskundige formules of volledige TeX‑pagina’s wilt insluiten in webpagina’s, mobiele apps of elke omgeving die TeX niet native kan weergeven.

## Waarom een afbeelding uit TeX genereren met Aspose.TeX?

- **Geen externe afhankelijkheden** – Aspose.TeX is een pure .NET‑bibliotheek, dus je hebt geen TeX‑distributie op de server nodig.  
- **Stream‑vriendelijke API** – Werkt direct met `MemoryStream`, wat het ideaal maakt voor cloud‑services en micro‑services.  
- **Fijne controle** – Je kunt de beeldresolutie, uitvoermap en zelfs interactieve terminalinvoer instellen.  

## Voorvereisten

Zorg ervoor dat je het volgende hebt:

- Basiskennis van C#.  
- Aspose.TeX voor .NET geïnstalleerd – je kunt het **[hier](https://releases.aspose.com/tex/net/)** downloaden.  
- Een C#‑ontwikkelomgeving (Visual Studio, VS Code, Rider, enz.).  

## Namespaces importeren

Voeg de benodigde `using`‑statements toe aan de bovenkant van je C#‑bestand zodat je toegang hebt tot de Aspose.TeX‑klassen:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Image;
using System.IO;
using System.Text;
```

## Stap 1: Conversie‑opties instellen

Configureer de conversiepijplijn. Hier vertellen we Aspose.TeX de applicatie als een console‑applicatie te behandelen, geven we invoer‑/uitvoermappen op, routeren we terminal‑I/O en vragen we PNG‑output met 300 dpi aan.

```csharp
// ExStart:TakeMainInputFromStream-AuxFromFileSystem-TakeTerminalInputFromConsole-AlternativeImagesStorage
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
options.JobName = "stream-in-image-out";
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
options.TerminalIn = new InputConsoleTerminal();
options.TerminalOut = new OutputConsoleTerminal();
options.SaveOptions = new PngSaveOptions() { Resolution = 300 };
```

## Stap 2: ImageDevice maken en de taak uitvoeren

Het `ImageDevice` legt de gerenderde PNG‑gegevens vast. We voeren een eenvoudig TeX‑fragment in via een `MemoryStream`, starten de taak en laten Aspose.TeX het zware werk doen.

```csharp
ImageDevice device = new ImageDevice();
TeXJob job = new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
    "\\hrule height 10pt width 95pt\\vskip10pt\\hrule height 5pt")),
    device, options);
job.Run();
```

## Stap 3: Invoer geven in de console

Wanneer de console om invoer vraagt, typ **ABC**, druk op **Enter**, typ vervolgens **\end** en druk opnieuw op **Enter**. Dit toont hoe terminalinvoer kan worden vastgelegd terwijl de TeX‑engine draait.

## Stap 4: Output fijn afstellen

Na afloop van de taak kun je een regeleinde naar de console schrijven en de ruwe PNG‑bytes van het apparaat ophalen. Het `result`‑array bevat één PNG‑afbeelding per pagina.

```csharp
options.TerminalOut.Writer.WriteLine();
byte[][] result = device.Result;
// ExEnd:TakeMainInputFromStream-AuxFromFileSystem-TakeTerminalInputFromConsole-AlternativeImagesStorage
```

Je kunt nu `result[0]` opslaan naar een bestand, verzenden via een netwerk, of direct inbedden in een UI‑component.

## Veelvoorkomende problemen en oplossingen

| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| **Geen PNG‑output** | `SaveOptions` niet ingesteld of resolutie is nul. | Zorg ervoor dat `options.SaveOptions = new PngSaveOptions() { Resolution = 300 };` |
| **Console blijft hangen** | De TeX‑invoer ontvangt nooit `\end`. | Zorg altijd voor een afsluiting van de TeX‑stream met `\end` (of `\stop`). |
| **Onjuiste afbeeldingsgrootte** | Standaard DPI is 96. | Verhoog `Resolution` in `PngSaveOptions`. |
| **Bestandssysteempaden niet gevonden** | Verkeerde werkmap‑strings. | Gebruik absolute paden of controleer dat de mappen bestaan vóór uitvoering. |

## Veelgestelde vragen

### Q1: Kan ik Aspose.TeX voor .NET gebruiken in een niet‑console‑applicatie?

A1: Zeker! Aspose.TeX werkt in desktop‑, web‑ en service‑georiënteerde apps. Je vervangt simpelweg de console‑terminals door aangepaste streams of UI‑besturingselementen.

### Q2: Hoe kan ik de resolutie van de output‑afbeelding aanpassen?

A2: In het voorbeeld wordt de resolutie ingesteld via `PngSaveOptions.Resolution`. Verander de gehele waarde (bijv. `Resolution = 600`) om PNG’s van hogere kwaliteit te krijgen.

### Q3: Is er een proefversie beschikbaar?

A3: Ja, je kunt Aspose.TeX uitproberen met een gratis proefversie **[hier](https://releases.aspose.com/)**.

### Q4: Waar vind ik extra ondersteuning en hulp?

A4: Bezoek het Aspose.TeX‑forum **[hier](https://forum.aspose.com/c/tex/47)** voor community‑ondersteuning en discussies.

### Q5: Hoe kan ik een tijdelijke licentie voor Aspose.TeX verkrijgen?

A5: Je kunt een tijdelijke licentie **[hier](https://purchase.aspose.com/temporary-license/)** verkrijgen.

## Conclusie

Je hebt nu gezien hoe je **TeX naar PNG kunt converteren** met Aspose.TeX voor C#. Door streams te configureren, een `ImageDevice` op te zetten en terminalinvoer af te handelen, kun je hoge‑resolutie‑afbeeldingen genereren uit elke TeX‑bron — perfect voor rapporten, web‑previews of geautomatiseerde pipelines. Experimenteer verder met verschillende TeX‑fragmenten, pas de DPI aan, of integreer de byte‑array in je eigen UI.

---

**Laatst bijgewerkt:** 2025-12-20  
**Getest met:** Aspose.TeX 24.11 voor .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}