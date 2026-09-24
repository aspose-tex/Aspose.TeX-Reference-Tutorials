---
date: 2026-09-24
description: Leer hoe u de TeX-invoermap, streams, afbeeldingen en terminalinvoer
  kunt configureren met Aspose.TeX voor .NET in C#.
keywords:
- configure tex input directory
- add image stream tex
- add images from stream
lastmod: 2026-09-24
linktitle: Geavanceerde Aspose.TeX Invoer en Uitvoer
og_description: Configureer de TeX-invoermap, voeg afbeeldingsstreams toe en verwerk
  terminalinvoer met Aspose.TeX voor .NET in C#. Leer stap voor stap.
og_image_alt: Guide showing how to configure TeX input directory and streams in Aspose.TeX
  for .NET
og_title: Configureer TeX-invoermap – Geavanceerde Aspose.TeX-gids
schemas:
- author: Aspose
  dateModified: '2026-09-24'
  description: Learn how to configure TeX input directory, streams, images, and terminal
    input using Aspose.TeX for .NET in C#.
  headline: Configure TeX input directory – Advanced Aspose.TeX Input and Output
  type: TechArticle
- description: Learn how to configure TeX input directory, streams, images, and terminal
    input using Aspose.TeX for .NET in C#.
  name: Configure TeX input directory – Advanced Aspose.TeX Input and Output
  steps:
  - name: instantiate TeXInputOptions
    text: Assign the base folder that holds the primary TeX source.
  - name: add extra search paths
    text: If your project stores figures in a separate folder (e.g., *Images*), call
      `AddSearchPath` to include it.
  - name: hand the options to the processor
    text: Create a `TeXProcessor`, provide the configured options, and invoke `Process`
      or `Render`.
  type: HowTo
- questions:
  - answer: Yes—you can create a new `TeXInputOptions` instance with a different `BaseFolder`
      and pass it to a fresh `TeXProcessor` whenever you need to reconfigure.
    question: Can I change the input directory at runtime?
  - answer: Retrieve the image as a `byte[]`, wrap it in a `MemoryStream`, and call
      `TeXInputOptions.AddImage("image.png", stream)`. The name must match the reference
      in your `.tex` file.
    question: How do I add images that are stored in a database?
  - answer: Absolutely. Convert the incoming string to a `MemoryStream`, set it as
      the source for `TeXProcessor`, and render directly to your desired output format.
    question: Is it possible to process LaTeX code received from a web API without
      saving a file?
  - answer: Dispose of any streams you create, and for large workloads invoke `TeXProcessor.Cleanup()`
      to free native resources.
    question: Do I need to call any cleanup methods after processing?
  - answer: The two tutorial links above contain full code samples that demonstrate
      each scenario in detail, including error handling and performance tips.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.TeX .NET API
tags:
- Aspose.TeX
- input directory
- C# document processing
title: Configureer de TeX-invoermap – Geavanceerde Aspose.TeX Invoer en Uitvoer
url: /nl/net/advanced-io/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configureer TeX‑invoermap in Aspose.TeX voor .NET

Aspose.TeX for .NET stelt je in staat om volledige TeX‑verwerking direct in je C#‑applicaties in te sluiten. In deze tutorial leer je hoe je de **configureer TeX‑invoermap**, LaTeX‑inhoud vanuit streams voedt, en afbeeldingen toevoegt zonder het bestandssysteem aan te raken. Als je nauwkeurige controle nodig hebt over waar de engine zoekt naar `.tex`‑bestanden en bronnen, ben je hier op de juiste plek.

## Snelle antwoorden
- **Wat betekent “configure tex input directory”?**  
  Het vertelt Aspose.TeX waar het hoofd‑`.tex`‑bestand, hulpprogramma‑bestanden en afbeeldingen kan vinden.
- **Welke klasse definieert de invoer‑paden?**  
  `TeXInputOptions` slaat de basismap en eventuele extra zoeklocaties op.
