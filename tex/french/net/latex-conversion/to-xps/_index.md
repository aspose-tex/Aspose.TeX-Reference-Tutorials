---
title: LaTeX vers XPS dans .NET - Conversion facile avec Aspose.TeX
linktitle: LaTeX vers XPS dans .NET - Conversion facile avec Aspose.TeX
second_title: API Aspose.TeX .NET
description: Convertissez sans effort LaTeX en XPS dans .NET avec Aspose.TeX. Haute qualité, personnalisable et efficace.
weight: 13
url: /fr/net/latex-conversion/to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# LaTeX vers XPS dans .NET - Conversion facile avec Aspose.TeX

## Introduction

Recherchez-vous un moyen transparent de convertir des documents LaTeX au format XPS dans vos applications .NET ? Aspose.TeX pour .NET fournit une solution puissante pour cette tâche, rendant le processus de conversion simple et efficace. Ce guide étape par étape vous guidera tout au long du processus de conversion de LaTeX en XPS à l'aide d'Aspose.TeX, vous garantissant ainsi d'obtenir des résultats précis et de haute qualité.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :

- Une connaissance pratique du développement C# et .NET.
-  Aspose.TeX pour la bibliothèque .NET installée. Vous pouvez le télécharger[ici](https://releases.aspose.com/tex/net/).
- Une compréhension de la syntaxe et de la structure de LaTeX.

## Importer des espaces de noms

Commençons par importer les espaces de noms nécessaires pour notre application .NET. Ces espaces de noms sont cruciaux pour interagir avec les fonctionnalités Aspose.TeX.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
using System.Text;
```

## Étape 1 : Configurer les options de conversion

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectLaTeX);
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

Ici, nous initialisons les options de conversion et définissons le répertoire de travail d'entrée pour vos fichiers LaTeX.

## Étape 2 : définir le mode d'interaction

```csharp
options.Interaction = Interaction.NonstopMode;
```

Spécifiez le mode d'interaction, où nous le définissons en mode non-stop pour une conversion ininterrompue.

## Étape 3 : Définir le nom du travail (facultatif)

```csharp
// options.JobName = "mon-nom-de-travail";
```

Vous pouvez définir un nom de tâche personnalisé si nécessaire.

## Étape 4 : définir la date dans le titre (facultatif)

```csharp
// options.DateTime = new System.DateTime(2022, 12, 18);
```

Forcez le moteur TeX à afficher une date spécifique dans le titre.

## Étape 5 : Ignorer les packages manquants

```csharp
options.IgnoreMissingPackages = true;
```

Définissez sur true si vous souhaitez que le moteur ignore les packages manquants sans erreur.

## Étape 6 : Désactiver les ligatures

```csharp
options.NoLigatures = true;
```

Défini sur true pour empêcher le moteur de construire des ligatures.

## Étape 7 : Répétez le travail (facultatif)

```csharp
// options.Répéter = vrai;
```

Demandez au moteur de répéter le travail si nécessaire.

## Étape 8 : Spécifier le répertoire de travail de sortie

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Définissez le répertoire de travail de sortie pour les fichiers XPS convertis.

## Étape 9 : initialiser les options de sauvegarde pour XPS

```csharp
options.SaveOptions = new XpsSaveOptions(); // Valeur par défaut. Cession arbitraire.
```

Initialisez les options d'enregistrement au format XPS.

## Étape 10 : pixelliser les formules (facultatif)

```csharp
options.SaveOptions.RasterizeFormulas = true;
```

Définissez sur true si vous souhaitez que les formules mathématiques soient converties en images raster.

## Étape 11 : pixelliser les graphiques inclus (facultatif)

```csharp
options.SaveOptions.RasterizeIncludedGraphics = true;
```

Définissez sur true si vous souhaitez que les graphiques inclus avec des éléments vectoriels soient convertis en images raster.

## Étape 12 : Sous-ensemble de polices

```csharp
options.SaveOptions.SubsetFonts = true;
```

Définissez sur true pour que les polices du sous-ensemble de périphérique soient utilisées dans le document.

## Étape 13 : Exécutez la conversion LaTeX vers XPS

```csharp
new TeXJob(Path.Combine("Your Input Directory", "sample.ltx"), new XpsDevice(), options).Run();
```

Lancez le processus de conversion LaTeX vers XPS.

## Étape 14 : Exécuter la conversion LaTeX vers XPS avec MemoryStream (alternative)

```csharp
// new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes (@"\documentclass{article} \begin{document} Bonjour tout le monde ! \end{document}")),
// nouveau XpsDevice(), options).Run();
```

Vous pouvez également exécuter la conversion à l'aide d'un MemoryStream pour saisir le contenu LaTeX.

## Étape 15 : Exécuter la conversion LaTeX en XPS avec le terminal d'entrée principal (alternative)

```csharp
// nouveau TeXJob(nouveau XpsDevice(), options).Run();
```

Exécutez la conversion directement depuis le terminal d’entrée principal.

## Conclusion

En suivant ces étapes simples, vous pouvez facilement convertir des documents LaTeX au format XPS à l'aide d'Aspose.TeX pour .NET. Cette puissante bibliothèque offre des options de flexibilité et de personnalisation pour répondre à vos besoins spécifiques.

## FAQ

### Q1 : Aspose.TeX est-il compatible avec les derniers frameworks .NET ?

A1 : Oui, Aspose.TeX est régulièrement mis à jour pour garantir la compatibilité avec les derniers frameworks .NET.

### Q2 : Puis-je personnaliser le format de sortie autre que XPS ?

 A2 : Aspose.TeX prend en charge différents formats de sortie. Se référer à la documentation[ici](https://reference.aspose.com/tex/net/) pour plus de détails.

### Q3 : Comment puis-je obtenir une licence temporaire pour Aspose.TeX ?

 A3 : Vous pouvez obtenir une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).

### Q4 : Où puis-je demander de l'aide ou partager mes expériences avec Aspose.TeX ?

 A4 : Visitez le forum Aspose.TeX[ici](https://forum.aspose.com/c/tex/47) pour le soutien de la communauté.

### Q5 : Existe-t-il des exemples de documents disponibles pour les tests ?

 A5 : Explorez les exemples Aspose.TeX[ici](https://github.com/aspose-tex/Aspose.TeX-for-.NET).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
