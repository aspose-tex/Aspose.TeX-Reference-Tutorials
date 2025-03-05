---
title: Jobnamen überschreiben und Terminalausgabe in Java schreiben
linktitle: Jobnamen überschreiben und Terminalausgabe in Java schreiben
second_title: Aspose.TeX Java-API
description: Entdecken Sie die Schritt-für-Schritt-Anleitung zum Überschreiben von Jobnamen und Schreiben von Terminalausgaben mit Aspose.TeX für Java. Verbessern Sie Ihre Dokumentenverarbeitung mit leistungsstarken Anpassungsoptionen.
type: docs
weight: 10
url: /de/java/customizing-output/override-job-name-disk/
---
## Einführung

Aspose.TeX für Java bietet leistungsstarke Funktionen für die Arbeit mit TeX-Dateien, die es Entwicklern ermöglichen, die Verarbeitung von TeX-Dokumenten zu manipulieren und anzupassen. In diesem Tutorial führen wir Sie durch den Prozess des Überschreibens des Jobnamens und des Schreibens der Terminalausgabe in das Dateisystem mithilfe von Aspose.TeX in Java.

## Voraussetzungen

Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Grundkenntnisse der Java-Programmierung.
-  Aspose.TeX für Java installiert. Sie können es hier herunterladen[Aspose.TeX Java-Dokumentation](https://reference.aspose.com/tex/java/).

## Pakete importieren

Importieren Sie zunächst die erforderlichen Pakete in Ihr Java-Projekt. Fügen Sie in Ihre Java-Datei die folgenden Importe ein:

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

## Jobnamen überschreiben und Terminalausgabe schreiben

### Schritt 1: Konvertierungsoptionen erstellen

Beginnen Sie mit der Erstellung von Konvertierungsoptionen für das Standard-ObjectTeX-Format bei der Erweiterung der ObjectTeX-Engine. Verwenden Sie den folgenden Codeausschnitt:

```java
//ExStart:OverrideJobName-WriteTerminalOutputToFileSystem
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

### Schritt 2: Geben Sie den Jobnamen und die Arbeitsverzeichnisse an

Geben Sie einen Jobnamen, ein Eingabearbeitsverzeichnis und ein Ausgabearbeitsverzeichnis an. Wenn der Jobname nicht angegeben ist, wird das erste Argument des TeXJob-Konstruktors als Jobname verwendet. Verwenden Sie den folgenden Codeausschnitt:

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### Schritt 3: Terminalausgabe in das Dateisystem schreiben

 Geben Sie an, dass die Terminalausgabe in eine Datei im Ausgabearbeitsverzeichnis geschrieben werden muss. Der Dateiname lautet`<job_name>.trm`. Fügen Sie den folgenden Code hinzu:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### Schritt 4: Führen Sie den Job aus

Führen Sie den TeX-Job mit den angegebenen Optionen und dem Jobnamen aus. So können Sie es machen:

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
// ExEnd:OverrideJobName-WriteTerminalOutputToFileSystem
```

Glückwunsch! Sie haben den Jobnamen erfolgreich überschrieben und die Terminalausgabe mithilfe von Aspose.TeX in Java erfolgreich in das Dateisystem geschrieben.

## Abschluss

In diesem Tutorial haben wir untersucht, wie man Aspose.TeX für Java verwendet, um den Jobnamen zu überschreiben und die Terminalausgabe zu erfassen. Diese Funktionen ermöglichen Entwicklern eine detaillierte Kontrolle über die Verarbeitung von TeX-Dokumenten und verbessern so die Anpassung und Flexibilität.

## FAQs

### F1: Kann ich Aspose.TeX für Java mit anderen Java-Bibliotheken verwenden?

A1: Ja, Aspose.TeX für Java ist so konzipiert, dass es sich nahtlos in andere Java-Bibliotheken integrieren lässt, um Ihre Dokumentverarbeitungsmöglichkeiten zu verbessern.

### F2: Wo finde ich Unterstützung für Aspose.TeX für Java?

 A2: Besuchen Sie die[Aspose.TeX-Forum](https://forum.aspose.com/c/tex/47) für Community-Unterstützung und Hilfe bei allen Problemen, auf die Sie stoßen könnten.

### F3: Gibt es eine kostenlose Testversion für Aspose.TeX für Java?

 A3: Ja, Sie können auf die kostenlose Testversion von Aspose.TeX für Java zugreifen[Hier](https://releases.aspose.com/).

### F4: Wie kann ich eine temporäre Lizenz für Aspose.TeX für Java erhalten?

 A4: Befolgen Sie diese Anweisungen[Verknüpfung](https://purchase.aspose.com/temporary-license/) um eine temporäre Lizenz für Test- und Evaluierungszwecke zu erhalten.

### F5: Wo kann ich Aspose.TeX für Java kaufen?

 A5: Besuchen Sie die[Kaufseite](https://purchase.aspose.com/buy) eine Lizenz für Aspose.TeX für Java erwerben.