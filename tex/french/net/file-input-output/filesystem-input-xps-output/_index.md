---
date: 2026-03-26
description: Apprenez à créer des XPS à partir de TeX en utilisant Aspose.TeX pour
  .NET, à gérer les entrées/sorties du système de fichiers et à générer des documents
  XPS de haute qualité.
linktitle: Create XPS from TeX with Filesystems – Aspose.TeX for .NET
second_title: Aspose.TeX .NET API
title: Créer un XPS à partir de TeX avec les systèmes de fichiers – Aspose.TeX pour
  .NET
url: /fr/net/file-input-output/filesystem-input-xps-output/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer XPS à partir de TeX avec les systèmes de fichiers – Aspose.TeX pour .NET

## Introduction

Bienvenue ! Dans ce tutoriel, vous apprendrez **comment créer XPS à partir de TeX** tout en travaillant avec des entrées et sorties de système de fichiers à l'aide d'Aspose.TeX pour .NET. Que vous construisiez un processeur par lots, un service web ou un utilitaire de bureau, les étapes ci‑dessous vous guideront pour configurer le moteur, le pointer vers vos fichiers et produire des documents XPS qui ressemblent exactement à la source LaTeX originale.

Nous décomposerons le processus en étapes claires et numérotées, expliquerons le « pourquoi » derrière chaque ligne de code et vous donnerons des conseils pratiques que vous pourrez appliquer immédiatement.

## Réponses rapides
- **Que signifie « créer XPS à partir de TeX » ?** Il s'agit de configurer un job Aspose.TeX qui lit des fichiers TeX et écrit le résultat sous forme de document XPS.  
- **Ai‑je besoin d’une licence ?** Une licence temporaire est disponible pour les tests ; une licence complète est requise pour la production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Puis‑je changer le format de sortie ?** Oui – remplacez `XpsDevice` par un autre dispositif (PDF, PNG, etc.).  
- **La sortie console est‑elle requise ?** Non – vous pouvez utiliser un terminal mémoire pour une exécution silencieuse.

## Comment créer XPS à partir de TeX avec Aspose.TeX

Créer un job TeX qui génère du XPS signifie initialiser le moteur Aspose.TeX, lui indiquer où lire les fichiers source et diriger les pages rendues vers un paquet XPS. XPS (XML Paper Specification) est un format à mise en page fixe qui préserve la typographie et les graphiques vectoriels, ce qui le rend idéal pour l’impression ou une conversion ultérieure.

## Qu’est‑ce que « create tex job xps » ?

Créer un job TeX qui génère du XPS signifie initialiser le moteur Aspose.TeX, lui indiquer où lire les fichiers source et diriger les pages rendues vers un paquet XPS. XPS (XML Paper Specification) est un format à mise en page fixe qui préserve la typographie et les graphiques vectoriels, ce qui le rend idéal pour l’impression ou une conversion ultérieure.

## Pourquoi utiliser Aspose.TeX pour la sortie XPS ?

- **Haute fidélité :** Le moteur reproduit avec précision la mise en page LaTeX en XPS.  
- **Aucune dépendance externe :** Bibliothèque pure .NET, aucune installation LaTeX native requise.  
- **Entrées/Sorties flexibles :** Fonctionne avec des répertoires de système de fichiers, des flux mémoire ou des fournisseurs personnalisés.  
- **Scalable :** Convient aux conversions d’un seul fichier ou aux pipelines de traitement en masse.

## Prérequis

Avant de commencer, assurez‑vous d’avoir les éléments suivants :

