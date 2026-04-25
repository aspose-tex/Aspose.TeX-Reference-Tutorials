---
date: 2026-03-26
description: Apprenez à créer un format tex personnalisé dans .NET avec Aspose.TeX
  et à définir le répertoire d’entrée tex pour une génération de documents flexible.
  Ce guide étape par étape vous montre comment configurer le fournisseur de format,
  définir le répertoire d’entrée tex et générer la sortie XPS.
linktitle: Creating Custom TeX Formats in .NET
second_title: Aspose.TeX .NET API
title: Comment créer un format TeX personnalisé dans .NET en utilisant Aspose.TeX
url: /fr/net/custom-tex-formats/create-custom-tex-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un format tex personnalisé en .NET avec Aspose.TeX

Dans le monde dynamique du développement .NET, **créer des fichiers de format tex personnalisés** vous offre un contrôle granulaire sur la composition des documents. Avec Aspose.TeX pour .NET, vous pouvez personnaliser le moteur TeX, le diriger vers un dossier d'entrée spécifique et produire une sortie XPS d'aspect professionnel — le tout en quelques lignes de code C#.

## Réponses rapides
- **Que signifie « créer un format tex personnalisé » ?** Cela signifie définir votre propre configuration du moteur TeX et des fichiers de format pour contrôler le processus de composition.  
- **Quelle bibliothèque faut‑il ?** Aspose.TeX pour .NET.  
- **Dois‑je définir un répertoire d'entrée tex ?** Oui – vous le spécifiez avec `InputFileSystemDirectory`.  
- **Quel type de sortie puis‑je générer ?** Tout dispositif pris en charge par Aspose.TeX, par ex. XPS, PDF ou PNG.  
- **Une licence est‑elle requise pour la production ?** Une licence valide d'Aspose.TeX est requise pour une utilisation commerciale.

## Qu’est‑ce qu’un format TeX personnalisé ?
Un format TeX personnalisé est un ensemble pré‑compilé de macros et de paramètres du moteur que le processeur TeX utilise pour interpréter vos fichiers source. En en créant un, vous pouvez intégrer la marque de votre entreprise, imposer des normes de documents ou accélérer la compilation pour des tâches répétitives.

## Pourquoi définir un répertoire d'entrée tex ?
Définir le **répertoire d'entrée tex** indique au moteur où chercher les fichiers auxiliaires, les polices personnalisées ou les fichiers de style supplémentaires. Cela garde votre projet organisé et évite les erreurs « file not found » lors de la compilation.

## Prérequis

Avant de vous lancer dans la personnalisation, assurez‑vous de disposer de :

