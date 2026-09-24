---
date: 2026-09-24
description: Apprenez comment configurer TeX input directory, streams, images, and
  terminal input using Aspose.TeX for .NET in C#.
keywords:
- configure tex input directory
- add image stream tex
- add images from stream
lastmod: 2026-09-24
linktitle: Avancé Aspose.TeX Input and Output
og_description: Configure TeX input directory, add image streams, and handle terminal
  input with Aspose.TeX for .NET in C#. Apprenez étape par étape.
og_image_alt: Guide showing how to configure TeX input directory and streams in Aspose.TeX
  for .NET
og_title: Configurer TeX input directory – Guide avancé Aspose.TeX
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
title: Configurer TeX input directory – Avancé Aspose.TeX Input and Output
url: /fr/net/advanced-io/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configurer le répertoire d'entrée TeX dans Aspose.TeX pour .NET

Aspose.TeX for .NET vous permet d'intégrer un traitement TeX complet directement dans vos applications C#. Dans ce tutoriel, vous apprendrez comment **configurer le répertoire d'entrée TeX**, alimenter le contenu LaTeX à partir de flux, et ajouter des images sans toucher au système de fichiers. Si vous avez besoin d'un contrôle précis sur l'endroit où le moteur recherche les fichiers `.tex` et les ressources, vous êtes au bon endroit.

## Réponses rapides
- **Que signifie « configure tex input directory » ?**  
  Il indique à Aspose.TeX où trouver le fichier `.tex` principal, les fichiers auxiliaires et les graphiques.
- **Quelle classe définit les chemins d'entrée ?**  
  `TeXInputOptions` stocke le dossier de base et les emplacements de recherche supplémentaires.
- **Puis-je charger une image depuis un flux mémoire ?**  
  Oui—utilisez `TeXInputOptions.AddImage` avec une instance de `Stream`.
- **Est‑il possible de compiler du code LaTeX fourni à l'exécution ?**  
  Absolument—passez un `MemoryStream` contenant le texte source au processeur.
- **Ai‑je besoin d'une licence pour une utilisation en production ?**  
  Une licence Aspose.TeX valide est requise pour les déploiements non‑évaluation.

## Qu'est-ce que TeXInputOptions ?
`TeXInputOptions` est l'objet de configuration qui définit le dossier de base et les chemins de recherche supplémentaires pour les ressources TeX. Le configurer correctement élimine les erreurs « file not found » et vous permet de garder les actifs organisés.

## Comment configurer le répertoire d'entrée tex ?
`TeXInputOptions` est un objet de configuration qui spécifie le dossier de base et les chemins de recherche supplémentaires pour les ressources TeX. Chargez votre document principal et indiquez au processeur où chercher tout en quelques lignes. Cette réponse directe explique les étapes essentielles avant tout détail supplémentaire.

Créez une instance de `TeXInputOptions`, définissez `BaseFolder` sur le dossier contenant votre fichier `.tex` principal, ajoutez les sous‑dossiers qui contiennent les images ou les fichiers auxiliaires, et transmettez les options à `TeXProcessor`. Le moteur résoudra alors automatiquement toutes les références relatives.

### Étape 1 : instancier TeXInputOptions
Attribuez le dossier de base qui contient la source TeX principale.

### Étape 2 : ajouter des chemins de recherche supplémentaires
Si votre projet stocke les figures dans un dossier séparé (par ex., *Images*), appelez `AddSearchPath` pour l'inclure.

### Étape 3 : transmettre les options au processeur
Créez un `TeXProcessor`, fournissez les options configurées, et invoquez `Process` ou `Render`.

## Comment ajouter des images avec Aspose.TeX
Les images référencées dans un fichier TeX peuvent être fournies soit via un dossier, soit directement à partir d'un flux. Fournir un flux est utile lorsque les images sont stockées dans une base de données ou générées à la volée. `AddImage(string name, Stream data)` enregistre un flux d'image avec le nom de fichier donné pour une utilisation dans le document TeX. Cette méthode vous permet d'éviter les fichiers temporaires et d'accélérer le traitement.

## Comment traiter les flux dans Aspose.TeX
Lorsque votre source LaTeX est générée dynamiquement—peut‑être à partir d'une entrée utilisateur ou d'un service web—vous pouvez la transmettre directement au processeur sans écrire de fichier. `TeXProcessor` traite le contenu TeX et peut accepter un `MemoryStream` contenant le code LaTeX source. Enveloppez la chaîne LaTeX dans un `MemoryStream`, définissez‑le comme flux source dans `TeXProcessor`, et lancez la conversion. Cette technique fonctionne tout aussi bien pour les services cloud‑native où les E/S disque sont coûteuses.