- **Aspose.TeX for .NET** – téléchargez la dernière version depuis le [site Aspose](https://releases.aspose.com/tex/net/).  
- **Environnement de développement .NET** – Visual Studio, Rider ou VS Code avec le SDK .NET.  
- **Dossiers d’entrée et de sortie** – créez deux répertoires sur votre machine (par ex., `C:\TeX\Input` et `C:\TeX\Output`).  
- **Licence (facultative pour les tests)** – vous pouvez obtenir une licence temporaire depuis le portail Aspose.

## Importer les espaces de noms

Tout d’abord, importez les espaces de noms requis afin d’accéder aux aides du système de fichiers et au dispositif XPS.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

Ces espaces de noms exposent `InputFileSystemDirectory`, `OutputFileSystemDirectory` et `XpsDevice`, qui sont essentiels pour le flux de travail **create XPS from TeX**.

## Étape 1 : Créer les options de conversion

Nous commençons par créer un objet `TeXOptions` qui indique au moteur d’utiliser la configuration ObjectTeX (la valeur par défaut pour la plupart des sources LaTeX).

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

> **Astuce :** `ConsoleAppOptions` définit des valeurs par défaut sensées pour les applications de type console, mais vous pouvez personnaliser les options ultérieurement si nécessaire.

## Étape 2 : Spécifier les répertoires d’entrée et de sortie

Pointez le moteur vers les dossiers que vous avez préparés précédemment. Remplacez les chaînes de caractères placeholders par les chemins réels sur votre machine.

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Le job TeX sait maintenant où trouver les fichiers `.tex` et où déposer les fichiers XPS générés.

## Étape 3 : Choisir un terminal de sortie

Le terminal contrôle où les messages d’état sont écrits. Pour un débogage rapide, nous resterons avec la console, mais vous pouvez passer à un terminal mémoire pour des exécutions silencieuses.

```csharp
options.TerminalOut = new OutputConsoleTerminal(); // Default value. Arbitrary assignment.
```

> **Pourquoi c’est important :** Utiliser un terminal console vous donne un retour immédiat sur les avertissements ou erreurs de compilation, ce qui accélère le dépannage.

## Étape 4 : Exécuter le job TeX

Créez une instance `TeXJob`, donnez‑lui un nom convivial, attachez le `XpsDevice` et exécutez‑le.

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

Lorsque `Run()` se termine, vous trouverez un fichier `hello-world.xps` dans le répertoire de sortie.

## Étape 5 : Affiner la sortie console

Ajouter une ligne vide après la fin du job rend le journal console plus lisible, surtout lorsque vous exécutez plusieurs jobs en lot.

```csharp
options.TerminalOut.Writer.WriteLine();
```

## Cas d’utilisation courants

| Scénario | Pourquoi XPS ? | Comment l’extrait aide |
|----------|----------------|------------------------|
| **Conversion par lots d’articles académiques** | Conserver la mise en page exacte pour l’impression d’archives. | L’approche basée sur le système de fichiers vous permet de pointer vers un dossier de fichiers `.tex` et de générer un ensemble correspondant de fichiers XPS. |
| **Service web qui rend LaTeX à la volée** | XPS peut être diffusé directement aux navigateurs qui le supportent. | En remplaçant `XpsDevice` par un flux mémoire, vous pouvez renvoyer le document sans toucher au disque. |
| **Outil de publication de bureau** | Besoin d’un aperçu à mise en page fixe avant la conversion PDF. | Le même job peut être enchaîné à un dispositif PDF ultérieurement pour la distribution finale. |

## Problèmes courants et solutions

| Problème | Cause | Solution |
|----------|-------|----------|
| **Le fichier XPS est vide** | Le chemin du répertoire de sortie est incorrect ou non inscriptible. | Vérifiez le chemin passé à `OutputFileSystemDirectory` et assurez‑vous que le processus a les permissions d’écriture. |
| **Erreurs de compilation** | La source LaTeX utilise des packages non fournis avec ObjectTeX. | Passez à une configuration de moteur TeX complet (`TeXConfig.FullTeX()`) ou ajoutez les fichiers de packages manquants au répertoire d’entrée. |
| **La console se bloque** | Le terminal attend une entrée à cause d’invites interactives. | Utilisez `OutputMemoryTerminal` pour supprimer les invites interactives dans les scripts automatisés. |

## Questions fréquentes

**Q1 : Puis‑je utiliser un format de sortie différent au lieu de XPS ?**  
R1 : Oui, Aspose.TeX prend en charge PDF, PNG, SVG et d’autres formats. Remplacez `new XpsDevice()` par la classe de dispositif appropriée (par ex., `new PdfDevice()`).

**Q2 : Une licence temporaire est‑elle disponible à des fins de test ?**  
R2 : Oui, vous pouvez obtenir une licence temporaire pour les tests via [ce lien](https://purchase.aspose.com/temporary-license/).

**Q3 : Où puis‑je trouver de la documentation supplémentaire ?**  
R3 : Consultez la [documentation Aspose.TeX pour .NET](https://reference.aspose.com/tex/net/) pour des informations détaillées.

**Q4 : Comment obtenir le support de la communauté ou poser des questions ?**  
R4 : Visitez le [forum Aspose.TeX](https://forum.aspose.com/c/tex/47) pour le support communautaire et les discussions.

**Q5 : Existe‑t‑il des projets d’exemple disponibles ?**  
R5 : Explorez le dépôt GitHub d’Aspose.TeX pour des projets d’exemple et des extraits de code.

## Conclusion

En suivant les étapes ci‑dessus, vous savez maintenant comment **créer XPS à partir de TeX** avec Aspose.TeX pour .NET, gérer vos dossiers d’entrée et de sortie, et affiner le processus pour les scénarios de développement et de production. N’hésitez pas à expérimenter d’autres dispositifs de sortie, à intégrer cette logique dans des flux de travail plus larges ou à automatiser des conversions par lots.

---

**Dernière mise à jour :** 2026-03-26  
**Testé avec :** Aspose.TeX 24.11 for .NET (latest at time of writing)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}