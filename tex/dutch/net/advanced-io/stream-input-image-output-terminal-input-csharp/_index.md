---
date: 2026-03-26
description: Leer hoe je latex‑png's maakt door TeX naar PNG te converteren met Aspose.TeX
  voor C#. Deze gids laat zien hoe je PNG genereert vanuit TeX, streams verwerkt en
  terminalinvoer vastlegt.
linktitle: Create latex png – Convert TeX to PNG with Aspose.TeX C#
second_title: Aspose.TeX .NET API
title: Maak LaTeX PNG – Converteer TeX naar PNG met Aspose.TeX C#
url: /nl/net/advanced-io/stream-input-image-output-terminal-input-csharp/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak latex png – Converteer TeX naar PNG met Aspose.TeX C#

In deze uitgebreide tutorial maak je **latex png** van een TeX‑bronstring met Aspose.TeX voor C#. Of je nu wiskundige formules in een webpagina wilt insluiten, voorbeeldafbeeldingen in een cloudservice wilt genereren, of rapporten automatisch wilt maken, we lopen stap voor stap door het verwerken van streams, het configureren van de afbeeldingoutput en het vastleggen van terminalinvoer – alles zonder ooit het bestandssysteem aan te raken.

## Snelle antwoorden
- **Wat doet Aspose.TeX?** Het parseert TeX‑bron en rendert het naar verschillende formaten, waaronder PNG.  
- **Kan ik TeX naar PNG converteren zonder bestanden naar schijf te schrijven?** Ja – je kunt TeX via een `MemoryStream` voeren en de PNG‑bytes direct vastleggen.  
- **Welke .NET‑versies worden ondersteund?** Alle moderne .NET‑versies (Framework 4.6+, .NET Core 3.1+, .NET 5/6).  
- **Heb ik een licentie nodig voor productiegebruik?** Een commerciële licentie is vereist voor productie; een gratis proefversie is beschikbaar.  
- **Welke beeldresolutie kan ik instellen?** De eigenschap `PngSaveOptions.Resolution` laat je DPI specificeren (bijv. 300 dpi).

## Hoe maak je latex png van TeX met Aspose.TeX?
Hieronder zie je een stap‑voor‑stap‑voorbeeld dat een TeX‑fragment uit een geheugen‑stream leest, de render‑taak uitvoert en de PNG‑bytes retourneert. Hetzelfde patroon werkt voor elk TeX‑document dat je moet **convert tex to png**.

## Wat is “convert tex to png”?

Het converteren van TeX naar PNG betekent dat je een TeX‑opmaakte string (de taal die wordt gebruikt voor wetenschappelijke documenten) neemt en deze rendert als een raster‑afbeelding. Dit is handig wanneer je wiskundige formules of volledige TeX‑pagina’s wilt insluiten in webpagina’s, mobiele apps of elke omgeving die TeX niet native kan weergeven.

## Waarom png genereren van tex met Aspose.TeX?

- **Geen externe afhankelijkheden** – Aspose.TeX is een pure .NET‑bibliotheek, dus je hebt geen TeX‑distributie op de server nodig.  
- **Stream‑vriendelijke API** – Werkt direct met `MemoryStream`, waardoor het ideaal is voor cloudservices en micro‑services.  
- **Fijne controle** – Je kunt de beeldresolutie, uitvoermap en zelfs interactieve terminalinvoer vastleggen.  

## Prerequisites

- Basiskennis van C#.  
- Aspose.TeX voor .NET geïnstalleerd – je kunt het downloaden **[hier](https://releases.aspose.com/tex/net/)**.  
- Een C# ontwikkelomgeving (Visual Studio, VS Code, Rider, enz.).  

## Namespaces importeren

Voeg de benodigde `using`‑statements toe aan de bovenkant van je C#‑bestand zodat je toegang hebt tot de Aspose.TeX‑klassen:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Image;
using System.IO;
using System.Text;
```

## Stap 1: Conversie‑opties instellen

Configureer de conversiepijplijn. Hier vertellen we Aspose.TeX dat de applicatie een console‑applicatie is, geven we invoer‑/uitvoermappen op, routeren we terminal‑I/O, en vragen we PNG‑output op 300 dpi aan.

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

## Stap 2: Image Device maken en de taak uitvoeren

De `ImageDevice` legt de gerenderde PNG‑data vast. We voeren een eenvoudig TeX‑fragment via een `MemoryStream` in, starten de taak, en laten Aspose.TeX het zware werk doen.

```csharp
ImageDevice device = new ImageDevice();
TeXJob job = new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
    "\\hrule height 10pt width 95pt\\vskip10pt\\hrule height 5pt")),
    device, options);
