---
title: Remplacer le nom du travail et écrire la sortie du terminal en Java
linktitle: Remplacer le nom du travail et écrire la sortie du terminal en Java
second_title: API Java Aspose.TeX
description: Explorez le guide étape par étape sur le remplacement des noms de tâches et l'écriture de la sortie du terminal à l'aide d'Aspose.TeX pour Java. Améliorez le traitement de vos documents grâce à de puissantes options de personnalisation.
type: docs
weight: 10
url: /fr/java/customizing-output/override-job-name-disk/
---
## Introduction

Aspose.TeX pour Java fournit des fonctionnalités puissantes pour travailler avec des fichiers TeX, permettant aux développeurs de manipuler et de personnaliser le traitement des documents TeX. Dans ce didacticiel, nous vous guiderons tout au long du processus de remplacement du nom du travail et d'écriture de la sortie du terminal sur le système de fichiers à l'aide d'Aspose.TeX en Java.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :

- Une connaissance pratique de la programmation Java.
-  Aspose.TeX pour Java installé. Vous pouvez le télécharger depuis le[Documentation Java Aspose.TeX](https://reference.aspose.com/tex/java/).

## Importer des packages

Pour commencer, importez les packages nécessaires dans votre projet Java. Dans votre fichier Java, incluez les importations suivantes :

```java
package com.aspose.tex.OverridenJobNameAndTerminalOutputWrittenToDisk;

import java.io.IOException;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

## Remplacer le nom du travail et la sortie du terminal d'écriture

### Étape 1 : Créer des options de conversion

Commencez par créer des options de conversion pour le format ObjectTeX par défaut lors de l'extension du moteur ObjectTeX. Utilisez l'extrait de code suivant :

```java
//ExStart : OverrideJobName-WriteTerminalOutputToFileSystem
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

### Étape 2 : Spécifiez le nom du travail et les répertoires de travail

Spécifiez un nom de travail, un répertoire de travail d'entrée et un répertoire de travail de sortie. Si le nom du travail n'est pas spécifié, le premier argument du constructeur TeXJob sera pris comme nom du travail. Utilisez l'extrait de code suivant :

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### Étape 3 : Écrire la sortie du terminal dans le système de fichiers

 Spécifiez que la sortie du terminal doit être écrite dans un fichier dans le répertoire de travail de sortie. Le nom du fichier sera`<job_name>.trm`. Ajoutez le code suivant :

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### Étape 4 : Exécuter le travail

Exécutez le travail TeX en utilisant les options et le nom du travail spécifiés. Voici comment procéder :

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
// ExEnd : OverrideJobName-WriteTerminalOutputToFileSystem
```

Toutes nos félicitations! Vous avez réussi à remplacer le nom du travail et à écrire la sortie du terminal sur le système de fichiers à l'aide d'Aspose.TeX en Java.

## Conclusion

Dans ce didacticiel, nous avons exploré comment utiliser Aspose.TeX pour Java pour remplacer le nom du travail et capturer la sortie du terminal. Ces fonctionnalités permettent aux développeurs d'avoir un contrôle précis sur le traitement des documents TeX, améliorant ainsi la personnalisation et la flexibilité.

## FAQ

### Q1 : Puis-je utiliser Aspose.TeX pour Java avec d’autres bibliothèques Java ?

A1 : Oui, Aspose.TeX pour Java est conçu pour s'intégrer de manière transparente à d'autres bibliothèques Java afin d'améliorer vos capacités de traitement de documents.

### Q2 : Où puis-je trouver du support pour Aspose.TeX pour Java ?

 A2 : Visitez le[Forum Aspose.TeX](https://forum.aspose.com/c/tex/47) pour le soutien et l’assistance de la communauté pour tout problème que vous pourriez rencontrer.

### Q3 : Existe-t-il un essai gratuit disponible pour Aspose.TeX pour Java ?

 A3 : Oui, vous pouvez accéder à la version d'essai gratuite d'Aspose.TeX pour Java[ici](https://releases.aspose.com/).

### Q4 : Comment puis-je obtenir une licence temporaire pour Aspose.TeX pour Java ?

 A4 : Suivez ceci[lien](https://purchase.aspose.com/temporary-license/) pour obtenir une licence temporaire à des fins de tests et d’évaluation.

### Q5 : Où puis-je acheter Aspose.TeX pour Java ?

 A5 : Visitez le[page d'achat](https://purchase.aspose.com/buy) pour acquérir une licence pour Aspose.TeX pour Java.