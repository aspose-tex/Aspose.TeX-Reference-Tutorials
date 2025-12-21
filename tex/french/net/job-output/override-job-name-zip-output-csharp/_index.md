---
date: 2025-12-21
description: Apprenez à convertir TeX en PDF, à remplacer le nom du travail et à écrire
  la sortie du terminal dans un fichier ZIP en utilisant Aspose.TeX pour .NET. Générez
  un PDF à partir de TeX avec C#.
linktitle: Convert TeX to PDF and Override Job Name – Write Output to ZIP (C#)
second_title: Aspose.TeX .NET API
title: Convertir TeX en PDF et remplacer le nom du travail – écrire la sortie dans
  un ZIP (C#)
url: /fr/net/job-output/override-job-name-zip-output-csharp/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertir TeX en PDF et remplacer le nom du travail – écrire la sortie dans un ZIP (C#)

## Introduction

Dans ce tutoriel, vous apprendrez **comment convertir TeX en PDF** tout en remplaçant le nom du travail et en capturant la sortie du terminal à l’intérieur d’une archive ZIP. Aspose.TeX pour .NET rend la génération de PDF à partir de TeX simple, vous offrant un contrôle complet sur la configuration du travail et la gestion de la sortie. Que vous automatisiez la génération de rapports ou que vous construisiez une chaîne de publication basée sur TeX, les étapes ci‑dessous vous permettront de passer d’une source TeX brute à un fichier PDF prêt à l’emploi stocké dans un conteneur ZIP.

## Réponses rapides
- **Quel est le sujet de ce tutoriel ?** Conversion de TeX en PDF, remplacement du nom du travail TeX et écriture de la sortie du terminal dans un fichier ZIP en utilisant C#.
- **Quelle bibliothèque est requise ?** Aspose.TeX pour .NET (la solution « create PDF using Aspose »).
- **Ai‑je besoin d’une licence ?** Une licence temporaire suffit pour les tests ; une licence complète est requise en production.
- **Quelles sont les principales conditions préalables ?** Environnement de développement .NET, Aspose.TeX installé, et fichiers ZIP d’entrée/sortie.
- **Combien de temps prend l’implémentation ?** Environ 10–15 minutes une fois l’environnement configuré.

## Qu’est‑ce que « convertir tex en pdf » ?
Convertir TeX en PDF signifie prendre un document source TeX et le traiter avec un moteur TeX afin de produire un rendu PDF. Aspose.TeX fournit une API .NET gérée qui effectue cette conversion sans nécessiter de distribution TeX externe.

## Pourquoi remplacer le nom du travail ?
Remplacer le nom du travail vous permet de contrôler le nom de base utilisé pour les fichiers auxiliaires (par ex., *.log, *.aux) et pour tout flux de sortie que vous redirigez. Ceci est particulièrement utile lorsque vous exécutez plusieurs travaux dans le même répertoire de travail ou lorsque vous avez besoin d’un schéma de nommage prévisible pour le traitement en aval.

## Prérequis

- Familiarité avec C# et le développement .NET.
- Aspose.TeX pour .NET installé (via NuGet ou paquet manuel).
- Une archive ZIP d’entrée contenant les fichiers source TeX.
- Une archive ZIP vide qui recevra la sortie du terminal.

## Importer les espaces de noms

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Pdf;
using System.IO;
```

## Comment convertir TeX en PDF et remplacer le nom du travail

Ci‑dessous, un guide étape par étape qui vous montre comment ouvrir les flux ZIP, configurer les options de conversion, exécuter le travail TeX et finaliser l’archive ZIP de sortie.

### Étape 1 : ouvrir les flux ZIP d’entrée et de sortie

```csharp
using (Stream inZipStream = File.Open(Path.Combine("Your Input Directory", "zip-in.zip"), FileMode.Open))
using (Stream outZipStream = File.Open(Path.Combine("Your Output Directory", "terminal-out-to-zip.zip"), FileMode.Create))
{
    // Code for step 1 goes here
}
```

*Explication* : les instructions `using` garantissent que les deux flux sont correctement libérés. Le ZIP d’entrée (`zip-in.zip`) contient les sources TeX, tandis que le ZIP de sortie (`terminal-out-to-zip.zip`) stockera le journal du terminal généré pendant la conversion.

### Étape 2 : définir les options de conversion (incluant **remplacer le nom du travail**)

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
options.JobName = "terminal-output-to-zip";
options.InputWorkingDirectory = new InputZipDirectory(inZipStream, "in");
options.OutputWorkingDirectory = new OutputZipDirectory(outZipStream);
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

*Explication* :  
- `JobName` est défini sur `"terminal-output-to-zip"` – cela remplace le nom de travail par défaut.  
- `InputWorkingDirectory` et `OutputWorkingDirectory` pointent vers les flux ZIP, permettant à Aspose.TeX de lire/écrire directement depuis les archives.  
- `TerminalOut` redirige la sortie console du moteur TeX vers un fichier à l’intérieur du ZIP de sortie.

### Étape 3 : définir les options d’enregistrement (générer le PDF à partir de TeX)

```csharp
options.SaveOptions = new PdfSaveOptions();
```

*Explication* : `PdfSaveOptions` indique à Aspose.TeX de produire un fichier PDF comme sortie finale.

### Étape 4 : exécuter le travail TeX

```csharp
new TeXJob("hello-world", new PdfDevice(), options).Run();
```

*Explication* : le constructeur `TeXJob` reçoit le nom du fichier TeX principal (`hello-world.tex`), le dispositif cible (`PdfDevice`) et les `options` configurées précédemment. L’appel à `.Run()` lance le processus de conversion.

### Étape 5 : finaliser l’archive ZIP de sortie

```csharp
((OutputZipDirectory)options.OutputWorkingDirectory).Finish();
```

*Explication* : cet appel vide les données en attente et ferme correctement le ZIP de sortie, garantissant que le journal du terminal et le PDF généré sont correctement stockés.

## Problèmes courants et dépannage

| Symptôme | Cause probable | Solution |
|----------|----------------|----------|
| PDF non créé | `options.SaveOptions` non défini | Vérifiez que l’étape 3 a été exécutée. |
| Journal du terminal vide | `options.TerminalOut` non assigné | Assurez‑vous que l’étape 2 inclut la ligne `TerminalOut`. |
| Erreur « Fichier introuvable » | Chemin d’accès incorrect vers le ZIP d’entrée | Vérifiez à nouveau les chemins de fichiers dans l’étape 1. |
| Le nom du travail n’est pas reflété dans les fichiers auxiliaires | Fautes de frappe dans `options.JobName` | Confirmez que le nom de la propriété est exactement `JobName`. |

## Questions fréquentes

### Q1 : Puis‑je utiliser Aspose.TeX pour .NET avec d’autres langages .NET comme VB.NET ?
**R :** Oui, Aspose.TeX pour .NET est compatible avec tous les langages .NET, y compris VB.NET, F# et C#.

### Q2 : Où puis‑je trouver plus de documentation pour Aspose.TeX pour .NET ?
**R :** Visitez la [documentation](https://reference.aspose.com/tex/net/) pour plus d’informations.

### Q3 : Comment obtenir une licence temporaire pour Aspose.TeX ?
**R :** Obtenez une [licence temporaire](https://purchase.aspose.com/temporary-license/) à des fins de test.

### Q4 : Existe‑t‑il un forum communautaire pour le support d’Aspose.TeX ?
**R :** Oui, rejoignez le [forum Aspose.TeX](https://forum.aspose.com/c/tex/47) pour le support communautaire.

### Q5 : Où puis‑je acheter Aspose.TeX pour .NET ?
**R :** Vous pouvez acheter Aspose.TeX [ici](https://purchase.aspose.com/buy).

### Q6 : Cette approche fonctionne‑t‑elle sur .NET Core / .NET 5+ ?
**R :** Absolument. Aspose.TeX prend en charge .NET Framework, .NET Core et .NET 5/6+. Il suffit de référencer le package NuGet approprié.

### Q7 : Puis‑je personnaliser la sortie PDF (par ex., ajouter des métadonnées) ?
**R :** Oui. Après la conversion, vous pouvez utiliser Aspose.PDF ou les propriétés `PdfSaveOptions` pour intégrer des métadonnées, définir les niveaux de compression ou modifier les paramètres de page.

## Conclusion

Vous disposez maintenant d’un exemple complet, prêt pour la production, qui **convertit TeX en PDF**, **remplace le nom du travail** et **écrit la sortie du terminal dans une archive ZIP** en utilisant Aspose.TeX pour .NET. N’hésitez pas à adapter les chemins, le nom du travail ou le format de sortie pour correspondre à votre propre flux de travail.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2025-12-21  
**Testé avec :** Aspose.TeX 24.12 pour .NET  
**Auteur :** Aspose  

---