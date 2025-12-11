---
date: 2025-12-11
description: Erfahren Sie, wie Sie TeX in Java mit Aspose.TeX in XPS konvertieren.
  Diese Schritt‑für‑Schritt‑Anleitung zeigt Ihnen, wie Sie XPS‑Dokumentströme effizient
  erzeugen.
linktitle: How to Convert TeX to XPS in Java with External Stream
second_title: Aspose.TeX Java API
title: Wie man TeX nach XPS in Java mit externem Stream konvertiert
url: /de/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man TeX in XPS in Java mit externem Stream konvertiert

## Einführung

Wenn Sie **TeX**-Dateien aus einer Java-Anwendung in hochwertige XPS-Ausgabe konvertieren müssen, macht Aspose.TeX für Java die Aufgabe einfach. In diesem Tutorial sehen Sie genau **wie man TeX** in ein XPS-Dokument mit einem externen Ausgabestream konvertiert, was ideal ist, wenn Sie das Ergebnis direkt an eine Antwort, einen Cloud‑Speicherdienst oder ein beliebiges benutzerdefiniertes Ziel weiterleiten möchten. Lassen Sie uns den gesamten Prozess durchgehen, von der Einrichtung der Umgebung bis zum Schreiben der finalen XPS-Datei.

## Schnelle Antworten
- **Worum geht es in diesem Tutorial?** Konvertierung von TeX zu XPS mit Aspose.TeX und einem externen Stream.  
- **Welche primäre Bibliothek wird benötigt?** Aspose.TeX für Java.  
- **Benötige ich eine Lizenz?** Für den Produktionseinsatz ist eine temporäre oder vollständige Lizenz erforderlich.  
- **Kann ich XPS-Dokument-Streams erzeugen?** Ja – das Beispiel schreibt das XPS direkt in einen `OutputStream`.  
- **Welche Java-Version wird unterstützt?** Jede JDK 8+ (das Tutorial verwendet JDK 11 als Referenz).

## Voraussetzungen

Bevor Sie in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes haben:

- Java Development Kit (JDK): Stellen Sie sicher, dass Java auf Ihrem System installiert ist. Sie können es von [hier](https://www.oracle.com/java/technologies/javase-downloads.html) herunterladen.
- Aspose.TeX für Java: Laden Sie Aspose.TeX für Java herunter und installieren Sie es. Den Download-Link finden Sie [hier](https://releases.aspose.com/tex/java/).

## Pakete importieren

Beginnen Sie mit dem Import der notwendigen Pakete, um Ihre TeX‑zu‑XPS-Konvertierung zu starten. Fügen Sie den folgenden Code‑Snippet in Ihr Java‑Projekt ein:

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

Beginnen Sie damit, Konvertierungsoptionen für das Standard‑ObjectTeX‑Format mit dem folgenden Code zu erstellen:

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

Dieser Schritt stellt sicher, dass detaillierte Protokolle zur Fehlersuche erfasst werden.

## Schritt 4: Ausgabestream öffnen

Öffnen Sie einen Stream, um das gesetzte XPS-Dokument zu schreiben:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

Ersetzen Sie "Your Output Directory" durch den entsprechenden Pfad.

## Schritt 5: Job ausführen

Führen Sie den TeX‑zu‑XPS-Konvertierungs‑Job aus:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

Damit ist der Vorgang abgeschlossen, und Sie finden Ihr erzeugtes XPS-Dokument im angegebenen Ausgabeverzeichnis.

## Häufige Probleme und Lösungen

| Problem | Warum es passiert | Wie zu beheben |
|---------|-------------------|----------------|
| **FileNotFoundException** beim Öffnen des Streams | Der Pfad des Ausgabeverzeichnisses ist falsch oder existiert nicht. | Pfad überprüfen, das Verzeichnis vorher erstellen oder `Files.createDirectories` verwenden. |
| **NullPointerException** bei `options.getOutputWorkingDirectory()` | `setOutputWorkingDirectory` wurde nicht aufgerufen oder gab `null` zurück. | Stellen Sie sicher, dass Sie `options.setOutputWorkingDirectory` vor der Verwendung aufrufen. |
| **LicenseException** zur Laufzeit | Ausführung ohne gültige Aspose.TeX‑Lizenz. | Eine temporäre oder permanente Lizenz anwenden mit `License license = new License(); license.setLicense("Aspose.TeX.lic");`. |

## Häufig gestellte Fragen

**Q: Kann ich Aspose.TeX für Java mit anderen Dokumentformaten verwenden?**  
A: Aspose.TeX konzentriert sich hauptsächlich auf die Verarbeitung von TeX‑bezogenen Dokumenten. Für andere Formate erkunden Sie das umfangreiche Produktportfolio von Aspose.

**Q: Gibt es eine Testversion?**  
A: Ja, Sie können Aspose.TeX ausprobieren, indem Sie die kostenlose Testversion [hier](https://releases.aspose.com/) herunterladen.

**Q: Wo finde ich umfassende Dokumentation?**  
A: Sie finden die Dokumentation [hier](https://reference.aspose.com/tex/java/) für detaillierte Informationen und Beispiele.

**Q: Wie erhalte ich Support oder Hilfe?**  
A: Besuchen Sie das Aspose.TeX‑Forum [hier](https://forum.aspose.com/c/tex/47) für Community‑Support und Diskussionen.

**Q: Kann ich eine temporäre Lizenz für Testzwecke erhalten?**  
A: Ja, Sie können eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/) erwerben.

## Fazit

Herzlichen Glückwunsch! Sie haben gerade **wie man TeX** in ein XPS-Dokument in Java mit Aspose.TeX und einem externen Stream konvertiert. Diese Technik gibt Ihnen die volle Kontrolle darüber, wohin die XPS‑Ausgabe geht – sei es ein Dateisystem, eine Web‑Antwort oder ein Cloud‑Bucket. Experimentieren Sie gern mit verschiedenen TeX‑Quellen, passen Sie die `TeXOptions` für benutzerdefinierte Schriften an oder integrieren Sie den Stream in eine größere Dokument‑Generierungspipeline.

---

**Zuletzt aktualisiert:** 2025-12-11  
**Getestet mit:** Aspose.TeX für Java 24.11 (zum Zeitpunkt des Schreibens die neueste Version)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}