---
date: 2026-02-12
description: Apprenez comment capturer la sortie console en Java avec Aspose.TeX,
  écrire la sortie du terminal dans un fichier et remplacer le nom du travail. Ce
  guide étape par étape couvre également la redirection de la sortie console en Java.
linktitle: Write Terminal Output to File and Override Job Name in Java
second_title: Aspose.TeX Java API
title: Comment capturer la sortie console et remplacer le nom du job en Java
url: /fr/java/customizing-output/override-job-name-disk/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Écrire la sortie du terminal dans un fichier et remplacer le nom du job en Java

## Introduction

Dans ce tutoriel, vous découvrirez **comment capturer la sortie console** lors du traitement de fichiers TeX avec Aspose.TeX pour Java. Nous verrons comment écrire la sortie du terminal dans un fichier, remplacer le nom de travail par défaut, et rediriger la sortie console Java afin que les journaux soient faciles à localiser et à analyser. Ces techniques sont essentielles lorsque vous avez besoin d’une journalisation fiable pour des conversions par lots ou des pipelines de documents automatisés.

## Réponses rapides
- **Puis‑je changer le nom du travail ?** Oui, utilisez `options.setJobName(...)` avant d’exécuter le travail.  
- **Où la sortie du terminal est‑elle enregistrée ?** Elle est sauvegardée sous `<job_name>.trm` dans le répertoire de travail de sortie.  
- **Ai‑je besoin d’une licence pour cette fonctionnalité ?** La fonctionnalité fonctionne avec n’importe quelle licence valide d’Aspose.TeX ; un essai gratuit est également disponible.  
- **Quel est le format du fichier de sortie ?** Un journal du terminal en texte brut qui reflète la sortie console.  
- **Cette fonctionnalité est‑elle compatible avec d’autres périphériques de sortie ?** Absolument — une fois le journal écrit, vous pouvez le traiter avec n’importe quel outil lisant des fichiers texte.

## Qu’est‑ce que **how to capture console** dans le contexte d’Aspose.TeX ?

Capturer la sortie console signifie rediriger tout ce qui apparaîtrait normalement sur le flux de sortie standard (le terminal) vers un fichier sur le disque. Avec Aspose.TeX, vous pouvez le faire facilement en configurant un `OutputFileTerminal` et en l’assignant aux options de conversion.

## Pourquoi remplacer le nom du job ?

Remplacer le nom du job attribue à chaque exécution de conversion un identifiant unique. Cela rend les fichiers journaux générés (`*.trm`) et les autres artefacts plus faciles à suivre, notamment lors de l’exécution de plusieurs jobs en parallèle ou de la planification de processus par lots.

## Prérequis

- Compétence de base en programmation Java.  
- Aspose.TeX pour Java installé (téléchargez depuis la documentation officielle [Aspose.TeX Java documentation](https://reference.aspose.com/tex/java/)).  
- Un IDE Java ou un outil de construction (Maven/Gradle) prêt à compiler et exécuter l’exemple.

## Importer les packages

Pour commencer, importez les packages nécessaires dans votre projet Java. Dans votre fichier Java, incluez les importations suivantes :

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

> **Astuce :** Conservez l’import `util.Utils` uniquement si vous avez besoin des méthodes d’aide des utilitaires d’exemple Aspose ; sinon vous pouvez le supprimer pour garder le code propre.

## Comment capturer la sortie console en Java

Voici un guide étape par étape qui montre exactement comment configurer les options de conversion, remplacer le nom du job et diriger la sortie du terminal vers un fichier sur le disque.

### Étape 1 : Créer les options de conversion

Tout d’abord, créez une instance `TeXOptions` qui utilise la configuration par défaut d’ObjectTeX. Cet objet contiendra tous les paramètres du processus de conversion.

```java
// ExStart:OverrideJobName-WriteTerminalOutputToFileSystem
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
// ExEnd:OverrideJobName-WriteTerminalOutputToFileSystem
```

### Étape 2 : Spécifier le nom du job et les répertoires de travail

Ensuite, définissez un nom de job personnalisé et indiquez où se trouvent les fichiers d’entrée et de sortie. Si vous ne définissez pas de nom de job, le premier argument du constructeur `TeXJob` devient automatiquement le nom du job.

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

> **Pourquoi remplacer le nom du job ?**  
> Remplacer le nom du job rend les fichiers journaux et les artefacts générés plus faciles à identifier, surtout lorsque vous exécutez plusieurs jobs en parallèle ou automatisez le traitement par lots.

### Étape 3 : Écrire la sortie du terminal sur le système de fichiers

Indiquez à Aspose.TeX de capturer tout ce qui apparaîtrait normalement sur la console et de l’écrire dans un fichier. Le fichier sera nommé `<job_name>.trm` et placé dans le répertoire de travail de sortie que vous avez défini ci‑dessus.

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### Étape 4 : Exécuter le job

Enfin, créez un `TeXJob` avec le fichier d’entrée souhaité (ici nous utilisons un simple exemple « hello‑world ») et le dispositif de rendu XPS. Puis appelez `run()` pour exécuter la conversion.

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
```

Lorsque le job se termine, vous trouverez un fichier nommé `overridden-job-name.trm` dans **Your Output Directory** contenant le journal complet du terminal.

## Problèmes courants & dépannage

| Problème | Cause | Solution |
|----------|-------|----------|
| **Aucun fichier `.trm` généré** | `setTerminalOut` non appelé ou répertoire de sortie manquant | Vérifiez que le répertoire de sortie existe et que `options.setTerminalOut(...)` est exécuté avant `job.run()`. |
| **Le nom du fichier n’est pas le nom remplacé** | Nom du job mal défini | Assurez‑vous que `options.setJobName("your‑desired‑name")` est appelé **avant** de créer le `TeXJob`. |
| **Fichier journal vide** | Exceptions levées avant le démarrage de la journalisation | Enveloppez `job.run()` dans un bloc try‑catch et inspectez la trace de la pile d’exception pour des polices manquantes ou une source TeX malformée. |

## Questions fréquentes

**Q : Puis‑je utiliser Aspose.TeX pour Java avec d’autres bibliothèques Java ?**  
R : Oui, Aspose.TeX est conçu pour s’intégrer parfaitement avec d’autres bibliothèques Java, vous permettant de combiner des utilitaires PDF, image ou base de données dans le même flux de travail.

**Q : Où puis‑je trouver du support pour Aspose.TeX pour Java ?**  
R : Consultez le [forum Aspose.TeX](https://forum.aspose.com/c/tex/47) pour obtenir de l’aide de la communauté, ou ouvrez un ticket de support via le portail de support Aspose.

**Q : Existe‑t‑il un essai gratuit disponible pour Aspose.TeX pour Java ?**  
R : Absolument. Vous pouvez télécharger un essai pleinement fonctionnel depuis la [page d’essai gratuit Aspose.TeX](https://releases.aspose.com/).

**Q : Comment obtenir une licence temporaire pour les tests ?**  
R : Utilisez le formulaire de demande de licence temporaire sur [Aspose temporary license](https://purchase.aspose.com/temporary-license/) pour obtenir une licence d’évaluation de 30 jours.

**Q : Où puis‑je acheter une licence permanente ?**  
R : Achetez une licence directement sur la [page d’achat Aspose.TeX](https://purchase.aspose.com/buy).

---

**Dernière mise à jour** : 2026-02-12  
**Testé avec** : Aspose.TeX 24.11 for Java  
**Auteur** : Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}