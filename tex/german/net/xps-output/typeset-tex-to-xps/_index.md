---
date: 2025-12-30
description: Erfahren Sie, wie Sie TeX in .NET mit Aspose.TeX in XPS konvertieren.
  Folgen Sie dieser Schritt‑für‑Schritt‑Anleitung für nahtlose Integration und zuverlässige
  Ergebnisse.
linktitle: How to Convert TeX to XPS in .NET
second_title: Aspose.TeX .NET API
title: Wie man TeX in XPS in .NET konvertiert
url: /de/net/xps-output/typeset-tex-to-xps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man TeX nach XPS in .NET konvertiert

## Wie man TeX nach XPS konvertiert – Einführung

Willkommen zu unserem umfassenden, Schritt‑für‑Schritt‑Leitfaden, wie man **TeX**‑Dokumente in das XPS‑Format innerhalb einer .NET‑Umgebung konvertiert. Mit der leistungsstarken Aspose.TeX‑Bibliothek können Sie die TeX‑zu‑XPS‑Konvertierung in jede .NET‑Anwendung integrieren – sei es ein Desktop‑Tool, ein Web‑Service oder eine automatisierte Reporting‑Pipeline. In den folgenden Abschnitten führen wir Sie durch alle erforderlichen Einstellungen, zeigen Ihnen den genauen Code und erklären, warum jedes Element wichtig ist, sodass Sie die Lösung mit Zuversicht implementieren können.

## Schnelle Antworten
- **Worum geht es in diesem Tutorial?** Konvertierung von TeX‑Dateien nach XPS mit Aspose.TeX für .NET.  
- **Welche .NET-Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion funktioniert für Tests; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Wie lange dauert die Implementierung?** In der Regel weniger als 15 Minuten für eine einfache Konvertierung.  
- **Wo kann ich die Bibliothek erhalten?** Download von der offiziellen Aspose.TeX‑Release‑Seite.

## Voraussetzungen

Bevor wir in das Tutorial einsteigen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllt haben:

