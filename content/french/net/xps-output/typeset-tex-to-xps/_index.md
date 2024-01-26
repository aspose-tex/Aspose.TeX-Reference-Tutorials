---
title: Composition de TeX en XPS dans .NET
linktitle: Composition de TeX en XPS dans .NET
second_title: API Aspose.TeX .NET
description: Convertissez sans effort des documents TeX en XPS dans .NET avec Aspose.TeX. Découvrez notre guide étape par étape pour une expérience d’intégration transparente.
type: docs
weight: 10
url: /fr/net/xps-output/typeset-tex-to-xps/
---
## Introduction

Bienvenue dans notre guide étape par étape sur la composition de TeX en XPS dans .NET à l'aide de la puissante bibliothèque Aspose.TeX. Si vous souhaitez convertir de manière transparente des documents TeX au format XPS dans vos applications .NET, vous êtes au bon endroit. Dans ce didacticiel, nous vous guiderons tout au long du processus, en décomposant chaque étape pour garantir une mise en œuvre fluide.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :

-  Aspose.TeX pour .NET : assurez-vous que la bibliothèque Aspose.TeX est installée. Vous pouvez le télécharger[ici](https://releases.aspose.com/tex/net/).

- Documentation : Familiarisez-vous avec la bibliothèque en vous référant à la documentation[ici](https://reference.aspose.com/tex/net/).

- Répertoires d'entrée et de sortie : configurez vos répertoires d'entrée et de sortie comme spécifié dans l'exemple de code.

Maintenant que tout est configuré, passons au guide étape par étape.

## Importer des espaces de noms

Dans votre application .NET, commencez par importer les espaces de noms nécessaires. Cela garantit que vous avez accès aux fonctionnalités Aspose.TeX requises pour la composition de TeX en XPS.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
```

## Étape 1 : Définir les options de conversion

Définissez les options de conversion, en spécifiant le format ObjectTeX sur l'extension du moteur ObjectTeX. Définissez également le nom du travail, les répertoires d'entrée et de sortie et les détails de sortie du terminal.

```csharp
// Créez des options de conversion pour le format ObjectTeX par défaut lors de l'extension du moteur ObjectTeX.
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
// Spécifiez un nom de travail.
options.JobName = "external-file-stream";
// Spécifiez un répertoire de travail du système de fichiers pour la saisie.
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
// Spécifiez un répertoire de travail du système de fichiers pour la sortie.
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
// Spécifiez que la sortie du terminal doit être écrite dans un fichier dans le répertoire de travail de sortie.
// Le nom du fichier est <nom_travail>.trm.
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## Étape 2 : Créer un flux de documents XPS

Ouvrez un flux pour écrire le document XPS composé. Le nom du fichier n'est pas nécessairement le même que le nom du travail.

```csharp
using (Stream stream = File.Open(Path.Combine("Your Output Directory", options.JobName + ".xps"), FileMode.Create))
```

## Étape 3 : Exécuter le travail TeX

Lancez et exécutez le travail TeX, en spécifiant le nom du document, XpsDevice et les options de conversion.

```csharp
new TeXJob("hello-world", new XpsDevice(stream), options).Run();
```

Toutes nos félicitations! Vous avez réussi à composer TeX en XPS dans .NET à l'aide d'Aspose.TeX. N'hésitez pas à explorer plus de fonctionnalités et d'options en fonction de vos besoins spécifiques.

## Conclusion

Dans ce didacticiel, nous avons couvert les étapes essentielles pour convertir de manière transparente des documents TeX au format XPS dans .NET à l'aide d'Aspose.TeX. En suivant ce guide, vous avez acquis des informations précieuses sur les capacités de la bibliothèque et sur la manière de les exploiter pour vos projets.

## FAQ

### Q1 : Aspose.TeX est-il compatible avec .NET Core ?

A1 : Oui, Aspose.TeX est entièrement compatible avec .NET Core.

### Q2 : Puis-je utiliser Aspose.TeX pour des projets commerciaux ?

A2 : Absolument ! Aspose.TeX est disponible pour un usage commercial et personnel.

### Q3 : Où puis-je trouver des exemples et des ressources supplémentaires ?

 A3 : Explorez la documentation Aspose.TeX[ici](https://reference.aspose.com/tex/net/)pour plus d’exemples et de ressources détaillées.

### Q4 : Comment puis-je obtenir de l'aide pour Aspose.TeX ?

 A4 : Visitez le forum d'assistance Aspose.TeX[ici](https://forum.aspose.com/c/tex/47) pour obtenir de l'aide de la communauté.

### Q5 : Existe-t-il un essai gratuit ?

 A5 : Oui, vous pouvez accéder à un essai gratuit[ici](https://releases.aspose.com/).