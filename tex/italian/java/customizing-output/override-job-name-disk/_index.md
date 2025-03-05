---
title: Sostituisci il nome del lavoro e scrivi l'output del terminale in Java
linktitle: Sostituisci il nome del lavoro e scrivi l'output del terminale in Java
second_title: API Java Aspose.TeX
description: Esplora la guida passo passo sulla sovrascrittura dei nomi dei lavori e sulla scrittura dell'output del terminale utilizzando Aspose.TeX per Java. Migliora l'elaborazione dei tuoi documenti con potenti opzioni di personalizzazione.
type: docs
weight: 10
url: /it/java/customizing-output/override-job-name-disk/
---
## introduzione

Aspose.TeX per Java fornisce potenti funzionalità per lavorare con i file TeX, consentendo agli sviluppatori di manipolare e personalizzare l'elaborazione dei documenti TeX. In questo tutorial, ti guideremo attraverso il processo di sovrascrittura del nome del lavoro e di scrittura dell'output del terminale nel file system utilizzando Aspose.TeX in Java.

## Prerequisiti

Prima di immergerci nel tutorial, assicurati di disporre dei seguenti prerequisiti:

- Una conoscenza pratica della programmazione Java.
-  Aspose.TeX per Java installato. Puoi scaricarlo da[Documentazione Java di Aspose.TeX](https://reference.aspose.com/tex/java/).

## Importa pacchetti

Per iniziare, importa i pacchetti necessari nel tuo progetto Java. Nel file Java, includi le seguenti importazioni:

```java
package com.aspose.tex.OverridenJobNameAndTerminalOutputWrittenToDisk;

import java.io.IOException;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

## Sostituisci il nome del lavoro e scrivi l'output del terminale

### Passaggio 1: crea opzioni di conversione

Inizia creando opzioni di conversione per il formato ObjectTeX predefinito sull'estensione del motore ObjectTeX. Utilizza il seguente snippet di codice:

```java
//ExStart:OverrideJobName-WriteTerminalOutputToFileSystem
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

### Passaggio 2: specificare il nome del lavoro e le directory di lavoro

Specificare un nome lavoro, una directory di lavoro di input e una directory di lavoro di output. Se il nome del lavoro non è specificato, il primo argomento del costruttore TeXJob verrà preso come nome del lavoro. Utilizza il seguente snippet di codice:

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### Passaggio 3: scrivere l'output del terminale nel file system

 Specificare che l'output del terminale deve essere scritto in un file nella directory di lavoro di output. Il nome del file sarà`<job_name>.trm`. Aggiungi il seguente codice:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### Passaggio 4: eseguire il lavoro

Esegui il lavoro TeX utilizzando le opzioni e il nome del lavoro specificati. Ecco come puoi farlo:

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
// ExEnd:OverrideJobName-WriteTerminalOutputToFileSystem
```

Congratulazioni! Hai sovrascritto con successo il nome del lavoro e scritto l'output del terminale nel file system utilizzando Aspose.TeX in Java.

## Conclusione

In questo tutorial, abbiamo esplorato come utilizzare Aspose.TeX per Java per sovrascrivere il nome del lavoro e acquisire l'output del terminale. Queste funzionalità consentono agli sviluppatori di avere un controllo capillare sull'elaborazione dei documenti TeX, migliorando la personalizzazione e la flessibilità.

## Domande frequenti

### Q1: posso utilizzare Aspose.TeX per Java con altre librerie Java?

A1: Sì, Aspose.TeX per Java è progettato per integrarsi perfettamente con altre librerie Java per migliorare le capacità di elaborazione dei documenti.

### Q2: Dove posso trovare supporto per Aspose.TeX per Java?

 A2: Visita il[Forum Aspose.TeX](https://forum.aspose.com/c/tex/47) per il supporto della comunità e l'assistenza per eventuali problemi che potresti incontrare.

### Q3: È disponibile una prova gratuita per Aspose.TeX per Java?

 A3: Sì, puoi accedere alla versione di prova gratuita di Aspose.TeX per Java[Qui](https://releases.aspose.com/).

### Q4: Come posso ottenere una licenza temporanea per Aspose.TeX per Java?

 A4: Segui questo[collegamento](https://purchase.aspose.com/temporary-license/) ottenere una licenza temporanea per scopi di test e valutazione.

### Q5: Dove posso acquistare Aspose.TeX per Java?

 A5: Visita il[pagina di acquisto](https://purchase.aspose.com/buy) acquisire una licenza per Aspose.TeX per Java.