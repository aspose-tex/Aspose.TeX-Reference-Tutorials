---
date: 2026-02-20
description: Erfahren Sie, wie Sie TeX in Java mit Aspose.TeX in XPS konvertieren.
  Diese Schritt‑für‑Schritt‑Anleitung zeigt Ihnen, wie Sie TeX‑Dateien konvertieren
  und XPS‑Dokumentströme effizient erzeugen.
linktitle: How to Convert TeX to XPS in Java with External Stream
second_title: Aspose.TeX Java API
title: Wie man TeX in XPS in Java mit externem Stream konvertiert
url: /de/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man TeX in XPS in Java mit externem Stream konvertiert

## Einführung

Wenn Sie **TeX**‑Dateien aus einer Java‑Anwendung in hochwertige XPS‑Ausgabe konvertieren müssen, macht Aspose.TeX für Java die Aufgabe einfach. In diesem Tutorial sehen Sie genau **wie man TeX** in ein XPS‑Dokument mit einem externen Ausgabestream konvertiert, was ideal ist, wenn Sie das Ergebnis direkt an eine Antwort, einen Cloud‑Speicherdienst oder ein beliebiges benutzerdefiniertes Ziel weiterleiten möchten. Lassen Sie uns den gesamten Prozess durchgehen, von der Einrichtung der Umgebung bis zum Schreiben der finalen XPS‑Datei.

## Schnelle Antworten
- **Worum geht es in diesem Tutorial?** Konvertierung von TeX zu XPS mit Aspose.TeX und einem externen Stream.  
- **Welche primäre Bibliothek wird benötigt?** Aspose.TeX für Java.  
- **Benötige ich eine Lizenz?** Für den Produktionseinsatz ist eine temporäre oder vollständige Lizenz erforderlich.  
- **Kann ich XPS‑Dokument‑Streams erzeugen?** Ja – das Beispiel schreibt das XPS direkt in einen `OutputStream`.  
- **Welche Java‑Version wird unterstützt?** Jede JDK 8+ (das Tutorial verwendet JDK 11 als Referenz).

## Wie man TeX zu XPS mit einem externen Stream konvertiert

Dieser Abschnitt wiederholt das Kern‑Keyword in einer eigenen Überschrift, wodurch es für Leser und KI‑Engines einfach ist, die genaue Lösung zu finden.

## Voraussetzungen

Bevor Sie in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes haben:

- Java Development Kit (JDK): Stellen Sie sicher, dass Java auf Ihrem System installiert ist. Sie können es von [hier](https://www.oracle.com/java/technologies/javase-downloads.html) herunterladen.

- Aspose.TeX für Java: Laden Sie Aspose.TeX für Java herunter und installieren Sie es. Den Download‑Link finden Sie [hier](https://releases.aspose.com/tex/java/).

## Pakete importieren

Beginnen Sie damit, die notwendigen Pakete zu importieren, um Ihre TeX‑zu‑XPS‑Konvertierung zu starten. Fügen Sie den folgenden Code‑Snippet in Ihr Java‑Projekt ein:

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

## Schritt 1: Konvertierungsoptionen konfigurieren

Beginnen Sie damit, Konvertierungsoptionen für das Standard‑ObjectTeX‑Format mit folgendem Code zu erstellen:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

## Schritt 2: Job‑Name und Verzeichnisse festlegen

Definieren Sie einen Job‑Namen und setzen Sie die Eingabe‑ und Ausgabe‑Arbeitsverzeichnisse:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Stellen Sie sicher, dass Sie Platzhalter wie "Your Input Directory" durch Ihre tatsächlichen Verzeichnispfade ersetzen.

## Schritt 3: Terminalausgabe konfigurieren

Geben Sie an, dass die Terminalausgabe in eine Datei im Ausgabe‑Arbeitsverzeichnis geschrieben werden soll:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

Dieser Schritt sorgt dafür, dass detaillierte Protokolle zur Fehlersuche erfasst werden.

## Schritt 4: Ausgabestream öffnen

Öffnen Sie einen Stream, um das gesetzte XPS‑Dokument zu schreiben:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

Ersetzen Sie "Your Output Directory" durch den entsprechenden Pfad.

## Schritt 5: Job ausführen

Führen Sie den TeX‑zu‑XPS‑Konvertierungs‑Job aus:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

Damit ist der Vorgang abgeschlossen, und Sie finden Ihr erzeugtes XPS‑Dokument im angegebenen Ausgabeverzeichnis.

## Warum das wichtig ist

Die Verwendung eines externen `OutputStream` gibt Ihnen die volle Kontrolle darüber, wohin die XPS‑Daten gehen – ob Sie sie direkt an einen Web‑Client senden, in Cloud‑Speicher ablegen oder in eine andere Verarbeitungspipeline einbinden. Sie eliminiert die Notwendigkeit von Zwischendateien und reduziert den I/O‑Overhead, was besonders in Hochdurchsatz‑ oder Server‑less‑Umgebungen wertvoll ist.

## Häufige Probleme und Lösungen

| Problem | Warum es passiert | Wie zu beheben |
|---------|-------------------|----------------|
| **FileNotFoundException** beim Öffnen des Streams | Der Pfad des Ausgabeverzeichnisses ist falsch oder existiert nicht. | Überprüfen Sie den Pfad, erstellen Sie das Verzeichnis vorher, oder verwenden Sie `Files.createDirectories`. |
| **NullPointerException** bei `options.getOutputWorkingDirectory()` | `setOutputWorkingDirectory` wurde nicht aufgerufen oder gab `null` zurück. | Stellen Sie sicher, dass Sie `options.setOutputWorkingDirectory` aufrufen, bevor Sie es verwenden. |
| **LicenseException** zur Laufzeit | Ausführung ohne gültige Aspose.TeX‑Lizenz. | Wenden Sie eine temporäre oder permanente Lizenz an mit `License license = new License(); license.setLicense("Aspose.TeX.lic");`. |

## FAQ

**F: Kann ich Aspose.TeX für Java mit anderen Dokumentformaten verwenden?**  
A: Aspose.TeX konzentriert sich hauptsächlich auf die Verarbeitung von TeX‑bezogenen Dokumenten. Für andere Formate erkunden Sie Asposes umfangreiches Produktportfolio.

**F: Gibt es eine Testversion?**  
A: Ja, Sie können Aspose.TeX ausprobieren, indem Sie die kostenlose Testversion [hier](https://releases.aspose.com/) herunterladen.

**F: Wo finde ich umfassende Dokumentation?**  
A: Siehe die Dokumentation [hier](https://reference.aspose.com/tex/java/) für detaillierte Informationen und Beispiele.

**F: Wie erhalte ich Support oder Hilfe?**  
A: Besuchen Sie das Aspose.TeX‑Forum [hier](https://forum.aspose.com/c/tex/47) für Community‑Support und Diskussionen.

**F: Kann ich eine temporäre Lizenz für Testzwecke erhalten?**  
A: Ja, Sie können eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/) erwerben.

## Fazit

Herzlichen Glückwunsch! Sie haben gerade **gelernt, wie man TeX** in ein XPS‑Dokument in Java mit Aspose.TeX und einem externen Stream konvertiert. Diese Technik gibt Ihnen die volle Kontrolle darüber, wohin die XPS‑Ausgabe geht – ob in ein Dateisystem, eine Web‑Antwort oder einen Cloud‑Bucket. Experimentieren Sie gern mit verschiedenen TeX‑Quellen, passen Sie die `TeXOptions` für benutzerdefinierte Schriftarten an oder binden Sie den Stream in eine größere Dokument‑Generierungs‑Pipeline ein.

---

**Last Updated:** 2026-02-20  
**Tested With:** Aspose.TeX for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}