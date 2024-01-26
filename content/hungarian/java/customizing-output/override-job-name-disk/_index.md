---
title: Felülírja a feladat nevét és írja be a terminál kimenetét Java nyelven
linktitle: Felülírja a feladat nevét és írja be a terminál kimenetét Java nyelven
second_title: Aspose.TeX Java API
description: Fedezze fel a lépésenkénti útmutatót a jobnevek felülírásáról és a terminálkimenet írásáról az Aspose.TeX for Java használatával. Javítsa dokumentumfeldolgozását hatékony testreszabási lehetőségekkel.
type: docs
weight: 10
url: /hu/java/customizing-output/override-job-name-disk/
---
## Bevezetés

Az Aspose.TeX for Java hatékony szolgáltatásokat nyújt a TeX fájlokkal való munkavégzéshez, lehetővé téve a fejlesztők számára a TeX dokumentumfeldolgozás kezelését és testreszabását. Ebben az oktatóanyagban végigvezetjük a feladat nevének felülbírálásán és a terminálkimenet fájlrendszerbe írásán a Java Aspose.TeX használatával.

## Előfeltételek

Mielőtt belevágnánk az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

- Java programozási ismeretek.
-  Aspose.TeX for Java telepítve. Letöltheti a[Aspose.TeX Java dokumentáció](https://reference.aspose.com/tex/java/).

## Csomagok importálása

A kezdéshez importálja a szükséges csomagokat a Java projektbe. A Java-fájlba foglalja bele a következő importokat:

```java
package com.aspose.tex.OverridenJobNameAndTerminalOutputWrittenToDisk;

import java.io.IOException;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

## Feladatnév felülírása és terminálkimenet írása

### 1. lépés: Hozzon létre konverziós beállításokat

Kezdje azzal, hogy az ObjectTeX motorbővítéskor hozzon létre konverziós beállításokat az alapértelmezett ObjectTeX formátumhoz. Használja a következő kódrészletet:

```java
//ExStart:OverrideJobName-WriteTerminalOutputTo FileSystem
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

### 2. lépés: Adja meg a feladat nevét és a munkakönyvtárakat

Adja meg a feladat nevét, a bemeneti munkakönyvtárat és a kimeneti munkakönyvtárat. Ha a job neve nincs megadva, akkor a TeXJob konstruktor első argumentuma lesz a job neve. Használja a következő kódrészletet:

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### 3. lépés: Írja be a terminál kimenetét a fájlrendszerbe

 Adja meg, hogy a terminál kimenetét a kimeneti munkakönyvtárban lévő fájlba kell írni. A fájl neve a következő lesz`<job_name>.trm`. Adja hozzá a következő kódot:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### 4. lépés: Futtassa a munkát

Futtassa a TeX-feladatot a megadott beállításokkal és feladatnévvel. A következőképpen teheti meg:

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
// ExEnd:OverrideJobName-WriteTerminalOutputTo FileSystem
```

Gratulálunk! Sikeresen felülbírálta a job nevét és a terminálkimenetet a fájlrendszerbe a Java Aspose.TeX használatával.

## Következtetés

Ebben az oktatóanyagban megvizsgáltuk, hogyan használható az Aspose.TeX for Java a job nevének felülbírálására és a terminál kimenetének rögzítésére. Ezek a funkciók lehetővé teszik a fejlesztők számára a TeX-dokumentumok feldolgozása feletti finom irányítást, növelve a testreszabást és a rugalmasságot.

## GYIK

### 1. kérdés: Használhatom az Aspose.TeX for Java programot más Java könyvtárakkal?

1. válasz: Igen, az Aspose.TeX for Java zökkenőmentesen integrálható más Java könyvtárakkal a dokumentumfeldolgozási képességek javítása érdekében.

### 2. kérdés: Hol találok támogatást az Aspose.TeX for Java számára?

 A2: Látogassa meg a[Aspose.TeX fórum](https://forum.aspose.com/c/tex/47) közösségi támogatásért és segítségért bármilyen felmerülő problémában.

### 3. kérdés: Elérhető ingyenes próbaverzió az Aspose.TeX for Java számára?

 3. válasz: Igen, elérheti az Aspose.TeX Java ingyenes próbaverzióját[itt](https://releases.aspose.com/).

### 4. kérdés: Hogyan szerezhetek ideiglenes licencet az Aspose.TeX for Java számára?

 A4: Kövesd ezt[link](https://purchase.aspose.com/temporary-license/) ideiglenes engedély megszerzésére tesztelési és értékelési célokra.

### 5. kérdés: Hol vásárolhatom meg az Aspose.TeX-et Java-hoz?

 A5: Látogassa meg a[vásárlási oldal](https://purchase.aspose.com/buy) hogy szerezzen licencet az Aspose.TeX for Java számára.