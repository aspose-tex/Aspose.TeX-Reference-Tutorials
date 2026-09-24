---
date: 2026-09-24
description: Scopri come configurare la directory di input TeX, i flussi, le immagini
  e l'input da terminale utilizzando Aspose.TeX per .NET in C#.
keywords:
- configure tex input directory
- add image stream tex
- add images from stream
lastmod: 2026-09-24
linktitle: Input e Output avanzati di Aspose.TeX
og_description: Configura la directory di input TeX, aggiungi flussi di immagini e
  gestisci l'input da terminale con Aspose.TeX per .NET in C#. Impara passo passo.
og_image_alt: Guide showing how to configure TeX input directory and streams in Aspose.TeX
  for .NET
og_title: Configura la directory di input TeX – Guida avanzata di Aspose.TeX
schemas:
- author: Aspose
  dateModified: '2026-09-24'
  description: Learn how to configure TeX input directory, streams, images, and terminal
    input using Aspose.TeX for .NET in C#.
  headline: Configure TeX input directory – Advanced Aspose.TeX Input and Output
  type: TechArticle
- description: Learn how to configure TeX input directory, streams, images, and terminal
    input using Aspose.TeX for .NET in C#.
  name: Configure TeX input directory – Advanced Aspose.TeX Input and Output
  steps:
  - name: instantiate TeXInputOptions
    text: Assign the base folder that holds the primary TeX source.
  - name: add extra search paths
    text: If your project stores figures in a separate folder (e.g., *Images*), call
      `AddSearchPath` to include it.
  - name: hand the options to the processor
    text: Create a `TeXProcessor`, provide the configured options, and invoke `Process`
      or `Render`.
  type: HowTo
- questions:
  - answer: Yes—you can create a new `TeXInputOptions` instance with a different `BaseFolder`
      and pass it to a fresh `TeXProcessor` whenever you need to reconfigure.
    question: Can I change the input directory at runtime?
  - answer: Retrieve the image as a `byte[]`, wrap it in a `MemoryStream`, and call
      `TeXInputOptions.AddImage("image.png", stream)`. The name must match the reference
      in your `.tex` file.
    question: How do I add images that are stored in a database?
  - answer: Absolutely. Convert the incoming string to a `MemoryStream`, set it as
      the source for `TeXProcessor`, and render directly to your desired output format.
    question: Is it possible to process LaTeX code received from a web API without
      saving a file?
  - answer: Dispose of any streams you create, and for large workloads invoke `TeXProcessor.Cleanup()`
      to free native resources.
    question: Do I need to call any cleanup methods after processing?
  - answer: The two tutorial links above contain full code samples that demonstrate
      each scenario in detail, including error handling and performance tips.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.TeX .NET API
tags:
- Aspose.TeX
- input directory
- C# document processing
title: Configura la directory di input TeX – Input e Output avanzati di Aspose.TeX
url: /it/net/advanced-io/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configura la directory di input TeX in Aspose.TeX per .NET

Aspose.TeX per .NET ti consente di incorporare l'elaborazione TeX completa direttamente nelle tue applicazioni C#. In questo tutorial imparerai a **configurare la directory di input TeX**, fornire contenuti LaTeX da stream e aggiungere immagini senza toccare il file system. Se hai bisogno di un controllo preciso su dove il motore cerca i file `.tex` e le risorse, sei nel posto giusto.

## Risposte rapide
- **Cosa significa “configurare la directory di input tex”?**  
  Indica ad Aspose.TeX dove trovare il file `.tex` principale, i file ausiliari e le grafiche.
- **Quale classe definisce i percorsi di input?**  
  `TeXInputOptions` memorizza la cartella base e eventuali percorsi di ricerca aggiuntivi.
- **Posso caricare un'immagine da uno stream di memoria?**  
  Sì—usa `TeXInputOptions.AddImage` con un'istanza `Stream`.
- **È possibile compilare codice LaTeX fornito a runtime?**  
  Assolutamente—passa un `MemoryStream` contenente il testo sorgente al processore.
- **Ho bisogno di una licenza per l'uso in produzione?**  
  È necessaria una licenza valida di Aspose.TeX per le distribuzioni non‑di valutazione.

## Cos'è TeXInputOptions?
`TeXInputOptions` è l'oggetto di configurazione che definisce la cartella base e i percorsi di ricerca aggiuntivi per le risorse TeX. Configurarlo correttamente elimina gli errori “file non trovato” e ti consente di mantenere gli asset organizzati.

## Come configurare la directory di input tex?
`TeXInputOptions` è un oggetto di configurazione che specifica la cartella base e i percorsi di ricerca aggiuntivi per le risorse TeX. Carica il tuo documento principale e indica al processore dove cercare tutto in poche righe. Questa risposta diretta spiega i passaggi essenziali prima di qualsiasi dettaglio aggiuntivo.

Crea un'istanza di `TeXInputOptions`, imposta `BaseFolder` sulla cartella che contiene il tuo file `.tex` principale, aggiungi eventuali sottocartelle che contengono immagini o file ausiliari e passa le opzioni a `TeXProcessor`. Il motore risolverà automaticamente tutti i riferimenti relativi.

### Passo 1: istanziare TeXInputOptions
Assegna la cartella base che contiene la sorgente TeX primaria.

### Passo 2: aggiungere percorsi di ricerca extra
Se il tuo progetto memorizza le figure in una cartella separata (ad es., *Images*), chiama `AddSearchPath` per includerla.

