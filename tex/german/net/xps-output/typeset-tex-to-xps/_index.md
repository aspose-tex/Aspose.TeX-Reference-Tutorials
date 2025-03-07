---
title: Satz von TeX zu XPS in .NET
linktitle: Satz von TeX zu XPS in .NET
second_title: Aspose.TeX .NET-API
description: Konvertieren Sie mit Aspose.TeX mühelos TeX-Dokumente in XPS in .NET. Entdecken Sie unsere Schritt-für-Schritt-Anleitung für eine nahtlose Integration.
weight: 10
url: /de/net/xps-output/typeset-tex-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Satz von TeX zu XPS in .NET

## Einführung

Willkommen zu unserer Schritt-für-Schritt-Anleitung zum Setzen von TeX in XPS in .NET mithilfe der leistungsstarken Aspose.TeX-Bibliothek. Wenn Sie TeX-Dokumente in Ihren .NET-Anwendungen nahtlos in das XPS-Format konvertieren möchten, sind Sie bei uns genau richtig. In diesem Tutorial führen wir Sie durch den gesamten Prozess und schlüsseln jeden Schritt auf, um eine reibungslose Implementierung zu gewährleisten.

## Voraussetzungen

Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

-  Aspose.TeX für .NET: Stellen Sie sicher, dass Sie die Aspose.TeX-Bibliothek installiert haben. Sie können es herunterladen[Hier](https://releases.aspose.com/tex/net/).

- Dokumentation: Machen Sie sich anhand der Dokumentation mit der Bibliothek vertraut[Hier](https://reference.aspose.com/tex/net/).

- Eingabe- und Ausgabeverzeichnisse: Richten Sie Ihre Eingabe- und Ausgabeverzeichnisse wie im Beispielcode angegeben ein.

Nachdem Sie nun alles eingerichtet haben, fahren wir mit der Schritt-für-Schritt-Anleitung fort.

## Namespaces importieren

Beginnen Sie in Ihrer .NET-Anwendung mit dem Importieren der erforderlichen Namespaces. Dadurch wird sichergestellt, dass Sie Zugriff auf die Aspose.TeX-Funktionen haben, die zum Setzen von TeX in XPS erforderlich sind.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
```

## Schritt 1: Konvertierungsoptionen festlegen

Definieren Sie die Konvertierungsoptionen und geben Sie das ObjectTeX-Format in der ObjectTeX-Engine-Erweiterung an. Legen Sie außerdem den Jobnamen, die Eingabe- und Ausgabeverzeichnisse sowie die Terminalausgabedetails fest.

```csharp
// Erstellen Sie Konvertierungsoptionen für das Standard-ObjectTeX-Format bei der Erweiterung der ObjectTeX-Engine.
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
// Geben Sie einen Jobnamen an.
options.JobName = "external-file-stream";
// Geben Sie ein Dateisystem-Arbeitsverzeichnis für die Eingabe an.
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
// Geben Sie ein Dateisystem-Arbeitsverzeichnis für die Ausgabe an.
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
// Geben Sie an, dass die Terminalausgabe in eine Datei im Ausgabearbeitsverzeichnis geschrieben werden muss.
// Der Dateiname ist <job_name>.trm.
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## Schritt 2: XPS-Dokumentstrom erstellen

Öffnen Sie einen Stream, um das gesetzte XPS-Dokument zu schreiben. Der Dateiname muss nicht unbedingt mit dem Jobnamen identisch sein.

```csharp
using (Stream stream = File.Open(Path.Combine("Your Output Directory", options.JobName + ".xps"), FileMode.Create))
```

## Schritt 3: Führen Sie den TeX-Job aus

Starten Sie den TeX-Job und führen Sie ihn aus. Geben Sie dabei den Dokumentnamen, XpsDevice und Konvertierungsoptionen an.

```csharp
new TeXJob("hello-world", new XpsDevice(stream), options).Run();
```

Glückwunsch! Sie haben TeX mit Aspose.TeX erfolgreich in .NET in XPS gesetzt. Entdecken Sie gerne weitere Funktionen und Optionen basierend auf Ihren spezifischen Anforderungen.

## Abschluss

In diesem Tutorial haben wir die wesentlichen Schritte zum nahtlosen Konvertieren von TeX-Dokumenten in das XPS-Format in .NET mit Aspose.TeX behandelt. Durch die Befolgung dieses Leitfadens haben Sie wertvolle Einblicke in die Funktionen der Bibliothek gewonnen und erfahren, wie Sie diese für Ihre Projekte nutzen können.

## FAQs

### F1: Ist Aspose.TeX mit .NET Core kompatibel?

A1: Ja, Aspose.TeX ist vollständig mit .NET Core kompatibel.

### F2: Kann ich Aspose.TeX für kommerzielle Projekte verwenden?

A2: Auf jeden Fall! Aspose.TeX ist sowohl für den kommerziellen als auch für den persönlichen Gebrauch verfügbar.

### F3: Wo finde ich zusätzliche Beispiele und Ressourcen?

 A3: Entdecken Sie die Aspose.TeX-Dokumentation[Hier](https://reference.aspose.com/tex/net/)Weitere Beispiele und detaillierte Ressourcen finden Sie hier.

### F4: Wie kann ich Unterstützung für Aspose.TeX erhalten?

 A4: Besuchen Sie das Aspose.TeX-Supportforum[Hier](https://forum.aspose.com/c/tex/47) um Hilfe von der Community zu erhalten.

### F5: Gibt es eine kostenlose Testversion?

 A5: Ja, Sie können auf eine kostenlose Testversion zugreifen[Hier](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
