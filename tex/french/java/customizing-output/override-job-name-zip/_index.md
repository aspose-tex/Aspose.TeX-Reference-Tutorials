---
title: Remplacer le nom du travail et écrire la sortie du terminal dans Zip en Java
linktitle: Remplacer le nom du travail et écrire la sortie du terminal dans Zip en Java
second_title: API Java Aspose.TeX
description: Découvrez comment remplacer les noms de tâches et écrire la sortie du terminal au format ZIP en Java avec Aspose.TeX. Un tutoriel complet pour les développeurs Java.
weight: 11
url: /fr/java/customizing-output/override-job-name-zip/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Remplacer le nom du travail et écrire la sortie du terminal dans Zip en Java

## Introduction

Dans le monde du développement Java, Aspose.TeX s'impose comme un outil puissant pour gérer les formats de fichiers TeX. Dans ce didacticiel, nous aborderons un scénario spécifique : remplacer les noms de tâches et écrire la sortie du terminal dans un fichier zip. Ce guide étape par étape vous guidera tout au long du processus d'utilisation d'Aspose.TeX pour Java.

## Conditions préalables

Avant de nous lancer dans ce didacticiel, assurez-vous d'avoir les prérequis suivants en place :
- Connaissance de base de la programmation Java.
-  Aspose.TeX installé pour Java. Sinon, vous pouvez le télécharger depuis le[Site Aspose](https://releases.aspose.com/tex/java/).
- Une compréhension de la façon de configurer un environnement de développement Java.

## Importer des packages

Commencez par importer les packages nécessaires dans votre projet Java. Cela garantit que vous avez accès aux fonctionnalités Aspose.TeX requises pour la tâche.

```java
package com.aspose.tex.OverridenJobNameAndTerminalOutputWrittenToZip;

import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.io.OutputStream;

import com.aspose.tex.InputZipDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.OutputZipDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.PdfDevice;
import com.aspose.tex.rendering.PdfSaveOptions;

import util.Utils;
```

## Étape 1 : Ouvrir les archives ZIP

Tout d'abord, ouvrez un flux sur l'archive ZIP qui servira de répertoire de travail d'entrée. Il s'agit de l'archive à partir de laquelle vos données seront traitées.

```java
// Ouvrir un flux sur l'archive ZIP d'entrée
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
```

## Étape 2 : ouvrir l'archive ZIP de sortie

Ensuite, ouvrez un flux sur une archive ZIP qui servira de répertoire de travail de sortie. C'est ici que la sortie du terminal sera écrite.

```java
// Ouvrir un flux sur l'archive ZIP de sortie
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "terminal-out-to-zip.zip");
```

## Étape 3 : Définir les options de conversion

Créez des options de conversion pour le format ObjectTeX par défaut lors de l'extension du moteur ObjectTeX. Spécifiez un nom de travail et des répertoires de travail d'archive ZIP pour l'entrée et la sortie.

```java
// Créer des options TeX pour le format ObjectTeX
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("terminal-output-to-zip");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
```

## Étape 4 : Spécifier la sortie du terminal

 Spécifiez que la sortie du terminal doit être écrite dans un fichier dans le répertoire de travail de sortie. Le nom du fichier sera`<job_name>.trm`.

```java
// Spécifier les paramètres de sortie du terminal
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

## Étape 5 : définir les options d'enregistrement et exécuter le travail

Définissez les options d'enregistrement, telles que les options d'enregistrement PDF dans ce cas. Exécutez le travail TeX pour exécuter la conversion.

```java
// Définir les options d'enregistrement et exécuter le travail
options.setSaveOptions(new PdfSaveOptions());
new TeXJob("hello-world", new PdfDevice(), options).run();
```

## Étape 6 : Finaliser l'archive ZIP de sortie

Une fois le travail terminé, finalisez l'archive ZIP de sortie pour garantir une exécution correcte.

```java
// Finaliser l'archive ZIP de sortie
((OutputZipDirectory) options.getOutputWorkingDirectory()).finish();
```

## Conclusion

Toutes nos félicitations! Vous avez appris avec succès comment remplacer les noms de tâches et écrire la sortie du terminal dans un fichier ZIP en Java à l'aide d'Aspose.TeX. Cette fonctionnalité puissante ajoute flexibilité et efficacité à vos projets de développement Java.

## FAQ

### Q1 : Qu'est-ce qu'Aspose.TeX ?

A1 : Aspose.TeX est une bibliothèque Java qui permet aux développeurs de travailler avec les formats de fichiers TeX, offrant des fonctionnalités avancées pour le traitement des documents.

### Q2 : Comment puis-je obtenir une licence temporaire pour Aspose.TeX ?

 A2 : Vous pouvez obtenir une licence temporaire auprès de[ce lien](https://purchase.aspose.com/temporary-license/).

### Q3 : Où puis-je trouver la documentation Aspose.TeX ?

 A3 : La documentation est disponible[ici](https://reference.aspose.com/tex/java/).

### Q4 : Existe-t-il une version d’essai gratuite d’Aspose.TeX ?

 A4 : Oui, vous pouvez trouver la version d'essai gratuite[ici](https://releases.aspose.com/).

### Q5 : Où puis-je demander de l'aide ou poser des questions sur Aspose.TeX ?

 A5 : Visitez le[Forum Aspose.TeX](https://forum.aspose.com/c/tex/47) pour du soutien et des discussions.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
