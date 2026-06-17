---
date: 2026-03-26
description: Leer hoe u een aangepast tex‑formaat maakt in .NET met Aspose.TeX en
  de tex‑invoermap instelt voor flexibele documentgeneratie. Deze stapsgewijze handleiding
  laat zien hoe u de formatprovider configureert, de tex‑invoermap instelt en XPS‑output
  genereert.
linktitle: Creating Custom TeX Formats in .NET
second_title: Aspose.TeX .NET API
title: Hoe maak je een aangepast tex‑formaat in .NET met Aspose.TeX
url: /nl/net/custom-tex-formats/create-custom-tex-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe maak je een aangepast tex-formaat in .NET met Aspose.TeX

In de dynamische wereld van .NET-ontwikkeling geeft **het maken van custom tex format** bestanden je fijne controle over hoe documenten worden gezet. Met Aspose.TeX voor .NET kun je de TeX-engine aanpassen, deze naar een specifieke invoermap wijzen, en professionele XPS-uitvoer produceren — allemaal met een paar regels C#-code.

## Snelle antwoorden
- **Wat betekent “create custom tex format”?** Het betekent het definiëren van je eigen TeX-engineconfiguratie en formatbestanden om het zetproces te beheersen.  
- **Welke bibliotheek heb ik nodig?** Aspose.TeX for .NET.  
- **Moet ik een tex-invoermap instellen?** Ja – je specificeert dit met `InputFileSystemDirectory`.  
- **Welke output kan ik genereren?** Elk apparaat dat door Aspose.TeX wordt ondersteund, bijv. XPS, PDF of PNG.  
- **Is een licentie vereist voor productie?** Een geldige Aspose.TeX-licentie is vereist voor commercieel gebruik.

## Wat is een custom TeX-format?
Een custom TeX-format is een vooraf gecompileerde set macro's en engine‑instellingen die de TeX-processor gebruikt om je bronbestanden te interpreteren. Door er een te maken, kun je bedrijfsbranding integreren, documentnormen afdwingen, of de compilatie versnellen voor repetitieve taken.

## Waarom een tex-invoermap instellen?
Het instellen van de **tex-invoermap** vertelt de engine waar naar hulpprogramma‑bestanden, aangepaste lettertypen of extra stijl‑bestanden moet worden gezocht. Dit houdt je project georganiseerd en voorkomt “file not found”-fouten tijdens de compilatie.

## Prerequisites

Before diving into the customization journey, make sure you have:

