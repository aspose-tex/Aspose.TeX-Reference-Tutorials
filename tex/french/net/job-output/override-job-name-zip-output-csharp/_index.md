---
title: Remplacer le nom du travail et écrire la sortie du terminal dans Zip (C#)
linktitle: Remplacer le nom du travail et écrire la sortie du terminal dans Zip (C#)
second_title: API Aspose.TeX .NET
description: Découvrez comment remplacer les noms de tâches et écrire la sortie du terminal dans un fichier ZIP à l'aide d'Aspose.TeX pour .NET. Guide étape par étape avec des exemples C#.
weight: 11
url: /fr/net/job-output/override-job-name-zip-output-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Remplacer le nom du travail et écrire la sortie du terminal dans Zip (C#)

## Introduction

Dans ce didacticiel, nous allons explorer comment remplacer le nom du travail et écrire la sortie du terminal dans un fichier ZIP à l'aide d'Aspose.TeX pour .NET. Aspose.TeX est une bibliothèque puissante qui permet aux développeurs de travailler avec des documents TeX dans leurs applications .NET. Dans cet exemple particulier, nous nous concentrerons sur une tâche courante : écrire la sortie du terminal dans un fichier ZIP avec la possibilité de remplacer le nom de la tâche.

## Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

- Une connaissance pratique de C#
- Aspose.TeX pour .NET installé
- Archive ZIP d'entrée pour le répertoire de travail
- Archive ZIP de sortie pour la sortie du terminal

## Importer des espaces de noms

Avant de plonger dans le code, assurez-vous d'inclure les espaces de noms nécessaires dans votre projet C# :

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Pdf;
using System.IO;
```

Maintenant, décomposons l'exemple en plusieurs étapes pour vous guider tout au long du processus.

## Étape 1 : ouvrir les flux ZIP d’entrée et de sortie

```csharp
using (Stream inZipStream = File.Open(Path.Combine("Your Input Directory", "zip-in.zip"), FileMode.Open))
using (Stream outZipStream = File.Open(Path.Combine("Your Output Directory", "terminal-out-to-zip.zip"), FileMode.Create))
{
    // Le code de l'étape 1 va ici
}
```

## Étape 2 : Définir les options de conversion

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
options.JobName = "terminal-output-to-zip";
options.InputWorkingDirectory = new InputZipDirectory(inZipStream, "in");
options.OutputWorkingDirectory = new OutputZipDirectory(outZipStream);
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## Étape 3 : Définir les options d'enregistrement

```csharp
options.SaveOptions = new PdfSaveOptions();
```

## Étape 4 : Exécuter le travail TeX

```csharp
new TeXJob("hello-world", new PdfDevice(), options).Run();
```

## Étape 5 : Finaliser l'archive ZIP de sortie

```csharp
((OutputZipDirectory)options.OutputWorkingDirectory).Finish();
```

## Conclusion

Toutes nos félicitations! Vous avez appris avec succès comment remplacer le nom du travail et écrire la sortie du terminal dans un fichier ZIP à l'aide d'Aspose.TeX pour .NET. Cette technique peut être incroyablement utile lorsque vous traitez des documents TeX dans vos applications C#.

## FAQ

### Q1 : Puis-je utiliser Aspose.TeX pour .NET avec d’autres langages .NET comme VB.NET ?

A1 : Oui, Aspose.TeX pour .NET est compatible avec tous les langages .NET.

### Q2 : Où puis-je trouver plus de documentation sur Aspose.TeX pour .NET ?

 A2 : Visitez le[Documentation](https://reference.aspose.com/tex/net/) pour des informations détaillées.

### Q3 : Comment puis-je obtenir une licence temporaire pour Aspose.TeX ?

 A3 : Obtenir un[permis temporaire](https://purchase.aspose.com/temporary-license/) à des fins de tests.

### Q4 : Existe-t-il un forum communautaire pour le support d'Aspose.TeX ?

 A4 : Oui, rejoignez le[Forum Aspose.TeX](https://forum.aspose.com/c/tex/47) pour le soutien de la communauté.

### Q5 : Où puis-je acheter Aspose.TeX pour .NET ?

 A5 : Vous pouvez acheter Aspose.TeX[ici](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
