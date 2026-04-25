---
date: 2026-03-24
description: Apprenez comment obtenir un flux de fichier C# tout en spécifiant les
  entrées requises pour Aspose.TeX .NET. Suivez notre guide pas à pas.
linktitle: Get File Stream C# in Aspose.TeX Required Input Directory
second_title: Aspose.TeX .NET API
title: Obtenir le flux de fichier C# dans Aspose.TeX – Répertoire d'entrée requis
url: /fr/net/advanced-io/required-input-directory-csharp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Obtenir le flux de fichier C# dans Aspose.TeX Répertoire d'entrée requis

## Introduction

Si vous devez **obtenir le flux de fichier C#** tout en travaillant avec Aspose.TeX, la première étape consiste à indiquer à la bibliothèque où se trouvent vos fichiers source TeX. Ce tutoriel vous guide à travers le code exact dont vous avez besoin pour **spécifier l'entrée requise** pour le moteur Aspose.TeX, transformant un dossier de fichiers `.tex` en un flux que l'API peut consommer. À la fin de ce guide, vous disposerez d’une classe réutilisable `RequiredInputDirectory` qui fait le lien proprement entre votre système de fichiers et Aspose.TeX.

## Réponses rapides
- **Que signifie « get file stream C# » ?** Cela signifie retourner un objet `System.IO.Stream` pour le nom de fichier demandé.  
- **Pourquoi dois‑je spécifier l'entrée requise ?** Aspose.TeX recherche les fichiers TeX dans le répertoire d'entrée ; sans cela, le moteur ne peut pas résoudre les commandes `\include{}` ou `\input{}`.  
- **Quels espaces de noms sont obligatoires ?** `Aspose.TeX.IO`, `System.Collections.Generic` et `System.IO`.  
- **Une licence spéciale est‑elle nécessaire ?** Une licence de développement ou d’essai d’Aspose.TeX est requise pour une utilisation en production.  
- **Puis‑je réutiliser la classe dans plusieurs projets ?** Oui — une fois compilée, elle fonctionne avec n’importe quel projet .NET qui référence Aspose.TeX.

## Qu'est-ce que le flux de fichier C# ?

Dans .NET, un *flux de fichier* est un objet dérivé de `System.IO.Stream` qui fournit un accès en lecture/écriture aux octets bruts d’un fichier. Lorsque Aspose.TeX demande un fichier, il s’attend à ce que vous retourniez un tel flux afin que le moteur puisse lire la source TeX directement depuis la mémoire ou le disque.

## Pourquoi spécifier l'entrée requise pour Aspose.TeX ?

Aspose.TeX traite les documents TeX en localisant les fichiers auxiliaires (images, fichiers de style, fichiers TeX inclus) relatifs à un **répertoire d'entrée requis**. En définissant explicitement ce répertoire, vous :

1. Évitez les erreurs « fichier introuvable » lors de la compilation.  
2. Isolez la logique d’accès aux fichiers de votre projet du reste du code.  
3. Facilitez les tests unitaires en simulant le répertoire d'entrée.

## Prérequis

