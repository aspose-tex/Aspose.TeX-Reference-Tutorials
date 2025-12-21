---
date: 2025-12-21
description: Erfahren Sie, wie Sie die Konsolenausgabe in C# mit Aspose.TeX erfassen,
  den Jobnamen überschreiben, das TeX‑Eingabeverzeichnis festlegen und die Terminalausgabe
  in eine Datei schreiben.
linktitle: Capture Console Output C# – Override Job Name & Write Output to Disk
second_title: Aspose.TeX .NET API
title: Konsolenausgabe in C# erfassen – Jobnamen überschreiben & Ausgabe auf Festplatte
  schreiben
url: /de/net/job-output/override-job-name-disk-output-csharp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Capture Console Output C# – Override Job Name and Write Terminal Output to Disk (C#)

## Einleitung

In diesem Schritt‑für‑Schritt‑Leitfaden lernen Sie **wie man console output C# erfasst**, wenn Sie mit Aspose.TeX für .NET arbeiten. Durch das Überschreiben des Jobnamens und das Weiterleiten der Terminalausgabe in eine Datei erhalten Sie die volle Kontrolle über TeX‑Verarbeitungspipelines – ideal für automatisierte Builds, CI/CD‑Szenarien oder jede Situation, in der Sie den Konsolenstrom für spätere Analysen protokollieren müssen.

## Schnelle Antworten
- **Was bedeutet „capture console output C#“?** Es leitet den von Aspose.TeX erzeugten Standard‑Terminal‑Stream in eine von Ihnen angegebene Datei um.  
- **Warum den Jobnamen überschreiben?** Das Überschreiben sorgt für vorhersehbare Dateinamen und verhindert Kollisionen bei gleichzeitiger Ausführung mehrerer Jobs.  
- **Welche Aspose.TeX‑Klasse schreibt die Ausgabe?** `OutputFileTerminal` (verwendet über `options.TerminalOut`).  
- **Kann ich einen benutzerdefinierten TeX‑Eingabeordner festlegen?** Ja – verwenden Sie `options.InputWorkingDirectory`, um **das TeX‑Eingabeverzeichnis** zu setzen.  
- **Ist dieser Ansatz mit .NET Core kompatibel?** Absolut; dieselbe API funktioniert sowohl unter .NET Framework als auch unter .NET Core.

## Was bedeutet „capture console output C#“ im Kontext von Aspose.TeX?
Das Erfassen der Konsolenausgabe bedeutet, alles, was normalerweise im Terminalfenster erscheint (Log‑Nachrichten, Warnungen, Kompilierungsdetails), in eine persistente Datei zu schreiben. Das ist besonders nützlich, um große TeX‑Projekte zu debuggen oder TeX‑Verarbeitung in automatisierte Workflows zu integrieren.

