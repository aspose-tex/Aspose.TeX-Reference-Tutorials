---
date: 2025-12-07
description: Apprenez à convertir TeX en PDF, à remplacer les noms de travaux et à
  écrire la sortie du terminal dans un fichier ZIP en utilisant Aspose.TeX pour Java.
  Guide étape par étape pour les développeurs Java.
language: fr
linktitle: Convert TeX to PDF, Override Job Name and Write Terminal Output to ZIP
  in Java
second_title: Aspose.TeX Java API
title: Convertir TeX en PDF, remplacer le nom du travail et écrire la sortie du terminal
  dans un ZIP en Java
url: /java/customizing-output/override-job-name-zip/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertir TeX en PDF, remplacer le nom du travail et écrire la sortie du terminal dans un ZIP en Java

## Introduction

Si vous devez **convertir TeX en PDF** tout en gardant le contrôle total sur le nom du travail et les journaux du terminal, Aspose.TeX for Java rend cela simple. Dans ce tutoriel, nous parcourrons un scénario réel : remplacer le nom du travail, diriger la sortie du terminal dans une archive ZIP, puis produire un document PDF. À la fin, vous disposerez d’un extrait de code réutilisable que vous pourrez intégrer à n’importe quel projet Java.

## Réponses rapides
- **Que réalise ce tutoriel ?** Il montre comment convertir TeX en PDF, définir un nom de travail personnalisé et capturer la sortie du terminal dans un fichier ZIP.  
- **Quelle bibliothèque est requise ?** Aspose.TeX for Java (dernière version).  
- **Ai‑je besoin d’une licence ?** Une licence temporaire suffit pour l’évaluation ; une licence complète est requise en production.  
- **Quels fichiers de sortie sont générés ?** Un document PDF et un journal terminal `<job_name>.trm` à l’intérieur du ZIP de sortie.  
- **Combien de temps prend l’implémentation ?** Environ 10‑15 minutes pour copier le code et l’exécuter.

## Qu’est‑ce que « convertir TeX en PDF » ?
Convertir TeX en PDF signifie prendre un fichier source TeX (ou une collection de fichiers TeX) et le rendre sous forme de document PDF. Aspose.TeX fournit un moteur haute performance qui gère l’ensemble du pipeline de compilation TeX sans nécessiter de distribution LaTeX externe.

## Pourquoi remplacer le nom du travail et écrire la sortie du terminal dans un ZIP ?
- **Clarté :** Un nom de travail personnalisé apparaît dans les fichiers journaux, ce qui facilite l’identification des exécutions dans les pipelines automatisés.  
- **Portabilité :** Stocker la sortie du terminal (`*.trm`) dans un ZIP garde tous les artefacts ensemble, pratique pour les CI/CD ou le traitement dans le cloud.  
- **Débogage :** Le journal du terminal contient des messages de compilation détaillés qui aident à résoudre les erreurs TeX.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

