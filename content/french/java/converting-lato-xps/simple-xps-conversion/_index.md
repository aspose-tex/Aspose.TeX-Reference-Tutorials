---
title: Convertissez facilement LaTeX au format XPS en Java
linktitle: Convertissez facilement LaTeX au format XPS en Java
second_title: API Java Aspose.TeX
description: Convertissez LaTeX en XPS sans effort en Java à l'aide d'Aspose.TeX. Suivez notre guide étape par étape pour une intégration transparente.
type: docs
weight: 10
url: /fr/java/converting-lato-xps/simple-xps-conversion/
---
## Introduction

Cherchez-vous à convertir de manière transparente des documents LaTeX au format XPS dans vos applications Java ? Aspose.TeX pour Java fournit une solution puissante, vous permettant d'y parvenir facilement. Dans ce guide étape par étape, nous vous guiderons tout au long du processus de conversion de LaTeX en XPS à l'aide d'Aspose.TeX.

## Conditions préalables

Avant de vous lancer dans le processus de conversion, assurez-vous d'avoir les conditions préalables suivantes en place :

- Kit de développement Java (JDK) installé sur votre système.
-  Bibliothèque Aspose.TeX pour Java téléchargée. Vous pouvez trouver le lien de téléchargement[ici](https://releases.aspose.com/tex/java/).

## Importer des packages

Pour commencer, importez les packages nécessaires à votre projet Java. Assurez-vous d'inclure la bibliothèque Aspose.TeX dans les dépendances de votre projet.

```java
package com.aspose.tex.LaTeXXpsConversionSimplest;

import java.io.ByteArrayInputStream;
import java.io.IOException;
import java.util.Calendar;
import java.util.GregorianCalendar;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.Interaction;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;
import com.aspose.tex.rendering.XpsSaveOptions;

import util.Utils;
```

Décomposons maintenant le processus de conversion en plusieurs étapes à l'aide des exemples de code fournis.

## Étape 1 : définir les répertoires d'entrée et de sortie

```java
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Spécifiez les répertoires où se trouve votre fichier d'entrée LaTeX et où vous souhaitez enregistrer le fichier XPS converti.

## Étape 2 : configurer les options TeX

Configurez diverses options pour personnaliser le processus de conversion en fonction de vos besoins.

```java
options.setInteraction(Interaction.NonstopMode);
options.setDateTime(new GregorianCalendar(2022, Calendar.DECEMBER, 18).getTime());
options.ignoreMissingPackages(true);
options.noLigatures(true);
options.repeat(true);
```

Ajustez le mode d'interaction, la date dans le titre, la gestion des packages manquants, les ligatures et la répétition si nécessaire.

## Étape 3 : initialiser les options d'enregistrement XPS

```java
options.setSaveOptions(new XpsSaveOptions());
```

Initialisez les options d'enregistrement au format XPS.

## Étape 4 : Personnaliser les options d'enregistrement XPS

```java
options.getSaveOptions().rasterizeFormulas(true);
options.getSaveOptions().rasterizeIncludedGraphics(true);
options.getSaveOptions().subsetFonts(true);
```

Personnalisez les options d'enregistrement XPS pour contrôler la conversion des formules, des graphiques inclus et des sous-paramètres de polices.

## Étape 5 : exécutez la conversion LaTeX vers XPS

```java
new TeXJob("Your Input Directory" + "sample.ltx", new XpsDevice(), options).run();
```

Lancez le processus de conversion en exécutant une tâche TeX avec le fichier d'entrée, le périphérique de sortie (XpsDevice) et les options spécifiés.

## Exemples supplémentaires

Explorez des méthodes de conversion supplémentaires en utilisant différentes sources d'entrée :

### Utiliser InputStream

```java
new TeXJob(new ByteArrayInputStream(
    "\\documentclass{article} \\begin{document} Hello, World! \\end{document}".getBytes("ASCII")),
    new XpsDevice(), options).run();
```

### Utiliser la borne d'entrée principale

```java
new TeXJob(new XpsDevice(), options).run();
```

## Conclusion

Avec Aspose.TeX pour Java, la conversion de LaTeX en XPS est un jeu d'enfant. Suivez ces étapes, personnalisez les options et intégrez de manière transparente cette fonctionnalité dans vos applications Java.

## FAQ

### Q1 : Puis-je convertir des documents LaTeX avec des formules complexes à l’aide d’Aspose.TeX ?

A1 : Absolument ! Aspose.TeX gère les formules complexes de manière transparente pendant le processus de conversion.

### Q2 : Existe-t-il une version d’essai disponible pour Aspose.TeX pour Java ?

 A2 : Oui, vous pouvez trouver la version d'essai gratuite[ici](https://releases.aspose.com/).

### Q3 : Comment puis-je obtenir de l'aide pour Aspose.TeX ?

 A3 : Visitez le[Forum Aspose.TeX](https://forum.aspose.com/c/tex/47) pour obtenir de l’aide et du soutien communautaire.

### Q4 : Des licences temporaires sont-elles disponibles pour Aspose.TeX ?

 A4 : Oui, vous pouvez obtenir des licences temporaires[ici](https://purchase.aspose.com/temporary-license/).

### Q5 : Où puis-je trouver la documentation pour Aspose.TeX ?

 A5 : Reportez-vous au[Documentation](https://reference.aspose.com/tex/java/) pour des conseils complets.