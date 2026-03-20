---
date: 2025-12-20
description: Apprenez à créer une sortie XPS de travail TeX à l'aide d'Aspose.TeX
  pour .NET, à gérer les entrées/sorties du système de fichiers et à générer des documents
  XPS de haute qualité.
linktitle: Create TeX Job XPS Output with Filesystems – Aspose.TeX for .NET
second_title: Aspose.TeX .NET API
title: Créer une sortie XPS d’un travail TeX avec les systèmes de fichiers – Aspose.TeX
  pour .NET
url: /fr/net/file-input-output/filesystem-input-xps-output/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une sortie XPS de travail TeX avec les systèmes de fichiers – Aspose.TeX pour .NET

## Introduction

Bienvenue ! Dans ce tutoriel, vous apprendrez **comment créer une sortie XPS d’un travail TeX** tout en travaillant avec des entrées et sorties de système de fichiers à l’aide d’Aspose.TeX pour .NET. Que vous construisiez un processeur par lots, un service web ou un utilitaire de bureau, les étapes ci‑dessous vous guideront dans la configuration du moteur, la désignation de vos fichiers et la production de documents XPS qui reproduisent exactement le source LaTeX d’origine.

Nous décomposerons le processus en étapes numérotées claires, expliquerons le « pourquoi » de chaque ligne de code et vous donnerons des astuces pratiques que vous pourrez appliquer immédiatement.

## Réponses rapides
- **Que signifie « create tex job xps » ?** Il s’agit de configurer un travail Aspose.TeX qui lit des fichiers TeX et écrit le résultat sous forme de document XPS.  
- **Ai‑je besoin d’une licence ?** Une licence temporaire est disponible pour les tests ; une licence complète est requise en production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Puis‑je changer le format de sortie ?** Oui – remplacez `XpsDevice` par un autre dispositif (PDF, PNG, etc.).  
- **Une sortie console est‑elle obligatoire ?** Non – vous pouvez utiliser un terminal mémoire pour une exécution silencieuse.

## Qu’est‑ce que « create tex job xps » ?

Créer un travail TeX qui produit du XPS signifie initialiser le moteur Aspose.TeX, indiquer où lire les fichiers sources et diriger les pages rendues vers un package XPS. XPS (XML Paper Specification) est un format à mise en page fixe qui préserve la typographie et les graphiques vectoriels, ce qui le rend idéal pour l’impression ou une conversion ultérieure.

## Pourquoi utiliser Aspose.TeX pour la sortie XPS ?

- **Haute fidélité :** Le moteur reproduit avec précision la mise en page LaTeX en XPS.  
- **Aucune dépendance externe :** Bibliothèque pure .NET, aucune installation LaTeX native requise.  
- **Entrées/Sorties flexibles :** Fonctionne avec des répertoires de système de fichiers, des flux mémoire ou des fournisseurs personnalisés.  
- **Scalable :** Adapté aux conversions de fichiers uniques ou aux pipelines de traitement par lots.

## Prérequis

Avant de commencer, assurez‑vous de disposer de :

