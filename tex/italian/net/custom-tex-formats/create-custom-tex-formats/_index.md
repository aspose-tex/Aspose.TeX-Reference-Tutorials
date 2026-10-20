---
date: 2026-10-19
description: Scopri come eseguire la generazione di documenti tex, creare un formato
  tex personalizzato e impostare la directory di input tex utilizzando Aspose.TeX
  per .NET. Guida passo‑passo con esempi di codice e suggerimenti per la risoluzione
  dei problemi.
keywords:
- tex document generation
- create custom tex format
- set tex input directory
- custom tex macros
lastmod: 2026-10-19
linktitle: Creare formati TeX personalizzati in .NET
og_description: La generazione di documenti tex con Aspose.TeX ti consente di creare
  un formato tex personalizzato e impostare la directory di input tex in .NET. Segui
  questa guida per output XPS, PDF o PNG.
og_image_alt: Developer guide showing tex document generation using Aspose.TeX in
  .NET
og_title: Come eseguire la generazione di documenti tex con formato in .NET
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
title: Come eseguire la generazione di documenti tex con formato in .NET
url: /it/net/custom-tex-formats/create-custom-tex-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come generare documenti tex con formato in .NET

In modern .NET development, **tex document generation** è un modo potente per produrre output tipografico di alta qualità senza dipendere da installazioni esterne di LaTeX. Aspose.TeX for .NET ti offre il controllo completo: puoi **creare un formato tex personalizzato**, indicare al motore una cartella di input dedicata e esportare in XPS, PDF, PNG o altri dispositivi—tutto da codice C# semplice.

## Risposte rapide
- **Cosa significa “creare un formato tex personalizzato”?** Significa definire la tua configurazione del motore TeX e il file di formato compilato affinché il processore segua le tue macro e impostazioni.  
- **Quale libreria è necessaria?** Aspose.TeX for .NET, che supporta oltre 30 formati di input e output.  
- **Devo impostare una cartella di input tex?** Sì – usa `InputWorkingDirectory` per indicare al motore dove risiedono i file ausiliari.  
- **Quali output posso generare?** XPS, PDF, PNG, TIFF e molti altri formati di dispositivo.  
- **È necessaria una licenza per la produzione?** Una licenza valida di Aspose.TeX è obbligatoria per le distribuzioni commerciali.

## Cos’è un formato tex personalizzato?
Un formato tex personalizzato è una collezione pre‑compilata di macro e impostazioni del motore che il processore TeX carica all’avvio. Creandone uno, puoi inserire il branding aziendale, imporre standard di layout e ridurre i tempi di compilazione per documenti ricorrenti. Consente uno stile coerente in tutti i documenti generati e semplifica la manutenzione di workflow tipografici complessi.

## Perché impostare una cartella di input tex?
Impostare la **cartella di input tex** indica al motore dove trovare i file ausiliari come file di stile, font personalizzati o pacchetti macro aggiuntivi. Questo elimina gli errori “file non trovato” e mantiene ordinata la cartella del progetto. Migliora inoltre la riproducibilità della build garantendo che tutte le risorse vengano risolte da una posizione nota.

## Prerequisiti

Prima di iniziare, assicurati di avere:

1. **Aspose.TeX for .NET** – scaricalo dal [sito Aspose.TeX](https://releases.aspose.com/tex/net/).  
2. Un **ambiente di sviluppo .NET** (Visual Studio, VS Code o la .NET CLI).  
3. (Opzionale) Una licenza valida di **Aspose.TeX** per l’uso in produzione.

## Importare gli spazi dei nomi

Gli spazi dei nomi seguenti ti danno accesso alle classi core di Aspose.TeX.  
Le classi correlate a `Document` si trovano sotto `Aspose.TeX`, mentre opzioni e dispositivi sono in `Aspose.TeX.Rendering`.

La classe `Document` è l’oggetto di livello superiore che rappresenta un singolo documento TeX in memoria.  

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using Aspose.TeX.ResourceProviders;
using System.IO;
using System.Text;
```

## Passo 1: creare il provider di formato

Il `FormatProvider` indica al motore dove risiede il file di formato compilato (`customtex.fmt`). Sostituisci `"Your Output Directory"` con il percorso assoluto che contiene il tuo formato personalizzato.

`FormatProvider` è un wrapper leggero che carica il file `.fmt` una sola volta e lo riutilizza per ogni conversione, migliorando drasticamente le prestazioni per lavori batch.

```csharp
using (FormatProvider formatProvider =
    new FormatProvider(new InputFileSystemDirectory("Your Output Directory"), "customtex"))
{
```

## Passo 2: configurare le opzioni di conversione (e impostare la cartella di input tex)

Qui creiamo un’istanza di `TeXOptions`. La proprietà `InputWorkingDirectory` **imposta la cartella di input tex** così il motore può trovare tutti i file di supporto, come pacchetti personalizzati o font.

`TeXOptions` consente anche di specificare il dispositivo di output, la dimensione della pagina e la qualità di rendering. Per generazioni su larga scala, puoi abilitare `EnableParallelProcessing` per velocizzare il rendering su server multi‑core.

```csharp
    TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX(formatProvider));
    options.JobName = "typeset-with-custom-format";
    options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
    options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

## Passo 3: eseguire il lavoro

Ora fornisci una semplice stringa TeX al motore, scegli un dispositivo di output (XPS in questo esempio) ed esegui il lavoro. Il `TeXEngine` legge il formato personalizzato, elabora la sorgente e scrive il risultato sul dispositivo selezionato.

`TeXEngine` è il processore core di Aspose.TeX che analizza la sorgente TeX, applica il formato personalizzato e trasmette le pagine renderizzate al dispositivo specificato.

```csharp
    new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
        "Congratulations! You have successfully typeset this text with your own TeX format!\\end")),
        new XpsDevice(), options).Run();
```

## Passo 4: rifinire l’output del terminale

Aggiungere una riga vuota dopo il completamento del lavoro rende i log della console più leggibili, soprattutto quando si concatenano più conversioni in uno script.

`Console.WriteLine()` scrive una riga di testo sullo stream di output standard. È usato qui solo per separazione visiva; non influisce sul documento generato.

```csharp
    options.TerminalOut.Writer.WriteLine();
}
// ExEnd:TypesetWithCustomTeXFormat
```

Congratulazioni! Hai ora **creato un formato tex personalizzato** e lo hai usato per **generare documenti tex** in .NET. Puoi sostituire `XpsDevice` con `PdfDevice`, `PngDevice` o qualsiasi altro dispositivo supportato per soddisfare le tue esigenze di distribuzione.

## Problemi comuni e soluzioni

| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| *“Format file not found”* | Percorso errato in `FormatProvider` | Verifica che `"Your Output Directory"` contenga `customtex.fmt` e che il percorso sia assoluto o correttamente relativo all’eseguibile. |
| *“Cannot find input file”* | `InputWorkingDirectory` punta a una cartella sbagliata | Assicurati che `"Your Input Directory"` contenga il file sorgente TeX o che tu stia passando la sorgente come stream (come nell’esempio). |
| *Output del terminale illeggibile* | Mismatch di codifica | Usa `Encoding.UTF8` se la tua sorgente TeX contiene caratteri non ASCII. |
| *Il file XPS è vuoto* | Il lavoro non è stato eseguito a causa di un’eccezione precedente | Controlla la console per messaggi di errore; spesso indicano pacchetti mancanti o errori di sintassi nella stringa TeX. |

## Domande frequenti

**D1: Posso usare Aspose.TeX for .NET con altre librerie Aspose?**  
R: Sì, Aspose.TeX si integra perfettamente con Aspose.PDF, Aspose.Words e altri prodotti Aspose per pipeline documentali end‑to‑end.

**D2: È disponibile una versione di prova gratuita per Aspose.TeX for .NET?**  
R: Sì, puoi scaricare una trial dalla **pagina di download della prova gratuita di Aspose.TeX** (https://releases.aspose.com/tex/net/).

**D3: Come posso ottenere supporto per Aspose.TeX for .NET?**  
R: Visita il [forum Aspose.TeX](https://forum.aspose.com/c/tex/47) per assistenza della community o esplora le opzioni premium nella **pagina di acquisto del supporto premium** (https://purchase.aspose.com/buy).

**D4: Sono disponibili licenze temporanee per Aspose.TeX for .NET?**  
R: Sì, richiedine una nella **pagina di richiesta licenza temporanea** (https://purchase.aspose.com/temporary-license/).

**D5: Dove posso trovare la documentazione API ufficiale?**  
R: La documentazione completa è ospitata nella **documentazione di riferimento API** (https://reference.aspose.com/tex/net/).

### Domande aggiuntive

**D: Posso generare PDF invece di XPS?**  
R: Assolutamente. Sostituisci `new XpsDevice()` con `new PdfDevice()` e adatta il percorso di output di conseguenza.

**D: Devo ricompilare il file di formato dopo ogni modifica?**  
R: Sì. Qualsiasi modifica a macro o impostazioni del motore richiede di rieseguire `tex -ini` per generare un nuovo file `.fmt`.

## Conclusione

Aspose.TeX for .NET offre una **soluzione robusta e ad alte prestazioni per la generazione di documenti tex**, consentendoti di **creare un formato tex personalizzato**, impostare la **cartella di input tex** e esportare verso qualsiasi dispositivo supportato. Integra i passaggi sopra nel tuo pipeline CI/CD, automatizza la generazione di report su larga scala o costruisci un motore di pubblicazione personalizzato che rispetti gli standard di branding della tua organizzazione.

---

**Ultimo aggiornamento:** 2026-10-19  
**Testato con:** Aspose.TeX 24.11 for .NET  
**Autore:** Aspose

## Tutorial correlati

- [Ottieni lo stream del file TeX (C#) usando Aspose.TeX API – Cartella di input richiesta](/tex/net/advanced-io/required-input-directory-csharp/)
- [Come creare PDF con Aspose.TeX for .NET – Passo dopo passo](/tex/net/pdf-output/)
- [Come creare documento XPS .NET – Converti TeX in output XPS con Aspose.TeX for .NET](/tex/net/xps-output/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}