---
date: 2026-02-05
description: Apprenez comment définir la licence et générer des PNG à partir de LaTeX
  en Java avec Aspose.TeX. Ce guide étape par étape couvre la configuration de la
  licence Aspose, la configuration du répertoire de sortie et la modification de la
  résolution PNG.
linktitle: Generate PNG from LaTeX in Java
second_title: Aspose.TeX Java API
title: Comment définir la licence et générer un PNG à partir de LaTeX (Java)
url: /fr/java/converting-lato-images/png-conversion/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Générer PNG à partir de LaTeX en Java avec Aspose.TeX

## Introduction

Si vous devez **générer PNG à partir de LaTeX** dans une application Java, Aspose.TeX rend la tâche simple. Dans ce tutoriel, nous passerons en revue tout ce dont vous avez besoin — **comment définir la licence** pour Aspose.TeX, configurer le répertoire de sortie Java et ajuster la qualité de l’image — afin que vous puissiez convertir des fichiers source LaTeX en images PNG de haute qualité en quelques lignes de code.

## Réponses rapides
- **Quelle bibliothèque convertit LaTeX en PNG en Java ?** Aspose.TeX for Java.  
- **Ai-je besoin d’une licence ?** Oui – vous devez *set Aspose license Java* avant d’exécuter les conversions.  
- **Quelle version de Java est requise ?** JDK 1.8 ou ultérieure.  
- **Puis-je choisir un autre format d’image ?** Absolument – JPEG, BMP et TIFF sont également pris en charge.  
- **Où les fichiers PNG sont‑ils enregistrés ?** Vous définissez un *output directory Java* dans les options de conversion.

## Comment définir la licence pour Aspose.TeX (Java)

Définir la licence est la première étape qui débloque toutes les fonctionnalités et supprime les filigranes d’évaluation. L’appel `Utils.setLicense()` charge le fichier `.lic` que vous avez obtenu auprès d’Aspose. Placez le fichier de licence quelque part sur le classpath (par exemple, dans `src/main/resources`) et appelez la méthode avant que tout travail de conversion ne commence.

> **Astuce :** Si vous déplacez le fichier de licence, mettez à jour le chemin dans `Utils.setLicense()` en conséquence ; sinon vous verrez une erreur de licence à l’exécution.

## Qu’est‑ce que « generate PNG from LaTeX » ?

Générer PNG à partir de LaTeX signifie prendre un fichier source `.ltx` (ou `.tex`) et le rendre sous forme d’image raster (PNG). Ceci est utile pour intégrer des équations, formules ou documents entiers dans des pages web, rapports ou toute interface qui ne peut pas rendre LaTeX directement.

## Pourquoi utiliser Aspose.TeX pour cette tâche ?

- **Aucune dépendance externe** – aucune installation locale de TeX n’est nécessaire.  
- **Contrôle total du rendu** – DPI, profondeur de couleur et format d’image sont configurables.  
- **Multi‑plateforme** – fonctionne sur tout OS supportant Java.  
- **Prêt pour l’entreprise** – inclut une licence robuste et un support.

## Modifier la résolution PNG (Optionnel)

Si la résolution par défaut ne répond pas à vos exigences de qualité, vous pouvez l’ajuster via `PngSaveOptions`. Par exemple, définir `setResolution(300)` vous donnera une sortie de 300 DPI, idéale pour les graphiques prêts à l’impression.

## Définir le dossier de sortie (output directory java)

Vous pouvez diriger les fichiers générés vers n’importe quel dossier. Cela est contrôlé avec la méthode `setOutputWorkingDirectory`. Assurez‑vous que le dossier existe et que le processus Java possède les permissions d’écriture.

## Prérequis

- **Aspose.TeX for Java** – téléchargez depuis la [Aspose.TeX Java Documentation](https://reference.aspose.com/tex/java/).  
- **Java Development Kit (JDK) 1.8+** – assurez‑vous que `java -version` indique 1.8 ou une version plus récente.  
- **Une licence Aspose.TeX valide** – vous utiliserez la méthode `set Aspose license Java` pour l’activer.

## Importer les packages

Dans votre projet Java, commencez par importer les classes Aspose.TeX nécessaires. Ces imports vous donnent accès au moteur de rendu, aux objets de configuration et aux aides du système de fichiers.

```java
package com.aspose.tex.LaTeXPngConversionSimplest;

import java.io.IOException;

import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.BmpSaveOptions;
import com.aspose.tex.rendering.ImageDevice;
import com.aspose.tex.rendering.JpegSaveOptions;
import com.aspose.tex.rendering.PngSaveOptions;
import com.aspose.tex.rendering.TiffSaveOptions;

import util.Utils;
```

### Étape 1 : Définir la licence Aspose (set Aspose license Java)

Avant que toute conversion ne puisse s’effectuer, vous devez enregistrer votre licence. Cette étape empêche les filigranes d’évaluation et débloque toutes les fonctionnalités.

```java
Utils.setLicense();
```

### Étape 2 : Créer les options de conversion

Nous configurons le moteur TeX pour travailler avec le format *Object LaTeX*. Cette option indique à Aspose.TeX comment interpréter le fichier source.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectLaTeX());
```

### Étape 3 : Spécifier le répertoire de sortie (output directory Java)

Indiquez à Aspose.TeX où écrire les fichiers PNG générés. Remplacez le texte de substitution par le chemin absolu ou relatif que vous préférez.

```java
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### Étape 4 : Initialiser les options d’enregistrement PNG