- Aspose.TeX für .NET: Stellen Sie sicher, dass die Aspose.TeX‑Bibliothek installiert ist. Sie können sie [hier](https://releases.aspose.com/tex/net/) herunterladen.

- Dokumentation: Machen Sie sich mit der Bibliothek vertraut, indem Sie die Dokumentation [hier](https://reference.aspose.com/tex/net/) konsultieren.

- Eingabe‑ und Ausgabeverzeichnisse: Richten Sie Ihre Eingabe‑ und Ausgabeverzeichnisse gemäß dem Beispielcode ein.

Jetzt, da alles eingerichtet ist, fahren wir mit der Schritt‑für‑Schritt‑Anleitung fort.

## Namespaces importieren

In Ihrer .NET‑Anwendung beginnen Sie mit dem Import der notwendigen Namespaces. Dadurch erhalten Sie Zugriff auf die Aspose.TeX‑Funktionalitäten, die für das Setzen von TeX nach XPS erforderlich sind.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
```

## Schritt 1: Konvertierungsoptionen festlegen

Definieren Sie die Konvertierungsoptionen und geben Sie das ObjectTeX‑Format über die ObjectTeX‑Engine‑Erweiterung an. Legen Sie außerdem den Job‑Namen, die Eingabe‑ und Ausgabeverzeichnisse sowie die Details für die Terminalausgabe fest.

```csharp
// Create conversion options for default ObjectTeX format upon ObjectTeX engine extension.
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
// Specify a job name.
options.JobName = "external-file-stream";
// Specify a file system working directory for input.
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
// Specify a file system working directory for output.
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
// Specify that the terminal output must be written to a file in the output working directory.
// The file name is <job_name>.trm.
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## Schritt 2: XPS‑Dokument‑Stream erstellen

Öffnen Sie einen Stream, um das gesetzte XPS‑Dokument zu schreiben. Der Dateiname muss nicht zwingend mit dem Job‑Namen übereinstimmen.

```csharp
using (Stream stream = File.Open(Path.Combine("Your Output Directory", options.JobName + ".xps"), FileMode.Create))
```

## Schritt 3: TeX‑Job ausführen

Starten und führen Sie den TeX‑Job aus, indem Sie den Dokumentnamen, das XpsDevice und die Konvertierungsoptionen angeben.

```csharp
new TeXJob("hello-world", new XpsDevice(stream), options).Run();
```

Herzlichen Glückwunsch! Sie haben erfolgreich TeX nach XPS in .NET mit Aspose.TeX gesetzt. Erkunden Sie gern weitere Funktionen und Optionen, die Ihren spezifischen Anforderungen entsprechen.

## Fazit

In diesem Tutorial haben wir die wesentlichen Schritte behandelt, um TeX‑Dokumente nahtlos in das XPS‑Format in .NET mit Aspose.TeX zu konvertieren. Durch das Befolgen dieser Anleitung haben Sie wertvolle Einblicke in die Möglichkeiten der Bibliothek erhalten und wissen, wie Sie sie in Ihren Projekten einsetzen können.

## FAQ's

### Q1: Ist Aspose.TeX mit .NET Core kompatibel?

A1: Ja, Aspose.TeX ist vollständig mit .NET Core kompatibel.

### Q2: Kann ich Aspose.TeX für kommerzielle Projekte verwenden?

A2: Absolut! Aspose.TeX ist sowohl für kommerzielle als auch für private Nutzung verfügbar.

### Q3: Wo finde ich zusätzliche Beispiele und Ressourcen?

A3: Entdecken Sie die Aspose.TeX‑Dokumentation [hier](https://reference.aspose.com/tex/net/) für weitere Beispiele und detaillierte Ressourcen.

### Q4: Wie kann ich Support für Aspose.TeX erhalten?

A4: Besuchen Sie das Aspose.TeX Support‑Forum [hier](https://forum.aspose.com/c/tex/47), um Hilfe von der Community zu erhalten.

### Q5: Gibt es eine kostenlose Testversion?

A5: Ja, Sie können eine kostenlose Testversion [hier](https://releases.aspose.com/) erhalten.

## Häufig gestellte Fragen

**Q: Kann ich die XPS‑Ausgabe anpassen (z. B. Seitengröße oder Ränder)?**  
A: Ja. Sie können die XpsDevice‑Einstellungen anpassen oder den TeX‑Quellcode ändern, um das Seitenlayout vor der Konvertierung zu steuern.

**Q: Was passiert, wenn die Eingabe‑TeX‑Datei Fehler enthält?**  
A: Der Konvertierungsprozess schreibt Fehlerdetails in die Terminalausgabedatei (`*.trm`). Überprüfen Sie diese Datei, um die Probleme zu diagnostizieren und zu beheben.

**Q: Ist es möglich, mehrere TeX‑Dateien in einem Durchlauf zu konvertieren?**  
A: Sie können über eine Sammlung von TeX‑Quelldateien iterieren, für jede einen separaten TeXJob erstellen und dabei dieselbe `TeXOptions`‑Instanz wiederverwenden.

**Q: Unterstützt Aspose.TeX LaTeX‑Pakete wie `amsmath` oder `graphicx`?**  
A: Die meisten gängigen LaTeX‑Pakete werden unterstützt. Prüfen Sie die offizielle Dokumentation für eine vollständige Liste kompatibler Pakete.

**Q: Wie bette ich Schriftarten in die erzeugte XPS‑Datei ein?**  
A: Aspose.TeX bettet die vom TeX‑Engine verwendeten Schriftarten automatisch ein. Stellen Sie sicher, dass die erforderlichen Schriftarten auf dem Rechner, der die Konvertierung ausführt, installiert sind.

---

**Zuletzt aktualisiert:** 2025-12-30  
**Getestet mit:** Aspose.TeX für .NET 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}