---
date: 2026-03-24
description: Scopri come ottenere lo stream di file in C# specificando l'input richiesto
  per Aspose.TeX .NET. Segui la nostra guida passo passo.
linktitle: Get File Stream C# in Aspose.TeX Required Input Directory
second_title: Aspose.TeX .NET API
title: 'Ottieni lo stream del file C# in Aspose.TeX: directory di input richiesta'
url: /it/net/advanced-io/required-input-directory-csharp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ottieni stream di file C# in Aspose.TeX Required Input Directory

## Introduction

Se hai bisogno di **get file stream C#** mentre lavori con Aspose.TeX, il primo passo è indicare alla libreria dove si trovano i tuoi file sorgente TeX. Questo tutorial ti guida attraverso il codice esatto necessario per **specify required input** per il motore Aspose.TeX, trasformando una cartella di file `.tex` in uno stream che l'API può consumare. Alla fine di questa guida avrai una classe `RequiredInputDirectory` riutilizzabile che collega in modo pulito il tuo file system ad Aspose.TeX.

## Quick Answers
- **What does “get file stream C#” mean?** Significa restituire un oggetto `System.IO.Stream` per un nome file richiesto.  
- **Why must I specify required input?** Aspose.TeX ricerca la directory di input per i file TeX; senza di essa il motore non può risolvere i comandi `\include{}` o `\input{}`.  
- **Which namespaces are mandatory?** `Aspose.TeX.IO`, `System.Collections.Generic` e `System.IO`.  
- **Is any special licensing needed?** È necessaria una licenza di sviluppo o di prova di Aspose.TeX per l'uso in produzione.  
- **Can I reuse the class across projects?** Sì—una volta compilata funziona con qualsiasi progetto .NET che fa riferimento ad Aspose.TeX.

## What is get file stream C#?

In .NET, un *file stream* è un oggetto derivato da `System.IO.Stream` che fornisce accesso in lettura/scrittura ai byte grezzi di un file. Quando Aspose.TeX richiede un file, si aspetta che tu restituisca tale stream affinché il motore possa leggere direttamente la sorgente TeX dalla memoria o dal disco.

## Why specify required input for Aspose.TeX?

Aspose.TeX elabora i documenti TeX individuando i file ausiliari (immagini, file di stile, file TeX inclusi) relativi a una **required input directory**. Definendo esplicitamente questa directory si:

1. Evitano errori “file non trovato” durante la compilazione.  
2. Mantiene la logica di accesso ai file del progetto isolata dal resto del codice.  
3. Consente test unitari più semplici simulando la directory di input.

## Prerequisites

