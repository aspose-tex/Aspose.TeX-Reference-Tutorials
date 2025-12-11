---
date: 2025-12-05
description: Apprenez à composer du TeX avec Aspose.TeX pour Java, y compris les étapes
  pour les formats personnalisés et comment obtenir une licence temporaire Aspose.
linktitle: How to Typeset TeX with Custom Formats in Java
second_title: Aspose.TeX Java API
title: Comment composer du TeX avec des formats personnalisés en Java
url: /fr/java/custom-tex-formats/typesetting-custom-tex-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment mettre en forme TeX avec des formats personnalisés en Java

## Introduction

Si vous devez **mettre en forme tex** dans une application Java, Aspose.TeX offre une solution propre et haute performance pour travailler avec des fichiers de format TeX personnalisés. Dans ce tutoriel, nous passerons en revue tout ce dont vous avez besoin — de la configuration de l'environnement à l'exécution d'un travail TeX utilisant votre propre format. Que vous construisiez un outil de publication scientifique ou un générateur de rapports personnalisé, les étapes ci‑dessous vous permettront de démarrer rapidement.

## Réponses rapides
- **Quelle bibliothèque faut‑il ?** Aspose.TeX for Java  
- **Puis‑je utiliser un format TeX personnalisé ?** Oui – il suffit de pointer le `FormatProvider` vers votre fichier.  
- **Ai‑je besoin d’une licence pour le développement ?** Une licence temporaire aspose fonctionne pour les tests ; une licence complète est requise en production.  
- **Quelle version de Java est prise en charge ?** JDK 8 ou supérieur.  
- **Quel format de sortie l’exemple génère‑t‑il ?** XPS (vous pouvez passer à PDF, PNG, etc.).

## Qu’est‑ce qu’un format TeX personnalisé ?

Un format TeX personnalisé est un ensemble pré‑compilé de macros et de primitives qui adapte le moteur TeX à votre style de document spécifique. En fournissant votre propre fichier `.fmt`, vous pouvez contrôler les polices, les règles de mise en page et les définitions de commandes sans modifier le code source TeX à chaque fois.

## Pourquoi utiliser Aspose.TeX pour Java ?

- **Pure Java** – Aucun binaire natif, facile à intégrer dans tout projet basé sur la JVM.  
- **Haute fidélité** – Génère une sortie qui correspond au rendu de style LaTeX.  
- **Extensible** – Prend en charge les formats personnalisés, plusieurs périphériques de sortie et le traitement par lots.  
- **Flexibilité de licence** – Commencez avec une licence temporaire aspose, puis passez à une licence complète lors du déploiement.

## Prérequis