1. **Aspose.TeX pour .NET** – téléchargez‑le depuis le [site Aspose.TeX](https://releases.aspose.com/tex/net/).  
2. Un **environnement de développement .NET** (Visual Studio, VS Code ou le .NET CLI).  
3. (Facultatif) Une licence **Aspose.TeX** valide si vous prévoyez d’exécuter le code en production.

## Importer les espaces de noms

Tout d'abord, importez les espaces de noms qui vous donnent accès à l'API Aspose.TeX. Cette étape garantit que les classes que nous utiliserons sont reconnues par le compilateur.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using Aspose.TeX.ResourceProviders;
using System.IO;
using System.Text;
```

## Étape 1 : Créer le fournisseur de format

Le `FormatProvider` indique au moteur le dossier contenant votre fichier de format personnalisé (`customtex.fmt`). Remplacez `"Your Output Directory"` par le chemin où vous avez stocké le format compilé.

```csharp
using (FormatProvider formatProvider =
    new FormatProvider(new InputFileSystemDirectory("Your Output Directory"), "customtex"))
{
```

## Étape 2 : Configurer les options de conversion (et définir le répertoire d'entrée tex)

Ici nous construisons l'objet `TeXOptions`. Notez le `InputWorkingDirectory` – c’est ici que nous **définissons le répertoire d'entrée tex** afin que le moteur puisse localiser les fichiers de support.

```csharp
    TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX(formatProvider));
    options.JobName = "typeset-with-custom-format";
    options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
    options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

## Étape 3 : Exécuter le travail

Nous alimentons maintenant le moteur avec une chaîne TeX simple, choisissons un dispositif de sortie (XPS dans cet exemple) et exécutons le travail.

```csharp
    new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
        "Congratulations! You have successfully typeset this text with your own TeX format!\\end")),
        new XpsDevice(), options).Run();
```

## Étape 4 : Peaufiner la sortie du terminal

Ajouter une ligne vide rend la sortie console plus lisible, surtout lorsque vous exécutez plusieurs travaux en lot.

```csharp
    options.TerminalOut.Writer.WriteLine();
}
// ExEnd:TypesetWithCustomTeXFormat
```

Félicitations ! Vous avez maintenant **créé un format tex personnalisé** et l’avez utilisé avec succès pour composer un document en .NET.

## Problèmes courants et solutions

| Problème | Raison | Solution |
|----------|--------|----------|
| *« Fichier de format introuvable »* | Chemin incorrect dans `FormatProvider` | Vérifiez que `"Your Output Directory"` contient `customtex.fmt` et que le chemin est absolu ou correctement relatif à l'exécutable. |
| *« Impossible de trouver le fichier d'entrée »* | `InputWorkingDirectory` pointe vers le mauvais dossier | Assurez‑vous que `"Your Input Directory"` contient le fichier source TeX ou que vous transmettez la source sous forme de flux (comme dans l'exemple). |
| *« Sortie du terminal illisible »* | Incompatibilité d'encodage | Utilisez `Encoding.UTF8` si votre source TeX contient des caractères non ASCII. |
| *« Le fichier XPS est vide »* | Le travail n'a pas été exécuté en raison d'une exception précédente | Vérifiez la console pour les messages d'erreur ; ils indiquent souvent des paquets manquants ou des erreurs de syntaxe dans la chaîne TeX. |

## Questions fréquentes

### Q1 : Puis‑je utiliser Aspose.TeX pour .NET avec d’autres bibliothèques de traitement de documents ?
**R :** Oui, Aspose.TeX est conçu pour s’intégrer parfaitement avec les autres bibliothèques de traitement de documents Aspose afin de gérer les documents de manière complète.

### Q2 : Existe‑t‑il une version d'essai gratuite d'Aspose.TeX pour .NET ?
**R :** Oui, vous pouvez accéder à la version d'essai gratuite [ici](https://releases.aspose.com/).

### Q3 : Comment obtenir du support pour Aspose.TeX pour .NET ?
**R :** Visitez le [forum Aspose.TeX](https://forum.aspose.com/c/tex/47) pour le support communautaire ou explorez les options de support premium [ici](https://purchase.aspose.com/buy).

### Q4 : Des licences temporaires sont‑elles disponibles pour Aspose.TeX pour .NET ?
**R :** Oui, vous pouvez obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

### Q5 : Où puis‑je trouver la documentation d'Aspose.TeX pour .NET ?
**R :** Consultez la documentation complète [ici](https://reference.aspose.com/tex/net/).

**Q : Puis‑je générer du PDF au lieu de XPS ?**  
**R :** Absolument. Remplacez `new XpsDevice()` par `new PdfDevice()` et ajustez le répertoire de sortie en conséquence.

**Q : Dois‑je recompiler le fichier de format après chaque modification ?**  
**R :** Oui. Toute modification des macros ou des paramètres du moteur nécessite de relancer `tex -ini` pour générer un nouveau fichier `.fmt`.

## Conclusion

En conclusion, Aspose.TeX pour .NET offre une solution robuste pour les scénarios **de création de format tex personnalisé**, offrant aux développeurs un contrôle sans précédent sur la composition des documents. Expérimentez différentes configurations, définissez le répertoire d'entrée tex approprié et intégrez le flux de travail dans vos applications .NET plus vastes pour une génération automatisée de documents de haute qualité.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2026-03-26  
**Testé avec :** Aspose.TeX 24.11 pour .NET  
**Auteur :** Aspose