1. **Aspose.TeX for .NET** – download het van de [Aspose.TeX website](https://releases.aspose.com/tex/net/).  
2. Een **.NET-ontwikkelomgeving** (Visual Studio, VS Code, of de .NET CLI).  
3. (Optioneel) Een geldige **Aspose.TeX-licentie** als je de code in productie wilt uitvoeren.

## Namespaces importeren

Importeer eerst de namespaces die je toegang geven tot de Aspose.TeX API. Deze stap zorgt ervoor dat de klassen die we gaan gebruiken door de compiler worden herkend.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using Aspose.TeX.ResourceProviders;
using System.IO;
using System.Text;
```

## Stap 1: Maak de Format Provider

De `FormatProvider` wijst de engine naar de map die je aangepaste format‑bestand (`customtex.fmt`) bevat. Vervang `"Your Output Directory"` door het pad waar je het gecompileerde format hebt opgeslagen.

```csharp
using (FormatProvider formatProvider =
    new FormatProvider(new InputFileSystemDirectory("Your Output Directory"), "customtex"))
{
```

## Stap 2: Configureer conversie‑opties (en stel tex-invoermap in)

Hier bouwen we het `TeXOptions`‑object. Let op de `InputWorkingDirectory` – dit is waar we de **tex-invoermap** instellen zodat de engine eventuele ondersteunende bestanden kan vinden.

```csharp
    TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX(formatProvider));
    options.JobName = "typeset-with-custom-format";
    options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
    options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

## Stap 3: Voer de taak uit

Nu voeren we een eenvoudige TeX‑string naar de engine, kiezen we een uitvoerapparaat (XPS in dit voorbeeld), en voeren we de taak uit.

```csharp
    new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
        "Congratulations! You have successfully typeset this text with your own TeX format!\\end")),
        new XpsDevice(), options).Run();
```

## Stap 4: Verfraai de terminaloutput

Het toevoegen van een lege regel maakt de console‑output makkelijker leesbaar, vooral wanneer je meerdere taken in één batch uitvoert.

```csharp
    options.TerminalOut.Writer.WriteLine();
}
// ExEnd:TypesetWithCustomTeXFormat
```

Gefeliciteerd! Je hebt nu **een custom tex format** gemaakt en succesvol gebruikt om een document in .NET te zetten.

## Veelvoorkomende problemen en oplossingen

| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| *“Format file not found”* | Verkeerd pad in `FormatProvider` | Controleer of `"Your Output Directory"` `customtex.fmt` bevat en dat het pad absoluut is of correct relatief ten opzichte van het uitvoerbare bestand. |
| *“Cannot find input file”* | `InputWorkingDirectory` wijst naar de verkeerde map | Zorg ervoor dat `"Your Input Directory"` het TeX‑bronbestand bevat of dat je de bron als stream doorgeeft (zoals in het voorbeeld). |
| *Terminal output garbled* | Encoding mismatch | Gebruik `Encoding.UTF8` als je TeX‑bron niet‑ASCII‑tekens bevat. |
| *XPS file is empty* | Taak is niet uitgevoerd vanwege eerdere uitzondering | Controleer de console op foutmeldingen; deze geven vaak ontbrekende pakketten of syntaxisfouten in de TeX‑string aan. |

## Veelgestelde vragen

### Q1: Kan ik Aspose.TeX voor .NET gebruiken met andere documentverwerkingsbibliotheken?
A1: Ja, Aspose.TeX is ontworpen om naadloos te integreren met andere Aspose documentverwerkingsbibliotheken voor uitgebreide documentafhandeling.

### Q2: Is er een gratis proefversie beschikbaar voor Aspose.TeX voor .NET?
A2: Ja, je kunt de gratis proefversie [hier](https://releases.aspose.com/) benaderen.

### Q3: Hoe kan ik ondersteuning krijgen voor Aspose.TeX voor .NET?
A3: Bezoek het [Aspose.TeX forum](https://forum.aspose.com/c/tex/47) voor community‑ondersteuning of bekijk premium‑ondersteuningsopties [hier](https://purchase.aspose.com/buy).

### Q4: Zijn tijdelijke licenties beschikbaar voor Aspose.TeX voor .NET?
A4: Ja, je kunt een tijdelijke licentie verkrijgen [hier](https://purchase.aspose.com/temporary-license/).

### Q5: Waar kan ik de documentatie voor Aspose.TeX voor .NET vinden?
A5: Raadpleeg de uitgebreide documentatie [hier](https://reference.aspose.com/tex/net/).

**Additional Q&A**

**Q: Kan ik PDF in plaats van XPS outputten?**  
A: Absoluut. Vervang `new XpsDevice()` door `new PdfDevice()` en pas de uitvoermap dienovereenkomstig aan.

**Q: Moet ik het format‑bestand na elke wijziging opnieuw compileren?**  
A: Ja. Elke wijziging aan macro's of engine‑instellingen vereist het opnieuw uitvoeren van `tex -ini` om een nieuw `.fmt`‑bestand te genereren.

## Conclusie

Kortom, Aspose.TeX voor .NET biedt een robuuste oplossing voor **create custom tex format** scenario's, waardoor ontwikkelaars ongekende controle krijgen over het zetten van documenten. Experimenteer met verschillende configuraties, stel de juiste tex-invoermap in, en integreer de workflow in je grotere .NET‑applicaties voor geautomatiseerde, hoogwaardige documentgeneratie.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Laatst bijgewerkt:** 2026-03-26  
**Getest met:** Aspose.TeX 24.11 for .NET  
**Auteur:** Aspose