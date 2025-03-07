---
title: Jobnamen überschreiben und Terminalausgabe in Zip schreiben (C#)
linktitle: Jobnamen überschreiben und Terminalausgabe in Zip schreiben (C#)
second_title: Aspose.TeX .NET-API
description: Erfahren Sie, wie Sie mit Aspose.TeX für .NET Jobnamen überschreiben und Terminalausgaben in eine ZIP-Datei schreiben. Schritt-für-Schritt-Anleitung mit C#-Beispielen.
weight: 11
url: /de/net/job-output/override-job-name-zip-output-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jobnamen überschreiben und Terminalausgabe in Zip schreiben (C#)

## Einführung

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.TeX für .NET den Jobnamen überschreiben und die Terminalausgabe in eine ZIP-Datei schreiben. Aspose.TeX ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, mit TeX-Dokumenten in ihren .NET-Anwendungen zu arbeiten. In diesem speziellen Beispiel konzentrieren wir uns auf eine häufige Aufgabe – das Schreiben der Terminalausgabe in eine ZIP-Datei mit der Möglichkeit, den Jobnamen zu überschreiben.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Grundkenntnisse in C#
- Aspose.TeX für .NET installiert
- Geben Sie das ZIP-Archiv für das Arbeitsverzeichnis ein
- Ausgabe-ZIP-Archiv für die Terminalausgabe

## Namespaces importieren

Stellen Sie vor dem Eintauchen in den Code sicher, dass Sie die erforderlichen Namespaces in Ihr C#-Projekt aufnehmen:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Pdf;
using System.IO;
```

Lassen Sie uns das Beispiel nun in mehrere Schritte unterteilen, um Sie durch den Prozess zu führen.

## Schritt 1: Öffnen Sie die Eingabe- und Ausgabe-ZIP-Streams

```csharp
using (Stream inZipStream = File.Open(Path.Combine("Your Input Directory", "zip-in.zip"), FileMode.Open))
using (Stream outZipStream = File.Open(Path.Combine("Your Output Directory", "terminal-out-to-zip.zip"), FileMode.Create))
{
    // Code für Schritt 1 finden Sie hier
}
```

## Schritt 2: Konvertierungsoptionen festlegen

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
options.JobName = "terminal-output-to-zip";
options.InputWorkingDirectory = new InputZipDirectory(inZipStream, "in");
options.OutputWorkingDirectory = new OutputZipDirectory(outZipStream);
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## Schritt 3: Speicheroptionen definieren

```csharp
options.SaveOptions = new PdfSaveOptions();
```

## Schritt 4: Führen Sie den TeX-Job aus

```csharp
new TeXJob("hello-world", new PdfDevice(), options).Run();
```

## Schritt 5: Finalisieren Sie das Ausgabe-ZIP-Archiv

```csharp
((OutputZipDirectory)options.OutputWorkingDirectory).Finish();
```

## Abschluss

Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.TeX für .NET den Jobnamen überschreiben und die Terminalausgabe in eine ZIP-Datei schreiben. Diese Technik kann beim Umgang mit TeX-Dokumenten in Ihren C#-Anwendungen unglaublich nützlich sein.

## FAQs

### F1: Kann ich Aspose.TeX für .NET mit anderen .NET-Sprachen wie VB.NET verwenden?

A1: Ja, Aspose.TeX für .NET ist mit allen .NET-Sprachen kompatibel.

### F2: Wo finde ich weitere Dokumentation zu Aspose.TeX für .NET?

 A2: Besuchen Sie die[Dokumentation](https://reference.aspose.com/tex/net/) für detaillierte Informationen.

### F3: Wie kann ich eine temporäre Lizenz für Aspose.TeX erhalten?

 A3: Erhalten Sie a[temporäre Lizenz](https://purchase.aspose.com/temporary-license/) zu Testzwecken.

### F4: Gibt es ein Community-Forum für Aspose.TeX-Unterstützung?

 A4: Ja, treten Sie dem bei[Aspose.TeX-Forum](https://forum.aspose.com/c/tex/47) für die Unterstützung der Gemeinschaft.

### F5: Wo kann ich Aspose.TeX für .NET kaufen?

 A5: Sie können Aspose.TeX kaufen[Hier](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
