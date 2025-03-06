---
title: Återge LaTeX-figurer till SVG med Aspose.TeX (C#)
linktitle: Återge LaTeX-figurer till SVG med Aspose.TeX (C#)
second_title: Aspose.TeX .NET API
description: Förbättra dokumentrenderingen i .NET med Aspose.TeX. Lär dig hur du renderar LaTeX-figurer till SVG i C# för sömlös integrering av matematiska uttryck.
weight: 11
url: /sv/net/render-latex-figures/svg-latex-figure-renderer-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Återge LaTeX-figurer till SVG med Aspose.TeX (C#)

## Introduktion

Om du vill förbättra dina dokumentåtergivningsmöjligheter i .NET med hjälp av LaTeX-figurer, är Aspose.TeX din bästa lösning. I den här steg-för-steg-guiden går vi igenom hur du renderar LaTeX-figurer till SVG med Aspose.TeX i C#. I slutet av denna handledning har du en tydlig förståelse av processen, vilket ger dig möjlighet att sömlöst införliva matematiska uttryck och figurer av hög kvalitet i dina dokument.

## Förutsättningar

Innan vi dyker in i handledningen, se till att du har följande förutsättningar på plats:

- Grundläggande kunskaper i programmeringsspråket C#.
-  Aspose.TeX för .NET-biblioteket installerat. Du kan ladda ner den[här](https://releases.aspose.com/tex/net/).

## Importera namnområden

Se till att importera de nödvändiga namnrymden i din C#-kod:

```csharp
using Aspose.TeX.Features;
```

Låt oss nu dela upp handledningen i flera steg:

## Steg 1: Skapa renderingsalternativ

```csharp
FigureRendererOptions options = new SvgFigureRendererOptions();
options.Preamble = "\\usepackage{pict2e}";
options.Scale = 3000;
options.BackgroundColor = Color.White;
options.LogStream = new System.IO.MemoryStream();
options.ShowTerminal = true;
```

Här ställer vi in renderingsalternativ, anger ingressen, skalningsfaktor, bakgrundsfärg, loggström och om terminalutdata ska visas.

## Steg 2: Definiera dimensioner och utdataström

```csharp
SizeF size = new SizeF();
using (Stream stream = File.Open(Path.Combine("Your Output Directory", "text-and-formula.svg"), FileMode.Create))
{
    // Kör rendering.
    new SvgFigureRenderer().Render("Your LaTeX Code", stream, options, out size);
}
```

Ersätt "Din utdatakatalog" med din önskade katalog och ange din LaTeX-kod som en sträng.

## Steg 3: Visa resultat

```csharp
Console.Out.WriteLine(options.ErrorReport);
Console.Out.WriteLine();
Console.Out.WriteLine("Size: " + size);
```

Det här steget visar eventuella felrapporter och storleken på den resulterande bilden.

## Slutsats

Grattis! Du har framgångsrikt lärt dig hur du renderar LaTeX-figurer till SVG med Aspose.TeX i C#. Nu kan du sömlöst integrera matematiska uttryck och figurer i dina .NET-applikationer.

## FAQ's

### F1: Är Aspose.TeX gratis att använda?

 S1: Aspose.TeX erbjuder en gratis provperiod. Du kan komma åt den[här](https://releases.aspose.com/).

### F2: Var kan jag hitta Aspose.TeX-dokumentation?

 S2: Se dokumentationen[här](https://reference.aspose.com/tex/net/).

### F3: Hur får jag support för Aspose.TeX?

 S3: Besök supportforumet[här](https://forum.aspose.com/c/tex/47).

### F4: Kan jag köpa Aspose.TeX?

 S4: Ja, du kan köpa Aspose.TeX[här](https://purchase.aspose.com/buy).

### F5: Behöver jag en tillfällig licens?

 S5: Om det behövs kan du få en tillfällig licens[här](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
