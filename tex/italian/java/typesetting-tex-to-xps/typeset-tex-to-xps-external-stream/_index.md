---
title: Comporre TeX in XPS in Java con flusso esterno
linktitle: Comporre TeX in XPS in Java con flusso esterno
second_title: API Java Aspose.TeX
description: Scopri come comporre TeX in XPS in Java utilizzando Aspose.TeX. Esplora le indicazioni dettagliate per un'elaborazione dei documenti senza interruzioni.
weight: 10
url: /it/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comporre TeX in XPS in Java con flusso esterno

## introduzione

Nel mondo dello sviluppo Java, Aspose.TeX si distingue come un potente strumento per impaginare documenti TeX in vari formati, incluso XPS. Se stai cercando di migliorare le capacità di elaborazione dei documenti della tua applicazione Java, questo tutorial è fatto su misura per te. In questa guida passo passo, ti guideremo attraverso il processo di impaginazione di TeX su XPS utilizzando Aspose.TeX per Java con un flusso esterno.

## Prerequisiti

Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:

-  Java Development Kit (JDK): assicurati di avere Java installato sul tuo sistema. Puoi scaricarlo da[Qui](https://www.oracle.com/java/technologies/javase-downloads.html).

-  Aspose.TeX per Java: scarica e installa Aspose.TeX per Java. È possibile trovare il collegamento per il download[Qui](https://releases.aspose.com/tex/java/).

## Importa pacchetti

Inizia importando i pacchetti necessari per avviare il tuo viaggio di conversione da TeX a XPS. Includi il seguente snippet di codice nel tuo progetto Java:

```java
package com.aspose.tex.TypesetXpsWrittenToExternalStream;

import java.io.FileOutputStream;
import java.io.IOException;
import java.io.OutputStream;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

## Passaggio 1: configura le opzioni di conversione

Inizia creando opzioni di conversione per il formato ObjectTeX predefinito utilizzando il seguente codice:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

Ciò costituisce la base per il processo di impaginazione.

## Passaggio 2: specificare il nome del lavoro e le directory

Definire un nome lavoro e impostare le directory di lavoro di input e output:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Assicurati di sostituire i segnaposto come "La tua directory di input" con i percorsi di directory effettivi.

## Passaggio 3: configurare l'uscita del terminale

Specificare che l'output del terminale deve essere scritto in un file nella directory di lavoro di output:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

Questo passaggio garantisce l'acquisizione di log dettagliati per il debug.

## Passaggio 4: aprire il flusso di output

Apri un flusso per scrivere il documento XPS composto:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

Sostituisci "La tua directory di output" con il percorso appropriato.

## Passaggio 5: eseguire il lavoro

Esegui il lavoro di conversione da TeX a XPS:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

Questo completa il processo e troverai il tuo documento XPS composto nella directory di output specificata.

## Conclusione

Congratulazioni! Hai composto con successo TeX in XPS in Java utilizzando Aspose.TeX. Ciò apre un mondo di possibilità per l'elaborazione dei documenti nelle vostre applicazioni Java. Sperimenta diversi file TeX ed esplora le diverse funzionalità offerte da Aspose.TeX.

## Domande frequenti

### Q1: Posso utilizzare Aspose.TeX per Java con altri formati di documenti?

R1: Aspose.TeX si concentra principalmente sull'elaborazione dei documenti relativi a TeX. Per altri formati, esplora l'ampia gamma di prodotti Aspose.

### Q2: È disponibile una versione di prova?

 A2: Sì, puoi provare Aspose.TeX scaricando la versione di prova gratuita[Qui](https://releases.aspose.com/).

### Q3: Dove posso trovare la documentazione completa?

 R3: Fare riferimento alla documentazione[Qui](https://reference.aspose.com/tex/java/) per informazioni dettagliate ed esempi.

### Q4: Come posso ottenere supporto o chiedere assistenza?

 A4: Visita il forum Aspose.TeX[Qui](https://forum.aspose.com/c/tex/47)per il supporto e le discussioni della comunità.

### Q5: Posso ottenere una licenza temporanea a scopo di test?

 R5: Sì, puoi acquisire una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
