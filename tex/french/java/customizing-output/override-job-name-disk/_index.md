---
date: 2026-08-18
description: Apprenez comment rediriger la console output en Java en utilisant Aspose.TeX,
  écrire le terminal output dans un file, et remplacer le job name pour un meilleur
  logging.
keywords:
- redirect console output java
- Aspose.TeX Java
- Java logging
- override job name
lastmod: 2026-08-18
linktitle: Écrire le Terminal Output dans un File et remplacer le Job Name en Java
og_description: Rediriger la console output en Java avec Aspose.TeX et remplacer le
  job name pour générer des log files distincts. Suivez ce step‑by‑step tutorial pour
  un logging fiable.
og_image_alt: Screenshot of Java console output redirection using Aspose.TeX
og_title: Rediriger la console output en Java et remplacer le job name – guide Aspose.TeX
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Learn how to redirect console output in Java using Aspose.TeX, write
    terminal output to a file, and override the job name for better logging.
  headline: How to redirect console output in Java and override job name
  type: TechArticle
- description: Learn how to redirect console output in Java using Aspose.TeX, write
    terminal output to a file, and override the job name for better logging.
  name: How to redirect console output in Java and override job name
  steps:
  - name: create conversion options
    text: '`TeXOptions` is the configuration object that controls how Aspose.TeX processes
      a TeX job. It holds settings such as output format, font handling, and terminal
      redirection.'
  - name: specify job name and working directories
    text: '`TeXJob` represents a single conversion task, linking input, output, and
      options together. Setting a custom job name ensures the generated log file is
      uniquely named. > **Why override the job name?** > Overriding the job name makes
      log files and generated artifacts easier to identify, especially whe'
  - name: write terminal output to file system
    text: '`setTerminalOut` tells Aspose.TeX where to write the console log file.
      The file will be named `<job_name>.trm` and placed in the output working directory
      you defined above. Configure the terminal output redirection:'
  - name: run the job
    text: '`run()` executes the conversion based on the supplied options and writes
      output files (including the `.trm` log) to the designated folder. Create a `TeXJob`
      with the desired input file (here we use a simple “hello‑world” example) and
      the XPS rendering device, then call `run()`: When the job finishes'
  type: HowTo
