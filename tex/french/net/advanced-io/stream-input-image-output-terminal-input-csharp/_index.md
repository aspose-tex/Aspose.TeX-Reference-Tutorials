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

## Réponses rapides
- **Que fait Aspose.TeX?** Il analyse le code source TeX et le rend dans divers formats, dont le PNG.
- **Puis‑je convertir TeX en PNG sans écrire de fichiers sur le disque?** Oui – vous pouvez fournir le TeX via un `MemoryStream` et capturer directement les octets PNG.
- **Quelles versions de .NET sont prises en charge ?** Toutes les versions modernes de .NET (Framework4.6+, .NETCore3.1+, .NET5/6).
- **Ai‑je besoin d’une licence pour une utilisation en production?** Une licence commerciale est requise pour la production; un essai gratuit est disponible.
- **Quelle résolution d'image puis‑je définir?** La propriété `PngSaveOptions.Resolution` vous permet de spécifier le DPI (par ex., 300dpi).

## Qu'est-ce que « convertir du tex en png » ?

Convertir TeX en PNG consiste à prendre une chaîne de balisage TeX (le langage utilisé pour les documents scientifiques) et à la rendre sous forme d'image raster. Cela est utile lorsque vous souhaitez intégrer des formules mathématiques ou des pages TeX complètes dans des pages web, des applications mobiles ou tout environnement qui ne peut pas rendre TeX nativement.

## Pourquoi générer une image depuis TeX avec Aspose.TeX ?

- **Aucune dépendance externe** – Aspose.TeX est une bibliothèque pure‑.NET, vous n'avez donc pas besoin d'une distribution TeX sur le serveur.
- **API adaptée aux flux** – Fonctionne directement avec `MemoryStream`, ce qui la rend idéale pour les services cloud et les micro‑services.
- **Contrôle fin** – Vous pouvez définir la résolution de l'image, les répertoires de sortie, et même capturer l'entrée interactive du terminal.

## Prérequis

Avant de Sous-marin dans le code, assurez-vous d’avoir :

- Des connaissances de base en C#.
- Aspose.TeX pour .NET installé – vous pouvez le télécharger **[ici](https://releases.aspose.com/tex/net/)**.
- Un environnement de développement C# (Visual Studio, VSCode, Rider, etc.).

## Importer des espaces de noms

Ajoutez les instructions « using » requises en haut de votre fichier C# afin de pouvoir accéder aux classes Aspose.TeX :

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Image;
using System.IO;
using System.Text;
```

## Étape 1 : Configurer les options de conversion

Configurez le pipeline de conversion. Ici, nous indiquons à Aspose.TeX de traiter l'application comme une application console, de spécifier les dossiers d'entrée/sortie, de router les E/S du terminal et de demander une sortie PNG à 300 dpi.

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

## Étape 2 : Créer un périphérique d’image et exécuter la tâche

Le périphérique `ImageDevice` capture les données PNG rendues. Nous fournissons un simple extrait de code TeX via un `MemoryStream`, exécutons la tâche et laissons Aspose.TeX se charger du reste.

```csharp
ImageDevice device = new ImageDevice();
TeXJob job = new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
    "\\hrule height 10pt width 95pt\\vskip10pt\\hrule height 5pt")),
    device, options);
job.Run();
```

## Étape 3 : Saisie dans la console

Lorsque la console vous y invite, saisissez **ABC**, appuyez sur **Entrée**, puis saisissez **\end** et appuyez de nouveau sur **Entrée**. Ceci illustre comment capturer des données saisies dans le terminal pendant l’exécution du moteur TeX.

## Étape 4 : Optimisation de la sortie

Une fois la tâche terminée, vous pouvez insérer un saut de ligne dans la console et récupérer les octets PNG bruts depuis le périphérique. Le tableau `result` contient une image PNG par page.

```csharp
options.TerminalOut.Writer.WriteLine();
byte[][] result = device.Result;
// ExEnd:TakeMainInputFromStream-AuxFromFileSystem-TakeTerminalInputFromConsole-AlternativeImagesStorage
```

Vous pouvez désormais enregistrer « result[0] » dans un fichier, l'envoyer sur un réseau ou l'intégrer directement dans un composant d'interface utilisateur.

## Problèmes courants et solutions

| Problème | Pourquoi cela se produit | Solutions |
|--------------|----------------|---------------|
| **Pas de sortie PNG** | `SaveOptions` non défini ou résolution à zéro. | Assurez-vous que `options.SaveOptions = new PngSaveOptions() { Résolution = 300 };` |
| **La console se bloque** | L’entrée TeX ne reçoit jamais `\end`. | Terminez toujours le flux TeX avec `\end` (ou `\stop`). |
| **Taille d'image incorrecte** | Le DPI par défaut est 96. | Augmentez `Resolution` dans `PngSaveOptions`. |
| **Chemins du système de fichiers introuvables** | Chaînes de répertoire de travail incorrectes. | Utilisez des chemins absolus ou vérifiez que les répertoires existent avant l’exécution. |

## Questions fréquemment posées

### Q1 : Puis-je utiliser Aspose.TeX pour .NET dans une application non-console ?

**R1 :** Absolument ! Aspose.TeX fonctionne dans les applications de bureau, web et orientées services. Il suffit de remplacer les terminaux console par des flux personnalisés ou des contrôles UI.

### Q2 : Comment puis-je personnaliser la résolution de l'image de sortie ?

**R2:** Dans l'exemple, la résolution est définie via `PngSaveOptions.Resolution`. Modifiez la valeur entière (par ex., `Resolution = 600`) pour obtenir des PNG de meilleure qualité.

### Q3 : Existe-t-il une version d'essai disponible ?

**R3:** Oui, vous pouvez explorer Aspose.TeX avec un essai gratuit disponible **[ici](https://releases.aspose.com/)**.

### Q4 : Où puis-je trouver une assistance et une assistance supplémentaires ?

**R4:** Consultez le forum Aspose.TeX **[ici](https://forum.aspose.com/c/tex/47)** pour le support communautaire et les discussions.

### Q5 : Comment puis-je obtenir une licence temporaire pour Aspose.TeX ?

**R5:** Vous pouvez une licence temporaire **[ici](https://purchase.aspose.com/temporary-license/)**.

## Conclusion

Vous avez maintenant vu comment **convertir TeX en PNG** en utilisant Aspose.TeX pour C#. En configurant les flux, en créant un `ImageDevice` et en gérant l’entrée du terminal, vous pouvez générer des images haute résolution à partir de n’importe quelle source TeX — idéal pour les rapports, les aperçus web ou les pipelines automatisés. Explorez davantage en expérimentant différents extraits de TeX, en ajustant le DPI, ou en intégrant le tableau d'octets dans votre propre interface.

**Dernière mise à jour:** 2025-12-20
**Testé avec:** Aspose.TeX 24.11 pour .NET
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}