- **Kan ik een afbeelding laden vanuit een geheugen‑stream?**  
  Ja—gebruik `TeXInputOptions.AddImage` met een `Stream`‑instantie.
- **Is het mogelijk om LaTeX‑code die tijdens runtime wordt geleverd te compileren?**  
  Absoluut—geef een `MemoryStream` met de brontekst door aan de processor.
- **Heb ik een licentie nodig voor productiegebruik?**  
  Een geldige Aspose.TeX‑licentie is vereist voor niet‑evaluatie‑implementaties.

## Wat is TeXInputOptions?
`TeXInputOptions` is het configuratie‑object dat de basismap en extra zoekpaden voor TeX‑bronnen definieert. Het correct instellen elimineert “bestand niet gevonden”‑fouten en stelt je in staat om assets georganiseerd te houden.

## Hoe configureer je de TeX‑invoermap?
`TeXInputOptions` is een configuratie‑object dat de basismap en extra zoekpaden voor TeX‑bronnen specificeert. Laad je hoofd‑document en vertel de processor waar alles te vinden is in slechts een paar regels. Dit directe antwoord legt de essentiële stappen uit vóór verdere details.

Maak een `TeXInputOptions`‑instantie, stel `BaseFolder` in op de map die je primaire `.tex`‑bestand bevat, voeg eventuele sub‑mappen toe die afbeeldingen of hulpprogramma‑bestanden bevatten, en geef de opties door aan `TeXProcessor`. De engine zal vervolgens alle relatieve verwijzingen automatisch oplossen.

### Stap 1: instantieer TeXInputOptions
Wijs de basismap toe die de primaire TeX‑bron bevat.

### Stap 2: voeg extra zoekpaden toe
Als je project figuren opslaat in een aparte map (bijv. *Images*), roep dan `AddSearchPath` aan om deze op te nemen.

### Stap 3: geef de opties door aan de processor
Maak een `TeXProcessor`, lever de geconfigureerde opties aan, en roep `Process` of `Render` aan.

## Hoe afbeeldingen toe te voegen met Aspose.TeX
Afbeeldingen die in een TeX‑bestand worden verwezen, kunnen worden geleverd via een map of direct vanuit een stream. Het leveren van een stream is handig wanneer afbeeldingen in een database zijn opgeslagen of on‑the‑fly worden gegenereerd. `AddImage(string name, Stream data)` registreert een afbeeldings‑stream met de opgegeven bestandsnaam voor gebruik in het TeX‑document. Deze methode stelt je in staat tijdelijke bestanden te vermijden en versnelt de verwerking.

## Hoe streams te verwerken in Aspose.TeX
Wanneer je LaTeX‑bron dynamisch wordt gegenereerd—bijvoorbeeld vanuit gebruikersinvoer of een webservice—kun je deze rechtstreeks aan de processor voeren zonder een bestand te schrijven. `TeXProcessor` verwerkt TeX‑inhoud en kan een `MemoryStream` accepteren die de bron‑LaTeX‑code bevat. Plaats de LaTeX‑string in een `MemoryStream`, stel deze in als de bron‑stream in `TeXProcessor`, en voer de conversie uit. Deze techniek werkt even goed voor cloud‑native services waar schijf‑I/O duur is.

## Waarom Aspose.TeX gebruiken voor geavanceerde I/O?
Aspose.TeX ondersteunt **30+ invoer‑ en uitvoerformaten** (inclusief PDF, PNG, SVG) en kan documenten van meerdere honderden pagina's renderen zonder het volledige bestand in het geheugen te laden. Het stream‑first‑ontwerp vermindert I/O‑overhead tot wel 40 % vergeleken met bestandsgebaseerde workflows, waardoor het ideaal is voor high‑throughput server‑applicaties.

## Vereisten
- .NET 6.0 of later (de bibliotheek werkt ook met .NET Core 3.1+ en .NET Framework 4.6.1+)
- Aspose.TeX for .NET NuGet‑pakket (versie 24.11 of nieuwer)
- Een geldige Aspose.TeX‑licentie voor productiegebruik