- questions:
  - answer: Yes, Aspose.TeX integrates seamlessly with other Java libraries, allowing
      you to combine PDF, image, or database utilities in the same workflow.
    question: Can I use Aspose.TeX for Java with other Java libraries?
  - answer: Visit the [Aspose.TeX forum](https://forum.aspose.com/c/tex/47) for community
      help, or open a support ticket through the Aspose support portal.
    question: Where can I find support for Aspose.TeX for Java?
  - answer: Absolutely. You can download a fully functional trial from the [Aspose.TeX
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.TeX for Java?
  - answer: Use the temporary‑license request form at [Aspose temporary license](https://purchase.aspose.com/temporary-license/)
      to get a 30‑day evaluation license.
    question: How can I obtain a temporary license for testing?
  - answer: Purchase a license directly from the [Aspose.TeX buying page](https://purchase.aspose.com/buy).
    question: Where can I purchase a permanent license?
  type: FAQPage
second_title: Aspose.TeX Java API
tags:
- redirect console output
- Aspose.TeX
- Java console logging
- job name override
title: Comment rediriger la console output en Java et remplacer le job name
url: /fr/java/customizing-output/override-job-name-disk/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Écrire la sortie du terminal dans un fichier et remplacer le nom du job en Java

## Introduction

Dans ce tutoriel, vous apprendrez comment **rediriger la sortie console en Java** lors du traitement de fichiers TeX avec Aspose.TeX. Nous vous montrerons comment écrire le journal du terminal dans un fichier `.trm`, remplacer le nom du job par défaut et garder vos journaux organisés pour les conversions par lots ou les pipelines automatisés. Aspose.TeX prend en charge **plus de 30 formats d’entrée et de sortie** et peut traiter des documents contenant jusqu’à **500 pages** sans charger le fichier complet en mémoire, ce qui le rend idéal pour les scénarios à haut volume.

## Réponses rapides

`options.setJobName(String name)` définit un identifiant de job personnalisé qui sera utilisé pour les fichiers de journal et de sortie générés.

- **Puis‑je changer le nom du job ?** Oui – appelez `options.setJobName("my‑job")` avant de créer le `TeXJob`.  
- **Où la sortie du terminal est‑elle enregistrée ?** Elle est sauvegardée sous `<job_name>.trm` dans le répertoire de travail de sortie que vous spécifiez.  
- **Ai‑je besoin d’une licence pour cette fonctionnalité ?** La fonctionnalité fonctionne avec n’importe quelle licence valide d’Aspose.TeX ; un essai gratuit est également disponible.  
- **Quel est le format du fichier de sortie ?** Journal du terminal en texte brut qui reflète tout ce qui est imprimé dans la console.  
- **Cette fonctionnalité est‑elle compatible avec d’autres périphériques de sortie ?** Absolument – une fois le journal écrit, vous pouvez le transmettre à n’importe quel outil de traitement de texte.

## Qu’est‑ce que **how to capture console** dans le contexte d’Aspose.TeX ?

Capturer la sortie console signifie rediriger tout ce qui apparaîtrait normalement sur le flux de sortie standard (le terminal) vers un fichier sur le disque. Avec Aspose.TeX, vous pouvez le faire facilement en configurant un `OutputFileTerminal` et en l’assignant aux options de conversion.

## Pourquoi remplacer le nom du job ?

Remplacer le nom du job attribue à chaque exécution de conversion un identifiant unique. Cela rend les fichiers de journal générés (`*.trm`) et les autres artefacts plus faciles à suivre, surtout lorsqu’on exécute plusieurs jobs en parallèle ou que l’on planifie des processus par lots. En fournissant un nom distinct, vous évitez également d’écraser les journaux précédents et simplifiez les scripts de post‑traitement qui s’appuient sur des noms de fichiers prévisibles.

## Prérequis

- Bonne maîtrise de la programmation Java.  
- Aspose.TeX pour Java installé (téléchargez-le depuis la documentation officielle [Aspose.TeX Java documentation](https://reference.aspose.com/tex/java/)).  
- Un IDE Java ou un outil de construction (Maven/Gradle) prêt à compiler et exécuter l’exemple.

## Importer les packages

Pour commencer, importez les packages nécessaires dans votre projet Java. Dans votre fichier Java, ajoutez les importations suivantes :

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

> **Astuce :** Conservez l’import `util.Utils` uniquement si vous avez besoin des méthodes d’aide des utilitaires d’exemple Aspose ; sinon, vous pouvez le supprimer pour garder le code propre.

## Comment capturer la sortie du terminal en Java

Voici un guide étape par étape qui montre exactement comment configurer les options de conversion, remplacer le nom du job et diriger la sortie du terminal vers un fichier sur le disque. Les étapes suivantes illustrent les appels d’API requis et démontrent comment préparer l’environnement afin que tous les messages du terminal soient capturés sans modifier le code cœur d’Aspose.TeX.

### Étape 1 : créer les options de conversion

`TeXOptions` est l’objet de configuration qui contrôle la façon dont Aspose.TeX traite un job TeX. Il contient des paramètres tels que le format de sortie, la gestion des polices et la redirection du terminal.

```java
// ExStart:OverrideJobName-WriteTerminalOutputToFileSystem
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
// ExEnd:OverrideJobName-WriteTerminalOutputToFileSystem
```

### Étape 2 : spécifier le nom du job et les répertoires de travail

`TeXJob` représente une tâche de conversion unique, reliant l’entrée, la sortie et les options. Définir un nom de job personnalisé garantit que le fichier de journal généré porte un nom unique.

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

> **Pourquoi remplacer le nom du job ?**  
> Remplacer le nom du job rend les fichiers de journal et les artefacts générés plus faciles à identifier, surtout lorsque vous exécutez plusieurs jobs en parallèle ou automatisez le traitement par lots.

### Étape 3 : écrire la sortie du terminal sur le système de fichiers

`setTerminalOut` indique à Aspose.TeX où écrire le fichier de journal du terminal. Le fichier sera nommé `<job_name>.trm` et placé dans le répertoire de travail de sortie que vous avez défini précédemment.

Configurez la redirection de la sortie du terminal :

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### Étape 4 : exécuter le job

`run()` exécute la conversion selon les options fournies et écrit les fichiers de sortie (y compris le journal `.trm`) dans le dossier désigné.

Créez un `TeXJob` avec le fichier d’entrée souhaité (ici nous utilisons un simple exemple « hello‑world ») et le dispositif de rendu XPS, puis appelez `run()` :

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
```

Lorsque le job se termine, vous trouverez un fichier nommé `overridden-job-name.trm` dans **Votre Répertoire de Sortie** contenant le journal complet du terminal.

## Problèmes courants & dépannage

| Problème | Cause | Solution |
|----------|-------|----------|
| **Aucun fichier `.trm` généré** | `setTerminalOut` non appelé ou répertoire de sortie manquant | Vérifiez que le répertoire de sortie existe et que `options.setTerminalOut(...)` est exécuté avant `job.run()`. |
| **Le nom du fichier n’est pas le nom remplacé** | Nom du job mal défini | Assurez‑vous que `options.setJobName("your‑desired‑name")` est appelé **avant** de créer le `TeXJob`. |
| **Fichier journal vide** | Exceptions levées avant le démarrage de la journalisation | Enveloppez `job.run()` dans un bloc try‑catch et inspectez la trace de la pile d’exceptions pour des polices manquantes ou une source TeX mal formée. |

## Questions fréquentes

**Q : Puis‑je utiliser Aspose.TeX pour Java avec d’autres bibliothèques Java ?**  
**R :** Oui, Aspose.TeX s’intègre parfaitement avec d’autres bibliothèques Java, vous permettant de combiner des utilitaires PDF, image ou base de données dans le même flux de travail.

**Q : Où puis‑je trouver du support pour Aspose.TeX pour Java ?**  
**R :** Consultez le [forum Aspose.TeX](https://forum.aspose.com/c/tex/47) pour obtenir de l’aide de la communauté, ou ouvrez un ticket de support via le portail d’assistance Aspose.

**Q : Existe‑t‑il un essai gratuit d’Aspose.TeX pour Java ?**  
**R :** Absolument. Vous pouvez télécharger un essai pleinement fonctionnel depuis la [page d’essai gratuit Aspose.TeX](https://releases.aspose.com/).

**Q : Comment obtenir une licence temporaire pour les tests ?**  
**R :** Utilisez le formulaire de demande de licence temporaire à l’adresse [Aspose licence temporaire](https://purchase.aspose.com/temporary-license/) pour obtenir une licence d’évaluation de 30 jours.

**Q : Où puis‑je acheter une licence permanente ?**  
**R :** Achetez une licence directement depuis la [page d’achat Aspose.TeX](https://purchase.aspose.com/buy).

---

**Dernière mise à jour :** 2026-08-18  
**Testé avec :** Aspose.TeX 24.11 pour Java  
**Auteur :** Aspose

## Tutoriels associés

- [Convertir TeX en PDF, remplacer le nom du job et écrire la sortie du terminal dans un ZIP en Java](/tex/java/customizing-output/override-job-name-zip/)
- [Comment utiliser les archives ZIP pour l’entrée et la sortie dans Aspose.TeX Java](/tex/java/zip-archives/zip-archives-input-output/)
- [Comment convertir TeX en PNG avec entrée en flux et gestion du terminal en Java](/tex/java/advanced-io/stream-input-image-output/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}