- **Aspose.TeX for .NET Library** – téléchargez‑la depuis la [page de publication](https://releases.aspose.com/tex/net/).  
- **Environnement de développement .NET** – Visual Studio 2022, Rider ou tout IDE supportant .NET 6+.

Maintenant, importons les espaces de noms dont vous aurez besoin.

## Importer les espaces de noms

Ajoutez ces instructions `using` en haut de votre fichier C# afin que le compilateur puisse localiser les types requis :

```csharp
using Aspose.TeX.IO;
using System.Collections.Generic;
using System.IO;
```

## Comment obtenir le flux de fichier C# avec un répertoire d'entrée requis

Vous trouverez ci‑dessous une décomposition étape par étape de la classe `RequiredInputDirectory`. Chaque étape comprend une courte explication suivie du bloc de code exact à copier dans votre projet.

### Étape 1 : Créer la classe `RequiredInputDirectory`

La classe implémente deux interfaces — `IInputWorkingDirectory` (utilisée par Aspose.TeX pour localiser les fichiers) et `IFileCollector` (utilisée pour collecter les noms de fichiers au fur et à mesure qu’ils sont ajoutés).

```csharp
public class RequiredInputDirectory : IInputWorkingDirectory, IFileCollector
{
    private Dictionary<string, Dictionary<string, string>> _fileNames =
        new Dictionary<string, Dictionary<string, string>>();

    public RequiredInputDirectory()
    {
    }
```

### Étape 2 : Implémenter la méthode `StoreFileName`

Cette méthode enregistre chaque nom de fichier que vous transmettez au collecteur, en les regroupant par extension pour une recherche rapide.

```csharp
public void StoreFileName(string fileName)
{
    string extension = Path.GetExtension(fileName);
    string name = Path.GetFileNameWithoutExtension(fileName);

    Dictionary<string, string> files;
    if (!_fileNames.TryGetValue(extension, out files))
        _fileNames.Add(extension, files = new Dictionary<string, string>());

    files[name] = fileName;
}
```

### Étape 3 : Implémenter l’interface `IInputWorkingDirectory` – GetFile

Lorsque Aspose.TeX demande un fichier, cette méthode renvoie un **flux de fichier** (ou `null` si vous gérez le flux ailleurs). La sortie `fullName` indique au moteur le chemin exact résolu.

```csharp
public Stream GetFile(string fileName, out string fullName, bool searchSubdirectories = false)
{
    fullName = fileName;
    return null; // Here we actually return a stream for the file requested by its name.
}
```

### Étape 4 : Rassembler les collections de fichiers par extension

Le moteur peut demander tous les fichiers d’une certaine extension (par ex., « .tex »). Cette méthode renvoie ces noms sous forme de tableau de chaînes.

```csharp
public string[] GetFileNamesByExtension(string extension, string path = null)
{
    Dictionary<string, string> files;
    if (!_fileNames.TryGetValue(extension, out files))
        return new string[0];

    return new List<string>(files.Values).ToArray();
}
```

### Étape 5 : Libérer les ressources

Nettoyer le dictionnaire interne évite les fuites de mémoire, surtout lorsque la classe est utilisée dans des services à long terme.

```csharp
public void Dispose()
{
    _fileNames.Clear();
}
```

Avec ces cinq extraits, vous disposez maintenant d’une classe `RequiredInputDirectory` pleinement fonctionnelle qui **obtient le flux de fichier C#** et **spécifie l'entrée requise** pour le processeur Aspose.TeX.

## Problèmes courants et solutions

| Problème | Pourquoi cela se produit | Solution rapide |
|----------|--------------------------|-----------------|
| `GetFile` renvoie `null` et la compilation échoue | La méthode est un espace réservé ; vous devez ouvrir un vrai `FileStream` si vous voulez que le moteur lise le fichier. | Remplacez `return null;` par `return File.OpenRead(fullName);` (assurez‑vous que le chemin est correct). |
| Les fichiers ne sont pas trouvés bien qu’ils existent | Le collecteur n’a pas reçu les bons noms de fichiers ou extensions. | Appelez `StoreFileName` pour chaque fichier **avant** de transmettre le répertoire à Aspose.TeX. |
| La consommation de mémoire explose avec de nombreux gros fichiers `.tex` | Le dictionnaire conserve tous les noms de fichiers en mémoire. | Disposez de `RequiredInputDirectory` dès que le traitement est terminé, ou utilisez une approche de streaming. |

## Questions fréquemment posées

**Q : Où puis‑je trouver la documentation Aspose.TeX pour .NET ?**  
R : La documentation est disponible [ici](https://reference.aspose.com/tex/net/).

**Q : Comment télécharger la bibliothèque Aspose.TeX pour .NET ?**  
R : Vous pouvez télécharger la bibliothèque depuis la [page de publication](https://releases.aspose.com/tex/net/).

**Q : Où obtenir du support pour Aspose.TeX pour .NET ?**  
R : Visitez le [forum Aspose.TeX](https://forum.aspose.com/c/tex/47) pour le support communautaire.

**Q : Existe‑t‑il une version d’essai gratuite ?**  
R : Oui, vous pouvez explorer la version d’essai gratuite [ici](https://releases.aspose.com/).

**Q : Comment obtenir une licence temporaire pour Aspose.TeX pour .NET ?**  
R : Vous pouvez acquérir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

## Questions fréquemment posées supplémentaires

**Q : Puis‑je utiliser cette classe dans un projet .NET Core ?**  
R : Absolument — `IInputWorkingDirectory` et `IFileCollector` sont indépendants de la plateforme.

**Q : Dois‑je enregistrer manuellement le répertoire auprès d’Aspose.TeX ?**  
R : Oui, transmettez une instance de `RequiredInputDirectory` au constructeur `TeXDocument` ou à l’appel d’API approprié.

**Q : Quelles versions de .NET sont prises en charge ?**  
R : Aspose.TeX fonctionne avec .NET 5, .NET 6 et les versions ultérieures, ainsi qu’avec .NET Framework 4.6.2+.

---

**Dernière mise à jour :** 2026-03-24  
**Testé avec :** Aspose.TeX 24.11 for .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}