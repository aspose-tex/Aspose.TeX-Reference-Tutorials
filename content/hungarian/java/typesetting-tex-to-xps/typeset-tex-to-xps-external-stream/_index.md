---
title: Írja be a TeX-et XPS-re Java nyelven külső adatfolyammal
linktitle: Írja be a TeX-et XPS-re Java nyelven külső adatfolyammal
second_title: Aspose.TeX Java API
description: Tanulja meg, hogyan lehet TeX-et XPS-re szedni Java nyelven az Aspose.TeX használatával. Fedezze fel a zökkenőmentes dokumentumfeldolgozáshoz lépésről lépésre szóló útmutatót.
type: docs
weight: 10
url: /hu/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
---
## Bevezetés

A Java fejlesztés világában az Aspose.TeX hatékony eszköz a TeX dokumentumok különféle formátumokba, köztük XPS formátumokba történő szedésére. Ha javítani szeretné Java-alkalmazása dokumentumfeldolgozási képességeit, ez az oktatóanyag az Ön számára készült. Ebben a lépésenkénti útmutatóban végigvezetjük a TeX-nek XPS-be történő szedés folyamatán az Aspose.TeX for Java használatával külső adatfolyammal.

## Előfeltételek

Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételeket teljesítette:

-  Java Development Kit (JDK): Győződjön meg arról, hogy a Java telepítve van a rendszeren. Letöltheti innen[itt](https://www.oracle.com/java/technologies/javase-downloads.html).

-  Aspose.TeX for Java: Töltse le és telepítse az Aspose.TeX for Java programot. A letöltési linket megtalálod[itt](https://releases.aspose.com/tex/java/).

## Csomagok importálása

Kezdje a szükséges csomagok importálásával, hogy elindítsa a TeX-ről XPS-re való konverziós utat. Helyezze be a következő kódrészletet a Java projektbe:

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

## 1. lépés: Konfigurálja a konverziós beállításokat

Kezdje a konverziós beállítások létrehozásával az alapértelmezett ObjectTeX formátumhoz a következő kód használatával:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

Ez megalapozza a szedés folyamatát.

## 2. lépés: Adja meg a feladat nevét és a könyvtárakat

Adja meg a feladat nevét, és állítsa be a bemeneti és kimeneti munkakönyvtárakat:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Győződjön meg arról, hogy az olyan helyőrzőket, mint a „Beviteli könyvtár” a tényleges könyvtárútvonalakra cseréli.

## 3. lépés: A terminálkimenet konfigurálása

Adja meg, hogy a terminál kimenetét egy fájlba kell írni a kimeneti munkakönyvtárban:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

Ez a lépés biztosítja a részletes naplók rögzítését hibakereséshez.

## 4. lépés: Nyissa meg a kimeneti adatfolyamot

Nyisson meg egy adatfolyamot a szedett XPS-dokumentum írásához:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

Cserélje ki a "Saját kimeneti könyvtár" részt a megfelelő elérési úttal.

## 5. lépés: Futtassa a munkát

Hajtsa végre a TeX-XPS konvertálási feladatot:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

Ezzel a folyamat befejeződik, és a megadott kimeneti könyvtárban megtalálja a betáplált XPS-dokumentumot.

## Következtetés

Gratulálunk! Sikeresen beírta a TeX-et XPS-re Java nyelven az Aspose.TeX használatával. Ez a lehetőségek világát nyitja meg a Java alkalmazások dokumentumfeldolgozásában. Kísérletezzen különböző TeX fájlokkal, és fedezze fel az Aspose.TeX által kínált különféle funkciókat.

## GYIK

### 1. kérdés: Használhatom az Aspose.TeX for Java-t más dokumentumformátumokkal?

1. válasz: Az Aspose.TeX elsősorban a TeX-hez kapcsolódó dokumentumfeldolgozásra összpontosít. Más formátumok esetén fedezze fel az Aspose kiterjedt termékkínálatát.

### 2. kérdés: Elérhető próbaverzió?

 2. válasz: Igen, kipróbálhatja az Aspose.TeX-et, ha letölti az ingyenes próbaverziót[itt](https://releases.aspose.com/).

### 3. kérdés: Hol találok átfogó dokumentációt?

 V3: Lásd a dokumentációt[itt](https://reference.aspose.com/tex/java/) részletes információkért és példákért.

### 4. kérdés: Hogyan kaphatok támogatást vagy kérhetek segítséget?

 4. válasz: Látogassa meg az Aspose.TeX fórumot[itt](https://forum.aspose.com/c/tex/47)közösségi támogatásra és beszélgetésekre.

### 5. kérdés: Kaphatok ideiglenes licencet tesztelési célokra?

 V5: Igen, szerezhet ideiglenes engedélyt[itt](https://purchase.aspose.com/temporary-license/).