## Ontdek Aspose.TeX: een toegangspoort tot geavanceerde documentverwerking
Om de configuratie in actie te zien, volg onze stap‑voor‑stap‑gids **[Specificeer Vereiste Invoermap voor Aspose.TeX (C#)](./required-input-directory-csharp/)**. Die tutorial leidt je door het maken van het `TeXInputOptions`‑object en het renderen van een PDF‑output.  
**[Specificeer Vereiste Invoermap voor Aspose.TeX (C#)](./required-input-directory-csharp/)**

## Meesterschap over streams, afbeeldingen en terminalinvoer in Aspose.TeX voor C#
Voor een diepere duik in het voeden van LaTeX vanuit het geheugen, het toevoegen van afbeeldingen via streams, en het gebruiken van terminal‑achtige invoer, bekijk **[Beheers Streams, Afbeeldingen & Terminalinvoer in Aspose.TeX voor C#](./stream-input-image-output-terminal-input-csharp/)**. Het toont hoe je Aspose.TeX integreert in web‑API's, achtergrondservices en console‑tools.  
**[Beheers Streams, Afbeeldingen & Terminalinvoer in Aspose.TeX voor C#](./stream-input-image-output-terminal-input-csharp/)**

## Veelvoorkomende problemen en oplossingen
- **“File not found”‑fouten** – Controleer of `BaseFolder` naar de juiste map wijst en of eventuele extra zoekpaden zijn toegevoegd vóór het renderen.
- **Afbeeldingen laden niet** – Zorg ervoor dat de afbeeldingsnaam in `AddImage` exact overeenkomt met de naam die in de TeX‑bron wordt gebruikt, inclusief bestandsextensie.
- **Geheugengebruik piekt** – Roep bij het verwerken van zeer grote documenten `TeXProcessor.Cleanup()` aan na het renderen om niet‑beheerste bronnen vrij te geven.

## Veelgestelde vragen

**Q: Kan ik de invoermap tijdens runtime wijzigen?**  
A: Ja—je kunt een nieuwe `TeXInputOptions`‑instantie maken met een andere `BaseFolder` en deze doorgeven aan een nieuwe `TeXProcessor` wanneer je opnieuw moet configureren.

**Q: Hoe voeg ik afbeeldingen toe die in een database zijn opgeslagen?**  
A: Haal de afbeelding op als een `byte[]`, plaats deze in een `MemoryStream`, en roep `TeXInputOptions.AddImage("image.png", stream)` aan. De naam moet overeenkomen met de referentie in je `.tex`‑bestand.

**Q: Is het mogelijk om LaTeX‑code ontvangen van een web‑API te verwerken zonder een bestand op te slaan?**  
A: Absoluut. Converteer de binnenkomende string naar een `MemoryStream`, stel deze in als bron voor `TeXProcessor`, en render direct naar het gewenste uitvoerformaat.

**Q: Moet ik na het verwerken enige opruimmethoden aanroepen?**  
A: Vernietig alle streams die je maakt, en bij grote workloads roep `TeXProcessor.Cleanup()` aan om native bronnen vrij te maken.

**Q: Waar kan ik meer geavanceerde voorbeelden vinden?**  
A: De twee bovenstaande tutorial‑links bevatten volledige code‑samples die elk scenario in detail demonstreren, inclusief foutafhandeling en prestatietips.

---

**Laatst bijgewerkt:** 2026-09-24  
**Getest met:** Aspose.TeX 24.11 for .NET  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Haal TeX‑bestand‑stream op (C#) met Aspose.TeX API Vereiste Invoermap](/tex/net/advanced-io/required-input-directory-csharp/)
- [Maak XPS van TeX met Filesystemen – Aspose.TeX voor .NET](/tex/net/file-input-output/filesystem-input-xps-output/)
- [Converteer LaTeX naar PNG met Aspose.TeX voor .NET – Verwerk Filesystem‑ en ZIP‑invoer](/tex/net/file-input-output/required-inputs-from-filesystem-and-zip/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}