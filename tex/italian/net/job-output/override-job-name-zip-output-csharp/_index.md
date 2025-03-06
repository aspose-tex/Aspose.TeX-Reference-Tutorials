---
title: Sostituisci il nome del lavoro e scrivi l'output del terminale su Zip (C#)
linktitle: Sostituisci il nome del lavoro e scrivi l'output del terminale su Zip (C#)
second_title: API Aspose.TeX .NET
description: Scopri come sovrascrivere i nomi dei lavori e scrivere l'output del terminale in un file ZIP utilizzando Aspose.TeX per .NET. Guida dettagliata con esempi in C#.
weight: 11
url: /it/net/job-output/override-job-name-zip-output-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Sostituisci il nome del lavoro e scrivi l'output del terminale su Zip (C#)

## introduzione

In questo tutorial, esploreremo come sovrascrivere il nome del lavoro e scrivere l'output del terminale in un file ZIP utilizzando Aspose.TeX per .NET. Aspose.TeX è una potente libreria che consente agli sviluppatori di lavorare con documenti TeX nelle loro applicazioni .NET. In questo esempio particolare, ci concentreremo su un'attività comune: scrivere l'output del terminale in un file ZIP con la possibilità di sovrascrivere il nome del lavoro.

## Prerequisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

- Una conoscenza pratica di C#
- Aspose.TeX per .NET installato
- Inserisci l'archivio ZIP per la directory di lavoro
- Archivio ZIP di output per l'output del terminale

## Importa spazi dei nomi

Prima di immergerti nel codice, assicurati di includere gli spazi dei nomi necessari nel tuo progetto C#:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Pdf;
using System.IO;
```

Ora suddividiamo l'esempio in più passaggi per guidarti attraverso il processo.

## Passaggio 1: aprire i flussi ZIP di input e output

```csharp
using (Stream inZipStream = File.Open(Path.Combine("Your Input Directory", "zip-in.zip"), FileMode.Open))
using (Stream outZipStream = File.Open(Path.Combine("Your Output Directory", "terminal-out-to-zip.zip"), FileMode.Create))
{
    // Il codice per il passaggio 1 va qui
}
```

## Passaggio 2: imposta le opzioni di conversione

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
options.JobName = "terminal-output-to-zip";
options.InputWorkingDirectory = new InputZipDirectory(inZipStream, "in");
options.OutputWorkingDirectory = new OutputZipDirectory(outZipStream);
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## Passaggio 3: definire le opzioni di salvataggio

```csharp
options.SaveOptions = new PdfSaveOptions();
```

## Passaggio 4: esegui il lavoro TeX

```csharp
new TeXJob("hello-world", new PdfDevice(), options).Run();
```

## Passaggio 5: finalizzare l'archivio ZIP di output

```csharp
((OutputZipDirectory)options.OutputWorkingDirectory).Finish();
```

## Conclusione

Congratulazioni! Hai imparato con successo come sovrascrivere il nome del lavoro e scrivere l'output del terminale in un file ZIP utilizzando Aspose.TeX per .NET. Questa tecnica può essere incredibilmente utile quando si gestiscono documenti TeX nelle applicazioni C#.

## Domande frequenti

### Q1: Posso utilizzare Aspose.TeX per .NET con altri linguaggi .NET come VB.NET?

A1: Sì, Aspose.TeX per .NET è compatibile con tutti i linguaggi .NET.

### Q2: Dove posso trovare ulteriore documentazione per Aspose.TeX per .NET?

 A2: Visita il[documentazione](https://reference.aspose.com/tex/net/) per informazioni dettagliate.

### Q3: Come posso ottenere una licenza temporanea per Aspose.TeX?

 A3: Ottieni a[licenza temporanea](https://purchase.aspose.com/temporary-license/) a scopo di test.

### Q4: Esiste un forum della comunità per il supporto di Aspose.TeX?

 A4: Sì, unisciti a[Forum Aspose.TeX](https://forum.aspose.com/c/tex/47) per il sostegno della comunità.

### Q5: Dove posso acquistare Aspose.TeX per .NET?

 A5: È possibile acquistare Aspose.TeX[Qui](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