- Un environnement de développement Java fonctionnel (JDK 8 ou supérieur).  
- Aspose.TeX for Java téléchargé depuis le [site Aspose](https://releases.aspose.com/tex/java/).  
- Une connaissance de base des flux d’E/S Java.  

## Importer les packages

Commencez par importer les classes nécessaires. Cela vous donne accès à l’API Aspose.TeX ainsi qu’aux utilitaires d’E/S Java standard.

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

## Étape 1 : Ouvrir l'archive ZIP d'entrée

Nous ouvrons d'abord un flux qui pointe vers le fichier ZIP contenant les sources TeX. Cette archive sert de **répertoire de travail d'entrée** pour le travail de conversion.

```java
// Open a stream on the input ZIP archive
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
```

## Étape 2 : Ouvrir l'archive ZIP de sortie

Ensuite, créez un flux pour le fichier ZIP qui recevra le PDF généré et le journal du terminal. Il s’agit du **répertoire de travail de sortie**.

```java
// Open a stream on the output ZIP archive
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "terminal-out-to-zip.zip");
```

## Étape 3 : Définir les options de conversion (y compris le nom du travail)

Ici nous configurons les options de conversion pour le format ObjectTeX, spécifions un nom de travail personnalisé et associons les répertoires ZIP d’entrée et de sortie.

```java
// Create TeX options for ObjectTeX format
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("terminal-output-to-zip");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
```

## Étape 4 : Diriger la sortie du terminal vers un fichier dans le ZIP

Nous indiquons à Aspose.TeX d’écrire la sortie du terminal de compilation dans un fichier nommé `<job_name>.trm` à l’intérieur du ZIP de sortie.

```java
// Specify terminal output settings
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

## Étape 5 : Définir les options d’enregistrement et exécuter le travail

Définissez le dispositif de rendu souhaité (PDF) et lancez le travail. Cette étape **convertit TeX en PDF** et stocke le résultat dans le ZIP de sortie.

```java
// Define saving options and run the job
options.setSaveOptions(new PdfSaveOptions());
new TeXJob("hello-world", new PdfDevice(), options).run();
```

## Étape 6 : Finaliser l'archive ZIP de sortie

Une fois le travail terminé, nous devons fermer correctement le flux ZIP afin de garantir la validité de l’archive.

```java
// Finalize the output ZIP archive
((OutputZipDirectory) options.getOutputWorkingDirectory()).finish();
```

## Problèmes courants et solutions

| Problème | Cause probable | Solution |
|----------|----------------|----------|
| **PDF vide** | L'archive ZIP d'entrée ne contient pas de fichier `*.tex` valide ou le fichier n’est pas placé sous le dossier `in`. | Vérifiez la structure du ZIP (`in/votrefichier.tex`). |
| **Fichier `.trm` manquant** | `setTerminalOut` n’a pas été appelé ou le répertoire de sortie n’est pas un `OutputZipDirectory`. | Assurez‑vous que `options.setTerminalOut(...)` est exécuté avant `run()`. |
| **`IOException` à la fin** | Le flux de sortie a déjà été fermé ailleurs. | Appelez `finish()` une seule fois, après la fin du travail. |
| **Échec de conversion avec des erreurs TeX** | Le source TeX contient des erreurs de syntaxe. | Ouvrez le journal `<job_name>.trm` généré pour voir les messages d’erreur détaillés. |

## Questions fréquentes

**Q : Qu’est‑ce qu’Aspose.TeX ?**  
R : Aspose.TeX est une bibliothèque Java qui permet aux développeurs de **créer des PDF à partir de sources TeX**, de manipuler des documents TeX et d’effectuer un rendu avancé sans installations LaTeX externes.

**Q : Comment obtenir une licence temporaire pour Aspose.TeX ?**  
R : Vous pouvez obtenir une licence temporaire via [ce lien](https://purchase.aspose.com/temporary-license/).

**Q : Où trouver la documentation officielle d’Aspose.TeX ?**  
R : La documentation est disponible [ici](https://reference.aspose.com/tex/java/).

**Q : Existe‑t‑il une version d’essai gratuite d’Aspose.TeX ?**  
R : Oui, vous pouvez télécharger l’essai gratuit [ici](https://releases.aspose.com/).

**Q : Où puis‑je demander de l’aide en cas de problème ?**  
R : Visitez le [forum Aspose.TeX](https://forum.aspose.com/c/tex/47) pour le support communautaire et l’assistance officielle.

## Conclusion

Vous avez maintenant vu comment **convertir TeX en PDF**, remplacer le nom du travail et capturer la sortie du terminal dans une archive ZIP en utilisant Aspose.TeX for Java. Cette approche est particulièrement utile dans les pipelines de construction automatisés, où regrouper les journaux avec les artefacts générés simplifie le débogage et les audits. N’hésitez pas à adapter le code à la structure de votre projet ou à l’étendre à d’autres formats de sortie supportés par Aspose.TeX.

---

**Dernière mise à jour :** 2025-12-07  
**Testé avec :** Aspose.TeX for Java 24.11 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}