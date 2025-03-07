---
title: Setzen Sie TeX in Java mit externem Stream in PDF
linktitle: Setzen Sie TeX in Java mit externem Stream in PDF
second_title: Aspose.TeX Java-API
description: Erfahren Sie, wie Sie TeX mithilfe externer Streams mit Aspose.TeX in Java in PDF umwandeln. Befolgen Sie unsere Schritt-für-Schritt-Anleitung für eine nahtlose Integration.
weight: 10
url: /de/java/typesetting-tex-to-pdf/typeset-tex-to-pdf-external-stream/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Setzen Sie TeX in Java mit externem Stream in PDF

## Einführung

In der Welt der Java-Entwicklung ist die Erstellung von PDFs aus TeX-Dateien eine häufige Anforderung. Aspose.TeX für Java vereinfacht diesen Prozess und bietet eine effiziente Lösung für den Satz von TeX in PDF. In diesem Tutorial führen wir Sie durch die Schritte zum Setzen von TeX in PDF mithilfe externer Streams. Am Ende werden Sie ein klares Verständnis dafür haben, wie Sie diesen Prozess nahtlos in Ihre Java-Anwendungen implementieren können.

## Voraussetzungen

Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Aspose.TeX für Java: Stellen Sie sicher, dass Sie die Aspose.TeX-Bibliothek für Java installiert haben. Sie können es hier herunterladen[Aspose.TeX für Java-Dokumentation](https://reference.aspose.com/tex/java/).

- Eingabe- und Ausgabeverzeichnisse: Bereiten Sie die Eingabe- und Ausgabeverzeichnisse vor. Sie können den bereitgestellten Download-Link verwenden, um die erforderlichen Dateien zu erhalten.

## Pakete importieren

Importieren Sie zunächst die erforderlichen Pakete in Ihr Java-Projekt:

```java
package com.aspose.tex.TypesetPdfWrittenToExternalStream;

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

## Schritt 1: Öffnen Sie Eingabe- und Ausgabestreams

Öffnen Sie zunächst Streams für das Eingabe-ZIP-Archiv (das als Eingabe-Arbeitsverzeichnis dient) und das Ausgabe-ZIP-Archiv (das als Ausgabe-Arbeitsverzeichnis dient). Stellen Sie sicher, dass Sie „Ihr Eingabeverzeichnis“ und „Ihr Ausgabeverzeichnis“ durch Ihre tatsächlichen Verzeichnispfade ersetzen.

```java
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "typeset-pdf-to-external-stream.zip");
```

## Schritt 2: TeXOptions konfigurieren

Erstellen Sie das TeXOptions-Objekt und konfigurieren Sie es entsprechend Ihren Anforderungen. Legen Sie den Jobnamen, das Eingabearbeitsverzeichnis, das Ausgabearbeitsverzeichnis und andere Optionen fest.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("typeset-pdf-to-external-stream");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
options.setSaveOptions(new PdfSaveOptions());
```

## Schritt 3: TeX in PDF umwandeln

Öffnen Sie nun einen Stream, um das Ausgabe-PDF an den gewünschten Speicherort zu schreiben. Sie können wählen, ob Sie es in eine lokale Datei oder direkt in das ZIP-Ausgabearchiv schreiben möchten.

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + "file-name.pdf");
try {
    new TeXJob("hello-world", new PdfDevice(stream), options).run();
} finally {
    stream.close();
}
```

## Schritt 4: Finalisieren Sie das Ausgabe-ZIP-Archiv

Beenden Sie das Ausgabe-ZIP-Archiv, um den Satzvorgang abzuschließen.

```java
((OutputZipDirectory)options.getOutputWorkingDirectory()).finish();
```

## Abschluss

Glückwunsch! Sie haben TeX mithilfe externer Streams mit Aspose.TeX erfolgreich in Java in PDF gesetzt. Dieses Tutorial bietet eine solide Grundlage für die nahtlose Integration der TeX-zu-PDF-Konvertierung in Ihre Java-Anwendungen.

## FAQs

### F1: Kann ich den Dateinamen der Ausgabe-PDF anpassen?

 A1: Ja, Sie können das ändern`options.setJobName("typeset-pdf-to-external-stream")` , um den gewünschten Jobnamen festzulegen.

### F2: Wie behebe ich häufige Probleme beim Satz?

 A2: Besuchen Sie die[Aspose.TeX-Forum](https://forum.aspose.com/c/tex/47) für die Unterstützung und Unterstützung der Gemeinschaft.

### F3: Gibt es eine kostenlose Testversion für Aspose.TeX für Java?

 A3: Ja, Sie können auf die kostenlose Testversion zugreifen[Hier](https://releases.aspose.com/).

### F4: Wo finde ich zusätzliche Dokumentation und Beispiele?

 A4: Entdecken Sie das Umfassende[Aspose.TeX-Dokumentation](https://reference.aspose.com/tex/java/) für detaillierte Informationen.

### F5: Kann ich eine temporäre Lizenz für Aspose.TeX erhalten?

 A5: Ja, Sie können eine temporäre Lizenz beantragen[Hier](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
