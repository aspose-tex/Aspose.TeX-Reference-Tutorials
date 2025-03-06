---
title: Comporre TeX in PDF in Java con flusso esterno
linktitle: Comporre TeX in PDF in Java con flusso esterno
second_title: API Java Aspose.TeX
description: Scopri come comporre TeX in PDF in Java utilizzando flussi esterni con Aspose.TeX. Segui la nostra guida passo passo per un'integrazione perfetta.
weight: 10
url: /it/java/typesetting-tex-to-pdf/typeset-tex-to-pdf-external-stream/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comporre TeX in PDF in Java con flusso esterno

## introduzione

Nel mondo dello sviluppo Java, la creazione di PDF da file TeX è un requisito comune. Aspose.TeX per Java semplifica questo processo, fornendo una soluzione efficiente per impaginare TeX in PDF. In questo tutorial ti guideremo attraverso i passaggi per impaginare TeX in PDF utilizzando flussi esterni. Alla fine, avrai una chiara comprensione di come implementare questo processo senza problemi nelle tue applicazioni Java.

## Prerequisiti

Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:

- Aspose.TeX per Java: assicurati di avere installata la libreria Aspose.TeX per Java. Puoi scaricarlo da[Aspose.TeX per la documentazione Java](https://reference.aspose.com/tex/java/).

- Directory di input e output: preparare le directory di input e output. È possibile utilizzare il collegamento per il download fornito per ottenere i file necessari.

## Importa pacchetti

Inizia importando i pacchetti richiesti nel tuo progetto Java:

```java
package com.aspose.tex.TypesetPdfWrittenToExternalStream;

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

## Passaggio 1: aprire i flussi di input e output

Inizia aprendo i flussi per l'archivio ZIP di input (che funge da directory di lavoro di input) e l'archivio ZIP di output (che funge da directory di lavoro di output). Assicurati di sostituire "La tua directory di input" e "La tua directory di output" con i percorsi effettivi delle directory.

```java
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "typeset-pdf-to-external-stream.zip");
```

## Passaggio 2: configura TeXOptions

Crea l'oggetto TeXOptions e configuralo in base alle tue esigenze. Imposta il nome del lavoro, la directory di lavoro di input, la directory di lavoro di output e altre opzioni.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("typeset-pdf-to-external-stream");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
options.setSaveOptions(new PdfSaveOptions());
```

## Passaggio 3: componi TeX in PDF

Ora apri uno stream per scrivere il PDF di output nella posizione desiderata. Puoi scegliere di scriverlo su un file locale o direttamente nell'archivio ZIP di output.

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + "file-name.pdf");
try {
    new TeXJob("hello-world", new PdfDevice(stream), options).run();
} finally {
    stream.close();
}
```

## Passaggio 4: finalizzare l'archivio ZIP di output

Completa l'archivio ZIP di output per completare il processo di composizione.

```java
((OutputZipDirectory)options.getOutputWorkingDirectory()).finish();
```

## Conclusione

Congratulazioni! Hai composto con successo TeX in PDF in Java utilizzando flussi esterni con Aspose.TeX. Questo tutorial fornisce una solida base per incorporare perfettamente la conversione da TeX a PDF nelle tue applicazioni Java.

## Domande frequenti

### Q1: Posso personalizzare il nome del file PDF di output?

 A1: Sì, puoi modificare il file`options.setJobName("typeset-pdf-to-external-stream")` per impostare il nome del lavoro desiderato.

### Q2: Come posso risolvere i problemi comuni durante la composizione?

 A2: Visita il[Forum Aspose.TeX](https://forum.aspose.com/c/tex/47) per il sostegno e l'assistenza della comunità.

### Q3: È disponibile una prova gratuita per Aspose.TeX per Java?

 R3: Sì, puoi accedere alla prova gratuita[Qui](https://releases.aspose.com/).

### Q4: Dove posso trovare documentazione ed esempi aggiuntivi?

 A4: Esplora il completo[Documentazione Aspose.TeX](https://reference.aspose.com/tex/java/) per informazioni dettagliate.

### Q5: Posso ottenere una licenza temporanea per Aspose.TeX?

 R5: Sì, puoi richiedere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
