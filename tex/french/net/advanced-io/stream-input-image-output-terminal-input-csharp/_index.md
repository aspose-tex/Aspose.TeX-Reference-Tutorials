---
date: 2026-03-26
description: Apprenez à créer des PNG LaTeX en convertissant du TeX en PNG à l'aide
  d'Aspose.TeX pour C#. Ce guide vous montre comment générer des PNG à partir de TeX,
  gérer les flux et capturer l'entrée du terminal.
linktitle: Create latex png – Convert TeX to PNG with Aspose.TeX C#
second_title: Aspose.TeX .NET API
title: Créer un PNG LaTeX – Convertir TeX en PNG avec Aspose.TeX C#
url: /fr/net/advanced-io/stream-input-image-output-terminal-input-csharp/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer latex png – Convertir TeX en PNG avec Aspose.TeX C#

Dans ce tutoriel complet, vous allez **create latex png** à partir d’une chaîne source TeX en utilisant Aspose.TeX pour C#. Que vous ayez besoin d’intégrer des formules mathématiques dans une page web, de générer des images d’aperçu dans un service cloud, ou d’automatiser la création de rapports, nous vous guiderons à travers la gestion des flux, la configuration de la sortie d’image et la capture de l’entrée du terminal — le tout sans jamais toucher le système de fichiers.

## Réponses rapides
- **Que fait Aspose.TeX ?** Il analyse le source TeX et le rend dans divers formats, y compris PNG.  
- **Puis‑je convertir TeX en PNG sans écrire de fichiers sur le disque ?** Oui – vous pouvez alimenter TeX via un `MemoryStream` et capturer les octets PNG directement.  
- **Quelles versions de .NET sont prises en charge ?** Toutes les versions modernes de .NET (Framework 4.6+, .NET Core 3.1+, .NET 5/6).  
- **Ai‑je besoin d’une licence pour une utilisation en production ?** Une licence commerciale est requise pour la production ; un essai gratuit est disponible.  
- **Quelle résolution d’image puis‑je définir ?** La propriété `PngSaveOptions.Resolution` vous permet de spécifier le DPI (par ex., 300 dpi).

## Comment créer latex png à partir de TeX avec Aspose.TeX ?
Vous verrez ci‑dessous un exemple pas à pas qui lit un extrait TeX depuis un flux mémoire, exécute le travail de rendu, et renvoie les octets PNG. Le même modèle fonctionne pour tout document TeX que vous devez **convert tex to png**.

## Qu’est‑ce que “convert tex to png” ?

Convertir TeX en PNG consiste à prendre une chaîne de balisage TeX (le langage utilisé pour les documents scientifiques) et à la rendre sous forme d’image raster. Ceci est utile lorsque vous souhaitez intégrer des formules mathématiques ou des pages TeX complètes dans des pages web, des applications mobiles, ou tout environnement qui ne peut pas rendre TeX nativement.

## Pourquoi générer un png à partir de tex avec Aspose.TeX ?

- **Aucune dépendance externe** – Aspose.TeX est une bibliothèque pure .NET, vous n’avez donc pas besoin d’une distribution TeX sur le serveur.  
- **API adaptée aux flux** – Fonctionne directement avec `MemoryStream`, ce qui la rend idéale pour les services cloud et les micro‑services.  
- **Contrôle granulaire** – Vous pouvez définir la résolution d’image, les répertoires de sortie, et même capturer l’entrée interactive du terminal.  

## Prérequis

- Connaissances de base en C#.  
- Aspose.TeX pour .NET installé – vous pouvez le télécharger **[here](https://releases.aspose.com/tex/net/)**.  
- Un environnement de développement C# (Visual Studio, VS Code, Rider, etc.).  

## Importer les espaces de noms

Ajoutez les déclarations `using` requises en haut de votre fichier C# afin de pouvoir accéder aux classes Aspose.TeX :

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Image;
using System.IO;
using System.Text;
```

## Étape 1 : Configurer les options de conversion

Configurez le pipeline de conversion. Ici nous indiquons à Aspose.TeX de traiter l’application comme une application console, de spécifier les dossiers d’entrée/sortie, de router les I/O du terminal, et de demander une sortie PNG à 300 dpi.

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

## Étape 2 : Créer le dispositif d’image et exécuter le travail

Le `ImageDevice` capture les données PNG rendues. Nous alimentons un extrait TeX simple via un `MemoryStream`, exécutons le travail, et laissons Aspose.TeX faire le travail lourd.

```csharp
ImageDevice device = new ImageDevice();
TeXJob job = new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
    "\\hrule height 10pt width 95pt\\vskip10pt\\hrule height 5pt")),
    device, options);
