---
title: LaTeX zu XPS in .NET – Einfache Konvertierung mit Aspose.TeX
linktitle: LaTeX zu XPS in .NET – Einfache Konvertierung mit Aspose.TeX
second_title: Aspose.TeX .NET-API
description: Konvertieren Sie mit Aspose.TeX mühelos LaTeX in XPS in .NET. Hochwertig, anpassbar und effizient.
weight: 13
url: /de/net/latex-conversion/to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# LaTeX zu XPS in .NET – Einfache Konvertierung mit Aspose.TeX

## Einführung

Suchen Sie nach einer nahtlosen Möglichkeit, LaTeX-Dokumente in Ihren .NET-Anwendungen in das XPS-Format zu konvertieren? Aspose.TeX für .NET bietet eine leistungsstarke Lösung für diese Aufgabe und macht den Konvertierungsprozess einfach und effizient. Diese Schritt-für-Schritt-Anleitung führt Sie durch den Prozess der Konvertierung von LaTeX in XPS mit Aspose.TeX und stellt sicher, dass Sie genaue und qualitativ hochwertige Ergebnisse erzielen.

## Voraussetzungen

Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Grundkenntnisse in der C#- und .NET-Entwicklung.
-  Aspose.TeX für .NET-Bibliothek installiert. Sie können es herunterladen[Hier](https://releases.aspose.com/tex/net/).
- Ein Verständnis der LaTeX-Syntax und -Struktur.

## Namespaces importieren

Beginnen wir mit dem Importieren der erforderlichen Namespaces für unsere .NET-Anwendung. Diese Namespaces sind für die Interaktion mit Aspose.TeX-Funktionen von entscheidender Bedeutung.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
using System.Text;
```

## Schritt 1: Konvertierungsoptionen einrichten

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectLaTeX);
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

Hier initialisieren wir die Konvertierungsoptionen und legen das Eingabearbeitsverzeichnis für Ihre LaTeX-Dateien fest.

## Schritt 2: Interaktionsmodus festlegen

```csharp
options.Interaction = Interaction.NonstopMode;
```

Geben Sie den Interaktionsmodus an, wobei wir ihn für eine unterbrechungsfreie Konvertierung auf den Non-Stop-Modus einstellen.

## Schritt 3: Jobnamen festlegen (optional)

```csharp
// options.JobName = "mein-Jobname";
```

Bei Bedarf können Sie einen benutzerdefinierten Jobnamen festlegen.

## Schritt 4: Datum im Titel festlegen (optional)

```csharp
// options.DateTime = new System.DateTime(2022, 12, 18);
```

Erzwingen Sie, dass die TeX-Engine ein bestimmtes Datum im Titel ausgibt.

## Schritt 5: Fehlende Pakete ignorieren

```csharp
options.IgnoreMissingPackages = true;
```

Auf „true“ setzen, wenn die Engine fehlende Pakete ohne Fehler überspringen soll.

## Schritt 6: Ligaturen deaktivieren

```csharp
options.NoLigatures = true;
```

Auf „true“ setzen, um zu verhindern, dass die Engine Ligaturen erstellt.

## Schritt 7: Wiederholen Sie den Job (optional)

```csharp
// Optionen.Repeat = true;
```

Bitten Sie den Motor, den Job bei Bedarf zu wiederholen.

## Schritt 8: Geben Sie das Ausgabearbeitsverzeichnis an

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Legen Sie das Ausgabearbeitsverzeichnis für die konvertierten XPS-Dateien fest.

## Schritt 9: Speicheroptionen für XPS initialisieren

```csharp
options.SaveOptions = new XpsSaveOptions(); // Standardwert. Beliebige Zuordnung.
```

Initialisieren Sie die Optionen zum Speichern im XPS-Format.

## Schritt 10: Formeln rastern (optional)

```csharp
options.SaveOptions.RasterizeFormulas = true;
```

Legen Sie den Wert auf „true“ fest, wenn Sie möchten, dass mathematische Formeln in Rasterbilder konvertiert werden.

## Schritt 11: Eingeschlossene Grafiken rastern (optional)

```csharp
options.SaveOptions.RasterizeIncludedGraphics = true;
```

Legen Sie den Wert auf „true“ fest, wenn Sie möchten, dass enthaltene Grafiken mit Vektorelementen in Rasterbilder konvertiert werden.

## Schritt 12: Schriftarten unterteilen

```csharp
options.SaveOptions.SubsetFonts = true;
```

Auf „true“ setzen, um die Schriftarten des Geräts als Teilmenge im Dokument zu verwenden.

## Schritt 13: Führen Sie die LaTeX-zu-XPS-Konvertierung aus

```csharp
new TeXJob(Path.Combine("Your Input Directory", "sample.ltx"), new XpsDevice(), options).Run();
```

Starten Sie den LaTeX-zu-XPS-Konvertierungsprozess.

## Schritt 14: LaTeX-zu-XPS-Konvertierung mit MemoryStream ausführen (Alternative)

```csharp
// new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(@"\documentclass{article} \begin{document} Hello, World! \end{document}")),
// new XpsDevice(), Optionen).Run();
```

Sie können die Konvertierung auch mit einem MemoryStream für eingegebene LaTeX-Inhalte ausführen.

## Schritt 15: Konvertierung von LaTeX in XPS mit dem Haupteingabeterminal ausführen (Alternative)

```csharp
// new TeXJob(new XpsDevice(), options).Run();
```

Führen Sie die Konvertierung direkt vom Haupteingabeterminal aus.

## Abschluss

Wenn Sie diese einfachen Schritte befolgen, können Sie LaTeX-Dokumente mit Aspose.TeX für .NET mühelos in das XPS-Format konvertieren. Diese leistungsstarke Bibliothek bietet Flexibilität und Anpassungsoptionen, um Ihre spezifischen Anforderungen zu erfüllen.

## FAQs

### F1: Ist Aspose.TeX mit den neuesten .NET-Frameworks kompatibel?

A1: Ja, Aspose.TeX wird regelmäßig aktualisiert, um die Kompatibilität mit den neuesten .NET-Frameworks sicherzustellen.

### F2: Kann ich ein anderes Ausgabeformat als XPS anpassen?

 A2: Aspose.TeX unterstützt verschiedene Ausgabeformate. Weitere Informationen finden Sie in der Dokumentation[Hier](https://reference.aspose.com/tex/net/) für Details.

### F3: Wie erhalte ich eine temporäre Lizenz für Aspose.TeX?

 A3: Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/).

### F4: Wo kann ich Hilfe suchen oder meine Erfahrungen mit Aspose.TeX teilen?

 A4: Besuchen Sie das Aspose.TeX-Forum[Hier](https://forum.aspose.com/c/tex/47) für die Unterstützung der Gemeinschaft.

### F5: Gibt es Musterdokumente zum Testen?

 A5: Entdecken Sie die Aspose.TeX-Beispiele[Hier](https://github.com/aspose-tex/Aspose.TeX-for-.NET).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
