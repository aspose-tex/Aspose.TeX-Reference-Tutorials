---
title: Feladat nevének felülírása és a terminálkimenet írása Zip-re (C#)
linktitle: Feladat nevének felülírása és a terminálkimenet írása Zip-re (C#)
second_title: Aspose.TeX .NET API
description: Ismerje meg, hogyan írhatja felül a jobneveket és írhatja a terminálkimenetet ZIP-fájlba az Aspose.TeX for .NET használatával. Lépésről lépésre útmutató C# példákkal.
weight: 11
url: /hu/net/job-output/override-job-name-zip-output-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Feladat nevének felülírása és a terminálkimenet írása Zip-re (C#)

## Bevezetés

Ebben az oktatóanyagban megvizsgáljuk, hogyan írhatjuk felül a feladat nevét, és hogyan írhatjuk a terminál kimenetét ZIP-fájlba az Aspose.TeX for .NET használatával. Az Aspose.TeX egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy TeX-dokumentumokkal dolgozzanak .NET-alkalmazásaikban. Ebben a konkrét példában egy gyakori feladatra összpontosítunk – a terminál kimenetének ZIP-fájlba írására, amely felülírhatja a feladat nevét.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

- C# gyakorlati ismerete
- Aspose.TeX for .NET telepítve
- Írja be a ZIP archívumot a munkakönyvtárhoz
- Kimeneti ZIP archívum a terminál kimenetéhez

## Névterek importálása

Mielőtt belemerülne a kódba, győződjön meg arról, hogy tartalmazza a szükséges névtereket a C# projektben:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Pdf;
using System.IO;
```

Most bontsuk le a példát több lépésre, hogy végigvezetjük a folyamaton.

## 1. lépés: Nyissa meg a bemeneti és kimeneti ZIP-folyamokat

```csharp
using (Stream inZipStream = File.Open(Path.Combine("Your Input Directory", "zip-in.zip"), FileMode.Open))
using (Stream outZipStream = File.Open(Path.Combine("Your Output Directory", "terminal-out-to-zip.zip"), FileMode.Create))
{
    // Az 1. lépés kódja itt található
}
```

## 2. lépés: Állítsa be a konverziós beállításokat

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
options.JobName = "terminal-output-to-zip";
options.InputWorkingDirectory = new InputZipDirectory(inZipStream, "in");
options.OutputWorkingDirectory = new OutputZipDirectory(outZipStream);
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## 3. lépés: Adja meg a mentési beállításokat

```csharp
options.SaveOptions = new PdfSaveOptions();
```

## 4. lépés: Futtassa a TeX feladatot

```csharp
new TeXJob("hello-world", new PdfDevice(), options).Run();
```

## 5. lépés: A kimeneti ZIP-archívum véglegesítése

```csharp
((OutputZipDirectory)options.OutputWorkingDirectory).Finish();
```

## Következtetés

Gratulálunk! Sikeresen megtanulta, hogyan írhatja felül a job nevét, és hogyan írhatja a terminál kimenetét ZIP-fájlba az Aspose.TeX for .NET használatával. Ez a technika hihetetlenül hasznos lehet, amikor TeX dokumentumokat kezel C# alkalmazásaiban.

## GYIK

### 1. kérdés: Használhatom az Aspose.TeX-et .NET-hez más .NET-nyelvekkel, például a VB.NET-tel?

1. válasz: Igen, az Aspose.TeX for .NET kompatibilis az összes .NET nyelvvel.

### 2. kérdés: Hol találok további dokumentációt az Aspose.TeX for .NET-hez?

 A2: Látogassa meg a[dokumentáció](https://reference.aspose.com/tex/net/) részletes információkért.

### 3. kérdés: Hogyan szerezhetek ideiglenes licencet az Aspose.TeX-hez?

 A3: Szerezzen be a[ideiglenes engedély](https://purchase.aspose.com/temporary-license/) tesztelési célokra.

### 4. kérdés: Létezik közösségi fórum az Aspose.TeX támogatására?

 A4: Igen, csatlakozz a[Aspose.TeX fórum](https://forum.aspose.com/c/tex/47) közösségi támogatásért.

### 5. kérdés: Hol vásárolhatom meg az Aspose.TeX-et .NET-hez?

 V5: Megvásárolhatja az Aspose.TeX-et[itt](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