## Warum den Jobnamen überschreiben und die Terminalausgabe in eine Datei schreiben?
- **Vorhersehbare Dateinamen:** Durch das Überschreiben des Jobnamens können Sie den Basisnamen für erzeugte Dateien festlegen, was das Schreiben von Nachbearbeitungsskripten erleichtert.  
- **Nachvollziehbarkeit:** Das Speichern des Terminal‑Logs liefert eine vollständige Audit‑Trail des TeX‑Kompilierungsprozesses.  
- **Parallele Ausführung:** Bei gleichzeitiger Ausführung mehrerer Jobs verhindern eindeutige Jobnamen Dateikollisionen.  

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- Aspose.TeX für .NET Bibliothek: Stellen Sie sicher, dass die Aspose.TeX für .NET Bibliothek installiert ist. Sie können sie von der [Aspose.TeX Website](https://releases.aspose.com/tex/net/) herunterladen.  
- .NET Entwicklungsumgebung: Eine funktionierende .NET‑Entwicklungsumgebung, inklusive einer integrierten Entwicklungsumgebung (IDE) wie Visual Studio.  
- Grundkenntnisse in C#: Vertrautheit mit den Grundlagen der Programmiersprache C#.  
- Eingabe‑ und Ausgabeverzeichnisse: Bereiten Sie die Eingabe‑ und Ausgabeverzeichnisse für Ihre TeX‑Dateien vor.

## Namespaces importieren

Stellen Sie in Ihrem C#‑Code sicher, dass die notwendigen Namespaces eingebunden sind, um auf die Aspose.TeX‑Funktionalitäten zuzugreifen:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

## Schritt 1: Konvertierungsoptionen erstellen

Zuerst erstellen wir eine `TeXOptions`‑Instanz, die Aspose.TeX mitteilt, dass wir in einem Konsolen‑Anwendungsszenario arbeiten.

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

Erstellen Sie `TeXOptions` mit `ConsoleAppOptions` und geben Sie `ObjectTeX` als `TeXConfig` an.

## Schritt 2: Jobnamen angeben (Standard überschreiben)

Das Überschreiben des Jobnamens gibt uns Kontrolle über den Basisnamen aller erzeugten Artefakte.

```csharp
options.JobName = "overridden-job-name";
```

Geben Sie den Jobnamen an, um den Standardnamen zu überschreiben.

## Schritt 3: TeX‑Eingabeverzeichnis festlegen

Teilen Sie Aspose.TeX mit, wo Ihre Quell‑`.tex`‑Dateien zu finden sind. Dies ist der **set tex input directory**‑Schritt.

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

Setzen Sie das Eingabearbeitsverzeichnis für Ihre TeX‑Dateien.

## Schritt 4: Ausgabearbeitsverzeichnis festlegen

Definieren Sie, wo die verarbeiteten Dateien und das erfasste Konsolen‑Log gespeichert werden sollen.

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Definieren Sie das Ausgabearbeitsverzeichnis, um die verarbeiteten TeX‑Dateien zu speichern.

## Schritt 5: Terminalausgabe in Datei schreiben

Jetzt leiten wir den Konsolen‑Stream in eine physische Datei im Ausgabeverzeichnis um. Dies erfüllt die Anforderung **write terminal output to file**.

```csharp
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

Konfigurieren Sie die Terminalausgabe so, dass sie in eine Datei im Ausgabeverzeichnis geschrieben wird.

## Schritt 6: Job ausführen

Abschließend erstellen wir einen `TeXJob` mit dem überschriebenen Jobnamen, dem XPS‑Ausgabegerät und den konfigurierten Optionen. Das Ausführen des Jobs erzeugt die XPS‑Datei und erfasst das Konsolen‑Log.

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

Erstellen Sie einen `TeXJob`, geben Sie einen Jobnamen, das Ausgabegerät (`XpsDevice`) und die Optionen an. Führen Sie schließlich den Job aus.

## Häufige Probleme & Fehlerbehebung

| Symptom | Wahrscheinliche Ursache | Lösung |
|---------|--------------------------|--------|
| Keine Ausgabedatei erstellt | Pfad des Ausgabeverzeichnisses ist falsch oder Schreibrechte fehlen | Überprüfen Sie, dass `options.OutputWorkingDirectory` auf einen gültigen Ordner zeigt und der Prozess Schreibzugriff hat. |
| Terminal‑Log ist leer | `TerminalOut` nicht gesetzt oder später überschrieben | Stellen Sie sicher, dass `options.TerminalOut = new OutputFileTerminal(...);` vor `job.Run();` ausgeführt wird. |
| Job schlägt mit „Datei nicht gefunden“ fehl | Eingabeverzeichnis nicht korrekt gesetzt | Prüfen Sie den Pfad, der an `InputFileSystemDirectory` übergeben wird, und dass die `.tex`‑Dateien dort vorhanden sind. |

## Häufig gestellte Fragen

### Q1: Kann ich Aspose.TeX für .NET mit anderen .NET‑Bibliotheken verwenden?

A1: Ja, Aspose.TeX für .NET lässt sich nahtlos mit anderen .NET‑Bibliotheken integrieren.

### Q2: Gibt es eine kostenlose Testversion von Aspose.TeX für .NET?

A2: Ja, Sie können eine kostenlose Testversion [hier](https://releases.aspose.com/) herunterladen.

### Q3: Wie erhalte ich Support für Aspose.TeX für .NET?

A3: Besuchen Sie das [Aspose.TeX Forum](https://forum.aspose.com/c/tex/47), um Community‑ und Support‑Hilfe zu erhalten.

### Q4: Gibt es temporäre Lizenzen für Aspose.TeX für .NET?

A4: Ja, Sie können eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/) erhalten.

### Q5: Wo finde ich die Dokumentation für Aspose.TeX für .NET?

A5: Die Dokumentation ist [hier](https://reference.aspose.com/tex/net/) verfügbar.

## Fazit

Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie man **console output C# erfasst**, indem man den Jobnamen überschreibt, das TeX‑Eingabeverzeichnis festlegt und die Terminalausgabe in eine Datei schreibt – alles mit Aspose.TeX für .NET. Diese Technik vereinfacht das Logging, verbessert die Rückverfolgbarkeit und macht automatisierte TeX‑Verarbeitungspipelines robuster.

---

**Zuletzt aktualisiert:** 2025-12-21  
**Getestet mit:** Aspose.TeX 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}