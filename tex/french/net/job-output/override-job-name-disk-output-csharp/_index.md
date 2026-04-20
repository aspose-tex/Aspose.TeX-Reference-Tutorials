---
date: 2025-12-21
description: Apprenez comment capturer la sortie console en C# avec Aspose.TeX, remplacer
  le nom du travail, définir le répertoire d'entrée TeX et écrire la sortie du terminal
  dans un fichier.
linktitle: Capture Console Output C# – Override Job Name & Write Output to Disk
second_title: Aspose.TeX .NET API
title: Capture de la sortie console C# – Remplacer le nom du job et écrire la sortie
  sur le disque
url: /fr/net/job-output/override-job-name-disk-output-csharp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Capturer la sortie console C# – Remplacer le nom du travail et écrire la sortie du terminal sur le disque (C#)

## Introduction

Dans ce guide étape par étape, vous apprendrez **comment capturer la sortie console C#** lors de l'utilisation d'Aspose.TeX pour .NET. En remplaçant le nom du travail et en dirigeant la sortie du terminal vers un fichier, vous obtenez un contrôle complet sur les pipelines de traitement TeX — idéal pour les builds automatisés, les scénarios CI/CD, ou toute situation où vous devez enregistrer le flux console pour une analyse ultérieure.

## Réponses rapides
- **Que signifie “capturer la sortie console C#” ?** Cela redirige le flux standard du terminal généré par Aspose.TeX vers un fichier que vous spécifiez.  
- **Pourquoi remplacer le nom du travail ?** Le remplacement garantit des noms de fichiers prévisibles et évite les conflits lors de l'exécution de plusieurs travaux.  
- **Quelle classe Aspose.TeX écrit la sortie ?** `OutputFileTerminal` (utilisée via `options.TerminalOut`).  
- **Puis-je définir un dossier d'entrée TeX personnalisé ?** Oui — utilisez `options.InputWorkingDirectory` pour **définir le répertoire d'entrée TeX**.  
- **Cette approche est‑elle compatible avec .NET Core ?** Absolument ; la même API fonctionne sur .NET Framework et .NET Core.

## Qu’est‑ce que “capturer la sortie console C#” dans le contexte d’Aspose.TeX ?

Capturer la sortie console signifie prendre tout ce qui apparaîtrait normalement dans la fenêtre du terminal (messages de journal, avertissements, détails de compilation) et l’écrire dans un fichier persistant. Cela est particulièrement utile pour déboguer de grands projets TeX ou intégrer le traitement TeX dans des flux de travail automatisés.

## Pourquoi remplacer le nom du travail et écrire la sortie du terminal dans un fichier ?

- **Noms de fichiers prévisibles :** Remplacer le nom du travail vous permet de choisir le nom de base des fichiers générés, facilitant l'écriture des scripts de post‑traitement.  
- **Traçabilité :** Stocker le journal du terminal vous fournit une trace d’audit complète du processus de compilation TeX.  
- **Exécution parallèle :** Lors de l’exécution simultanée de plusieurs travaux, des noms de travail uniques évitent les collisions de fichiers.  

## Prérequis

- Bibliothèque Aspose.TeX pour .NET : Assurez‑vous d’avoir la bibliothèque Aspose.TeX pour .NET installée. Vous pouvez la télécharger depuis le [site Aspose.TeX](https://releases.aspose.com/tex/net/).  
- Environnement de développement .NET : Disposez d’un environnement de développement .NET fonctionnel, incluant un IDE tel que Visual Studio.  
- Connaissances de base en C# : Familiarité avec les bases du langage de programmation C#.  
- Répertoires d’entrée et de sortie : Préparez les répertoires d’entrée et de sortie pour vos fichiers TeX.  

## Importer les espaces de noms

Dans votre code C#, assurez‑vous d’inclure les espaces de noms nécessaires pour accéder aux fonctionnalités d’Aspose.TeX :

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

## Étape 1 : Créer les options de conversion

Tout d’abord, nous créons une instance `TeXOptions` qui indique à Aspose.TeX que nous exécutons dans un scénario d’application console.

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

## Étape 2 : Spécifier le nom du travail (remplacer la valeur par défaut)

Remplacer le nom du travail nous donne le contrôle sur le nom de base de tous les artefacts générés.

```csharp
options.JobName = "overridden-job-name";
```

## Étape 3 : Définir le répertoire d’entrée TeX

Indiquez à Aspose.TeX où trouver vos fichiers source `.tex`. Il s’agit de l’étape **définir le répertoire d’entrée TeX**.

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

## Étape 4 : Spécifier le répertoire de travail de sortie

Définissez où les fichiers traités et le journal console capturé seront enregistrés.

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

## Étape 5 : Écrire la sortie du terminal dans un fichier

Nous dirigeons maintenant le flux console vers un fichier physique dans le répertoire de sortie. Cela implémente l’exigence **écrire la sortie du terminal dans un fichier**.

```csharp
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## Étape 6 : Exécuter le travail

Enfin, nous créons un `TeXJob` avec le nom du travail remplacé, le dispositif de sortie XPS, et les options que nous avons configurées. L’exécution du travail générera le fichier XPS et capturera le journal console.

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

## Problèmes courants & dépannage

| Symptôme | Cause probable | Solution |
|----------|----------------|----------|
| Aucun fichier de sortie créé | Le chemin du répertoire de sortie est incorrect ou les permissions d’écriture sont manquantes | Vérifiez que `options.OutputWorkingDirectory` pointe vers un dossier valide et que le processus dispose des droits d’écriture. |
| Le journal du terminal est vide | `TerminalOut` n’est pas défini ou est écrasé plus tard | Assurez‑vous que `options.TerminalOut = new OutputFileTerminal(...);` est exécuté avant `job.Run();`. |
| Le travail échoue avec “file not found” | Le répertoire d’entrée n’est pas correctement défini | Revérifiez le chemin passé à `InputFileSystemDirectory` et assurez‑vous que les fichiers `.tex` y existent. |

## Questions fréquemment posées

### Q1 : Puis‑je utiliser Aspose.TeX pour .NET avec d’autres bibliothèques .NET ?

**R1 :** Oui, Aspose.TeX pour .NET peut être intégré de manière transparente avec d’autres bibliothèques .NET.

### Q2 : Existe‑t‑il une version d’essai gratuite d’Aspose.TeX pour .NET ?

**R2 :** Oui, vous pouvez télécharger une version d’essai gratuite [ici](https://releases.aspose.com/).

### Q3 : Comment obtenir du support pour Aspose.TeX pour .NET ?

**R3 :** Visitez le [forum Aspose.TeX](https://forum.aspose.com/c/tex/47) pour obtenir l’aide de la communauté et du support.

### Q4 : Des licences temporaires sont‑elles disponibles pour Aspose.TeX pour .NET ?

**R4 :** Oui, vous pouvez obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

### Q5 : Où puis‑je trouver la documentation d’Aspose.TeX pour .NET ?

**R5 :** La documentation est disponible [ici](https://reference.aspose.com/tex/net/).

## Conclusion

Félicitations ! Vous avez appris avec succès comment **capturer la sortie console C#** en remplaçant le nom du travail, en définissant le répertoire d’entrée TeX, et en écrivant la sortie du terminal dans un fichier à l’aide d’Aspose.TeX pour .NET. Cette technique simplifie la journalisation, améliore la traçabilité et rend les pipelines de traitement TeX automatisés plus robustes.

---

**Dernière mise à jour :** 2025-12-21  
**Testé avec :** Aspose.TeX 24.11 for .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}