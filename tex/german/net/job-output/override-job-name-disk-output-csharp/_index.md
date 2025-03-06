---
title: Jobnamen überschreiben und Terminalausgabe auf Festplatte schreiben (C#)
linktitle: Jobnamen überschreiben und Terminalausgabe auf Festplatte schreiben (C#)
second_title: Aspose.TeX .NET-API
description: Erfahren Sie, wie Sie Aspose.TeX für .NET verwenden, um Jobnamen zu überschreiben und Terminalausgaben zu erfassen. Befolgen Sie unseren umfassenden Leitfaden für eine nahtlose TeX-Dateiverwaltung.
weight: 10
url: /de/net/job-output/override-job-name-disk-output-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jobnamen überschreiben und Terminalausgabe auf Festplatte schreiben (C#)

## Einführung

Willkommen zu dieser Schritt-für-Schritt-Anleitung zur Verwendung von Aspose.TeX für .NET zum Überschreiben von Jobnamen und zum Schreiben von Terminalausgaben auf die Festplatte in der Programmiersprache C#. Aspose.TeX für .NET ist eine leistungsstarke Bibliothek, die Ihnen die nahtlose Arbeit mit TeX-Dateien ermöglicht. In diesem Tutorial konzentrieren wir uns auf eine bestimmte Aufgabe: das Überschreiben von Jobnamen und das Erfassen der Terminalausgabe.

## Voraussetzungen

Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

-  Aspose.TeX für .NET-Bibliothek: Stellen Sie sicher, dass Sie die Aspose.TeX für .NET-Bibliothek installiert haben. Sie können es hier herunterladen[Aspose.TeX-Website](https://releases.aspose.com/tex/net/).

- .NET-Entwicklungsumgebung: Verfügen Sie über eine funktionierende .NET-Entwicklungsumgebung, einschließlich einer integrierten Entwicklungsumgebung (IDE) wie Visual Studio.

- Grundlegende C#-Kenntnisse: Machen Sie sich mit den Grundlagen der Programmiersprache C# vertraut.

- Eingabe- und Ausgabeverzeichnisse: Bereiten Sie die Eingabe- und Ausgabeverzeichnisse für Ihre TeX-Dateien vor.

## Namespaces importieren

Stellen Sie sicher, dass Sie in Ihrem C#-Code die erforderlichen Namespaces für den Zugriff auf die Aspose.TeX-Funktionen einschließen:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

## Schritt 1: Konvertierungsoptionen erstellen

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

Erstellen Sie TeXOptions mit ConsoleAppOptions und geben Sie ObjectTeX als TeXConfig an.

## Schritt 2: Geben Sie den Jobnamen an

```csharp
options.JobName = "overridden-job-name";
```

Geben Sie den Jobnamen an, um den Standardnamen zu überschreiben.

## Schritt 3: Geben Sie das Eingabearbeitsverzeichnis an

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

Legen Sie das Eingabearbeitsverzeichnis für Ihre TeX-Dateien fest.

## Schritt 4: Geben Sie das Ausgabearbeitsverzeichnis an

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Definieren Sie das Ausgabearbeitsverzeichnis zum Speichern der verarbeiteten TeX-Dateien.

## Schritt 5: Schreiben Sie die Terminalausgabe auf die Festplatte

```csharp
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

Konfigurieren Sie die Terminalausgabe so, dass sie in eine Datei im Ausgabeverzeichnis geschrieben wird.

## Schritt 6: Führen Sie den Job aus

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

Erstellen Sie einen TeXJob und geben Sie dabei einen Jobnamen, ein Ausgabegerät (XpsDevice) und Optionen an. Führen Sie abschließend den Job aus.

## Abschluss

Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.TeX für .NET in C# Jobnamen überschreiben und Terminalausgaben auf die Festplatte schreiben. Diese Funktion ist für die effiziente Verwaltung Ihrer TeX-Verarbeitungsaufgaben wertvoll.

## FAQs

### F1: Kann ich Aspose.TeX für .NET mit anderen .NET-Bibliotheken verwenden?

A1: Ja, Aspose.TeX für .NET kann nahtlos in andere .NET-Bibliotheken integriert werden.

### F2: Gibt es eine kostenlose Testversion für Aspose.TeX für .NET?

 A2: Ja, Sie können eine kostenlose Testversion herunterladen[Hier](https://releases.aspose.com/).

### F3: Wie erhalte ich Unterstützung für Aspose.TeX für .NET?

 A3: Besuchen Sie die[Aspose.TeX-Forum](https://forum.aspose.com/c/tex/47) um Gemeinschaft und Unterstützung zu bekommen.

### F4: Sind temporäre Lizenzen für Aspose.TeX für .NET verfügbar?

 A4: Ja, Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/).

### F5: Wo finde ich die Dokumentation für Aspose.TeX für .NET?

 A5: Die Dokumentation ist verfügbar[Hier](https://reference.aspose.com/tex/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
