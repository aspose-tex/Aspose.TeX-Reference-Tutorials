---
title: Rendering di figure LaTeX in SVG con Aspose.TeX (C#)
linktitle: Rendering di figure LaTeX in SVG con Aspose.TeX (C#)
second_title: API Aspose.TeX .NET
description: Migliora il rendering dei documenti in .NET con Aspose.TeX. Scopri come eseguire il rendering delle figure LaTeX in SVG in C# per una perfetta integrazione delle espressioni matematiche.
weight: 11
url: /it/net/render-latex-figures/svg-latex-figure-renderer-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Rendering di figure LaTeX in SVG con Aspose.TeX (C#)

## introduzione

Se stai cercando di migliorare le capacità di rendering dei tuoi documenti in .NET utilizzando figure LaTeX, Aspose.TeX è la soluzione giusta. In questa guida passo passo ti guideremo attraverso il rendering delle figure LaTeX in SVG utilizzando Aspose.TeX in C#. Alla fine di questo tutorial, avrai una chiara comprensione del processo, che ti consentirà di incorporare senza problemi espressioni e figure matematiche di alta qualità nei tuoi documenti.

## Prerequisiti

Prima di immergerci nel tutorial, assicurati di disporre dei seguenti prerequisiti:

- Conoscenza base del linguaggio di programmazione C#.
-  Aspose.TeX per la libreria .NET installata. Puoi scaricarlo[Qui](https://releases.aspose.com/tex/net/).

## Importa spazi dei nomi

Nel codice C#, assicurati di importare gli spazi dei nomi necessari:

```csharp
using Aspose.TeX.Features;
```

Ora suddividiamo il tutorial in più passaggi:

## Passaggio 1: crea opzioni di rendering

```csharp
FigureRendererOptions options = new SvgFigureRendererOptions();
options.Preamble = "\\usepackage{pict2e}";
options.Scale = 3000;
options.BackgroundColor = Color.White;
options.LogStream = new System.IO.MemoryStream();
options.ShowTerminal = true;
```

Qui impostiamo le opzioni di rendering, specificando il preambolo, il fattore di scala, il colore di sfondo, il flusso di registro e se mostrare l'output del terminale.

## Passaggio 2: definire le dimensioni e il flusso di output

```csharp
SizeF size = new SizeF();
using (Stream stream = File.Open(Path.Combine("Your Output Directory", "text-and-formula.svg"), FileMode.Create))
{
    // Esegui il rendering.
    new SvgFigureRenderer().Render("Your LaTeX Code", stream, options, out size);
}
```

Sostituisci "La tua directory di output" con la directory desiderata e fornisci il codice LaTeX come stringa.

## Passaggio 3: visualizzare i risultati

```csharp
Console.Out.WriteLine(options.ErrorReport);
Console.Out.WriteLine();
Console.Out.WriteLine("Size: " + size);
```

Questo passaggio visualizza eventuali segnalazioni di errori e la dimensione dell'immagine risultante.

## Conclusione

Congratulazioni! Hai imparato con successo come eseguire il rendering delle figure LaTeX in SVG utilizzando Aspose.TeX in C#. Ora puoi integrare perfettamente espressioni e figure matematiche nelle tue applicazioni .NET.

## Domande frequenti

### Q1: Aspose.TeX è gratuito?

 A1: Aspose.TeX offre una prova gratuita. Puoi accedervi[Qui](https://releases.aspose.com/).

### Q2: Dove posso trovare la documentazione Aspose.TeX?

 A2: Fare riferimento alla documentazione[Qui](https://reference.aspose.com/tex/net/).

### Q3: Come posso ottenere supporto per Aspose.TeX?

 R3: Visita il forum di supporto[Qui](https://forum.aspose.com/c/tex/47).

### Q4: Posso acquistare Aspose.TeX?

 R4: Sì, puoi acquistare Aspose.TeX[Qui](https://purchase.aspose.com/buy).

### Q5: Ho bisogno di una licenza temporanea?

 R5: Se necessario, è possibile ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
