---
title: Rendre les figures LaTeX en SVG en Java
linktitle: Rendre les figures LaTeX en SVG en Java
second_title: API Java Aspose.TeX
description: Apprenez à restituer sans effort des figures LaTeX au format SVG en Java à l'aide d'Aspose.TeX. Suivez ce guide étape par étape pour une intégration transparente.
type: docs
weight: 14
url: /fr/java/customizing-output/render-lafigures-svg/
---
## Introduction

La création et le rendu de figures LaTeX en Java peuvent être une tâche complexe mais cruciale pour diverses applications. Dans ce didacticiel, nous allons explorer comment restituer des figures LaTeX au format SVG à l'aide d'Aspose.TeX pour Java. Aspose.TeX fournit des fonctionnalités puissantes pour gérer les documents LaTeX et les convertir en différents formats, dont SVG.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous d'avoir les prérequis suivants :

- Environnement de développement Java : assurez-vous d'avoir configuré un environnement de développement Java sur votre système.
-  Aspose.TeX pour Java : téléchargez et installez la bibliothèque Aspose.TeX pour Java à partir du[lien de téléchargement](https://releases.aspose.com/tex/java/).
- Compréhension de base de LaTeX : Familiarisez-vous avec la syntaxe de base de LaTeX et la création de figures.

## Importer des packages

Pour commencer, importez les packages nécessaires depuis Aspose.TeX. Ces packages fourniront les outils nécessaires au rendu des figures LaTeX en SVG.

```java
package com.aspose.tex.SvgLaTeXFigureRenderer;

import java.awt.Color;
import java.io.ByteArrayOutputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.OutputStream;

import com.aspose.tex.SvgFigureRenderer;
import com.aspose.tex.SvgFigureRendererOptions;

import util.Utils;
```

## Étape 1 : Configurer les options de rendu

Créez des options de rendu, en spécifiant des paramètres tels que le préambule, le facteur de mise à l'échelle, la couleur d'arrière-plan, le flux de journaux et la visibilité de la sortie du terminal.

```java
SvgFigureRendererOptions options = new SvgFigureRendererOptions();
options.setPreamble("\\usepackage{pict2e}");
options.setScale(3000);
options.setBackgroundColor(Color.WHITE);
options.setLogStream(new ByteArrayOutputStream());
options.showTerminal(true);
```

## Étape 2 : Définir la figure LaTeX et le répertoire de sortie

Définissez la figure LaTeX que vous souhaitez restituer et spécifiez le répertoire de sortie du fichier SVG.

```java
com.aspose.tex.Size2D size = new com.aspose.tex.Size2D.Float();
final OutputStream stream = new FileOutputStream("Your Output Directory" + "text-and-formula.svg");
```

## Étape 3 : Exécuter le rendu

 Exécutez le processus de rendu en utilisant le`SvgFigureRenderer` classe.

```java
new SvgFigureRenderer().render("\\setlength{\\unitlength}{0.8cm}\r\n" +
    // Contenu des figures LaTeX
    "\\begin{picture}(6,5)\r\n" +
    // ... (détails des figures)
    "\\end{picture}", stream, options, size);
```

## Étape 4 : Fermer le flux de sortie

Assurez-vous de fermer le flux de sortie après le rendu.

```java
if (stream != null)
    stream.close();
```

## Étape 5 : Afficher les résultats

Affichez tous les rapports d'erreur et les dimensions de l'image SVG résultante.

```java
System.out.println(options.getErrorReport());
System.out.println();
System.out.println("Size: " + size.getWidth() + "x" + size.getHeight());
```

En suivant ces étapes, vous pouvez restituer de manière transparente les figures LaTeX au format SVG à l'aide d'Aspose.TeX pour Java.

## Conclusion

Le rendu des figures LaTeX au format SVG en Java peut être réalisé efficacement avec Aspose.TeX. Ce guide étape par étape vous a guidé tout au long du processus, depuis la configuration des options de rendu jusqu'à l'affichage des résultats finaux. Expérimentez avec différentes figures LaTeX pour améliorer votre compréhension et votre application de cette fonctionnalité puissante.

## FAQ

### Q1 : Puis-je restituer des figures LaTeX avec des expressions mathématiques complexes à l'aide d'Aspose.TeX ?

A1 : Oui, Aspose.TeX prend en charge le rendu des figures LaTeX avec des expressions mathématiques complexes.

### Q2 : Une licence temporaire est-elle disponible pour Aspose.TeX pour Java ?

 A2 : Oui, vous pouvez obtenir une licence temporaire auprès de[ici](https://purchase.aspose.com/temporary-license/).

### Q3 : Comment puis-je obtenir une assistance pour Aspose.TeX pour Java ?

 A3 : Visitez le[Forum Aspose.TeX](https://forum.aspose.com/c/tex/47) pour un soutien communautaire.

### Q4 : Dans quels formats puis-je convertir des chiffres LaTeX en utilisant Aspose.TeX ?

A4 : Aspose.TeX permet la conversion vers différents formats, notamment SVG, PNG, etc.

### Q5 : Où puis-je trouver une documentation détaillée pour Aspose.TeX pour Java ?

 A5 : Reportez-vous au[Documentation Aspose.TeX](https://reference.aspose.com/tex/java/) pour des informations complètes.