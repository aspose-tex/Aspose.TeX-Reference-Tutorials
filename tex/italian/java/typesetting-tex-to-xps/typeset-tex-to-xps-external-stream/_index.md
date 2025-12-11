---
date: 2025-12-11
description: Scopri come convertire TeX in XPS in Java usando Aspose.TeX. Questa guida
  passo‑passo ti mostra come generare flussi di documenti XPS in modo efficiente.
linktitle: How to Convert TeX to XPS in Java with External Stream
second_title: Aspose.TeX Java API
title: Come convertire TeX in XPS in Java con flusso esterno
url: /it/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come convertire TeX in XPS in Java con flusso esterno

## Introduzione

Se hai bisogno di **convertire TeX** in file con output XPS di alta qualità da un'applicazione Java, Aspose.TeX per Java rende il lavoro semplice. In questo tutorial vedrai esattamente **come convertire TeX** in un documento XPS usando un flusso di output esterno, ideale quando vuoi inviare il risultato direttamente a una risposta, a un servizio di storage cloud o a qualsiasi destinazione personalizzata. Cammineremo attraverso l'intero processo, dalla configurazione dell'ambiente alla scrittura del file XPS finale.

## Risposte rapide
- **What does this tutorial cover?** Convertire TeX in XPS usando Aspose.TeX con un flusso esterno.  
- **Which primary library is required?** Aspose.TeX per Java.  
- **Do I need a license?** È necessaria una licenza temporanea o completa per l'uso in produzione.  
- **Can I generate XPS document streams?** Sì – l'esempio scrive l'XPS direttamente su un `OutputStream`.  
- **What Java version is supported?** Qualsiasi JDK 8+ (il tutorial utilizza JDK 11 come riferimento).

## Prerequisiti

Prima di immergerti nel codice, assicurati di avere quanto segue:

- Java Development Kit (JDK): Assicurati di avere Java installato sul tuo sistema. Puoi scaricarlo da [here](https://www.oracle.com/java/technologies/javase-downloads.html).

- Aspose.TeX per Java: Scarica e installa Aspose.TeX per Java. Puoi trovare il link per il download [here](https://releases.aspose.com/tex/java/).

## Importare i pacchetti

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

## Passo 1: Configurare le opzioni di conversione

Inizia creando le opzioni di conversione per il formato predefinito ObjectTeX usando il codice seguente:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

Questo imposta la base per il processo di composizione.

## Passo 2: Specificare il nome del lavoro e le directory

Definisci un nome per il lavoro e imposta le directory di lavoro di input e output:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Assicurati di sostituire i segnaposto come "Your Input Directory" con i percorsi reali delle tue directory.

## Passo 3: Configurare l'output del terminale

Specifica che l'output del terminale deve essere scritto in un file nella directory di lavoro di output:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

Questo passo garantisce che i log dettagliati vengano catturati per il debug.

## Passo 4: Aprire lo stream di output

Apri uno stream per scrivere il documento XPS composto:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

Sostituisci "Your Output Directory" con il percorso appropriato.

## Passo 5: Eseguire il lavoro

Esegui il lavoro di conversione da TeX a XPS:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

Questo completa il processo e troverai il documento XPS generato nella directory di output specificata.

## Problemi comuni e soluzioni

| Problema | Perché accade | Come risolvere |
|----------|----------------|----------------|
| **FileNotFoundException** when opening the stream | Il percorso della directory di output è errato o non esiste. | Verifica il percorso, crea la directory in anticipo, o usa `Files.createDirectories`. |
| **NullPointerException** on `options.getOutputWorkingDirectory()` | `setOutputWorkingDirectory` non è stato chiamato o ha restituito `null`. | Assicurati di chiamare `options.setOutputWorkingDirectory` prima di usarlo. |
| **LicenseException** at runtime | Esecuzione senza una licenza valida di Aspose.TeX. | Applica una licenza temporanea o permanente usando `License license = new License(); license.setLicense("Aspose.TeX.lic");`. |

## Domande frequenti

**Q: Posso usare Aspose.TeX per Java con altri formati di documento?**  
A: Aspose.TeX si concentra principalmente sull'elaborazione di documenti correlati a TeX. Per altri formati, esplora l'ampia gamma di prodotti di Aspose.

**Q: È disponibile una versione di prova?**  
A: Sì, puoi provare Aspose.TeX scaricando la versione di prova gratuita [here](https://releases.aspose.com/).

**Q: Dove posso trovare una documentazione completa?**  
A: Consulta la documentazione [here](https://reference.aspose.com/tex/java/) per informazioni dettagliate ed esempi.

**Q: Come posso ottenere supporto o assistenza?**  
A: Visita il forum Aspose.TeX [here](https://forum.aspose.com/c/tex/47) per supporto della community e discussioni.

**Q: Posso ottenere una licenza temporanea per scopi di test?**  
A: Sì, puoi ottenere una licenza temporanea [here](https://purchase.aspose.com/temporary-license/).

## Conclusione

Congratulazioni! Hai appena imparato **come convertire TeX** in un documento XPS in Java usando Aspose.TeX e un flusso esterno. Questa tecnica ti dà il pieno controllo su dove va l'output XPS—che sia un file system, una risposta web o un bucket cloud. Sentiti libero di sperimentare con diverse sorgenti TeX, regolare le `TeXOptions` per font personalizzati, o collegare lo stream a una pipeline più ampia di generazione di documenti.

---

**Ultimo aggiornamento:** 2025-12-11  
**Testato con:** Aspose.TeX for Java 24.11 (latest at time of writing)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}