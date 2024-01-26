---
title: Render LaTeX-figuren naar SVG met Aspose.TeX (C#)
linktitle: Render LaTeX-figuren naar SVG met Aspose.TeX (C#)
second_title: Aspose.TeX .NET-API
description: Verbeter de documentweergave in .NET met Aspose.TeX. Leer hoe u LaTeX-figuren kunt renderen naar SVG in C# voor een naadloze integratie van wiskundige uitdrukkingen.
type: docs
weight: 11
url: /nl/net/render-latex-figures/svg-latex-figure-renderer-csharp/
---
## Invoering

Als u uw documentweergavemogelijkheden in .NET wilt verbeteren met behulp van LaTeX-cijfers, is Aspose.TeX uw beste oplossing. In deze stapsgewijze handleiding begeleiden we u bij het renderen van LaTeX-figuren naar SVG met behulp van Aspose.TeX in C#. Aan het einde van deze zelfstudie heeft u een duidelijk inzicht in het proces, waardoor u hoogwaardige wiskundige uitdrukkingen en cijfers naadloos in uw documenten kunt opnemen.

## Vereisten

Voordat we in de tutorial duiken, moet je ervoor zorgen dat je aan de volgende vereisten voldoet:

- Basiskennis van de programmeertaal C#.
-  Aspose.TeX voor .NET-bibliotheek geïnstalleerd. Je kunt het downloaden[hier](https://releases.aspose.com/tex/net/).

## Naamruimten importeren

Zorg ervoor dat u in uw C#-code de benodigde naamruimten importeert:

```csharp
using Aspose.TeX.Features;
```

Laten we de tutorial nu in meerdere stappen opsplitsen:

## Stap 1: Renderingopties maken

```csharp
FigureRendererOptions options = new SvgFigureRendererOptions();
options.Preamble = "\\usepackage{pict2e}";
options.Scale = 3000;
options.BackgroundColor = Color.White;
options.LogStream = new System.IO.MemoryStream();
options.ShowTerminal = true;
```

Hier hebben we weergaveopties ingesteld, waarbij we de preambule, schaalfactor, achtergrondkleur, logstream en of de terminaluitvoer moet worden weergegeven specificeren.

## Stap 2: Definieer afmetingen en uitvoerstroom

```csharp
SizeF size = new SizeF();
using (Stream stream = File.Open(Path.Combine("Your Output Directory", "text-and-formula.svg"), FileMode.Create))
{
    // Voer het renderen uit.
    new SvgFigureRenderer().Render("Your LaTeX Code", stream, options, out size);
}
```

Vervang "Uw uitvoermap" door de gewenste map en geef uw LaTeX-code op als string.

## Stap 3: Resultaten weergeven

```csharp
Console.Out.WriteLine(options.ErrorReport);
Console.Out.WriteLine();
Console.Out.WriteLine("Size: " + size);
```

Bij deze stap worden eventuele foutrapporten en de grootte van de resulterende afbeelding weergegeven.

## Conclusie

Gefeliciteerd! Je hebt met succes geleerd hoe je LaTeX-figuren naar SVG kunt renderen met behulp van Aspose.TeX in C#. Nu kunt u wiskundige uitdrukkingen en cijfers naadloos integreren in uw .NET-toepassingen.

## Veelgestelde vragen

### Vraag 1: Is Aspose.TeX gratis te gebruiken?

 A1: Aspose.TeX biedt een gratis proefperiode. Je hebt er toegang toe[hier](https://releases.aspose.com/).

### V2: Waar kan ik Aspose.TeX-documentatie vinden?

 A2: Raadpleeg de documentatie[hier](https://reference.aspose.com/tex/net/).

### V3: Hoe krijg ik ondersteuning voor Aspose.TeX?

 A3: Bezoek het ondersteuningsforum[hier](https://forum.aspose.com/c/tex/47).

### V4: Kan ik Aspose.TeX kopen?

 A4: Ja, u kunt Aspose.TeX kopen[hier](https://purchase.aspose.com/buy).

### Vraag 5: Heb ik een tijdelijke licentie nodig?

 A5: Indien nodig kunt u een tijdelijke licentie verkrijgen[hier](https://purchase.aspose.com/temporary-license/).