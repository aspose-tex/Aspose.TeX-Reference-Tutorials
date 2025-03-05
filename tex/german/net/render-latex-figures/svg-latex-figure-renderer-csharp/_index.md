---
title: Rendern Sie LaTeX-Figuren in SVG mit Aspose.TeX (C#)
linktitle: Rendern Sie LaTeX-Figuren in SVG mit Aspose.TeX (C#)
second_title: Aspose.TeX .NET-API
description: Verbessern Sie das Rendern von Dokumenten in .NET mit Aspose.TeX. Erfahren Sie, wie Sie LaTeX-Figuren in C# in SVG rendern, um mathematische Ausdrücke nahtlos zu integrieren.
type: docs
weight: 11
url: /de/net/render-latex-figures/svg-latex-figure-renderer-csharp/
---
## Einführung

Wenn Sie Ihre Funktionen zur Dokumentwiedergabe in .NET mithilfe von LaTeX-Figuren verbessern möchten, ist Aspose.TeX Ihre Lösung der Wahl. In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch das Rendern von LaTeX-Figuren in SVG mit Aspose.TeX in C#. Am Ende dieses Tutorials haben Sie ein klares Verständnis des Prozesses und sind in der Lage, hochwertige mathematische Ausdrücke und Zahlen nahtlos in Ihre Dokumente zu integrieren.

## Voraussetzungen

Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Grundkenntnisse der Programmiersprache C#.
-  Aspose.TeX für .NET-Bibliothek installiert. Sie können es herunterladen[Hier](https://releases.aspose.com/tex/net/).

## Namespaces importieren

Stellen Sie sicher, dass Sie in Ihrem C#-Code die erforderlichen Namespaces importieren:

```csharp
using Aspose.TeX.Features;
```

Lassen Sie uns das Tutorial nun in mehrere Schritte unterteilen:

## Schritt 1: Erstellen Sie Rendering-Optionen

```csharp
FigureRendererOptions options = new SvgFigureRendererOptions();
options.Preamble = "\\usepackage{pict2e}";
options.Scale = 3000;
options.BackgroundColor = Color.White;
options.LogStream = new System.IO.MemoryStream();
options.ShowTerminal = true;
```

Hier richten wir Rendering-Optionen ein und geben die Präambel, den Skalierungsfaktor, die Hintergrundfarbe, den Protokollstream und die Anzeige der Terminalausgabe an.

## Schritt 2: Definieren Sie Dimensionen und Ausgabestream

```csharp
SizeF size = new SizeF();
using (Stream stream = File.Open(Path.Combine("Your Output Directory", "text-and-formula.svg"), FileMode.Create))
{
    // Führen Sie das Rendern aus.
    new SvgFigureRenderer().Render("Your LaTeX Code", stream, options, out size);
}
```

Ersetzen Sie „Ihr Ausgabeverzeichnis“ durch Ihr gewünschtes Verzeichnis und geben Sie Ihren LaTeX-Code als Zeichenfolge an.

## Schritt 3: Ergebnisse anzeigen

```csharp
Console.Out.WriteLine(options.ErrorReport);
Console.Out.WriteLine();
Console.Out.WriteLine("Size: " + size);
```

In diesem Schritt werden alle Fehlerberichte und die Größe des resultierenden Bildes angezeigt.

## Abschluss

Glückwunsch! Sie haben erfolgreich gelernt, wie Sie LaTeX-Figuren mithilfe von Aspose.TeX in C# in SVG rendern. Jetzt können Sie mathematische Ausdrücke und Zahlen nahtlos in Ihre .NET-Anwendungen integrieren.

## FAQs

### F1: Ist die Nutzung von Aspose.TeX kostenlos?

 A1: Aspose.TeX bietet eine kostenlose Testversion. Sie können darauf zugreifen[Hier](https://releases.aspose.com/).

### F2: Wo finde ich die Aspose.TeX-Dokumentation?

 A2: Sehen Sie sich die Dokumentation an[Hier](https://reference.aspose.com/tex/net/).

### F3: Wie erhalte ich Unterstützung für Aspose.TeX?

 A3: Besuchen Sie das Support-Forum[Hier](https://forum.aspose.com/c/tex/47).

### F4: Kann ich Aspose.TeX kaufen?

 A4: Ja, Sie können Aspose.TeX kaufen[Hier](https://purchase.aspose.com/buy).

### F5: Benötige ich eine temporäre Lizenz?

 A5: Bei Bedarf können Sie eine temporäre Lizenz erwerben[Hier](https://purchase.aspose.com/temporary-license/).