1. **Java Development Kit (JDK)** – JDK 8 ou plus récent installé. Téléchargez‑le depuis le site officiel [Java website](https://www.oracle.com/java/technologies/javase-downloads.html) si ce n’est pas déjà fait.  
2. **Bibliothèque Aspose.TeX pour Java** – Récupérez le dernier JAR depuis la [page de téléchargement Aspose.TeX pour Java](https://releases.aspose.com/tex/java/).  
3. **Votre fichier de format TeX personnalisé** – Placez le fichier `.fmt` compilé (par ex., `customtex.fmt`) dans un dossier qui servira de répertoire de sortie.  

> **Astuce :** Si vous évaluez le produit, demandez une *licence temporaire aspose* depuis le portail Aspose ; elle supprime le filigrane d’évaluation pendant une période limitée.

## Importer les packages

Tout d’abord, ajoutez les imports requis à votre projet Java. Ces classes vous donnent accès au fournisseur de format, à la configuration du travail et au dispositif de rendu.

```java
package com.aspose.tex.TypesetWithCustomTeXFormat;

import java.io.ByteArrayInputStream;
import java.io.IOException;

import com.aspose.tex.FormatProvider;
import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

## Guide étape par étape

### Étape 1 : Créer un fournisseur de format

Le `FormatProvider` pointe vers le répertoire contenant votre fichier de format TeX personnalisé. Remplacez `"Your Output Directory"` par le chemin réel où se trouve `customtex.fmt`.

```java
final FormatProvider formatProvider = new FormatProvider(
        new InputFileSystemDirectory("Your Output Directory"), "customtex");
```

### Étape 2 : Définir les options de conversion

Configurez le travail pour utiliser le moteur ObjectTeX (le moteur qui comprend les formats personnalisés). Ici, nous définissons également le nom du travail et spécifions les répertoires de travail d’entrée/sortie.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX(formatProvider));
options.setJobName("typeset-with-custom-format");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### Étape 3 : Exécuter le travail TeX

Créez une instance `TeXJob`, fournissez‑lui un extrait TeX simple, et indiquez‑lui de rendre le résultat avec un `XpsDevice`. L’extrait se termine par `\end` pour fermer le document.

```java
new TeXJob(new ByteArrayInputStream(
        "Congratulations! You have successfully typeset this text with your own TeX format!\\end".getBytes("ASCII")),
        new XpsDevice(), options).run();
```

### Étape 4 : Finaliser la sortie

Après la fin du travail, ajoutez un retour à la ligne à la sortie du terminal afin que la console reste propre.

```java
options.getTerminalOut().getWriter().newLine();
```

### Étape 5 : Fermer le fournisseur de format

Lorsque vous avez terminé, fermez le fournisseur pour libérer les poignées de fichiers et les ressources.

```java
formatProvider.close();
```

## Problèmes courants et solutions

| Problème | Cause | Solution |
|----------|-------|----------|
| **« Fichier de format introuvable »** | Chemin incorrect dans `FormatProvider` | Vérifiez que le répertoire et le nom de fichier (`customtex.fmt`) sont corrects et accessibles. |
| **Erreurs d’encodage** | Caractères non‑ASCII dans la chaîne TeX | Utilisez l’encodage UTF‑8 (`"UTF-8"` au lieu de `"ASCII"`). |
| **Sortie non générée** | Le répertoire de sortie n’a pas les droits d’écriture | Assurez‑vous que le processus Java a les droits d’écriture sur `"Your Output Directory"`. |
| **Filigrane de licence** | Utilisation uniquement de la licence d’évaluation | Appliquez une *licence temporaire aspose* pour les tests ou achetez une licence complète pour la production. |

**Ressources associées :** [Référence API Aspose.TeX](https://docs.aspose.com/tex/java/) | [Télécharger l’essai gratuit](https://releases.aspose.com/tex/java/)

## Questions fréquentes

**Q : Puis‑je utiliser Aspose.TeX avec d’autres bibliothèques Java ?**  
R : Absolument. L’API est pure Java et fonctionne aux côtés de bibliothèques telles qu’Apache PDFBox, iText ou Spring Boot.

**Q : Où puis‑je obtenir une licence temporaire aspose pour l’évaluation ?**  
R : Demandez‑en une depuis la [page de licence temporaire Aspose](https://purchase.aspose.com/temporary-license/). Elle supprime le filigrane d’évaluation pendant jusqu’à 30 jours.

**Q : Aspose.TeX prend‑il en charge des formats de sortie autres que XPS ?**  
R : Oui. Vous pouvez remplacer `new XpsDevice()` par `new PdfDevice()`, `new PngDevice()`, etc., selon vos besoins.

**Q : Comment déboguer un travail TeX qui échoue ?**  
R : Activez la journalisation détaillée en appelant `options.setLogLevel(LogLevel.DEBUG);` et examinez la sortie console pour des messages d’erreur détaillés.

**Q : Existe‑t‑il un essai gratuit ?**  
R : Oui – téléchargez les binaires d’essai depuis la [page de téléchargement Aspose.TeX](https://releases.aspose.com/tex/java/).

## Conclusion

Vous savez maintenant **comment mettre en forme tex** dans une application Java en utilisant un format TeX personnalisé avec Aspose.TeX. En suivant les étapes ci‑dessus, vous pouvez intégrer une composition de haute qualité dans n’importe quel flux de travail basé sur Java, expérimenter avec vos propres fichiers de format, et passer du prototype à la production avec une licence appropriée.

---

**Dernière mise à jour :** 2025-12-05  
**Testé avec :** Aspose.TeX for Java 24.10  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}