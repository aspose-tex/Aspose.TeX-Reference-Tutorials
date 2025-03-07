---
title: Konvertieren Sie LaTeX ganz einfach in das XPS-Format in Java
linktitle: Konvertieren Sie LaTeX ganz einfach in das XPS-Format in Java
second_title: Aspose.TeX Java-API
description: Konvertieren Sie LaTeX mühelos in Java mit Aspose.TeX in XPS. Befolgen Sie unsere Schritt-für-Schritt-Anleitung für eine nahtlose Integration.
weight: 10
url: /de/java/converting-lato-xps/simple-xps-conversion/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konvertieren Sie LaTeX ganz einfach in das XPS-Format in Java

## Einführung

Möchten Sie LaTeX-Dokumente in Ihren Java-Anwendungen nahtlos in das XPS-Format konvertieren? Aspose.TeX für Java bietet eine leistungsstarke Lösung, mit der Sie dies problemlos erreichen können. In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch den Prozess der Konvertierung von LaTeX in XPS mit Aspose.TeX.

## Voraussetzungen

Bevor Sie mit dem Konvertierungsprozess beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Java Development Kit (JDK) auf Ihrem System installiert.
-  Aspose.TeX für Java-Bibliothek heruntergeladen. Den Download-Link finden Sie hier[Hier](https://releases.aspose.com/tex/java/).

## Pakete importieren

Importieren Sie zunächst die erforderlichen Pakete für Ihr Java-Projekt. Stellen Sie sicher, dass Sie die Aspose.TeX-Bibliothek in Ihre Projektabhängigkeiten einschließen.

```java
package com.aspose.tex.LaTeXXpsConversionSimplest;

import java.io.ByteArrayInputStream;
import java.io.IOException;
import java.util.Calendar;
import java.util.GregorianCalendar;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.Interaction;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;
import com.aspose.tex.rendering.XpsSaveOptions;

import util.Utils;
```

Lassen Sie uns nun den Konvertierungsprozess mithilfe der bereitgestellten Codebeispiele in mehrere Schritte aufteilen.

## Schritt 1: Eingabe- und Ausgabeverzeichnisse festlegen

```java
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Geben Sie die Verzeichnisse an, in denen sich Ihre LaTeX-Eingabedatei befindet und in denen Sie die konvertierte XPS-Datei speichern möchten.

## Schritt 2: TeX-Optionen konfigurieren

Konfigurieren Sie verschiedene Optionen, um den Konvertierungsprozess an Ihre Bedürfnisse anzupassen.

```java
options.setInteraction(Interaction.NonstopMode);
options.setDateTime(new GregorianCalendar(2022, Calendar.DECEMBER, 18).getTime());
options.ignoreMissingPackages(true);
options.noLigatures(true);
options.repeat(true);
```

Passen Sie den Interaktionsmodus, das Datum im Titel, den Umgang mit fehlenden Paketen, Ligaturen und Wiederholungen nach Bedarf an.

## Schritt 3: XPS-Speicheroptionen initialisieren

```java
options.setSaveOptions(new XpsSaveOptions());
```

Initialisieren Sie die Optionen zum Speichern im XPS-Format.

## Schritt 4: Passen Sie die XPS-Speicheroptionen an

```java
options.getSaveOptions().rasterizeFormulas(true);
options.getSaveOptions().rasterizeIncludedGraphics(true);
options.getSaveOptions().subsetFonts(true);
```

Passen Sie die XPS-Speicheroptionen an, um die Konvertierung von Formeln, eingeschlossenen Grafiken und Schriftartenuntersätzen zu steuern.

## Schritt 5: Führen Sie die LaTeX-zu-XPS-Konvertierung aus

```java
new TeXJob("Your Input Directory" + "sample.ltx", new XpsDevice(), options).run();
```

Starten Sie den Konvertierungsprozess, indem Sie einen TeX-Job mit der angegebenen Eingabedatei, dem Ausgabegerät (XpsDevice) und den angegebenen Optionen ausführen.

## Zusätzliche Beispiele

Entdecken Sie zusätzliche Konvertierungsmethoden mit verschiedenen Eingabequellen:

### Verwenden Sie InputStream

```java
new TeXJob(new ByteArrayInputStream(
    "\\documentclass{article} \\begin{document} Hello, World! \\end{document}".getBytes("ASCII")),
    new XpsDevice(), options).run();
```

### Verwenden Sie den Haupteingangsanschluss

```java
new TeXJob(new XpsDevice(), options).run();
```

## Abschluss

Mit Aspose.TeX für Java ist die Konvertierung von LaTeX in XPS ein Kinderspiel. Befolgen Sie diese Schritte, passen Sie die Optionen an und integrieren Sie diese Funktionalität nahtlos in Ihre Java-Anwendungen.

## FAQs

### F1: Kann ich LaTeX-Dokumente mit komplexen Formeln mit Aspose.TeX konvertieren?

A1: Auf jeden Fall! Aspose.TeX verarbeitet komplexe Formeln während des Konvertierungsprozesses nahtlos.

### F2: Gibt es eine Testversion für Aspose.TeX für Java?

 A2: Ja, Sie können die kostenlose Testversion finden[Hier](https://releases.aspose.com/).

### F3: Wie erhalte ich Unterstützung für Aspose.TeX?

 A3: Besuchen Sie die[Aspose.TeX-Forum](https://forum.aspose.com/c/tex/47) für Hilfe und gemeinschaftliche Unterstützung.

### F4: Sind temporäre Lizenzen für Aspose.TeX verfügbar?

 A4: Ja, Sie können temporäre Lizenzen erhalten[Hier](https://purchase.aspose.com/temporary-license/).

### F5: Wo finde ich die Dokumentation für Aspose.TeX?

 A5: Siehe[Dokumentation](https://reference.aspose.com/tex/java/) für eine umfassende Beratung.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
