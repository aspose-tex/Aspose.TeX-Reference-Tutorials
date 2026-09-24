---
date: 2026-09-24
description: Lär dig hur du konfigurerar TeX-inmatningskatalog, strömmar, bilder och
  terminalinmatning med Aspose.TeX för .NET i C#.
keywords:
- configure tex input directory
- add image stream tex
- add images from stream
lastmod: 2026-09-24
linktitle: Avancerad Aspose.TeX inmatning och utmatning
og_description: Konfigurera TeX-inmatningskatalog, lägg till bildströmmar och hantera
  terminalinmatning med Aspose.TeX för .NET i C#. Lär dig steg för steg.
og_image_alt: Guide showing how to configure TeX input directory and streams in Aspose.TeX
  for .NET
og_title: Konfigurera TeX-inmatningskatalog – Avancerad Aspose.TeX‑guide
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
title: Konfigurera TeX-inmatningskatalog – Avancerad Aspose.TeX inmatning och utmatning
url: /sv/net/advanced-io/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konfigurera TeX‑indatakatalog i Aspose.TeX för .NET

Aspose.TeX för .NET låter dig bädda in full‑funktionell TeX‑behandling direkt i dina C#‑applikationer. I den här handledningen lär du dig hur du **configure TeX input directory**, matar LaTeX‑innehåll från strömmar och lägger till bilder utan att röra filsystemet. Om du behöver exakt kontroll över var motorn letar efter `.tex`‑filer och resurser, är du på rätt plats.

## Snabba svar
- **What does “configure tex input directory” mean?**  
  Det talar om för Aspose.TeX var huvud‑`.tex`‑filen, hjälpfiler och grafik finns.
- **Which class defines the input paths?**  
  `TeXInputOptions` lagrar basmappen och eventuella extra sökvägar.
- **Can I load an image from a memory stream?**  
  Ja — använd `TeXInputOptions.AddImage` med en `Stream`‑instans.
- **Is it possible to compile LaTeX code supplied at runtime?**  
  Absolut — skicka en `MemoryStream` som innehåller källtexten till processorn.
- **Do I need a license for production use?**  
  En giltig Aspose.TeX‑licens krävs för icke‑utvärderingsdistributioner.

## Vad är TeXInputOptions?
`TeXInputOptions` är konfigurationsobjektet som definierar basmappen och extra sökvägar för TeX‑resurser. Att ställa in det korrekt eliminerar “file not found”-fel och låter dig hålla tillgångar organiserade.

## Hur konfigurerar man tex‑indatakatalogen?
`TeXInputOptions` är ett konfigurationsobjekt som specificerar basmappen och ytterligare sökvägar för TeX‑resurser. Ladda ditt huvud‑dokument och tala om för processorn var den ska leta efter allt med bara några rader kod. Detta direkta svar förklarar de väsentliga stegen innan någon ytterligare detalj.

Skapa en `TeXInputOptions`‑instans, sätt `BaseFolder` till mappen som innehåller din primära `.tex`‑fil, lägg till eventuella undermappar som innehåller bilder eller hjälpfiler, och skicka alternativen till `TeXProcessor`. Processorn kommer då automatiskt att lösa alla relativa referenser.

### Steg 1: instansiera TeXInputOptions
Tilldela basmappen som innehåller den primära TeX‑källan.

### Steg 2: lägg till extra sökvägar
Om ditt projekt lagrar figurer i en separat mapp (t.ex. *Images*), anropa `AddSearchPath` för att inkludera den.

### Steg 3: överlämna alternativen till processorn
Skapa en `TeXProcessor`, tillhandahåll de konfigurerade alternativen och anropa `Process` eller `Render`.

## Hur man lägger till bilder med Aspose.TeX
Bilder som refereras i en TeX‑fil kan tillhandahållas antingen via en mapp eller direkt från en ström. Att leverera en ström är användbart när bilder lagras i en databas eller genereras i farten. `AddImage(string name, Stream data)` registrerar en bildström med det angivna filnamnet för användning i TeX‑dokumentet. Denna metod låter dig undvika temporära filer och snabbar upp bearbetningen.

## Hur man bearbetar strömmar i Aspose.TeX
När ditt LaTeX‑källkod genereras dynamiskt — kanske från användarinmatning eller en webbtjänst — kan du mata den rakt till processorn utan att skriva en fil. `TeXProcessor` bearbetar TeX‑innehåll och kan acceptera en `MemoryStream` som innehåller käll‑LaTeX‑koden. Wrappa LaTeX‑strängen i en `MemoryStream`, sätt den som källström i `TeXProcessor` och kör konverteringen. Denna teknik fungerar lika bra för molnbaserade tjänster där disk‑I/O är dyrt.