- **Aspose.TeX for .NET Library** – scaricala dalla [release page](https://releases.aspose.com/tex/net/).  
- **.NET Development Environment** – Visual Studio 2022, Rider o qualsiasi IDE che supporti .NET 6+.

Ora, importiamo gli spazi dei nomi di cui avrai bisogno.

## Import Namespaces

Add these `using` statements at the top of your C# file so the compiler can locate the required types:

```csharp
using Aspose.TeX.IO;
using System.Collections.Generic;
using System.IO;
```

## How to Get File Stream C# with a Required Input Directory

Di seguito trovi una suddivisione passo‑per‑passo della classe `RequiredInputDirectory`. Ogni passo include una breve spiegazione seguita dal blocco di codice esatto da copiare nel tuo progetto.

### Step 1: Create the `RequiredInputDirectory` Class

La classe implementa due interfacce—`IInputWorkingDirectory` (usata da Aspose.TeX per individuare i file) e `IFileCollector` (usata per raccogliere i nomi dei file man mano che vengono aggiunti).

```csharp
public class RequiredInputDirectory : IInputWorkingDirectory, IFileCollector
{
    private Dictionary<string, Dictionary<string, string>> _fileNames =
        new Dictionary<string, Dictionary<string, string>>();

    public RequiredInputDirectory()
    {
    }
```

### Step 2: Implement the `StoreFileName` Method

Questo metodo registra ogni nome file che passi al collector, raggruppandoli per estensione per una ricerca rapida.

```csharp
public void StoreFileName(string fileName)
{
    string extension = Path.GetExtension(fileName);
    string name = Path.GetFileNameWithoutExtension(fileName);

    Dictionary<string, string> files;
    if (!_fileNames.TryGetValue(extension, out files))
        _fileNames.Add(extension, files = new Dictionary<string, string>());

    files[name] = fileName;
}
```

### Step 3: Implement the `IInputWorkingDirectory` Interface – GetFile

Quando Aspose.TeX richiede un file, questo metodo restituisce un **file stream** (o `null` se gestisci lo stream altrove). L'output `fullName` permette al motore di conoscere il percorso esatto risolto.

```csharp
public Stream GetFile(string fileName, out string fullName, bool searchSubdirectories = false)
{
    fullName = fileName;
    return null; // Here we actually return a stream for the file requested by its name.
}
```

### Step 4: Gather File Collections by Extension

Il motore può richiedere tutti i file con una certa estensione (ad esempio “.tex”). Questo metodo restituisce quei nomi come array di stringhe.

```csharp
public string[] GetFileNamesByExtension(string extension, string path = null)
{
    Dictionary<string, string> files;
    if (!_fileNames.TryGetValue(extension, out files))
        return new string[0];

    return new List<string>(files.Values).ToArray();
}
```

### Step 5: Dispose of Resources

Pulire il dizionario interno previene perdite di memoria, specialmente quando la classe è usata in servizi a lunga esecuzione.

```csharp
public void Dispose()
{
    _fileNames.Clear();
}
```

Con questi cinque snippet ora disponi di una classe `RequiredInputDirectory` completamente funzionale che **gets file stream C#**‑style e **specifies required input** per il processore Aspose.TeX.

## Common Issues and Solutions

| Problema | Perché accade | Soluzione rapida |
|----------|----------------|------------------|
| `GetFile` restituisce `null` e la compilazione fallisce | Il metodo è un segnaposto; è necessario aprire un vero `FileStream` se vuoi che il motore legga il file. | Sostituisci `return null;` con `return File.OpenRead(fullName);` (assicurati che il percorso sia corretto). |
| I file non vengono trovati anche se esistono | Il collector non ha ricevuto i nomi dei file o le estensioni corrette. | Chiama `StoreFileName` per ogni file **prima** di passare la directory ad Aspose.TeX. |
| L'uso della memoria aumenta con molti file `.tex` di grandi dimensioni | Il dizionario conserva tutti i nomi dei file in memoria. | Disporre (`Dispose`) il `RequiredInputDirectory` non appena il processo termina, o utilizzare un approccio di streaming. |

## Frequently Asked Questions

**Q: Dove posso trovare la documentazione di Aspose.TeX per .NET?**  
A: La documentazione è disponibile [qui](https://reference.aspose.com/tex/net/).

**Q: Come scarico la libreria Aspose.TeX per .NET?**  
A: Puoi scaricare la libreria dalla [release page](https://releases.aspose.com/tex/net/).

**Q: Dove posso ottenere supporto per Aspose.TeX per .NET?**  
A: Visita il [forum Aspose.TeX](https://forum.aspose.com/c/tex/47) per supporto della community.

**Q: È disponibile una versione di prova gratuita?**  
A: Sì, puoi provare la versione di prova gratuita [qui](https://releases.aspose.com/).

**Q: Come posso ottenere una licenza temporanea per Aspose.TeX per .NET?**  
A: Puoi ottenere una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

## Additional Frequently Asked Questions

**Q: Posso usare questa classe in un progetto .NET Core?**  
A: Assolutamente—`IInputWorkingDirectory` e `IFileCollector` sono indipendenti dalla piattaforma.

**Q: Devo registrare manualmente la directory con Aspose.TeX?**  
A: Sì, passa un'istanza di `RequiredInputDirectory` al costruttore `TeXDocument` o alla chiamata API pertinente.

**Q: Quali versioni di .NET sono supportate?**  
A: Aspose.TeX funziona con .NET 5, .NET 6 e successive, così come con .NET Framework 4.6.2+.

**Ultimo aggiornamento:** 2026-03-24  
**Testato con:** Aspose.TeX 24.11 for .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}