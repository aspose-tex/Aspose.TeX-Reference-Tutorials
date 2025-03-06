---
title: Felülírja a feladat nevét, és írja be a terminál kimenetét Zip-be Java nyelven
linktitle: Felülírja a feladat nevét, és írja be a terminál kimenetét Zip-be Java nyelven
second_title: Aspose.TeX Java API
description: Tanulja meg, hogyan írhatja felül a jobneveket, és hogyan írhat terminálkimenetet ZIP-re Java nyelven az Aspose.TeX segítségével. Átfogó oktatóanyag Java fejlesztőknek.
weight: 11
url: /hu/java/customizing-output/override-job-name-zip/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Felülírja a feladat nevét, és írja be a terminál kimenetét Zip-be Java nyelven

## Bevezetés

A Java fejlesztés világában az Aspose.TeX a TeX fájlformátumok kezelésének hatékony eszközeként tűnik ki. Ebben az oktatóanyagban egy konkrét forgatókönyvet vizsgálunk meg – a jobnevek felülbírálását és a terminál kimenetének zip fájlba írását. Ez a lépésenkénti útmutató végigvezeti a folyamaton az Aspose.TeX for Java használatával.

## Előfeltételek

Mielőtt elkezdené ezt az oktatóanyagot, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
- Java programozási alapismeretek.
-  Aspose.TeX for Java telepítve. Ha nem, akkor letöltheti a[Aspose honlapja](https://releases.aspose.com/tex/java/).
- A Java fejlesztői környezet beállításának ismerete.

## Csomagok importálása

Kezdje azzal, hogy importálja a szükséges csomagokat a Java projektbe. Ez biztosítja, hogy hozzáférjen a feladathoz szükséges Aspose.TeX funkciókhoz.

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

## 1. lépés: Nyissa meg a ZIP-archívumot

Először is nyisson meg egy adatfolyamot a ZIP-archívumban, amely a bemeneti munkakönyvtárként fog szolgálni. Ez az archívum, amelyből az Ön adatait feldolgozzuk.

```java
// Nyisson meg egy adatfolyamot a bemeneti ZIP-archívumban
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
```

## 2. lépés: Nyissa meg a kimeneti ZIP-archívumot

Ezután nyisson meg egy adatfolyamot egy ZIP-archívumban, amely a kimeneti munkakönyvtárként fog szolgálni. Ide kerül a terminál kimenete.

```java
// Nyisson meg egy adatfolyamot a kimeneti ZIP-archívumban
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "terminal-out-to-zip.zip");
```

## 3. lépés: Állítsa be a konverziós beállításokat

Hozzon létre konverziós beállításokat az alapértelmezett ObjectTeX formátumhoz az ObjectTeX motorbővítménykor. Adja meg a feladat nevét és a ZIP-archívum munkakönyvtárait a bemenethez és a kimenethez egyaránt.

```java
// Hozzon létre TeX beállításokat az ObjectTeX formátumhoz
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("terminal-output-to-zip");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
```

## 4. lépés: Adja meg a terminál kimenetét

 Adja meg, hogy a terminál kimenetét a kimeneti munkakönyvtárban lévő fájlba kell írni. A fájl neve a következő lesz`<job_name>.trm`.

```java
// Adja meg a terminál kimeneti beállításait
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

## 5. lépés: Adja meg a mentési beállításokat, és futtassa a feladatot

Adja meg a mentési beállításokat, például ebben az esetben a PDF-mentési beállításokat. Futtassa a TeX feladatot az átalakítás végrehajtásához.

```java
// Határozza meg a mentési beállításokat, és futtassa a feladatot
options.setSaveOptions(new PdfSaveOptions());
new TeXJob("hello-world", new PdfDevice(), options).run();
```

## 6. lépés: A kimeneti ZIP-archívum véglegesítése

A feladat befejezése után véglegesítse a kimeneti ZIP-archívumot a megfelelő befejezés érdekében.

```java
// Véglegesítse a kimeneti ZIP archívumot
((OutputZipDirectory) options.getOutputWorkingDirectory()).finish();
```

## Következtetés

Gratulálunk! Sikeresen megtanulta, hogyan írhatja felül a jobneveket, és hogyan írhat terminálkimenetet ZIP-fájlba Java nyelven az Aspose.TeX használatával. Ez a hatékony funkció rugalmasságot és hatékonyságot ad Java fejlesztési projektjeihez.

## GYIK

### 1. kérdés: Mi az Aspose.TeX?

1. válasz: Az Aspose.TeX egy Java-könyvtár, amely lehetővé teszi a fejlesztők számára, hogy TeX fájlformátumokkal dolgozzanak, fejlett funkciókat biztosítva a dokumentumfeldolgozáshoz.

### 2. kérdés: Hogyan szerezhetek ideiglenes licencet az Aspose.TeX-hez?

 V2: Ideiglenes licencet szerezhet be[ez a link](https://purchase.aspose.com/temporary-license/).

### 3. kérdés: Hol találom az Aspose.TeX dokumentációt?

 A3: A dokumentáció elérhető[itt](https://reference.aspose.com/tex/java/).

### 4. kérdés: Létezik az Aspose.TeX ingyenes próbaverziója?

 A4: Igen, megtalálja az ingyenes próbaverziót[itt](https://releases.aspose.com/).

### 5. kérdés: Hol kérhetek támogatást vagy tehetek fel kérdéseket az Aspose.TeX-szel kapcsolatban?

 A5: Látogassa meg a[Aspose.TeX fórum](https://forum.aspose.com/c/tex/47) támogatásért és megbeszélésekért.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
