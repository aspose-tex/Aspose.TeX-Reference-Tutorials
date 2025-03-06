---
title: Remplacer le nom du travail et écrire la sortie du terminal sur le disque (C#)
linktitle: Remplacer le nom du travail et écrire la sortie du terminal sur le disque (C#)
second_title: API Aspose.TeX .NET
description: Découvrez comment utiliser Aspose.TeX pour .NET pour remplacer les noms de tâches et capturer la sortie du terminal. Suivez notre guide complet pour une gestion transparente des fichiers TeX.
weight: 10
url: /fr/net/job-output/override-job-name-disk-output-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Remplacer le nom du travail et écrire la sortie du terminal sur le disque (C#)

## Introduction

Bienvenue dans ce guide étape par étape sur l'utilisation d'Aspose.TeX pour .NET pour remplacer les noms de tâches et écrire la sortie du terminal sur le disque dans le langage de programmation C#. Aspose.TeX pour .NET est une bibliothèque puissante qui vous permet de travailler de manière transparente avec des fichiers TeX, et dans ce didacticiel, nous nous concentrerons sur une tâche spécifique : remplacer les noms de tâches et capturer la sortie du terminal.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :

-  Bibliothèque Aspose.TeX pour .NET : assurez-vous que la bibliothèque Aspose.TeX pour .NET est installée. Vous pouvez le télécharger depuis le[Site Web Aspose.TeX](https://releases.aspose.com/tex/net/).

- Environnement de développement .NET : disposer d'un environnement de développement .NET fonctionnel, y compris un environnement de développement intégré (IDE) tel que Visual Studio.

- Connaissances de base en C# : Familiarisez-vous avec les bases du langage de programmation C#.

- Répertoires d'entrée et de sortie : préparez les répertoires d'entrée et de sortie pour vos fichiers TeX.

## Importer des espaces de noms

Dans votre code C#, assurez-vous d'inclure les espaces de noms nécessaires pour accéder aux fonctionnalités Aspose.TeX :

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

## Étape 1 : Créer des options de conversion

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

Créez TeXOptions avec ConsoleAppOptions, en spécifiant ObjectTeX comme TeXConfig.

## Étape 2 : Spécifiez le nom du travail

```csharp
options.JobName = "overridden-job-name";
```

Spécifiez le nom du travail pour remplacer le nom par défaut.

## Étape 3 : Spécifier le répertoire de travail d'entrée

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

Définissez le répertoire de travail d'entrée pour vos fichiers TeX.

## Étape 4 : Spécifier le répertoire de travail de sortie

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Définissez le répertoire de travail de sortie pour enregistrer les fichiers TeX traités.

## Étape 5 : Écrire la sortie du terminal sur le disque

```csharp
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

Configurez la sortie du terminal pour qu'elle soit écrite dans un fichier du répertoire de sortie.

## Étape 6 : Exécuter le travail

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

Créez un TeXJob en spécifiant un nom de travail, un périphérique de sortie (XpsDevice) et des options. Enfin, exécutez le travail.

## Conclusion

Toutes nos félicitations! Vous avez appris avec succès comment remplacer les noms de tâches et écrire la sortie du terminal sur le disque à l'aide d'Aspose.TeX pour .NET en C#. Cette fonctionnalité est précieuse pour gérer efficacement vos tâches de traitement TeX.

## FAQ

### Q1 : Puis-je utiliser Aspose.TeX pour .NET avec d’autres bibliothèques .NET ?

A1 : Oui, Aspose.TeX pour .NET peut être intégré de manière transparente à d’autres bibliothèques .NET.

### Q2 : Existe-t-il un essai gratuit disponible pour Aspose.TeX pour .NET ?

 A2 : Oui, vous pouvez télécharger une version d'essai gratuite[ici](https://releases.aspose.com/).

### Q3 : Comment puis-je obtenir une assistance pour Aspose.TeX pour .NET ?

 A3 : Visitez le[Forum Aspose.TeX](https://forum.aspose.com/c/tex/47) pour obtenir de la communauté et du soutien.

### Q4 : Des licences temporaires sont-elles disponibles pour Aspose.TeX pour .NET ?

 A4 : Oui, vous pouvez obtenir une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).

### Q5 : Où puis-je trouver la documentation d'Aspose.TeX pour .NET ?

 A5 : La documentation est disponible[ici](https://reference.aspose.com/tex/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