job.Run();
```

## Étape 3 : Fournir l’entrée dans la console

Lorsque la console vous invite, tapez **ABC**, appuyez sur **Enter**, puis tapez **\end** et appuyez de nouveau sur **Enter**. Cela montre comment l’entrée du terminal peut être capturée pendant que le moteur TeX s’exécute.

## Étape 4 : Affiner la sortie

Après la fin du travail, vous pouvez écrire un saut de ligne dans la console et récupérer les octets PNG bruts depuis le dispositif. Le tableau `result` contient une image PNG par page.

```csharp
options.TerminalOut.Writer.WriteLine();
byte[][] result = device.Result;
// ExEnd:TakeMainInputFromStream-AuxFromFileSystem-TakeTerminalInputFromConsole-AlternativeImagesStorage
```

Vous pouvez maintenant enregistrer `result[0]` dans un fichier, l’envoyer sur un réseau, ou l’intégrer directement dans un composant UI.

## Problèmes courants et solutions

| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| **Pas de sortie PNG** | `SaveOptions` non défini ou résolution à zéro. | Assurez‑vous que `options.SaveOptions = new PngSaveOptions() { Resolution = 300 };` |
| **La console se bloque** | L’entrée TeX ne reçoit jamais `\end`. | Terminez toujours le flux TeX avec `\end` (ou `\stop`). |
| **Taille d’image incorrecte** | DPI par défaut est 96. | Augmentez `Resolution` dans `PngSaveOptions`. |
| **Chemins du système de fichiers introuvables** | Chaînes de répertoire de travail incorrectes. | Utilisez des chemins absolus ou vérifiez que les répertoires existent avant l’exécution. |

## Questions fréquemment posées

### Q1 : Puis‑je utiliser Aspose.TeX pour .NET dans une application non console ?

**R1 :** Absolument ! Aspose.TeX fonctionne dans les applications de bureau, web et orientées services. Vous remplacez simplement les terminaux console par des flux personnalisés ou des contrôles UI.

### Q2 : Comment puis‑je personnaliser la résolution de l’image de sortie ?

**R2 :** Dans l’exemple, la résolution est définie via `PngSaveOptions.Resolution`. Changez la valeur entière (par ex., `Resolution = 600`) pour obtenir des PNG de meilleure qualité.

### Q3 : Une version d’essai est‑elle disponible ?

**R3 :** Oui, vous pouvez explorer Aspose.TeX avec un essai gratuit disponible **[here](https://releases.aspose.com/)**.

### Q4 : Où puis‑je trouver un support et une assistance supplémentaires ?

**R4 :** Visitez le forum Aspose.TeX **[here](https://forum.aspose.com/c/tex/47)** pour le support communautaire et les discussions.

### Q5 : Comment obtenir une licence temporaire pour Aspose.TeX ?

**R5 :** Vous pouvez acquérir une licence temporaire **[here](https://purchase.aspose.com/temporary-license/)**.

## Conclusion

Vous avez maintenant vu comment **create latex png** en utilisant Aspose.TeX pour C#. En configurant les flux, en mettant en place un `ImageDevice`, et en gérant l’entrée du terminal, vous pouvez générer des images haute résolution à partir de n’importe quelle source TeX—parfait pour les rapports, les aperçus web, ou les pipelines automatisés. Expérimentez avec différents extraits TeX, ajustez le DPI, ou intégrez le tableau d’octets résultant dans votre propre UI pour une expérience fluide.

---

**Last Updated:** 2026-03-26  
**Tested With:** Aspose.TeX 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}