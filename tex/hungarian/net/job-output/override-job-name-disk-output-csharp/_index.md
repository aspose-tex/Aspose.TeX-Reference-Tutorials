---
title: Feladat nevének felülírása és a terminál kimenetének lemezre írása (C#)
linktitle: Feladat nevének felülírása és a terminál kimenetének lemezre írása (C#)
second_title: Aspose.TeX .NET API
description: Fedezze fel, hogyan használja az Aspose.TeX for .NET-et a jobnevek felülbírálásához és a terminálkimenet rögzítéséhez. Kövesse átfogó útmutatónkat a zökkenőmentes TeX fájlkezeléshez.
weight: 10
url: /hu/net/job-output/override-job-name-disk-output-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Feladat nevének felülírása és a terminál kimenetének lemezre írása (C#)

## Bevezetés

Üdvözöljük ebben a lépésről lépésre szóló útmutatóban az Aspose.TeX for .NET használatáról a jobnevek felülbírálásához és a terminálkimenet lemezre írásához C# programozási nyelven. Az Aspose.TeX for .NET egy hatékony könyvtár, amely lehetővé teszi a TeX fájlokkal való zökkenőmentes munkát, és ebben az oktatóanyagban egy konkrét feladatra összpontosítunk: a jobnevek felülbírálására és a terminál kimenetének rögzítésére.

## Előfeltételek

Mielőtt belevágnánk az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

-  Aspose.TeX for .NET Library: Győződjön meg arról, hogy telepítve van az Aspose.TeX for .NET könyvtár. Letöltheti a[Aspose.TeX weboldal](https://releases.aspose.com/tex/net/).

- .NET fejlesztői környezet: Működő .NET fejlesztői környezettel kell rendelkeznie, beleértve az integrált fejlesztői környezetet (IDE), például a Visual Studiot.

- Alapvető C# ismeretek: Ismerkedjen meg a C# programozási nyelv alapjaival.

- Bemeneti és kimeneti könyvtárak: Készítse elő a bemeneti és kimeneti könyvtárakat a TeX fájlokhoz.

## Névterek importálása

Győződjön meg arról, hogy a C# kódban tartalmazza az Aspose.TeX funkciók eléréséhez szükséges névtereket:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

## 1. lépés: Hozzon létre konverziós beállításokat

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

Hozzon létre TeXOptions-t a ConsoleAppOptions segítségével, és adja meg az ObjectTeX-et TeXConfig-ként.

## 2. lépés: Adja meg a feladat nevét

```csharp
options.JobName = "overridden-job-name";
```

Adja meg a feladat nevét az alapértelmezett név felülbírálásához.

## 3. lépés: Adja meg a beviteli munkakönyvtárat

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

Állítsa be a TeX-fájlok bemeneti munkakönyvtárát.

## 4. lépés: Adja meg a kimeneti munkakönyvtárat

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Határozza meg a kimeneti munkakönyvtárat a feldolgozott TeX-fájlok mentéséhez.

## 5. lépés: Írja a terminál kimenetét a lemezre

```csharp
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

Állítsa be a terminál kimenetét úgy, hogy a kimeneti könyvtárban lévő fájlba írja be.

## 6. lépés: Futtassa a munkát

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

Hozzon létre egy TeXJob-ot, megadva a feladat nevét, a kimeneti eszközt (XpsDevice) és a beállításokat. Végül futtassa a munkát.

## Következtetés

Gratulálunk! Sikeresen megtanulta, hogyan írhatja felül a jobneveket és írhatja lemezre a terminálkimenetet az Aspose.TeX for .NET segítségével C# nyelven. Ez a képesség értékes a TeX feldolgozási feladatok hatékony kezeléséhez.

## GYIK

### 1. kérdés: Használhatom az Aspose.TeX-et .NET-hez más .NET-könyvtárakkal?

1. válasz: Igen, az Aspose.TeX for .NET zökkenőmentesen integrálható más .NET-könyvtárakba.

### 2. kérdés: Elérhető ingyenes próbaverzió az Aspose.TeX for .NET számára?

 2. válasz: Igen, letölthet egy ingyenes próbaverziót[itt](https://releases.aspose.com/).

### 3. kérdés: Hogyan kaphatok támogatást az Aspose.TeX for .NET-hez?

 A3: Látogassa meg a[Aspose.TeX fórum](https://forum.aspose.com/c/tex/47) közösséget és támogatást kapni.

### 4. kérdés: Rendelkezésre állnak ideiglenes licencek az Aspose.TeX for .NET számára?

 V4: Igen, ideiglenes engedélyt kaphat[itt](https://purchase.aspose.com/temporary-license/).

### 5. kérdés: Hol találom az Aspose.TeX for .NET dokumentációját?

 V5: A dokumentáció elérhető[itt](https://reference.aspose.com/tex/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
