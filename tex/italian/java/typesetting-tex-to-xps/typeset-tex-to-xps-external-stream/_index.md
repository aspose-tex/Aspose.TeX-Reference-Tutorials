---
date: 2026-02-20
description: Scopri come convertire TeX in XPS in Java usando Aspose.TeX. Questa guida
  passo‑passo ti mostra come convertire i file TeX e generare flussi di documenti
  XPS in modo efficiente.
linktitle: How to Convert TeX to XPS in Java with External Stream
second_title: Aspose.TeX Java API
title: Come convertire TeX in XPS in Java con flusso esterno
url: /it/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
weight: 10
---

.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come Convertire TeX in XPS in Java con Stream Esterno

## Introduzione

Se hai bisogno di **convertire file TeX** in output XPS di alta qualità da un'applicazione Java, Aspose.TeX per Java rende il lavoro semplice. In questo tutorial vedrai esattamente **come convertire TeX** in un documento XPS utilizzando uno stream di output esterno, ideale quando vuoi inviare il risultato direttamente a una risposta, a un servizio di storage cloud o a qualsiasi destinazione personalizzata. Cammineremo attraverso l'intero processo, dalla configurazione dell'ambiente alla scrittura del file XPS finale.

## Risposte Rapide
- **Cosa copre questo tutorial?** Conversione di TeX in XPS usando Aspose.TeX con uno stream esterno.  
- **Quale libreria principale è necessaria?** Aspose.TeX per Java.  
- **È necessaria una licenza?** È richiesta una licenza temporanea o completa per l'uso in produzione.  
- **Posso generare stream di documenti XPS?** Sì – l'esempio scrive l'XPS direttamente su un `OutputStream`.  
- **Quale versione di Java è supportata?** Qualsiasi JDK 8+ (il tutorial usa JDK 11 come riferimento).

## Come Convertire TeX in XPS Utilizzando uno Stream Esterno

Questa sezione ripete la parola chiave principale in un'intestazione dedicata, facilitando la ricerca della soluzione esatta da parte dei lettori e dei motori AI.

## Prerequisiti

Prima di immergerti nel codice, assicurati di avere quanto segue:

- Java Development Kit (JDK): Assicurati di avere Java installato sul tuo sistema. Puoi scaricarlo da [here](https://www.oracle.com/java/technologies/javase-downloads.html).

- Aspose.TeX per Java: Scarica e installa Aspose.TeX per Java. Puoi trovare il link per il download [here](https://releases.aspose.com/tex/java/).

## Importare Pacchetti

Inizia importando i pacchetti necessari per avviare il tuo percorso di conversione da TeX a XPS. Includi il seguente frammento di codice nel tuo progetto Java:

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

## Passo 1: Configurare le Opzioni di Conversione

Crea le opzioni di conversione per il formato predefinito ObjectTeX usando il codice seguente:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

Questo imposta le basi per il processo di composizione.

## Passo 2: Specificare il Nome del Job e le Directory

Definisci un nome per il job e imposta le directory di lavoro di input e output:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Assicurati di sostituire i segnaposto come "Your Input Directory" con i percorsi delle tue directory effettive.

## Passo 3: Configurare l'Output del Terminale

Specifica che l'output del terminale debba essere scritto in un file nella directory di lavoro di output:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

Questo passaggio garantisce che i log dettagliati vengano catturati per il debug.

## Passo 4: Aprire lo Stream di Output

Apri uno stream per scrivere il documento XPS tipografato:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

Sostituisci "Your Output Directory" con il percorso appropriato.

## Passo 5: Eseguire il Job

Esegui il job di conversione da TeX a XPS:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

Questo completa il processo e troverai il documento XPS generato nella directory di output specificata.

## Perché Questo è Importante

Utilizzare un `OutputStream` esterno ti dà il pieno controllo su dove vanno i dati XPS—che tu li stia inviando direttamente a un client web, memorizzandoli in cloud, o concatenandoli in un altro pipeline di elaborazione. Elimina la necessità di file intermedi e riduce il sovraccarico I/O, particolarmente prezioso in ambienti ad alto throughput o serverless.

## Problemi Comuni e Soluzioni

| Problema | Perché Accade | Come Risolvere |
|----------|----------------|----------------|
| **FileNotFoundException** durante l'apertura dello stream | Il percorso della directory di output è errato o non esiste. | Verifica il percorso, crea la directory in anticipo, oppure usa `Files.createDirectories`. |
| **NullPointerException** su `options.getOutputWorkingDirectory()` | `setOutputWorkingDirectory` non è stato chiamato o ha restituito `null`. | Assicurati di chiamare `options.setOutputWorkingDirectory` prima di usarlo. |
| **LicenseException** a runtime | Esecuzione senza una licenza valida di Aspose.TeX. | Applica una licenza temporanea o permanente usando `License license = new License(); license.setLicense("Aspose.TeX.lic");`. |

## FAQ

**D: Posso usare Aspose.TeX per Java con altri formati di documento?**  
R: Aspose.TeX si concentra principalmente sull'elaborazione di documenti correlati a TeX. Per altri formati, esplora l'ampia gamma di prodotti Aspose.

**D: È disponibile una versione di prova?**  
R: Sì, puoi provare Aspose.TeX scaricando la versione di prova gratuita [here](https://releases.aspose.com/).

**D: Dove posso trovare la documentazione completa?**  
R: Consulta la documentazione [here](https://reference.aspose.com/tex/java/) per informazioni dettagliate ed esempi.

**D: Come posso ottenere supporto o assistenza?**  
R: Visita il forum Aspose.TeX [here](https://forum.aspose.com/c/tex/47) per supporto della community e discussioni.

**D: Posso ottenere una licenza temporanea per scopi di test?**  
R: Sì, puoi acquisire una licenza temporanea [here](https://purchase.aspose.com/temporary-license/).

## Conclusione

Congratulazioni! Hai appena imparato **come convertire TeX** in un documento XPS in Java usando Aspose.TeX e uno stream esterno. Questa tecnica ti dà il pieno controllo su dove va l'output XPS—che sia un file system, una risposta web o un bucket cloud. Sentiti libero di sperimentare con diverse sorgenti TeX, regolare le `TeXOptions` per font personalizzati, o collegare lo stream a un pipeline più ampio di generazione di documenti.

---

**Ultimo Aggiornamento:** 2026-02-20  
**Testato Con:** Aspose.TeX per Java 24.11 (ultima versione al momento della scrittura)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}