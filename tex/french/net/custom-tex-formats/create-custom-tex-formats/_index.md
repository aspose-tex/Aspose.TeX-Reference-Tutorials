---
date: 2026-10-19
description: Apprenez à effectuer la génération de documents tex, créer un format
  tex personnalisé et définir le répertoire d'entrée tex à l'aide d'Aspose.TeX pour
  .NET. Guide étape par étape avec des extraits de code et des conseils de dépannage.
keywords:
- tex document generation
- create custom tex format
- set tex input directory
- custom tex macros
lastmod: 2026-10-19
linktitle: Création de formats TeX personnalisés dans .NET
og_description: La génération de documents tex avec Aspose.TeX vous permet de créer
  un format tex personnalisé et de définir le répertoire d'entrée tex dans .NET. Suivez
  ce guide pour obtenir une sortie XPS, PDF ou PNG.
og_image_alt: Developer guide showing tex document generation using Aspose.TeX in
  .NET
og_title: Comment générer des documents tex avec un format dans .NET
schemas:
- author: Aspose
  dateModified: '2026-10-19'
  description: Learn how to perform tex document generation, create custom tex format
    and set tex input directory using Aspose.TeX for .NET. Step‑by‑step guide with
    code snippets and troubleshooting tips.
  headline: How to do tex document generation with format in .NET
  type: TechArticle
- description: Learn how to perform tex document generation, create custom tex format
    and set tex input directory using Aspose.TeX for .NET. Step‑by‑step guide with
    code snippets and troubleshooting tips.
  name: How to do tex document generation with format in .NET
  steps:
  - name: '**Aspose.TeX for .NET** – download it from the [Aspose.TeX website](https://releases.aspose.com/tex/net/).'
    text: '**Aspose.TeX for .NET** – download it from the [Aspose.TeX website](https://releases.aspose.com/tex/net/).'
  - name: A **.NET development environment** (Visual Studio, VS Code, or the .NET
      CLI).
    text: A **.NET development environment** (Visual Studio, VS Code, or the .NET
      CLI).
  - name: (Optional) A valid **Aspose.TeX license** for production use.
    text: (Optional) A valid **Aspose.TeX license** for production use.
  type: HowTo
- questions:
  - answer: Absolutely. Replace `new XpsDevice()` with `new PdfDevice()` and adjust
      the output path accordingly.
    question: Can I output PDF instead of XPS?
  - answer: Yes. Any modification to macros or engine settings requires re‑running
      `tex -ini` to generate a fresh `.fmt` file.
    question: Do I need to re‑compile the format file after every change?
  type: FAQPage
second_title: Aspose.TeX .NET API
tags:
- tex document generation
- Aspose.TeX
- .NET document processing
- custom tex format
title: Comment générer des documents tex avec un format dans .NET
url: /fr/net/custom-tex-formats/create-custom-tex-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer des documents tex avec un format dans .NET

Dans le développement .NET moderne, la **génération de documents tex** est un moyen puissant de produire une sortie typographique de haute qualité sans dépendre d’installations LaTeX externes. Aspose.TeX pour .NET vous donne un contrôle complet : vous pouvez **créer un format tex personnalisé**, indiquer au moteur un dossier d’entrée dédié, et exporter vers XPS, PDF, PNG ou d’autres périphériques — le tout à partir d’un code C# simple.

## Réponses rapides
- **Que signifie « create custom tex format » ?** Il s'agit de définir votre propre configuration du moteur TeX et le fichier de format compilé afin que le processeur suive vos macros et paramètres.  
- **Quelle bibliothèque faut‑il ?** Aspose.TeX for .NET, qui prend en charge plus de 30 formats d’entrée et de sortie.  
- **Do I have to set a tex input directory?** Yes – use `InputWorkingDirectory` to tell the engine where auxiliary files live.  
- **Quel type de sortie puis‑je générer ?** XPS, PDF, PNG, TIFF, et de nombreux autres formats de périphérique.  
- **Une licence est‑elle requise pour la production ?** Une licence Aspose.TeX valide est obligatoire pour les déploiements commerciaux.