### Passo 3: passare le opzioni al processore
Crea un `TeXProcessor`, fornisci le opzioni configurate e invoca `Process` o `Render`.

## Come aggiungere immagini con Aspose.TeX
Le immagini referenziate in un file TeX possono essere fornite sia tramite una cartella sia direttamente da uno stream. Fornire uno stream è utile quando le immagini sono archiviate in un database o generate al volo. `AddImage(string name, Stream data)` registra uno stream di immagine con il nome file fornito per l'uso nel documento TeX. Questo metodo ti consente di evitare file temporanei e velocizza l'elaborazione.

## Come elaborare gli stream in Aspose.TeX
Quando la tua sorgente LaTeX è generata dinamicamente—ad esempio da input utente o da un servizio web—puoi inviarla direttamente al processore senza scrivere un file. `TeXProcessor` elabora contenuti TeX e può accettare un `MemoryStream` contenente il codice LaTeX sorgente. Avvolgi la stringa LaTeX in un `MemoryStream`, impostala come stream di origine in `TeXProcessor` ed esegui la conversione. Questa tecnica funziona altrettanto bene per i servizi cloud‑native dove l'I/O su disco è costoso.

## Perché usare Aspose.TeX per I/O avanzato?
Aspose.TeX supporta **oltre 30 formati di input e output** (inclusi PDF, PNG, SVG) e può renderizzare documenti di centinaia di pagine senza caricare l'intero file in memoria. Il suo design stream‑first riduce il sovraccarico I/O fino al 40 % rispetto ai flussi di lavoro basati su file, rendendolo ideale per applicazioni server ad alto throughput.

## Prerequisiti
- .NET 6.0 o versioni successive (la libreria funziona anche con .NET Core 3.1+ e .NET Framework 4.6.1+)
- Pacchetto NuGet Aspose.TeX per .NET (versione 24.11 o successiva)
- Una licenza valida di Aspose.TeX per l'uso in produzione

## Esplora Aspose.TeX: un gateway per l'elaborazione avanzata dei documenti
Per vedere la configurazione in azione, segui la nostra guida passo‑passo **[Specify Required Input Directory for Aspose.TeX (C#)](./required-input-directory-csharp/)**. Quel tutorial ti guida nella creazione dell'oggetto `TeXInputOptions` e nella generazione di un output PDF.  
**[Specify Required Input Directory for Aspose.TeX (C#)](./required-input-directory-csharp/)**

## Padronanza di stream, immagini e input da terminale in Aspose.TeX per C#
Per un approfondimento su come fornire LaTeX dalla memoria, aggiungere immagini tramite stream e utilizzare input in stile terminale, consulta **[Master Streams, Images, & Terminal Input in Aspose.TeX for C#](./stream-input-image-output-terminal-input-csharp/)**. Mostra come integrare Aspose.TeX in API web, servizi in background e strumenti da console.  
**[Master Streams, Images, & Terminal Input in Aspose.TeX for C#](./stream-input-image-output-terminal-input-csharp/)**

## Problemi comuni e soluzioni
- **Errori “File not found”** – Verifica che `BaseFolder` punti alla directory corretta e che tutti i percorsi di ricerca aggiuntivi siano aggiunti prima del rendering.
- **Immagini non caricate** – Assicurati che il nome dell'immagine in `AddImage` corrisponda esattamente al nome usato nella sorgente TeX, inclusa l'estensione del file.
- **Picchi di utilizzo della memoria** – Quando si elaborano documenti molto grandi, chiama `TeXProcessor.Cleanup()` dopo il rendering per rilasciare le risorse non gestite.

## Domande frequenti

**D: Posso cambiare la directory di input a runtime?**  
R: Sì—puoi creare una nuova istanza di `TeXInputOptions` con un `BaseFolder` diverso e passarla a un nuovo `TeXProcessor` ogni volta che è necessario riconfigurare.

**D: Come aggiungo immagini archiviate in un database?**  
R: Recupera l'immagine come `byte[]`, avvolgila in un `MemoryStream` e chiama `TeXInputOptions.AddImage("image.png", stream)`. Il nome deve corrispondere al riferimento nel tuo file `.tex`.

**D: È possibile elaborare codice LaTeX ricevuto da un'API web senza salvare un file?**  
R: Assolutamente. Converti la stringa in ingresso in un `MemoryStream`, impostala come sorgente per `TeXProcessor` e renderizza direttamente nel formato di output desiderato.

**D: Devo chiamare qualche metodo di pulizia dopo l'elaborazione?**  
R: Rilascia tutti gli stream che crei e, per carichi di lavoro elevati, invoca `TeXProcessor.Cleanup()` per liberare le risorse native.

**D: Dove posso trovare esempi più avanzati?**  
R: I due link tutorial sopra contengono esempi di codice completi che mostrano ogni scenario in dettaglio, inclusi la gestione degli errori e suggerimenti sulle prestazioni.

---

**Ultimo aggiornamento:** 2026-09-24  
**Testato con:** Aspose.TeX 24.11 per .NET  
**Autore:** Aspose

## Tutorial correlati

- [Ottieni lo stream del file TeX (C#) usando l'API Aspose.TeX (Directory di input richiesta)](/tex/net/advanced-io/required-input-directory-csharp/)
- [Crea XPS da TeX con filesystem – Aspose.TeX per .NET](/tex/net/file-input-output/filesystem-input-xps-output/)
- [Converti LaTeX in PNG usando Aspose.TeX per .NET – Elabora input da filesystem e ZIP](/tex/net/file-input-output/required-inputs-from-filesystem-and-zip/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}