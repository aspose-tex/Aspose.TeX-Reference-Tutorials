---
title: Composer TeX en PDF en Java avec flux externe
linktitle: Composer TeX en PDF en Java avec flux externe
second_title: API Java Aspose.TeX
description: Découvrez comment composer TeX en PDF en Java à l'aide de flux externes avec Aspose.TeX. Suivez notre guide étape par étape pour une intégration transparente.
type: docs
weight: 10
url: /fr/java/typesetting-tex-to-pdf/typeset-tex-to-pdf-external-stream/
---
## Introduction

Dans le monde du développement Java, la création de PDF à partir de fichiers TeX est une exigence courante. Aspose.TeX pour Java simplifie ce processus, fournissant une solution efficace pour la composition de TeX en PDF. Dans ce didacticiel, nous vous guiderons à travers les étapes de composition de TeX en PDF à l'aide de flux externes. À la fin, vous comprendrez clairement comment implémenter ce processus de manière transparente dans vos applications Java.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :

- Aspose.TeX pour Java : assurez-vous que la bibliothèque Aspose.TeX pour Java est installée. Vous pouvez le télécharger depuis le[Documentation Aspose.TeX pour Java](https://reference.aspose.com/tex/java/).

- Répertoires d'entrée et de sortie : préparez les répertoires d'entrée et de sortie. Vous pouvez utiliser le lien de téléchargement fourni pour obtenir les fichiers nécessaires.

## Importer des packages

Commencez par importer les packages requis dans votre projet Java :

```java
package com.aspose.tex.TypesetPdfWrittenToExternalStream;

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

## Étape 1 : Ouvrir les flux d'entrée et de sortie

Commencez par ouvrir les flux pour l'archive ZIP d'entrée (agissant comme répertoire de travail d'entrée) et l'archive ZIP de sortie (servant de répertoire de travail de sortie). Assurez-vous de remplacer « Votre répertoire d'entrée » et « Votre répertoire de sortie » par vos chemins de répertoire réels.

```java
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "typeset-pdf-to-external-stream.zip");
```

## Étape 2 : configurer TeXOptions

Créez l'objet TeXOptions et configurez-le selon vos besoins. Définissez le nom du travail, le répertoire de travail d'entrée, le répertoire de travail de sortie et d'autres options.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("typeset-pdf-to-external-stream");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
options.setSaveOptions(new PdfSaveOptions());
```

## Étape 3 : composer TeX en PDF

Maintenant, ouvrez un flux pour écrire le PDF de sortie à l'emplacement souhaité. Vous pouvez choisir de l'écrire dans un fichier local ou directement dans l'archive ZIP de sortie.

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + "file-name.pdf");
try {
    new TeXJob("hello-world", new PdfDevice(stream), options).run();
} finally {
    stream.close();
}
```

## Étape 4 : Finaliser l'archive ZIP de sortie

Terminez l'archive ZIP de sortie pour terminer le processus de composition.

```java
((OutputZipDirectory)options.getOutputWorkingDirectory()).finish();
```

## Conclusion

Toutes nos félicitations! Vous avez réussi à composer TeX en PDF en Java en utilisant des flux externes avec Aspose.TeX. Ce didacticiel fournit une base solide pour intégrer de manière transparente la conversion TeX en PDF dans vos applications Java.

## FAQ

### Q1 : Puis-je personnaliser le nom du fichier PDF de sortie ?

 A1 : Oui, vous pouvez modifier le`options.setJobName("typeset-pdf-to-external-stream")` pour définir le nom du travail souhaité.

### Q2 : Comment résoudre les problèmes courants lors de la composition ?

 A2 : Visitez le[Forum Aspose.TeX](https://forum.aspose.com/c/tex/47) pour le soutien et l’assistance de la communauté.

### Q3 : Existe-t-il un essai gratuit disponible pour Aspose.TeX pour Java ?

 A3 : Oui, vous pouvez accéder à l'essai gratuit[ici](https://releases.aspose.com/).

### Q4 : Où puis-je trouver de la documentation et des exemples supplémentaires ?

 A4 : Explorer l'ensemble[Documentation Aspose.TeX](https://reference.aspose.com/tex/java/) pour des informations détaillées.

### Q5 : Puis-je obtenir une licence temporaire pour Aspose.TeX ?

 A5 : Oui, vous pouvez demander une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).