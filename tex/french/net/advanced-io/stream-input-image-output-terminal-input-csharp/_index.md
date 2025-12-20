---
date: 2025-12-20
description: Apprenez comment convertir TeX en PNG en utilisant Aspose.TeX pour C#.
  Ce guide vous montre comment générer une image à partir de TeX, gérer les flux et
  capturer l'entrée du terminal.
linktitle: Convert TeX to PNG – Master Streams, Images, & Terminal Input in Aspose.TeX
  for C#
second_title: Aspose.TeX .NET API
title: Convertir TeX en PNG – Maîtriser les flux, les images et l'entrée du terminal
  dans Aspose.TeX pour C#
url: /fr/net/advanced-io/stream-input-image-output-terminal-input-csharp/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertir TeX en PNG – Maîtriser les flux, les images et l'entrée du terminal avec Aspose.TeX pour C#

## Introduction

Dans ce tutoriel complet, vous apprendrez **comment convertir TeX en PNG** avec Aspose.TeX pour C#. Que vous ayez besoin de **générer une image à partir de TeX** pour des rapports, des aperçus web ou des pipelines de documents automatisés, ce guide vous montre comment gérer les flux, les images et capturer l'entrée du terminal — le tout dans un exemple simple et facile à suivre.

## Quick Answers
- **Que fait Aspose.TeX ?** Il analyse le code source TeX et le rend dans divers formats, dont le PNG.  
- **Puis‑je convertir TeX en PNG sans écrire de fichiers sur le disque ?** Oui – vous pouvez fournir le TeX via un `MemoryStream` et capturer directement les octets PNG.  
- **Quelles versions de .NET sont prises en charge ?** Toutes les versions modernes de .NET (Framework 4.6+, .NET Core 3.1+, .NET 5/6).  
- **Ai‑je besoin d’une licence pour une utilisation en production ?** Une licence commerciale est requise pour la production ; un essai gratuit est disponible.  
- **Quelle résolution d’image puis‑je définir ?** La propriété `PngSaveOptions.Resolution` vous permet de spécifier le DPI (par ex., 300 dpi).

## What is “convert tex to png”?

Convertir TeX en PNG consiste à prendre une chaîne de balisage TeX (le langage utilisé pour les documents scientifiques) et à la rendre sous forme d’image raster. Cela est utile lorsque vous souhaitez intégrer des formules mathématiques ou des pages TeX complètes dans des pages web, des applications mobiles ou tout environnement qui ne peut pas rendre TeX nativement.

## Why generate image from TeX with Aspose.TeX?

- **Aucune dépendance externe** – Aspose.TeX est une bibliothèque pure‑.NET, vous n’avez donc pas besoin d’une distribution TeX sur le serveur.  
- **API adaptée aux flux** – Fonctionne directement avec `MemoryStream`, ce qui la rend idéale pour les services cloud et les micro‑services.  
- **Contrôle fin** – Vous pouvez définir la résolution de l’image, les répertoires de sortie, et même capturer l’entrée interactive du terminal.  

## Prerequisites

Avant de plonger dans le code, assurez‑vous d’avoir :

- Des connaissances de base en C#.  
- Aspose.TeX pour .NET installé – vous pouvez le télécharger **[ici](https://releases.aspose.com/tex/net/)**.  
- Un environnement de développement C# (Visual Studio, VS Code, Rider, etc.).  

## Import Namespaces

Add the required `using` statements at the top of your C# file so you can access Aspose.TeX classes:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Image;
using System.IO;
using System.Text;
```

## Step 1: Set Up Conversion Options

Configure the conversion pipeline. Here we tell Aspose.TeX to treat the application as a console app, specify input/output folders, route terminal I/O, and request PNG output at 300 dpi.

```csharp
// ExStart:TakeMainInputFromStream-AuxFromFileSystem-TakeTerminalInputFromConsole-AlternativeImagesStorage
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
options.JobName = "stream-in-image-out";
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
options.TerminalIn = new InputConsoleTerminal();
options.TerminalOut = new OutputConsoleTerminal();
options.SaveOptions = new PngSaveOptions() { Resolution = 300 };
```

## Step 2: Create Image Device and Run the Job

The `ImageDevice` captures the rendered PNG data. We feed a simple TeX snippet via a `MemoryStream`, run the job, and let Aspose.TeX do the heavy lifting.

```csharp
ImageDevice device = new ImageDevice();
TeXJob job = new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
    "\\hrule height 10pt width 95pt\\vskip10pt\\hrule height 5pt")),
    device, options);
job.Run();
```

## Step 3: Provide Input in the Console

When the console prompts, type **ABC**, press **Enter**, then type **\end** and press **Enter** again. This demonstrates how terminal input can be captured while the TeX engine is running.

## Step 4: Fine‑Tune Output

After the job finishes, you can write a line break to the console and retrieve the raw PNG bytes from the device. The `result` array holds one PNG image per page.

```csharp
options.TerminalOut.Writer.WriteLine();
byte[][] result = device.Result;
// ExEnd:TakeMainInputFromStream-AuxFromFileSystem-TakeTerminalInputFromConsole-AlternativeImagesStorage
```

You can now save `result[0]` to a file, send it over a network, or embed it directly into a UI component.

## Common Issues and Solutions

| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| **Pas de sortie PNG** | `SaveOptions` non défini ou résolution à zéro. | Assurez‑vous que `options.SaveOptions = new PngSaveOptions() { Resolution = 300 };` |
| **La console se bloque** | L’entrée TeX ne reçoit jamais `\end`. | Terminez toujours le flux TeX avec `\end` (ou `\stop`). |
| **Taille d’image incorrecte** | DPI par défaut est 96. | Augmentez `Resolution` dans `PngSaveOptions`. |
| **Chemins du système de fichiers introuvables** | Chaînes de répertoire de travail incorrectes. | Utilisez des chemins absolus ou vérifiez que les répertoires existent avant l’exécution. |

## Frequently Asked Questions

### Q1: Can I use Aspose.TeX for .NET in a non‑console application?

**R1:** Absolument ! Aspose.TeX fonctionne dans les applications de bureau, web et orientées services. Il suffit de remplacer les terminaux console par des flux personnalisés ou des contrôles UI.

### Q2: How can I customize the output image resolution?

**R2:** Dans l’exemple, la résolution est définie via `PngSaveOptions.Resolution`. Modifiez la valeur entière (par ex., `Resolution = 600`) pour obtenir des PNG de meilleure qualité.

### Q3: Is there a trial version available?

**R3:** Oui, vous pouvez explorer Aspose.TeX avec un essai gratuit disponible **[ici](https://releases.aspose.com/)**.

### Q4: Where can I find additional support and assistance?

**R4:** Consultez le forum Aspose.TeX **[ici](https://forum.aspose.com/c/tex/47)** pour le support communautaire et les discussions.

### Q5: How can I obtain a temporary license for Aspose.TeX?

**R5:** Vous pouvez obtenir une licence temporaire **[ici](https://purchase.aspose.com/temporary-license/)**.

## Conclusion

Vous avez maintenant vu comment **convertir TeX en PNG** en utilisant Aspose.TeX pour C#. En configurant les flux, en créant un `ImageDevice` et en gérant l’entrée du terminal, vous pouvez générer des images haute résolution à partir de n’importe quelle source TeX — idéal pour les rapports, les aperçus web ou les pipelines automatisés. Explorez davantage en expérimentant différents extraits TeX, en ajustant le DPI, ou en intégrant le tableau d’octets dans votre propre interface.

**Dernière mise à jour :** 2025-12-20  
**Testé avec :** Aspose.TeX 24.11 for .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}