---
date: 2026-10-19
description: Leer hoe je tex-documentgeneratie uitvoert, een aangepast tex-formaat
  maakt en de tex-invoermap instelt met Aspose.TeX voor .NET. Stapsgewijze handleiding
  met codevoorbeelden en tips voor probleemoplossing.
keywords:
- tex document generation
- create custom tex format
- set tex input directory
- custom tex macros
lastmod: 2026-10-19
linktitle: Aangepaste TeX-formaten maken in .NET
og_description: tex-documentgeneratie met Aspose.TeX stelt je in staat om een aangepast
  tex-formaat te maken en de tex-invoermap in .NET in te stellen. Volg deze handleiding
  voor XPS-, PDF- of PNG-uitvoer.
og_image_alt: Developer guide showing tex document generation using Aspose.TeX in
  .NET
og_title: Hoe tex-documentgeneratie met formaat in .NET te doen
schemas:
- author: Aspose
  dateModified: '2026-10-19'
  description: Learn how to perform tex document generation, create custom tex format
    and set tex input directory using Aspose.TeX for .NET. Step‑by‑step guide with
    code snippets and troubleshooting tips.
  headline: How to do tex document generation with format in .NET
  type: TechArticle
- description: Learn how to perform tex document generation, create custom tex format
    and set tex input directory using Aspose.TeX for .NET. Step‑by‑step guide with
    code snippets and troubleshooting tips.
  name: How to do tex document generation with format in .NET
  steps:
  - name: '**Aspose.TeX for .NET** – download it from the [Aspose.TeX website](https://releases.aspose.com/tex/net/).'
    text: '**Aspose.TeX for .NET** – download it from the [Aspose.TeX website](https://releases.aspose.com/tex/net/).'
  - name: A **.NET development environment** (Visual Studio, VS Code, or the .NET
      CLI).
    text: A **.NET development environment** (Visual Studio, VS Code, or the .NET
      CLI).
  - name: (Optional) A valid **Aspose.TeX license** for production use.
    text: (Optional) A valid **Aspose.TeX license** for production use.
  type: HowTo
- questions:
  - answer: Absolutely. Replace `new XpsDevice()` with `new PdfDevice()` and adjust
      the output path accordingly.
    question: Can I output PDF instead of XPS?
  - answer: Yes. Any modification to macros or engine settings requires re‑running
      `tex -ini` to generate a fresh `.fmt` file.
    question: Do I need to re‑compile the format file after every change?
  type: FAQPage
second_title: Aspose.TeX .NET API
tags:
- tex document generation
- Aspose.TeX
- .NET document processing
- custom tex format
title: Hoe tex-documentgeneratie met formaat in .NET te doen
url: /nl/net/custom-tex-formats/create-custom-tex-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe tex-documentgeneratie met formaat in .NET uit te voeren

In moderne .NET-ontwikkeling is **tex document generation** een krachtige manier om hoogwaardige typeset-uitvoer te produceren zonder afhankelijk te zijn van externe LaTeX‑installaties. Aspose.TeX for .NET geeft je volledige controle: je kunt **create custom tex format**, wijst de engine op een speciale invoermap, en exporteert naar XPS, PDF, PNG of andere apparaten — allemaal vanuit eenvoudige C#‑code.

## Snelle antwoorden
- **Wat betekent “create custom tex format”?** Het betekent dat je je eigen TeX‑engine‑configuratie en gecompileerd formaatbestand definieert zodat de processor je macro's en instellingen volgt.  
- **Welke bibliotheek heb ik nodig?** Aspose.TeX for .NET, which supports 30+ input and output formats.  
- **Moet ik een tex-invoermap instellen?** Ja – gebruik `InputWorkingDirectory` om de engine te vertellen waar de hulpprogramma‑bestanden zich bevinden.  
- **Welke output kan ik genereren?** XPS, PDF, PNG, TIFF, en nog veel meer apparaatformaten.  
- **Is een licentie vereist voor productie?** Een geldige Aspose.TeX‑licentie is verplicht voor commerciële implementaties.