## Pourquoi utiliser Aspose.TeX pour des I/O avancées ?
Aspose.TeX prend en charge **plus de 30 formats d'entrée et de sortie** (y compris PDF, PNG, SVG) et peut rendre des documents de plusieurs centaines de pages sans charger le fichier complet en mémoire. Son architecture orientée flux réduit la surcharge I/O jusqu'à 40 % par rapport aux flux de travail basés sur des fichiers, ce qui le rend idéal pour les applications serveur à haut débit.

## Prérequis
- .NET 6.0 ou ultérieur (la bibliothèque fonctionne également avec .NET Core 3.1+ et .NET Framework 4.6.1+)
- Package NuGet Aspose.TeX pour .NET (version 24.11 ou plus récente)
- Une licence Aspose.TeX valide pour une utilisation en production

## Explorer Aspose.TeX : une passerelle vers le traitement avancé de documents
Pour voir la configuration en action, suivez notre guide étape par étape **[Spécifier le répertoire d'entrée requis pour Aspose.TeX (C#)](./required-input-directory-csharp/)**. Ce tutoriel vous guide à travers la création de l'objet `TeXInputOptions` et le rendu d'une sortie PDF.  
**[Spécifier le répertoire d'entrée requis pour Aspose.TeX (C#)](./required-input-directory-csharp/)**

## Maîtriser les flux, les images et l'entrée terminale dans Aspose.TeX pour C#
Pour une exploration plus approfondie de l'alimentation de LaTeX depuis la mémoire, de l'ajout d'images via des flux, et de l'utilisation d'une entrée de type terminal, consultez **[Maîtriser les flux, les images et l'entrée terminale dans Aspose.TeX pour C#](./stream-input-image-output-terminal-input-csharp/)**. Il montre comment intégrer Aspose.TeX dans les API web, les services en arrière‑plan et les outils en ligne de commande.  
**[Maîtriser les flux, les images et l'entrée terminale dans Aspose.TeX pour C#](./stream-input-image-output-terminal-input-csharp/)**

## Problèmes courants et solutions
- **“File not found” errors** – Vérifiez que `BaseFolder` pointe vers le répertoire correct et que tous les chemins de recherche supplémentaires sont ajoutés avant le rendu.
- **Images not loading** – Assurez‑vous que le nom de l'image dans `AddImage` correspond exactement au nom utilisé dans la source TeX, y compris l'extension du fichier.
- **Memory usage spikes** – Lors du traitement de documents très volumineux, appelez `TeXProcessor.Cleanup()` après le rendu pour libérer les ressources non gérées.

## Questions fréquemment posées

**Q : Puis‑je changer le répertoire d'entrée à l'exécution ?**  
R : Oui—vous pouvez créer une nouvelle instance de `TeXInputOptions` avec un `BaseFolder` différent et la transmettre à un nouveau `TeXProcessor` chaque fois que vous devez reconfigurer.

**Q : Comment ajouter des images stockées dans une base de données ?**  
R : Récupérez l'image sous forme de `byte[]`, enveloppez‑la dans un `MemoryStream`, et appelez `TeXInputOptions.AddImage("image.png", stream)`. Le nom doit correspondre à la référence dans votre fichier `.tex`.

**Q : Est‑il possible de traiter du code LaTeX reçu d'une API web sans enregistrer de fichier ?**  
R : Absolument. Convertissez la chaîne entrante en `MemoryStream`, définissez‑la comme source pour `TeXProcessor`, et rendez directement dans le format de sortie souhaité.

**Q : Dois‑je appeler des méthodes de nettoyage après le traitement ?**  
R : Libérez tous les flux que vous créez, et pour de lourdes charges de travail invoquez `TeXProcessor.Cleanup()` pour libérer les ressources natives.

**Q : Où puis‑je trouver des exemples plus avancés ?**  
R : Les deux liens de tutoriels ci‑dessus contiennent des exemples de code complets qui démontrent chaque scénario en détail, y compris la gestion des erreurs et les astuces de performance.

---

**Dernière mise à jour :** 2026-09-24  
**Testé avec :** Aspose.TeX 24.11 pour .NET  
**Auteur :** Aspose

## Tutoriels associés

- [Obtenir le flux de fichier TeX (C#) avec l'API Aspose.TeX – Répertoire d'entrée requis](/tex/net/advanced-io/required-input-directory-csharp/)
- [Créer XPS à partir de TeX avec les systèmes de fichiers – Aspose.TeX pour .NET](/tex/net/file-input-output/filesystem-input-xps-output/)
- [Convertir LaTeX en PNG avec Aspose.TeX pour .NET – Traiter les entrées système de fichiers et ZIP](/tex/net/file-input-output/required-inputs-from-filesystem-and-zip/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}