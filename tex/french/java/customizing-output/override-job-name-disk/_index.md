---
date: 2025-12-05
description: Apprenez à écrire la sortie du terminal dans un fichier et à remplacer
  le nom d’un travail en utilisant Aspose.TeX pour Java. Suivez ce guide étape par
  étape avec des exemples de code complets.
linktitle: Write Terminal Output to File and Override Job Name in Java
second_title: Aspose.TeX Java API
title: Écrire la sortie du terminal dans un fichier et remplacer le nom de la tâche
  en Java
url: /fr/java/customizing-output/override-job-name-disk/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Écrire la sortie du terminal dans un fichier et remplacer le nom du travail en Java

## Introduction

Aspose.TeX for Java offre des fonctionnalités puissantes pour travailler avec des fichiers TeX, permettant aux développeurs de manipuler et de personnaliser le pipeline de traitement des documents TeX. Dans ce tutoriel, vous apprendrez **comment écrire la sortie du terminal dans un fichier** tout en remplaçant le nom du travail par défaut — deux capacités qui vous donnent un contrôle fin sur le traitement par lots et la journalisation.

## Réponses rapides
- **Puis‑je changer le nom du travail ?** Oui, utilisez `options.setJobName(...)` avant d’exécuter le travail.  
- **Où la sortie du terminal est‑elle enregistrée ?** Elle est sauvegardée sous `<job_name>.trm` dans le répertoire de travail de sortie.  
- **Ai‑je besoin d’une licence pour cette fonctionnalité ?** La fonctionnalité fonctionne avec n’importe quelle licence valide d’Aspose.TeX ; un essai gratuit est également disponible.  
- **Quel format a le fichier de sortie ?** Journal texte brut qui reflète la sortie console.  
- **Cette fonctionnalité est‑elle compatible avec d’autres périphériques de sortie ?** Absolument — une fois le journal écrit, vous pouvez le traiter avec n’importe quel outil lisant des fichiers texte.

## Prérequis

Avant de plonger dans le code, assurez‑vous de disposer de :

- Une bonne compréhension des fondamentaux de la programmation Java.  
- Aspose.TeX for Java installé (téléchargez‑le depuis la [documentation officielle d’Aspose.TeX Java](https://reference.aspose.com/tex/java/)).  
- Un IDE Java ou un outil de construction (Maven/Gradle) prêt à compiler et exécuter l’exemple.

## Importer les packages

Pour commencer, importez les packages nécessaires dans votre projet Java. Dans votre fichier Java, incluez les imports suivants :

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

> **Astuce :** Conservez l’import `util.Utils` uniquement si vous avez besoin des méthodes d’assistance des utilitaires d’exemple Aspose ; sinon, vous pouvez le supprimer pour garder le code propre.

## Comment écrire la sortie du terminal dans un fichier en Java

Voici un guide étape par étape qui montre exactement comment configurer les options de conversion, remplacer le nom du travail et diriger la sortie du terminal vers un fichier sur le disque.

### Étape 1 : Créer les options de conversion

Tout d’abord, créez une instance `TeXOptions` qui utilise la configuration par défaut ObjectTeX. Cet objet contiendra tous les paramètres du processus de conversion.

```java
// ExStart:OverrideJobName-WriteTerminalOutputToFileSystem
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
// ExEnd:OverrideJobName-WriteTerminalOutputToFileSystem
```

### Étape 2 : Spécifier le nom du travail et les répertoires de travail

Ensuite, définissez un nom de travail personnalisé et indiquez où se trouvent les fichiers d’entrée et de sortie. Si vous ne définissez pas de nom de travail, le premier argument du constructeur `TeXJob` devient automatiquement le nom du travail.

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

> **Pourquoi remplacer le nom du travail ?**  
> Remplacer le nom du travail rend les fichiers journaux et les artefacts générés plus faciles à identifier, surtout lorsque vous exécutez plusieurs travaux en parallèle ou automatisez le traitement par lots.

### Étape 3 : Écrire la sortie du terminal sur le système de fichiers

Indiquez à Aspose.TeX de capturer tout ce qui apparaîtrait normalement dans la console et de l’écrire dans un fichier. Le fichier sera nommé `<job_name>.trm` et placé dans le répertoire de travail de sortie que vous avez défini précédemment.

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### Étape 4 : Exécuter le travail

Enfin, créez un `TeXJob` avec le fichier d’entrée souhaité (ici nous utilisons un simple exemple « hello‑world ») et le dispositif de rendu XPS. Puis appelez `run()` pour lancer la conversion.

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
```

Lorsque le travail se termine, vous trouverez un fichier nommé `overridden-job-name.trm` dans **Votre répertoire de sortie** contenant le journal complet du terminal.

## Pièges courants et dépannage

| Problème | Cause | Solution |
|----------|-------|----------|
| **Aucun fichier `.trm` généré** | `setTerminalOut` non appelé ou répertoire de sortie manquant | Vérifiez que le répertoire de sortie existe et que `options.setTerminalOut(...)` est exécuté avant `job.run()`. |
| **Le nom du fichier n’est pas celui remplacé** | Nom du travail mal défini | Assurez‑vous que `options.setJobName("your‑desired‑name")` est appelé **avant** la création du `TeXJob`. |
| **Fichier journal vide** | Exceptions levées avant le démarrage de la journalisation | Enveloppez `job.run()` dans un bloc try‑catch et examinez la trace d’exception pour des polices manquantes ou une source TeX malformée. |

## Questions fréquentes

**Q : Puis‑je utiliser Aspose.TeX for Java avec d’autres bibliothèques Java ?**  
R : Oui, Aspose.TeX est conçu pour s’intégrer parfaitement avec d’autres bibliothèques Java, vous permettant de combiner des utilitaires PDF, image ou base de données dans le même flux de travail.

**Q : Où puis‑je obtenir de l’aide pour Aspose.TeX for Java ?**  
R : Visitez le [forum Aspose.TeX](https://forum.aspose.com/c/tex/47) pour obtenir de l’aide de la communauté, ou ouvrez un ticket de support via le portail de support Aspose.

**Q : Existe‑t‑il un essai gratuit pour Aspose.TeX for Java ?**  
R : Absolument. Vous pouvez télécharger un essai pleinement fonctionnel depuis la [page d’essai gratuit d’Aspose.TeX](https://releases.aspose.com/).

**Q : Comment obtenir une licence temporaire pour les tests ?**  
R : Utilisez le formulaire de demande de licence temporaire à [Aspose licence temporaire](https://purchase.aspose.com/temporary-license/) pour obtenir une licence d’évaluation de 30 jours.

**Q : Où puis‑je acheter une licence permanente ?**  
R : Achetez une licence directement depuis la [page d’achat d’Aspose.TeX](https://purchase.aspose.com/buy).

## Conclusion

Dans ce guide, nous avons démontré comment **écrire la sortie du terminal dans un fichier** et remplacer le nom du travail par défaut à l’aide d’Aspose.TeX for Java. Ces capacités vous permettent de conserver des journaux détaillés pour le débogage, d’automatiser le traitement par lots et de maintenir une structure de sortie propre et organisée—essentiel pour des pipelines de conversion de documents de niveau production.

---

**Dernière mise à jour :** 2025-12-05  
**Testé avec :** Aspose.TeX 24.11 for Java  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}