## Wat is een custom tex format?
Een custom tex format is een vooraf gecompileerde collectie macro's en engine‑instellingen die de TeX‑processor bij het opstarten laadt. Door er een te maken, kun je bedrijfsbranding integreren, lay-outstandaarden afdwingen en de compilatietijd voor repetitieve documenten verkorten. Het zorgt voor consistente styling in alle gegenereerde documenten en vereenvoudigt het onderhoud van complexe typesetting‑workflows.

## Waarom een tex-invoermap instellen?
Het instellen van de **tex input directory** vertelt de engine waar auxiliaire bestanden zoals stijlbestanden, aangepaste lettertypen of extra macro‑pakketten te vinden zijn. Dit elimineert “file not found”-fouten en houdt je projectmap opgeruimd. Het verbetert ook de reproduceerbaarheid van builds door ervoor te zorgen dat alle bronnen vanuit een bekende locatie worden opgehaald.

## Vereisten

Voordat je begint, zorg ervoor dat je het volgende hebt:

1. **Aspose.TeX for .NET** – download het van de [Aspose.TeX website](https://releases.aspose.com/tex/net/).  
2. Een **.NET development environment** (Visual Studio, VS Code, of de .NET CLI).  
3. (Optioneel) Een geldige **Aspose.TeX license** voor productiegebruik.

## Namespaces importeren

De volgende namespaces geven je toegang tot de kernklassen van Aspose.TeX.  
Klassen gerelateerd aan `Document` bevinden zich onder `Aspose.TeX`, terwijl opties en devices in `Aspose.TeX.Rendering` staan.

De `Document`‑klasse is het top‑level object dat een enkel TeX‑document in het geheugen vertegenwoordigt.  

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using Aspose.TeX.ResourceProviders;
using System.IO;
using System.Text;
```

## Stap 1: maak de format provider

De `FormatProvider` vertelt de engine waar het gecompileerde formaatbestand (`customtex.fmt`) zich bevindt. Vervang `"Your Output Directory"` door het absolute pad dat je custom format bevat.

`FormatProvider` is een lichtgewicht wrapper die het `.fmt`‑bestand één keer laadt en hergebruikt voor elke conversie, waardoor de prestaties voor batch‑taken aanzienlijk verbeteren.

```csharp
using (FormatProvider formatProvider =
    new FormatProvider(new InputFileSystemDirectory("Your Output Directory"), "customtex"))
{
```

## Stap 2: configureer conversie‑opties (en stel tex input directory in)

Hier bouwen we een `TeXOptions`‑instantie. De eigenschap `InputWorkingDirectory` **stelt de tex input directory** in zodat de engine alle ondersteunende bestanden zoals aangepaste pakketten of lettertypen kan vinden.

`TeXOptions` laat je ook het output‑device, paginagrootte en render‑kwaliteit specificeren. Voor grootschalige generatie kun je `EnableParallelProcessing` inschakelen om het renderen op multi‑core servers te versnellen.

```csharp
    TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX(formatProvider));
    options.JobName = "typeset-with-custom-format";
    options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
    options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

## Stap 3: voer de taak uit

Voer nu een eenvoudige TeX‑string in de engine, kies een output‑device (XPS in dit voorbeeld), en voer de taak uit. De `TeXEngine` leest het custom format, verwerkt de bron, en schrijft het resultaat naar het geselecteerde device.

`TeXEngine` is de kernprocessor van Aspose.TeX die de TeX‑bron parseert, het custom format toepast, en de gerenderde pagina's naar het door jou opgegeven device streamt.

```csharp
    new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
        "Congratulations! You have successfully typeset this text with your own TeX format!\\end")),
        new XpsDevice(), options).Run();
```

## Stap 4: verfijn de terminaloutput

Het toevoegen van een lege regel na het voltooien van de taak maakt console‑logboeken makkelijker leesbaar, vooral wanneer je meerdere conversies in een script aaneenschakelt.

`Console.WriteLine()` schrijft een regel tekst naar de standaard output‑stream. Het wordt hier uitsluitend gebruikt voor visuele scheiding; het heeft geen invloed op het gegenereerde document.

```csharp
    options.TerminalOut.Writer.WriteLine();
}
// ExEnd:TypesetWithCustomTeXFormat
```

Gefeliciteerd! Je hebt nu **created a custom tex format** en gebruikt voor **tex document generation** in .NET. Je kunt de `XpsDevice` vervangen door `PdfDevice`, `PngDevice`, of elk ander ondersteund device om aan je leveringsbehoeften te voldoen.

## Veelvoorkomende problemen en oplossingen

| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| *“Format file not found”* | Verkeerd pad in `FormatProvider` | Controleer of `"Your Output Directory"` `customtex.fmt` bevat en dat het pad absoluut is of correct relatief ten opzichte van het uitvoerbare bestand. |
| *“Cannot find input file”* | `InputWorkingDirectory` wijst naar de verkeerde map | Zorg ervoor dat `"Your Input Directory"` het TeX‑bronbestand bevat of dat je de bron als stream doorgeeft (zoals in het voorbeeld). |
| *Terminal output garbled* | Codering mismatch | Gebruik `Encoding.UTF8` als je TeX‑bron niet‑ASCII‑tekens bevat. |
| *XPS file is empty* | Taak is niet uitgevoerd vanwege een eerdere uitzondering | Controleer de console op foutmeldingen; deze geven vaak ontbrekende pakketten of syntaxisfouten in de TeX‑string aan. |

## Veelgestelde vragen

**Q1: Kan ik Aspose.TeX for .NET gebruiken met andere Aspose‑bibliotheken?**  
A: Ja, Aspose.TeX integreert naadloos met Aspose.PDF, Aspose.Words, en andere Aspose‑producten voor end‑to‑end document‑pijplijnen.

**Q2: Is er een gratis proefversie beschikbaar voor Aspose.TeX for .NET?**  
A: Ja, je kunt een proefversie downloaden van de **Aspose.TeX free trial download page** (https://releases.aspose.com/tex/net/).

**Q3: Hoe kan ik ondersteuning krijgen voor Aspose.TeX for .NET?**  
A: Bezoek het [Aspose.TeX forum](https://forum.aspose.com/c/tex/47) voor community‑hulp of bekijk premiumopties op de **premium support purchase page** (https://purchase.aspose.com/buy).

**Q4: Zijn tijdelijke licenties beschikbaar voor Aspose.TeX for .NET?**  
A: Ja, vraag er een aan op de **temporary license request page** (https://purchase.aspose.com/temporary-license/).

**Q5: Waar kan ik de officiële API‑referentie vinden?**  
A: De uitgebreide documentatie is te vinden op de **API reference documentation** (https://reference.aspose.com/tex/net/).

### Aanvullende Q&A

**Q: Kan ik PDF outputten in plaats van XPS?**  
A: Absoluut. Vervang `new XpsDevice()` door `new PdfDevice()` en pas het output‑pad dienovereenkomstig aan.

**Q: Moet ik het formaatbestand na elke wijziging opnieuw compileren?**  
A: Ja. Elke wijziging aan macro's of engine‑instellingen vereist het opnieuw uitvoeren van `tex -ini` om een nieuw `.fmt`‑bestand te genereren.

## Conclusie

Aspose.TeX for .NET levert een **robust, high‑performance solution for tex document generation**, waarmee je **create custom tex format**, de **tex input directory** instelt, en uitvoert naar elk ondersteund device. Neem de bovenstaande stappen op in je CI/CD‑pipeline, automatiseer grootschalige rapportgeneratie, of bouw een custom publishing engine die voldoet aan de branding‑standaarden van je organisatie.

---

**Laatst bijgewerkt:** 2026-10-19  
**Getest met:** Aspose.TeX 24.11 for .NET  
**Auteur:** Aspose

## Gerelateerde tutorials

- [TeX-bestandstream ophalen (C#) met Aspose.TeX API Vereiste invoermap](/tex/net/advanced-io/required-input-directory-csharp/)
- [Hoe PDF te maken met Aspose.TeX for .NET – Stap voor stap](/tex/net/pdf-output/)
- [Hoe XPS-document te maken .NET – Converteer TeX naar XPS-output met Aspose.TeX for .NET](/tex/net/xps-output/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}