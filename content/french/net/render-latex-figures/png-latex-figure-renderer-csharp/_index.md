---
title: Rendre les figures LaTeX au format PNG avec Aspose.TeX (C#)
linktitle: Rendre les figures LaTeX au format PNG avec Aspose.TeX (C#)
second_title: API Aspose.TeX .NET
description: Découvrez un guide complet sur le rendu des figures LaTeX au format PNG à l'aide d'Aspose.TeX en C#. Apprenez étape par étape avec des exemples de code.
type: docs
weight: 10
url: /fr/net/render-latex-figures/png-latex-figure-renderer-csharp/
---
## Introduction

Si vous plongez dans le monde de la composition et de la création de documents dans .NET, vous connaissez probablement les défis liés au rendu des figures LaTeX. Dans ce guide étape par étape, nous explorerons comment utiliser Aspose.TeX pour .NET pour restituer des figures LaTeX au format PNG à l'aide de C#. Aspose.TeX fournit une solution puissante et flexible pour gérer les documents LaTeX, ce qui en fait un outil inestimable pour les développeurs travaillant sur la génération et le formatage de documents.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :

-  Bibliothèque Aspose.TeX pour .NET : assurez-vous que la bibliothèque Aspose.TeX pour .NET est installée. Vous pouvez le télécharger[ici](https://releases.aspose.com/tex/net/).

## Importer des espaces de noms

Dans votre code C#, commencez par importer les espaces de noms nécessaires. Cette étape garantit que vous avez accès aux classes et fonctionnalités requises.

```csharp
using Aspose.TeX.Features;
```

## Rendre les figures LaTeX au format PNG

### Étape 1 : Configurer les options de rendu

Commencez par créer des options de rendu et définir des paramètres tels que la résolution de l'image, le préambule, le facteur d'échelle, la couleur d'arrière-plan, etc.

```csharp
FigureRendererOptions options = new PngFigureRendererOptions() { Resolution = 150 };
options.Preamble = "\\usepackage{pict2e}";
options.Scale = 3000;
options.BackgroundColor = System.Drawing.Color.White;
options.LogStream = new System.IO.MemoryStream();
options.ShowTerminal = true;
```

### Étape 2 : Définir le flux de sortie et les dimensions

Créez un flux de sortie pour l'image PNG et les variables afin de stocker les dimensions de l'image résultante.

```csharp
System.Drawing.SizeF size = new System.Drawing.SizeF();
using (System.IO.Stream stream = System.IO.File.Open(
   System.IO.Path.Combine("Your Output Directory", "text-and-formula.png"), System.IO.FileMode.Create))
{
    // Le code pour le rendu va ici
}
```

### Étape 3 : Exécuter le rendu

Implémentez le processus de rendu à l'aide de la bibliothèque Aspose.TeX. Fournissez le code LaTeX, le flux de sortie, les options de rendu et la variable de taille.

```csharp
new PngFigureRenderer().Render(@"\setlength{\unitlength}{0.8cm}
\begin{picture}(6,5)
    % LaTeX figure code goes here
\end{picture}", stream, options, out size);
```

### Étape 4 : Afficher les résultats

Enfin, affichez les résultats, y compris les éventuels rapports d'erreurs et la taille de l'image rendue.

```csharp
System.Console.Out.WriteLine(options.ErrorReport);
System.Console.Out.WriteLine();
System.Console.Out.WriteLine("Size: " + size);
```

## Conclusion

Avec Aspose.TeX pour .NET, le rendu des figures LaTeX au format PNG devient un processus transparent. Ce didacticiel vous a guidé à travers les étapes essentielles, depuis la configuration des options de rendu jusqu'à l'affichage des résultats finaux.

## FAQ

### Q1 : Aspose.TeX est-il compatible avec toutes les commandes LaTeX ?

 A1 : Aspose.TeX prend en charge un large éventail de commandes LaTeX, mais il est recommandé de se référer au[Documentation](https://reference.aspose.com/tex/net/) pour des informations détaillées.

### Q2 : Puis-je essayer Aspose.TeX avant d’acheter ?

 A2 : Oui, vous pouvez explorer une version d'essai gratuite[ici](https://releases.aspose.com/).

### Q3 : Comment puis-je obtenir de l'aide pour Aspose.TeX ?

 A3 : Visitez le[Forum Aspose.TeX](https://forum.aspose.com/c/tex/47)pour le soutien et les discussions de la communauté.

### Q4 : Où puis-je trouver des licences temporaires pour Aspose.TeX ?

 A4 : Des licences temporaires sont disponibles[ici](https://purchase.aspose.com/temporary-license/).

### Q5 : Quelle est la structure tarifaire d’Aspose.TeX ?

A5 : Explorez les détails des prix et effectuez un achat[ici](https://purchase.aspose.com/buy).