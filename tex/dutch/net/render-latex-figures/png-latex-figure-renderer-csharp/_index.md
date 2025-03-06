---
title: Render LaTeX-figuren naar PNG met Aspose.TeX (C#)
linktitle: Render LaTeX-figuren naar PNG met Aspose.TeX (C#)
second_title: Aspose.TeX .NET-API
description: Ontdek een uitgebreide handleiding over het renderen van LaTeX-figuren naar PNG met behulp van Aspose.TeX in C#. Leer stap voor stap met codevoorbeelden.
weight: 10
url: /nl/net/render-latex-figures/png-latex-figure-renderer-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Render LaTeX-figuren naar PNG met Aspose.TeX (C#)

## Invoering

Als u zich verdiept in de wereld van het zetwerk en het maken van documenten in .NET, bent u waarschijnlijk bekend met de uitdagingen van het weergeven van LaTeX-figuren. In deze stapsgewijze handleiding onderzoeken we hoe u Aspose.TeX voor .NET kunt gebruiken om LaTeX-figuren naar PNG-indeling weer te geven met behulp van C#. Aspose.TeX biedt een krachtige en flexibele oplossing voor het verwerken van LaTeX-documenten, waardoor het een hulpmiddel van onschatbare waarde is voor ontwikkelaars die werken met het genereren en formatteren van documenten.

## Vereisten

Voordat we ingaan op de tutorial, zorg ervoor dat je aan de volgende vereisten voldoet:

-  Aspose.TeX voor .NET-bibliotheek: Zorg ervoor dat de Aspose.TeX-bibliotheek voor .NET is geïnstalleerd. Je kunt het downloaden[hier](https://releases.aspose.com/tex/net/).

## Naamruimten importeren

Begin in uw C#-code met het importeren van de benodigde naamruimten. Deze stap zorgt ervoor dat je toegang hebt tot de benodigde lessen en functionaliteiten.

```csharp
using Aspose.TeX.Features;
```

## Render LaTeX-figuren naar PNG

### Stap 1: Renderingopties instellen

Begin met het maken van weergaveopties en het instellen van parameters zoals afbeeldingsresolutie, preambule, schaalfactor, achtergrondkleur en meer.

```csharp
FigureRendererOptions options = new PngFigureRendererOptions() { Resolution = 150 };
options.Preamble = "\\usepackage{pict2e}";
options.Scale = 3000;
options.BackgroundColor = System.Drawing.Color.White;
options.LogStream = new System.IO.MemoryStream();
options.ShowTerminal = true;
```

### Stap 2: Definieer de uitvoerstroom en afmetingen

Maak een uitvoerstroom voor de PNG-afbeelding en variabelen om de afmetingen van de resulterende afbeelding op te slaan.

```csharp
System.Drawing.SizeF size = new System.Drawing.SizeF();
using (System.IO.Stream stream = System.IO.File.Open(
   System.IO.Path.Combine("Your Output Directory", "text-and-formula.png"), System.IO.FileMode.Create))
{
    // Code voor weergave vindt u hier
}
```

### Stap 3: Voer het renderen uit

Implementeer het weergaveproces met behulp van de Aspose.TeX-bibliotheek. Geef de LaTeX-code, uitvoerstroom, weergaveopties en groottevariabele op.

```csharp
new PngFigureRenderer().Render(@"\setlength{\unitlength}{0.8cm}
\begin{picture}(6,5)
    % LaTeX figure code goes here
\end{picture}", stream, options, out size);
```

### Stap 4: Resultaten weergeven

Geef ten slotte de resultaten weer, inclusief eventuele foutrapporten en de grootte van de weergegeven afbeelding.

```csharp
System.Console.Out.WriteLine(options.ErrorReport);
System.Console.Out.WriteLine();
System.Console.Out.WriteLine("Size: " + size);
```

## Conclusie

Met Aspose.TeX voor .NET wordt het renderen van LaTeX-figuren naar PNG-formaat een naadloos proces. Deze tutorial heeft u door de essentiële stappen geleid, van het instellen van weergaveopties tot het weergeven van de uiteindelijke resultaten.

## Veelgestelde vragen

### Vraag 1: Is Aspose.TeX compatibel met alle LaTeX-opdrachten?

 A1: Aspose.TeX ondersteunt een breed scala aan LaTeX-opdrachten, maar het wordt aanbevolen om de[documentatie](https://reference.aspose.com/tex/net/) voor gedetailleerde informatie.

### V2: Kan ik Aspose.TeX uitproberen voordat ik een aankoop doe?

 A2: Ja, u kunt een gratis proefversie uitproberen[hier](https://releases.aspose.com/).

### V3: Hoe krijg ik ondersteuning voor Aspose.TeX?

 A3: Bezoek de[Aspose.TeX-forum](https://forum.aspose.com/c/tex/47)voor gemeenschapsondersteuning en discussies.

### V4: Waar kan ik tijdelijke licenties voor Aspose.TeX vinden?

 A4: Er zijn tijdelijke licenties beschikbaar[hier](https://purchase.aspose.com/temporary-license/).

### V5: Wat is de prijsstructuur voor Aspose.TeX?

A5: Ontdek prijsdetails en doe een aankoop[hier](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