## Qu’est‑ce qu’un format tex personnalisé ?
Un format tex personnalisé est une collection pré‑compilée de macros et de paramètres du moteur que le processeur TeX charge au démarrage. En en créant un, vous pouvez intégrer l’image de marque de votre entreprise, imposer des normes de mise en page et réduire le temps de compilation pour les documents récurrents. Il assure une cohérence de style sur tous les documents générés et simplifie la maintenance de flux de travail typographiques complexes.

## Pourquoi définir un répertoire d’entrée tex ?
Définir le **répertoire d’entrée tex** indique au moteur où rechercher les fichiers auxiliaires tels que les fichiers de style, les polices personnalisées ou les packages de macros supplémentaires. Cela élimine les erreurs « file not found » et garde votre dossier de projet propre. Cela améliore également la reproductibilité des builds en garantissant que toutes les ressources sont résolues à partir d’un emplacement connu.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

1. **Aspose.TeX for .NET** – téléchargez‑le depuis le site [Aspose.TeX website](https://releases.aspose.com/tex/net/).  
2. Un **environnement de développement .NET** (Visual Studio, VS Code ou la CLI .NET).  
3. (Facultatif) Une licence **Aspose.TeX** valide pour une utilisation en production.

## Importer les espaces de noms

Les espaces de noms suivants vous donnent accès aux classes principales d’Aspose.TeX.  
Les classes liées au `Document` se trouvent sous `Aspose.TeX`, tandis que les options et les périphériques sont dans `Aspose.TeX.Rendering`.

La classe `Document` est l’objet de haut niveau qui représente un document TeX unique en mémoire.  

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using Aspose.TeX.ResourceProviders;
using System.IO;
using System.Text;
```

## Étape 1 : créer le fournisseur de format

Le `FormatProvider` indique au moteur où se trouve le fichier de format compilé (`customtex.fmt`). Remplacez `"Your Output Directory"` par le chemin absolu contenant votre format personnalisé.

`FormatProvider` est un wrapper léger qui charge le fichier `.fmt` une seule fois et le réutilise pour chaque conversion, améliorant considérablement les performances pour les traitements par lots.

```csharp
using (FormatProvider formatProvider =
    new FormatProvider(new InputFileSystemDirectory("Your Output Directory"), "customtex"))
{
```

## Étape 2 : configurer les options de conversion (et définir le répertoire d’entrée tex)

Ici nous construisons une instance de `TeXOptions`. La propriété `InputWorkingDirectory` **définit le répertoire d’entrée tex** afin que le moteur puisse localiser les fichiers de support tels que les packages personnalisés ou les polices.

`TeXOptions` vous permet également de spécifier le périphérique de sortie, la taille de page et la qualité de rendu. Pour une génération à grande échelle, vous pouvez activer `EnableParallelProcessing` afin d’accélérer le rendu sur des serveurs multi‑cœurs.

```csharp
    TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX(formatProvider));
    options.JobName = "typeset-with-custom-format";
    options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
    options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

## Étape 3 : exécuter la tâche

Alimentez maintenant une chaîne TeX simple au moteur, choisissez un périphérique de sortie (XPS dans cet exemple), et lancez la tâche. Le `TeXEngine` lit le format personnalisé, traite la source et écrit le résultat sur le périphérique sélectionné.

`TeXEngine` est le processeur central d’Aspose.TeX qui analyse la source TeX, applique le format personnalisé et transmet les pages rendues au périphérique que vous avez spécifié.

```csharp
    new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
        "Congratulations! You have successfully typeset this text with your own TeX format!\\end")),
        new XpsDevice(), options).Run();
```

## Étape 4 : affiner la sortie du terminal

Ajouter une ligne vide après la fin de la tâche rend les journaux de console plus lisibles, surtout lorsque vous enchaînez plusieurs conversions dans un script.

`Console.WriteLine()` écrit une ligne de texte sur le flux de sortie standard. Il est utilisé ici uniquement pour une séparation visuelle ; il n’affecte pas le document généré.

```csharp
    options.TerminalOut.Writer.WriteLine();
}
// ExEnd:TypesetWithCustomTeXFormat
```

Félicitations ! Vous avez maintenant **créé un format tex personnalisé** et l’avez utilisé pour la **génération de documents tex** dans .NET. Vous pouvez remplacer le `XpsDevice` par `PdfDevice`, `PngDevice` ou tout autre périphérique supporté selon vos besoins de diffusion.

## Problèmes courants et solutions

| Problème | Raison | Solution |
|----------|--------|----------|
| *« Format file not found »* | Chemin incorrect dans `FormatProvider` | Vérifiez que `"Your Output Directory"` contient `customtex.fmt` et que le chemin est absolu ou correctement relatif à l’exécutable. |
| *« Cannot find input file »* | `InputWorkingDirectory` pointe vers le mauvais dossier | Assurez‑vous que `"Your Input Directory"` contient le fichier source TeX ou que vous transmettez la source sous forme de flux (comme dans l’exemple). |
| *Sortie du terminal illisible* | Incompatibilité d’encodage | Utilisez `Encoding.UTF8` si votre source TeX contient des caractères non‑ASCII. |
| *Le fichier XPS est vide* | La tâche n’a pas été exécutée à cause d’une exception antérieure | Consultez la console pour les messages d’erreur ; ils indiquent souvent des packages manquants ou des erreurs de syntaxe dans la chaîne TeX. |

## Questions fréquentes

**Q1 : Puis‑je utiliser Aspose.TeX for .NET avec d’autres bibliothèques Aspose ?**  
R : Oui, Aspose.TeX s’intègre parfaitement avec Aspose.PDF, Aspose.Words et d’autres produits Aspose pour des pipelines documentaires de bout en bout.

**Q2 : Existe‑t‑il une version d’essai gratuite d’Aspose.TeX for .NET ?**  
R : Oui, vous pouvez télécharger un essai depuis la **page de téléchargement d’essai Aspose.TeX** (https://releases.aspose.com/tex/net/).

**Q3 : Comment obtenir du support pour Aspose.TeX for .NET ?**  
R : Visitez le [forum Aspose.TeX](https://forum.aspose.com/c/tex/47) pour l’aide de la communauté ou explorez les options premium sur la **page d’achat du support premium** (https://purchase.aspose.com/buy).

**Q4 : Des licences temporaires sont‑elles disponibles pour Aspose.TeX for .NET ?**  
R : Oui, faites une demande sur la **page de demande de licence temporaire** (https://purchase.aspose.com/temporary-license/).

**Q5 : Où puis‑je trouver la référence API officielle ?**  
R : La documentation complète est hébergée sur la **documentation de référence API** (https://reference.aspose.com/tex/net/).

### Questions‑réponses supplémentaires

**Q : Puis‑je générer un PDF au lieu d’un XPS ?**  
R : Absolument. Remplacez `new XpsDevice()` par `new PdfDevice()` et ajustez le chemin de sortie en conséquence.

**Q : Dois‑je recompiler le fichier de format après chaque modification ?**  
R : Oui. Toute modification des macros ou des paramètres du moteur nécessite de relancer `tex -ini` pour générer un nouveau fichier `.fmt`.

## Conclusion

Aspose.TeX for .NET offre une **solution robuste et haute performance pour la génération de documents tex**, vous permettant de **créer un format tex personnalisé**, de définir le **répertoire d’entrée tex**, et de sortir vers n’importe quel périphérique supporté. Intégrez les étapes ci‑dessus dans votre pipeline CI/CD, automatisez la génération de rapports à grande échelle, ou construisez un moteur de publication personnalisé qui répond aux normes de marque de votre organisation.

---

**Dernière mise à jour :** 2026-10-19  
**Testé avec :** Aspose.TeX 24.11 for .NET  
**Auteur :** Aspose

## Tutoriels associés

- [Get TeX File Stream (C#) Using Aspose.TeX API Required Input Directory](/tex/net/advanced-io/required-input-directory-csharp/)
- [How to Create PDF with Aspose.TeX for .NET – Step by Step](/tex/net/pdf-output/)
- [How to create XPS document .NET – Convert TeX to XPS Output with Aspose.TeX for .NET](/tex/net/xps-output/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}