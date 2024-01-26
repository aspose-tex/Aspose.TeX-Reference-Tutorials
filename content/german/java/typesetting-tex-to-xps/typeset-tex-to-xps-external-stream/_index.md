---
title: Setzen Sie TeX in Java mit externem Stream auf XPS
linktitle: Setzen Sie TeX in Java mit externem Stream auf XPS
second_title: Aspose.TeX Java-API
description: Erfahren Sie, wie Sie TeX mit Aspose.TeX in Java in XPS umwandeln. Entdecken Sie die Schritt-für-Schritt-Anleitung für eine reibungslose Dokumentenverarbeitung.
type: docs
weight: 10
url: /de/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
---
## Einführung

In der Welt der Java-Entwicklung sticht Aspose.TeX als leistungsstarkes Werkzeug zum Setzen von TeX-Dokumenten in verschiedene Formate, einschließlich XPS, hervor. Wenn Sie die Dokumentverarbeitungsfunktionen Ihrer Java-Anwendung verbessern möchten, ist dieses Tutorial genau das Richtige für Sie. In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch den Prozess des Setzens von TeX in XPS mithilfe von Aspose.TeX für Java mit einem externen Stream.

## Voraussetzungen

Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

-  Java Development Kit (JDK): Stellen Sie sicher, dass Java auf Ihrem System installiert ist. Sie können es herunterladen unter[Hier](https://www.oracle.com/java/technologies/javase-downloads.html).

-  Aspose.TeX für Java: Laden Sie Aspose.TeX für Java herunter und installieren Sie es. Den Download-Link finden Sie hier[Hier](https://releases.aspose.com/tex/java/).

## Pakete importieren

Beginnen Sie mit dem Importieren der erforderlichen Pakete, um Ihre Reise zur Konvertierung von TeX in XPS zu starten. Fügen Sie den folgenden Codeausschnitt in Ihr Java-Projekt ein:

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

Erstellen Sie zunächst Konvertierungsoptionen für das Standard-ObjectTeX-Format mit dem folgenden Code:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

Damit wird die Grundlage für den Satzprozess gelegt.

## Schritt 2: Geben Sie den Jobnamen und die Verzeichnisse an

Definieren Sie einen Jobnamen und legen Sie die Eingabe- und Ausgabearbeitsverzeichnisse fest:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Stellen Sie sicher, dass Sie Platzhalter wie „Ihr Eingabeverzeichnis“ durch Ihre tatsächlichen Verzeichnispfade ersetzen.

## Schritt 3: Konfigurieren Sie die Terminalausgabe

Geben Sie an, dass die Terminalausgabe in eine Datei im Ausgabearbeitsverzeichnis geschrieben werden soll:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

Dieser Schritt stellt sicher, dass detaillierte Protokolle zum Debuggen erfasst werden.

## Schritt 4: Öffnen Sie den Ausgabestream

Öffnen Sie einen Stream, um das gesetzte XPS-Dokument zu schreiben:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

Ersetzen Sie „Ihr Ausgabeverzeichnis“ durch den entsprechenden Pfad.

## Schritt 5: Führen Sie den Job aus

Führen Sie den TeX-zu-XPS-Konvertierungsauftrag aus:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

Damit ist der Vorgang abgeschlossen und Sie finden Ihr gesetztes XPS-Dokument im angegebenen Ausgabeverzeichnis.

## Abschluss

Glückwunsch! Sie haben TeX mit Aspose.TeX erfolgreich in Java in XPS gesetzt. Dies eröffnet eine Welt voller Möglichkeiten für die Dokumentenverarbeitung in Ihren Java-Anwendungen. Experimentieren Sie mit verschiedenen TeX-Dateien und erkunden Sie die vielfältigen Funktionen von Aspose.TeX.

## FAQs

### F1: Kann ich Aspose.TeX für Java mit anderen Dokumentformaten verwenden?

A1: Aspose.TeX konzentriert sich hauptsächlich auf die TeX-bezogene Dokumentverarbeitung. Für andere Formate erkunden Sie die umfangreiche Produktpalette von Aspose.

### F2: Gibt es eine Testversion?

 A2: Ja, Sie können Aspose.TeX erleben, indem Sie die kostenlose Testversion herunterladen[Hier](https://releases.aspose.com/).

### F3: Wo finde ich eine umfassende Dokumentation?

 A3: Sehen Sie sich die Dokumentation an[Hier](https://reference.aspose.com/tex/java/) Ausführliche Informationen und Beispiele finden Sie hier.

### F4: Wie erhalte ich Unterstützung oder suche Hilfe?

 A4: Besuchen Sie das Aspose.TeX-Forum[Hier](https://forum.aspose.com/c/tex/47)für Community-Unterstützung und Diskussionen.

### F5: Kann ich zu Testzwecken eine temporäre Lizenz erhalten?

 A5: Ja, Sie können eine temporäre Lizenz erwerben[Hier](https://purchase.aspose.com/temporary-license/).