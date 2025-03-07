---
title: Jobnamen überschreiben und Terminalausgabe in Zip in Java schreiben
linktitle: Jobnamen überschreiben und Terminalausgabe in Zip in Java schreiben
second_title: Aspose.TeX Java-API
description: Erfahren Sie, wie Sie mit Aspose.TeX Jobnamen überschreiben und Terminalausgaben in Java in ZIP schreiben. Ein umfassendes Tutorial für Java-Entwickler.
weight: 11
url: /de/java/customizing-output/override-job-name-zip/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jobnamen überschreiben und Terminalausgabe in Zip in Java schreiben

## Einführung

In der Welt der Java-Entwicklung sticht Aspose.TeX als leistungsstarkes Tool für den Umgang mit TeX-Dateiformaten hervor. In diesem Tutorial befassen wir uns mit einem bestimmten Szenario – dem Überschreiben von Jobnamen und dem Schreiben der Terminalausgabe in eine ZIP-Datei. Diese Schritt-für-Schritt-Anleitung führt Sie durch den Prozess mit Aspose.TeX für Java.

## Voraussetzungen

Bevor wir mit diesem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Grundkenntnisse der Java-Programmierung.
-  Installierte Aspose.TeX für Java. Wenn nicht, können Sie es hier herunterladen[Aspose-Website](https://releases.aspose.com/tex/java/).
- Ein Verständnis dafür, wie man eine Java-Entwicklungsumgebung einrichtet.

## Pakete importieren

Beginnen Sie mit dem Importieren der erforderlichen Pakete in Ihr Java-Projekt. Dadurch wird sichergestellt, dass Sie Zugriff auf die für die Aufgabe erforderlichen Aspose.TeX-Funktionalitäten haben.

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

## Schritt 1: Öffnen Sie das ZIP-Archiv

Öffnen Sie zunächst einen Stream im ZIP-Archiv, der als Eingabearbeitsverzeichnis dient. Dies ist das Archiv, aus dem Ihre Daten verarbeitet werden.

```java
// Öffnen Sie einen Stream im Eingabe-ZIP-Archiv
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
```

## Schritt 2: Öffnen Sie das Ausgabe-ZIP-Archiv

Öffnen Sie als Nächstes einen Stream in einem ZIP-Archiv, das als Ausgabearbeitsverzeichnis dient. Hier wird die Terminalausgabe geschrieben.

```java
// Öffnen Sie einen Stream im Ausgabe-ZIP-Archiv
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "terminal-out-to-zip.zip");
```

## Schritt 3: Konvertierungsoptionen festlegen

Erstellen Sie Konvertierungsoptionen für das Standard-ObjectTeX-Format bei der Erweiterung der ObjectTeX-Engine. Geben Sie einen Jobnamen und ZIP-Archiv-Arbeitsverzeichnisse für die Eingabe und Ausgabe an.

```java
// Erstellen Sie TeX-Optionen für das ObjectTeX-Format
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("terminal-output-to-zip");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
```

## Schritt 4: Geben Sie die Terminalausgabe an

 Geben Sie an, dass die Terminalausgabe in eine Datei im Ausgabearbeitsverzeichnis geschrieben werden muss. Der Dateiname lautet`<job_name>.trm`.

```java
// Geben Sie die Einstellungen für die Terminalausgabe an
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

## Schritt 5: Definieren Sie Speicheroptionen und führen Sie den Job aus

Definieren Sie Speicheroptionen, in diesem Fall beispielsweise PDF-Speicheroptionen. Führen Sie den TeX-Job aus, um die Konvertierung auszuführen.

```java
// Definieren Sie Speicheroptionen und führen Sie den Job aus
options.setSaveOptions(new PdfSaveOptions());
new TeXJob("hello-world", new PdfDevice(), options).run();
```

## Schritt 6: Finalisieren Sie das Ausgabe-ZIP-Archiv

Nachdem der Auftrag abgeschlossen ist, schließen Sie das Ausgabe-ZIP-Archiv ab, um eine ordnungsgemäße Fertigstellung sicherzustellen.

```java
// Finalisieren Sie das Ausgabe-ZIP-Archiv
((OutputZipDirectory) options.getOutputWorkingDirectory()).finish();
```

## Abschluss

Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.TeX Jobnamen überschreiben und Terminalausgaben in eine ZIP-Datei in Java schreiben. Diese leistungsstarke Funktionalität verleiht Ihren Java-Entwicklungsprojekten Flexibilität und Effizienz.

## FAQs

### F1: Was ist Aspose.TeX?

A1: Aspose.TeX ist eine Java-Bibliothek, die Entwicklern die Arbeit mit TeX-Dateiformaten ermöglicht und erweiterte Funktionen für die Dokumentverarbeitung bereitstellt.

### F2: Wie kann ich eine temporäre Lizenz für Aspose.TeX erhalten?

 A2: Sie können eine temporäre Lizenz erhalten von[dieser Link](https://purchase.aspose.com/temporary-license/).

### F3: Wo finde ich die Aspose.TeX-Dokumentation?

 A3: Die Dokumentation ist verfügbar[Hier](https://reference.aspose.com/tex/java/).

### F4: Gibt es eine kostenlose Testversion von Aspose.TeX?

 A4: Ja, Sie können die kostenlose Testversion finden[Hier](https://releases.aspose.com/).

### F5: Wo kann ich Unterstützung suchen oder Fragen zu Aspose.TeX stellen?

 A5: Besuchen Sie die[Aspose.TeX-Forum](https://forum.aspose.com/c/tex/47) für Unterstützung und Diskussionen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
