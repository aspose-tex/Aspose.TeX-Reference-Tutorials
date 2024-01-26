---
title: Composer TeX en XPS en Java avec flux externe
linktitle: Composer TeX en XPS en Java avec flux externe
second_title: API Java Aspose.TeX
description: Découvrez comment composer TeX en XPS en Java à l'aide d'Aspose.TeX. Découvrez des conseils étape par étape pour un traitement fluide des documents.
type: docs
weight: 10
url: /fr/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
---
## Introduction

Dans le monde du développement Java, Aspose.TeX se distingue comme un outil puissant pour composer des documents TeX dans différents formats, dont XPS. Si vous souhaitez améliorer les capacités de traitement de documents de votre application Java, ce didacticiel est conçu pour vous. Dans ce guide étape par étape, nous vous guiderons tout au long du processus de composition de TeX vers XPS à l'aide d'Aspose.TeX pour Java avec un flux externe.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :

-  Kit de développement Java (JDK) : assurez-vous que Java est installé sur votre système. Vous pouvez le télécharger depuis[ici](https://www.oracle.com/java/technologies/javase-downloads.html).

-  Aspose.TeX pour Java : Téléchargez et installez Aspose.TeX pour Java. Vous pouvez trouver le lien de téléchargement[ici](https://releases.aspose.com/tex/java/).

## Importer des packages

Commencez par importer les packages nécessaires pour lancer votre parcours de conversion TeX vers XPS. Incluez l'extrait de code suivant dans votre projet Java :

```java
package com.aspose.tex.TypesetXpsWrittenToExternalStream;

import java.io.FileOutputStream;
import java.io.IOException;
import java.io.OutputStream;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

## Étape 1 : Configurer les options de conversion

Commencez par créer des options de conversion pour le format ObjectTeX par défaut à l'aide du code suivant :

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

Cela jette les bases du processus de composition.

## Étape 2 : Spécifiez le nom du travail et les répertoires

Définissez un nom de tâche et définissez les répertoires de travail d'entrée et de sortie :

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Assurez-vous de remplacer les espaces réservés tels que « Votre répertoire d'entrée » par vos chemins de répertoire réels.

## Étape 3 : configurer la sortie du terminal

Spécifiez que la sortie du terminal doit être écrite dans un fichier dans le répertoire de travail de sortie :

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

Cette étape garantit que les journaux détaillés sont capturés pour le débogage.

## Étape 4 : ouvrir le flux de sortie

Ouvrez un flux pour écrire le document XPS composé :

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

Remplacez « Votre répertoire de sortie » par le chemin approprié.

## Étape 5 : Exécuter le travail

Exécutez le travail de conversion TeX en XPS :

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

Ceci termine le processus et vous trouverez votre document XPS composé dans le répertoire de sortie spécifié.

## Conclusion

Toutes nos félicitations! Vous avez réussi à composer TeX en XPS en Java à l'aide d'Aspose.TeX. Cela ouvre un monde de possibilités pour le traitement des documents dans vos applications Java. Expérimentez avec différents fichiers TeX et explorez les diverses fonctionnalités offertes par Aspose.TeX.

## FAQ

### Q1 : Puis-je utiliser Aspose.TeX pour Java avec d’autres formats de document ?

A1 : Aspose.TeX se concentre principalement sur le traitement de documents liés à TeX. Pour d'autres formats, explorez la vaste gamme de produits Aspose.

### Q2 : Existe-t-il une version d'essai disponible ?

 A2 : Oui, vous pouvez découvrir Aspose.TeX en téléchargeant la version d'essai gratuite[ici](https://releases.aspose.com/).

### Q3 : Où puis-je trouver une documentation complète ?

 A3 : Se référer à la documentation[ici](https://reference.aspose.com/tex/java/) pour des informations détaillées et des exemples.

### Q4 : Comment puis-je obtenir de l'aide ou demander de l'aide ?

 A4 : Visitez le forum Aspose.TeX[ici](https://forum.aspose.com/c/tex/47)pour le soutien et les discussions de la communauté.

### Q5 : Puis-je obtenir une licence temporaire à des fins de test ?

 A5 : Oui, vous pouvez acquérir une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).