job.Run();
```

## Stap 3: Invoer geven in de console

Wanneer de console om invoer vraagt, typ **ABC**, druk op **Enter**, typ vervolgens **\end** en druk opnieuw op **Enter**. Dit toont hoe terminal‑invoer kan worden vastgelegd terwijl de TeX‑engine draait.

## Stap 4: Output verfijnen

Na afloop van de taak kun je een regeleinde naar de console schrijven en de ruwe PNG‑bytes van het apparaat ophalen. Het `result`‑array bevat één PNG‑afbeelding per pagina.

```csharp
options.TerminalOut.Writer.WriteLine();
byte[][] result = device.Result;
// ExEnd:TakeMainInputFromStream-AuxFromFileSystem-TakeTerminalInputFromConsole-AlternativeImagesStorage
```

Je kunt nu `result[0]` opslaan naar een bestand, over een netwerk verzenden, of direct insluiten in een UI‑component.

## Veelvoorkomende problemen en oplossingen

| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| **Geen PNG-uitvoer** | `SaveOptions` niet ingesteld of resolutie is nul. | Zorg ervoor dat `options.SaveOptions = new PngSaveOptions() { Resolution = 300 };` |
| **Console blijft hangen** | De TeX‑invoer ontvangt nooit `\end`. | Zorg ervoor dat je de TeX‑stream altijd beëindigt met `\end` (of `\stop`). |
| **Onjuiste afbeeldingsgrootte** | Standaard DPI is 96. | Verhoog `Resolution` in `PngSaveOptions`. |
| **Bestandssysteempaden niet gevonden** | Verkeerde werkmap‑strings. | Gebruik absolute paden of controleer of mappen bestaan voordat je uitvoert. |

## Veelgestelde vragen

### V1: Kan ik Aspose.TeX voor .NET gebruiken in een niet‑console applicatie?

A1: Zeker! Aspose.TeX werkt in desktop-, web- en service‑gerichte apps. Je vervangt gewoon de console‑terminals door aangepaste streams of UI‑besturingselementen.

### V2: Hoe kan ik de resolutie van de uitvoerafbeelding aanpassen?

A2: In het voorbeeld wordt de resolutie ingesteld via `PngSaveOptions.Resolution`. Verander de gehele getalwaarde (bijv. `Resolution = 600`) om PNG's van hogere kwaliteit te krijgen.

### V3: Is er een proefversie beschikbaar?

A3: Ja, je kunt Aspose.TeX uitproberen met een gratis proefversie **[hier](https://releases.aspose.com/)**.

### V4: Waar kan ik extra ondersteuning en hulp vinden?

A4: Bezoek het Aspose.TeX‑forum **[hier](https://forum.aspose.com/c/tex/47)** voor community‑ondersteuning en discussies.

### V5: Hoe kan ik een tijdelijke licentie voor Aspose.TeX verkrijgen?

A5: Je kunt een tijdelijke licentie verkrijgen **[hier](https://purchase.aspose.com/temporary-license/)**.

## Conclusie

Je hebt nu gezien hoe je **latex png** kunt maken met Aspose.TeX voor C#. Door streams te configureren, een `ImageDevice` op te zetten en terminalinvoer te verwerken, kun je hoge‑resolutie‑afbeeldingen genereren uit elke TeX‑bron – perfect voor rapporten, web‑previews of geautomatiseerde pipelines. Experimenteer met verschillende TeX‑fragmenten, pas de DPI aan, of integreer de resulterende byte‑array in je eigen UI voor een naadloze ervaring.

---

**Last Updated:** 2026-03-26  
**Tested With:** Aspose.TeX 24.11 for .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}