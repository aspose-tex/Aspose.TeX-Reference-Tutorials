---
title: Composizione di TeX in XPS in .NET
linktitle: Composizione di TeX in XPS in .NET
second_title: API Aspose.TeX .NET
description: Converti senza sforzo documenti TeX in XPS in .NET con Aspose.TeX. Esplora la nostra guida passo passo per un'esperienza di integrazione perfetta.
weight: 10
url: /it/net/xps-output/typeset-tex-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Composizione di TeX in XPS in .NET

## introduzione

Benvenuti nella nostra guida passo passo sulla composizione di TeX in XPS in .NET utilizzando la potente libreria Aspose.TeX. Se stai cercando di convertire senza problemi documenti TeX in formato XPS nelle tue applicazioni .NET, sei nel posto giusto. In questo tutorial ti guideremo attraverso l'intero processo, suddividendo ogni passaggio per garantire un'implementazione fluida.

## Prerequisiti

Prima di immergerci nel tutorial, assicurati di disporre dei seguenti prerequisiti:

-  Aspose.TeX per .NET: assicurati di avere la libreria Aspose.TeX installata. Puoi scaricarlo[Qui](https://releases.aspose.com/tex/net/).

- Documentazione: familiarizzare con la libreria facendo riferimento alla documentazione[Qui](https://reference.aspose.com/tex/net/).

- Directory di input e output: configura le directory di input e output come specificato nel codice di esempio.

Ora che hai impostato tutto, procediamo con la guida passo passo.

## Importa spazi dei nomi

Nell'applicazione .NET iniziare importando gli spazi dei nomi necessari. Ciò garantisce l'accesso alle funzionalità Aspose.TeX richieste per la composizione di TeX su XPS.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
```

## Passaggio 1: imposta le opzioni di conversione

Definire le opzioni di conversione, specificando il formato ObjectTeX sull'estensione del motore ObjectTeX. Inoltre, impostare il nome del lavoro, le directory di input e output e i dettagli di output del terminale.

```csharp
// Crea opzioni di conversione per il formato ObjectTeX predefinito sull'estensione del motore ObjectTeX.
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
// Specificare un nome lavoro.
options.JobName = "external-file-stream";
// Specificare una directory di lavoro del file system per l'input.
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
// Specificare una directory di lavoro del file system per l'output.
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
// Specificare che l'output del terminale deve essere scritto in un file nella directory di lavoro di output.
// Il nome del file è <nome_lavoro>.trm.
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## Passaggio 2: crea un flusso di documenti XPS

Aprire un flusso per scrivere il documento XPS composto. Il nome del file non è necessariamente uguale al nome del lavoro.

```csharp
using (Stream stream = File.Open(Path.Combine("Your Output Directory", options.JobName + ".xps"), FileMode.Create))
```

## Passaggio 3: eseguire il lavoro TeX

Avvia ed esegui il lavoro TeX, specificando il nome del documento, XpsDevice e le opzioni di conversione.

```csharp
new TeXJob("hello-world", new XpsDevice(stream), options).Run();
```

Congratulazioni! Hai composto con successo TeX in XPS in .NET utilizzando Aspose.TeX. Sentiti libero di esplorare più funzionalità e opzioni in base alle tue esigenze specifiche.

## Conclusione

In questo tutorial, abbiamo coperto i passaggi essenziali per convertire senza problemi i documenti TeX in formato XPS in .NET utilizzando Aspose.TeX. Seguendo questa guida, hai acquisito preziose informazioni sulle funzionalità della libreria e su come sfruttarle per i tuoi progetti.

## Domande frequenti

### Q1: Aspose.TeX è compatibile con .NET Core?

A1: Sì, Aspose.TeX è completamente compatibile con .NET Core.

### Q2: Posso utilizzare Aspose.TeX per progetti commerciali?

A2: Assolutamente! Aspose.TeX è disponibile sia per uso commerciale che personale.

### Q3: Dove posso trovare ulteriori esempi e risorse?

 A3: Esplora la documentazione di Aspose.TeX[Qui](https://reference.aspose.com/tex/net/)per ulteriori esempi e risorse dettagliate.

### Q4: Come posso ottenere supporto per Aspose.TeX?

 R4: Visita il forum di supporto Aspose.TeX[Qui](https://forum.aspose.com/c/tex/47) per ottenere assistenza dalla comunità.

### Q5: È disponibile una prova gratuita?

 R5: Sì, puoi accedere a una prova gratuita[Qui](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
