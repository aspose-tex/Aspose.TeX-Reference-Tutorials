---
date: 2026-02-20
description: Apprenez à convertir le TeX en XPS en Java avec Aspose.TeX. Ce guide
  étape par étape vous montre comment convertir les fichiers TeX et générer efficacement
  des flux de documents XPS.
linktitle: How to Convert TeX to XPS in Java with External Stream
second_title: Aspose.TeX Java API
title: Comment convertir TeX en XPS en Java avec un flux externe
url: /fr/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment convertir TeX en XPS en Java avec un flux externe

## Introduction

Si vous devez **convertir des fichiers TeX** en sortie XPS de haute qualité depuis une application Java, Aspose.TeX for Java rend la tâche simple. Dans ce tutoriel, vous verrez exactement **comment convertir TeX** en document XPS en utilisant un flux de sortie externe, ce qui est idéal lorsque vous souhaitez acheminer le résultat directement vers une réponse, un service de stockage cloud ou toute destination personnalisée. Parcourons l’ensemble du processus, de la configuration de l’environnement à l’écriture du fichier XPS final.

## Réponses rapides
- **Que couvre ce tutoriel ?** Conversion de TeX en XPS avec Aspose.TeX et un flux externe.  
- **Quelle bibliothèque principale est requise ?** Aspose.TeX for Java.  
- **Ai‑je besoin d’une licence ?** Une licence temporaire ou complète est requise pour une utilisation en production.  
- **Puis‑je générer des flux de documents XPS ?** Oui – l’exemple écrit le XPS directement dans un `OutputStream`.  
- **Quelle version de Java est prise en charge ?** Tout JDK 8+ (le tutoriel utilise JDK 11 comme référence).

## Comment convertir TeX en XPS en utilisant un flux externe

Cette section répète le mot‑clé principal dans un titre dédié, facilitant la localisation de la solution exacte pour les lecteurs et les moteurs d’IA.

## Prérequis

Avant de plonger dans le code, assurez‑vous de disposer de ce qui suit :

- Java Development Kit (JDK) : Assurez‑vous que Java est installé sur votre système. Vous pouvez le télécharger [ici](https://www.oracle.com/java/technologies/javase-downloads.html).

- Aspose.TeX for Java : Téléchargez et installez Aspose.TeX for Java. Vous trouverez le lien de téléchargement [ici](https://releases.aspose.com/tex/java/).

## Importer les packages

Commencez par importer les packages nécessaires pour lancer votre conversion TeX‑vers‑XPS. Incluez le fragment de code suivant dans votre projet Java :

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

## Étape 1 : Configurer les options de conversion

Commencez par créer les options de conversion pour le format ObjectTeX par défaut en utilisant le code suivant :

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

Cela prépare les bases du processus de composition.

## Étape 2 : Spécifier le nom du travail et les répertoires

Définissez un nom de travail et indiquez les répertoires de travail d’entrée et de sortie :

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Assurez‑vous de remplacer les espaces réservés comme « Your Input Directory » par vos chemins réels.

## Étape 3 : Configurer la sortie du terminal

Spécifiez que la sortie du terminal doit être écrite dans un fichier du répertoire de travail de sortie :

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

Cette étape garantit que des journaux détaillés sont capturés pour le débogage.

## Étape 4 : Ouvrir le flux de sortie

Ouvrez un flux pour écrire le document XPS composé :

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

Remplacez « Your Output Directory » par le chemin approprié.

## Étape 5 : Exécuter le travail

Exécutez le travail de conversion de TeX en XPS :

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

Cela termine le processus, et vous trouverez votre document XPS généré dans le répertoire de sortie spécifié.

## Pourquoi c’est important

Utiliser un `OutputStream` externe vous donne un contrôle total sur la destination des données XPS — que vous les envoyiez directement à un client web, les stockiez dans le cloud ou les chaîniez dans un autre pipeline de traitement. Cela élimine le besoin de fichiers intermédiaires et réduit la surcharge d’E/S, ce qui est particulièrement précieux dans des environnements à haut débit ou sans serveur.

## Problèmes courants et solutions

| Problème | Pourquoi cela se produit | Comment résoudre |
|----------|--------------------------|------------------|
| **FileNotFoundException** lors de l’ouverture du flux | Le chemin du répertoire de sortie est incorrect ou n’existe pas. | Vérifiez le chemin, créez le répertoire au préalable, ou utilisez `Files.createDirectories`. |
| **NullPointerException** sur `options.getOutputWorkingDirectory()` | `setOutputWorkingDirectory` n’a pas été appelé ou a renvoyé `null`. | Assurez‑vous d’appeler `options.setOutputWorkingDirectory` avant de l’utiliser. |
| **LicenseException** à l’exécution | Exécution sans licence Aspose.TeX valide. | Appliquez une licence temporaire ou permanente avec `License license = new License(); license.setLicense("Aspose.TeX.lic");`. |

## FAQ

**Q : Puis‑je utiliser Aspose.TeX for Java avec d’autres formats de documents ?**  
R : Aspose.TeX se concentre principalement sur le traitement de documents liés à TeX. Pour d’autres formats, explorez la vaste gamme de produits Aspose.

**Q : Existe‑t‑il une version d’essai disponible ?**  
R : Oui, vous pouvez tester Aspose.TeX en téléchargeant l’essai gratuit [ici](https://releases.aspose.com/).

**Q : Où puis‑je trouver une documentation complète ?**  
R : Consultez la documentation [ici](https://reference.aspose.com/tex/java/) pour des informations détaillées et des exemples.

**Q : Comment obtenir du support ou de l’aide ?**  
R : Visitez le forum Aspose.TeX [ici](https://forum.aspose.com/c/tex/47) pour le support communautaire et les discussions.

**Q : Puis‑je obtenir une licence temporaire à des fins de test ?**  
R : Oui, vous pouvez acquérir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

## Conclusion

Félicitations ! Vous venez d’apprendre **comment convertir TeX** en document XPS en Java en utilisant Aspose.TeX et un flux externe. Cette technique vous donne un contrôle total sur la destination de la sortie XPS — qu’il s’agisse d’un système de fichiers, d’une réponse web ou d’un bucket cloud. N’hésitez pas à expérimenter avec différentes sources TeX, à ajuster les `TeXOptions` pour des polices personnalisées, ou à intégrer le flux dans un pipeline de génération de documents plus vaste.

---

**Dernière mise à jour** : 2026-02-20  
**Testé avec** : Aspose.TeX for Java 24.11 (dernière version au moment de la rédaction)  
**Auteur** : Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}