Sélectionnez PNG comme format d’image cible. Vous pouvez affiner davantage la résolution, l’anti‑aliasing et la profondeur de couleur via `PngSaveOptions` si nécessaire.

```java
options.setSaveOptions(new PngSaveOptions());
```

### Étape 5 : Exécuter la conversion LaTeX‑vers‑PNG

Enfin, pointez le travail sur votre fichier source `.ltx`, attachez un `ImageDevice` (qui gère la sortie raster) et exécutez le travail.

```java
new TeXJob("Your Input Directory" + "hello-world.ltx", new ImageDevice(), options).run();
```

## Problèmes courants et comment les résoudre

| Problème | Cause probable | Solution |
|----------|----------------|----------|
| **Aucun fichier PNG n’apparaît** | Le chemin du répertoire de sortie est incorrect ou les permissions d’écriture manquent. | Vérifiez le chemin passé à `OutputFileSystemDirectory` et assurez‑vous que le processus Java peut écrire dans ce dossier. |
| **Erreur de licence** | `Utils.setLicense()` non appelé ou fichier de licence introuvable. | Placez le fichier de licence à un emplacement accessible via le classpath et revérifiez l’implémentation de la méthode. |
| **Images à basse résolution** | Le DPI par défaut est trop faible. | Créez une instance de `PngSaveOptions` et définissez `setResolution(300)` avant de la passer à `options.setSaveOptions()`. |

## Questions fréquentes

### Q1 : Aspose.TeX est‑il compatible avec les dernières versions de Java ?

**R :** Oui. La bibliothèque fonctionne avec JDK 1.8 et toutes les versions ultérieures, y compris Java 11, 17 et 21.

### Q2 : Puis‑je personnaliser la résolution de l’image de sortie ?

**R :** Absolument. Ajustez la méthode `setResolution(int dpi)` de l’objet `PngSaveOptions` pour répondre à vos exigences de qualité.

### Q3 : Existe‑t‑il d’autres formats de sortie pris en charge en plus du PNG ?

**R :** Oui. Aspose.TeX prend également en charge JPEG, BMP et TIFF. Remplacez `new PngSaveOptions()` par la classe d’option d’enregistrement correspondante.

### Q4 : Où puis‑je trouver le support communautaire pour Aspose.TeX ?

**R :** Consultez le [Aspose.TeX Forum](https://forum.aspose.com/c/tex/47) pour des discussions, des exemples et de l’aide au dépannage.

### Q5 : Comment obtenir une licence temporaire à des fins de test ?

**R :** Vous pouvez demander une licence d’essai sur [Aspose.Trial](https://purchase.aspose.com/temporary-license/).

**Questions supplémentaires**

**Q : Comment changer programmétiquement la couleur de fond du PNG ?**  
**R :** Utilisez `PngSaveOptions.setBackgroundColor(java.awt.Color)` avant d’assigner les options à l’objet `TeXOptions`.

**Q : Est‑il possible de convertir plusieurs fichiers LaTeX en une seule exécution ?**  
**R :** Oui. Parcourez votre liste de fichiers et créez une nouvelle instance de `TeXJob` pour chaque fichier, en réutilisant la même instance `options`.

## Conclusion

Vous disposez maintenant d’un flux de travail complet et prêt pour la production afin de **générer PNG à partir de LaTeX** en Java avec Aspose.TeX. En définissant la licence Aspose, en configurant le répertoire de sortie Java et en sélectionnant les options d’enregistrement PNG (ou en ajustant la résolution), vous pouvez intégrer le rendu LaTeX dans n’importe quel système basé sur Java en toute confiance.

---

**Dernière mise à jour :** 2026-02-05  
**Testé avec :** Aspose.TeX for Java 24.11 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}