- **Aspose.TeX pour .NET** – téléchargez la dernière version depuis le [site Aspose](https://releases.aspose.com/tex/net/).  
- **Environnement de développement .NET** – Visual Studio, Rider ou VS Code avec le SDK .NET.  
- **Dossiers d’entrée et de sortie** – créez deux répertoires sur votre machine (par ex. `C:\TeX\Input` et `C:\TeX\Output`).  
- **Licence (facultative pour les tests)** – vous pouvez obtenir une licence temporaire depuis le portail Aspose.

## Importer les espaces de noms

Tout d’abord, importez les espaces de noms requis afin d’accéder aux aides du système de fichiers et au dispositif XPS.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

Ces espaces de noms exposent `InputFileSystemDirectory`, `OutputFileSystemDirectory` et `XpsDevice`, qui sont essentiels au flux de travail **create tex job xps**.

## Étape 1 : Créer les options de conversion

Nous commençons par construire un objet `TeXOptions` qui indique au moteur d’utiliser la configuration ObjectTeX (la valeur par défaut pour la plupart des sources LaTeX).

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

> **Astuce :** `ConsoleAppOptions` définit des valeurs par défaut sensées pour les applications de type console, mais vous pouvez personnaliser les options ultérieurement si besoin.

## Étape 2 : Spécifier les répertoires d’entrée et de sortie

Pointez le moteur vers les dossiers que vous avez préparés précédemment. Remplacez les chaînes de substitution par les chemins réels sur votre machine.

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Le travail TeX sait maintenant où trouver les fichiers `.tex` et où déposer les fichiers XPS générés.

## Étape 3 : Choisir un terminal de sortie

Le terminal contrôle où les messages d’état sont écrits. Pour un débogage rapide, nous resterons avec la console, mais vous pouvez passer à un terminal mémoire pour des exécutions silencieuses.

```csharp
options.TerminalOut = new OutputConsoleTerminal(); // Default value. Arbitrary assignment.
```

> **Pourquoi c’est important :** Utiliser un terminal console vous donne un retour immédiat sur les avertissements ou erreurs de compilation, ce qui accélère le dépannage.

## Étape 4 : Exécuter le travail TeX

Créez une instance `TeXJob`, donnez‑lui un nom convivial, attachez le `XpsDevice` et lancez‑le.

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

Lorsque `Run()` se termine, vous trouverez un fichier `hello-world.xps` dans le répertoire de sortie.

## Étape 5 : Affiner la sortie console

Ajouter une ligne vide après la fin du travail rend le journal console plus lisible, surtout lorsque vous exécutez plusieurs travaux en lot.

```csharp
options.TerminalOut.Writer.WriteLine();
```

## Problèmes courants et solutions

| Problème | Cause | Solution |
|----------|-------|----------|
| **Le fichier XPS est vide** | Le chemin du répertoire de sortie est incorrect ou non accessible en écriture. | Vérifiez le chemin passé à `OutputFileSystemDirectory` et assurez‑vous que le processus possède les droits d’écriture. |
| **Erreurs de compilation** | Le source LaTeX utilise des packages non fournis avec ObjectTeX. | Passez à une configuration de moteur TeX complète (`TeXConfig.FullTeX()`) ou ajoutez les fichiers de packages manquants dans le répertoire d’entrée. |
| **La console se bloque** | Le terminal attend une entrée à cause d’invites interactives. | Utilisez `OutputMemoryTerminal` pour supprimer les invites interactives dans les scripts automatisés. |

## Questions fréquentes

**Q1 : Puis‑je utiliser un autre format de sortie à la place du XPS ?**  
R1 : Oui, Aspose.TeX prend en charge PDF, PNG, SVG et d’autres formats. Remplacez `new XpsDevice()` par la classe de dispositif appropriée (par ex. `new PdfDevice()`).

**Q2 : Une licence temporaire est‑elle disponible pour les tests ?**  
R2 : Oui, vous pouvez obtenir une licence temporaire pour les tests depuis [ce lien](https://purchase.aspose.com/temporary-license/).

**Q3 : Où puis‑je trouver une documentation supplémentaire ?**  
R3 : Consultez la [documentation Aspose.TeX pour .NET](https://reference.aspose.com/tex/net/) pour des informations détaillées.

**Q4 : Comment obtenir le support de la communauté ou poser des questions ?**  
R4 : Visitez le [forum Aspose.TeX](https://forum.aspose.com/c/tex/47) pour le support communautaire et les discussions.

**Q5 : Existe‑t‑il des projets d’exemple disponibles ?**  
R5 : Explorez le dépôt GitHub d’Aspose.TeX pour des projets d’exemple et des extraits de code.

## Conclusion

En suivant les étapes ci‑dessus, vous savez maintenant comment **créer une sortie XPS d’un travail TeX** avec Aspose.TeX pour .NET, gérer vos dossiers d’entrée et de sortie, et affiner le processus tant pour le développement que pour la production. N’hésitez pas à expérimenter avec d’autres dispositifs de sortie, à intégrer cette logique dans des flux de travail plus larges ou à automatiser des conversions par lots.

---

**Dernière mise à jour :** 2025-12-20  
**Testé avec :** Aspose.TeX 24.11 pour .NET (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}