## Varför använda Aspose.TeX för avancerad I/O?
Aspose.TeX stöder **30+ in‑ och utdataformat** (inklusive PDF, PNG, SVG) och kan rendera dokument på flera hundra sidor utan att ladda hela filen i minnet. Dess ström‑först‑design minskar I/O‑overhead med upp till 40 % jämfört med fil‑baserade arbetsflöden, vilket gör den idealisk för hög‑genomströmning serverapplikationer.

## Förutsättningar
- .NET 6.0 eller senare (biblioteket fungerar också med .NET Core 3.1+ och .NET Framework 4.6.1+)
- Aspose.TeX för .NET NuGet‑paket (version 24.11 eller nyare)
- En giltig Aspose.TeX‑licens för produktionsanvändning

## Utforska Aspose.TeX: en port till avancerad dokumentbehandling
För att se konfigurationen i praktiken, följ vår steg‑för‑steg‑guide **[Specify Required Input Directory for Aspose.TeX (C#)](./required-input-directory-csharp/)**. Den handledningen går igenom hur du skapar `TeXInputOptions`‑objektet och renderar en PDF‑utdata.  
**[Specify Required Input Directory for Aspose.TeX (C#)](./required-input-directory-csharp/)**

## Mästra strömmar, bilder och terminalinmatning i Aspose.TeX för C#
För en djupare genomgång av att mata LaTeX från minnet, lägga till bilder via strömmar och använda terminal‑liknande inmatning, kolla in **[Master Streams, Images, & Terminal Input in Aspose.TeX for C#](./stream-input-image-output-terminal-input-csharp/)**. Den visar hur du integrerar Aspose.TeX i webb‑API:er, bakgrundstjänster och konsolverktyg.  
**[Master Streams, Images, & Terminal Input in Aspose.TeX for C#](./stream-input-image-output-terminal-input-csharp/)**

## Vanliga problem och lösningar
- **“File not found”-fel** – Verifiera att `BaseFolder` pekar på rätt katalog och att eventuella extra sökvägar har lagts till innan rendering.
- **Bilder laddas inte** – Säkerställ att bildnamnet i `AddImage` exakt matchar namnet som används i TeX‑källan, inklusive filändelse.
- **Minnesanvändning skjuter i höjden** – När du bearbetar mycket stora dokument, anropa `TeXProcessor.Cleanup()` efter rendering för att frigöra ohanterade resurser.

## Vanliga frågor

**Q: Kan jag ändra indatakatalogen vid körning?**  
A: Ja — du kan skapa en ny `TeXInputOptions`‑instans med en annan `BaseFolder` och skicka den till en ny `TeXProcessor` när du behöver omkonfigurera.

**Q: Hur lägger jag till bilder som lagras i en databas?**  
A: Hämta bilden som en `byte[]`, wrappa den i en `MemoryStream` och anropa `TeXInputOptions.AddImage("image.png", stream)`. Namnet måste matcha referensen i din `.tex`‑fil.

**Q: Är det möjligt att bearbeta LaTeX‑kod mottagen från ett web‑API utan att spara en fil?**  
A: Absolut. Konvertera den inkommande strängen till en `MemoryStream`, sätt den som källa för `TeXProcessor` och rendera direkt till önskat utdataformat.

**Q: Måste jag anropa några städrutiner efter bearbetning?**  
A: Disposera alla strömmar du skapar, och för stora arbetsbelastningar anropa `TeXProcessor.Cleanup()` för att frigöra inhemska resurser.

**Q: Var kan jag hitta mer avancerade exempel?**  
A: De två handledningslänkarna ovan innehåller kompletta kodexempel som demonstrerar varje scenario i detalj, inklusive felhantering och prestandatips.

---

**Last Updated:** 2026-09-24  
**Tested With:** Aspose.TeX 24.11 för .NET  
**Author:** Aspose

## Relaterade handledningar

- [Get TeX File Stream (C#) Using Aspose.TeX API Required Input Directory](/tex/net/advanced-io/required-input-directory-csharp/)
- [Create XPS from TeX with Filesystems – Aspose.TeX for .NET](/tex/net/file-input-output/filesystem-input-xps-output/)
- [Convert LaTeX to PNG Using Aspose.TeX for .NET – Process Filesystem & ZIP Inputs](/tex/net/file-input-output/required-inputs-from-filesystem-and-zip/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}