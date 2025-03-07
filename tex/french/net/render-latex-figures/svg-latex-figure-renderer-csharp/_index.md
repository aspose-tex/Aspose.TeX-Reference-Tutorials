---
title: Rendre les figures LaTeX en SVG avec Aspose.TeX (C#)
linktitle: Rendre les figures LaTeX en SVG avec Aspose.TeX (C#)
second_title: API Aspose.TeX .NET
description: Améliorez le rendu des documents dans .NET avec Aspose.TeX. Découvrez comment restituer des figures LaTeX au format SVG en C# pour une intégration transparente des expressions mathématiques.
weight: 11
url: /fr/net/render-latex-figures/svg-latex-figure-renderer-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Rendre les figures LaTeX en SVG avec Aspose.TeX (C#)

## Introduction

Si vous souhaitez améliorer vos capacités de rendu de documents dans .NET à l'aide de chiffres LaTeX, Aspose.TeX est votre solution incontournable. Dans ce guide étape par étape, nous vous guiderons dans le rendu des figures LaTeX au format SVG à l'aide d'Aspose.TeX en C#. À la fin de ce didacticiel, vous aurez une compréhension claire du processus, ce qui vous permettra d'incorporer de manière transparente des expressions et des chiffres mathématiques de haute qualité dans vos documents.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :

- Connaissance de base du langage de programmation C#.
-  Aspose.TeX pour la bibliothèque .NET installée. Vous pouvez le télécharger[ici](https://releases.aspose.com/tex/net/).

## Importer des espaces de noms

Dans votre code C#, assurez-vous d'importer les espaces de noms nécessaires :

```csharp
using Aspose.TeX.Features;
```

Maintenant, décomposons le didacticiel en plusieurs étapes :

## Étape 1 : Créer des options de rendu

```csharp
FigureRendererOptions options = new SvgFigureRendererOptions();
options.Preamble = "\\usepackage{pict2e}";
options.Scale = 3000;
options.BackgroundColor = Color.White;
options.LogStream = new System.IO.MemoryStream();
options.ShowTerminal = true;
```

Ici, nous configurons les options de rendu, en spécifiant le préambule, le facteur de mise à l'échelle, la couleur d'arrière-plan, le flux de journal et s'il faut afficher la sortie du terminal.

## Étape 2 : Définir les dimensions et le flux de sortie

```csharp
SizeF size = new SizeF();
using (Stream stream = File.Open(Path.Combine("Your Output Directory", "text-and-formula.svg"), FileMode.Create))
{
    // Exécutez le rendu.
    new SvgFigureRenderer().Render("Your LaTeX Code", stream, options, out size);
}
```

Remplacez « Votre répertoire de sortie » par le répertoire souhaité et fournissez votre code LaTeX sous forme de chaîne.

## Étape 3 : Afficher les résultats

```csharp
Console.Out.WriteLine(options.ErrorReport);
Console.Out.WriteLine();
Console.Out.WriteLine("Size: " + size);
```

Cette étape affiche tous les rapports d'erreur et la taille de l'image résultante.

## Conclusion

Toutes nos félicitations! Vous avez appris avec succès comment restituer des figures LaTeX en SVG à l'aide d'Aspose.TeX en C#. Désormais, vous pouvez intégrer de manière transparente des expressions et des chiffres mathématiques dans vos applications .NET.

## FAQ

### Q1 : L'utilisation d'Aspose.TeX est-elle gratuite ?

 A1 : Aspose.TeX propose un essai gratuit. Vous pouvez y accéder[ici](https://releases.aspose.com/).

### Q2 : Où puis-je trouver la documentation Aspose.TeX ?

 A2 : Se référer à la documentation[ici](https://reference.aspose.com/tex/net/).

### Q3 : Comment puis-je obtenir de l'aide pour Aspose.TeX ?

 A3 : Visitez le forum d'assistance[ici](https://forum.aspose.com/c/tex/47).

### Q4 : Puis-je acheter Aspose.TeX ?

 A4 : Oui, vous pouvez acheter Aspose.TeX[ici](https://purchase.aspose.com/buy).

### Q5 : Ai-je besoin d’une licence temporaire ?

 A5 : Si nécessaire, vous pouvez obtenir un permis temporaire[ici](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
