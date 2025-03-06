---
title: Sostituisci il nome del lavoro e scrivi l'output del terminale su Zip in Java
linktitle: Sostituisci il nome del lavoro e scrivi l'output del terminale su Zip in Java
second_title: API Java Aspose.TeX
description: Scopri come sovrascrivere i nomi dei lavori e scrivere l'output del terminale su ZIP in Java con Aspose.TeX. Un tutorial completo per gli sviluppatori Java.
weight: 11
url: /it/java/customizing-output/override-job-name-zip/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Sostituisci il nome del lavoro e scrivi l'output del terminale su Zip in Java

## introduzione

Nel mondo dello sviluppo Java, Aspose.TeX si distingue come un potente strumento per gestire i formati di file TeX. In questo tutorial, approfondiremo uno scenario specifico: sovrascrivere i nomi dei lavori e scrivere l'output del terminale in un file zip. Questa guida passo passo ti guiderà attraverso il processo utilizzando Aspose.TeX per Java.

## Prerequisiti

Prima di intraprendere questo tutorial, assicurati di disporre dei seguenti prerequisiti:
- Conoscenza base della programmazione Java.
-  Aspose.TeX installato per Java. In caso contrario, puoi scaricarlo da[Sito web Aspose](https://releases.aspose.com/tex/java/).
- Una comprensione di come impostare un ambiente di sviluppo Java.

## Importa pacchetti

Inizia importando i pacchetti necessari nel tuo progetto Java. Ciò garantisce l'accesso alle funzionalità Aspose.TeX richieste per l'attività.

```java
package com.aspose.tex.OverridenJobNameAndTerminalOutputWrittenToZip;

import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.io.OutputStream;

import com.aspose.tex.InputZipDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.OutputZipDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.PdfDevice;
import com.aspose.tex.rendering.PdfSaveOptions;

import util.Utils;
```

## Passaggio 1: apri gli archivi ZIP

Innanzitutto, apri uno stream sull'archivio ZIP che fungerà da directory di lavoro di input. Questo è l'archivio da cui verranno trattati i tuoi dati.

```java
// Apri uno stream nell'archivio ZIP di input
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
```

## Passaggio 2: aprire l'archivio ZIP di output

Successivamente, apri uno stream su un archivio ZIP che fungerà da directory di lavoro di output. Qui è dove verrà scritto l'output del terminale.

```java
// Apri uno stream nell'archivio ZIP di output
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "terminal-out-to-zip.zip");
```

## Passaggio 3: imposta le opzioni di conversione

Crea opzioni di conversione per il formato ObjectTeX predefinito sull'estensione del motore ObjectTeX. Specificare un nome lavoro e le directory di lavoro dell'archivio ZIP sia per l'input che per l'output.

```java
// Crea opzioni TeX per il formato ObjectTeX
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("terminal-output-to-zip");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
```

## Passaggio 4: specificare l'output del terminale

 Specificare che l'output del terminale deve essere scritto in un file nella directory di lavoro di output. Il nome del file sarà`<job_name>.trm`.

```java
// Specificare le impostazioni di output del terminale
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

## Passaggio 5: definire le opzioni di salvataggio ed eseguire il lavoro

Definire le opzioni di salvataggio, come le opzioni di salvataggio PDF in questo caso. Esegui il lavoro TeX per eseguire la conversione.

```java
// Definire le opzioni di salvataggio ed eseguire il lavoro
options.setSaveOptions(new PdfSaveOptions());
new TeXJob("hello-world", new PdfDevice(), options).run();
```

## Passaggio 6: finalizzare l'archivio ZIP di output

Una volta completato il lavoro, finalizzare l'archivio ZIP di output per garantire il corretto completamento.

```java
// Finalizzare l'archivio ZIP di output
((OutputZipDirectory) options.getOutputWorkingDirectory()).finish();
```

## Conclusione

Congratulazioni! Hai imparato con successo come sovrascrivere i nomi dei lavori e scrivere l'output del terminale in un file ZIP in Java utilizzando Aspose.TeX. Questa potente funzionalità aggiunge flessibilità ed efficienza ai tuoi progetti di sviluppo Java.

## Domande frequenti

### Q1: Cos'è Aspose.TeX?

A1: Aspose.TeX è una libreria Java che consente agli sviluppatori di lavorare con i formati di file TeX, fornendo funzionalità avanzate per l'elaborazione dei documenti.

### Q2: Come posso ottenere una licenza temporanea per Aspose.TeX?

 A2: Puoi ottenere una licenza temporanea da[questo link](https://purchase.aspose.com/temporary-license/).

### Q3: Dove posso trovare la documentazione Aspose.TeX?

 A3: La documentazione è disponibile[Qui](https://reference.aspose.com/tex/java/).

### Q4: Esiste una versione di prova gratuita di Aspose.TeX?

 R4: Sì, puoi trovare la versione di prova gratuita[Qui](https://releases.aspose.com/).

### Q5: Dove posso chiedere supporto o porre domande su Aspose.TeX?

 A5: Visita il[Forum Aspose.TeX](https://forum.aspose.com/c/tex/47) per supporto e discussioni.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
