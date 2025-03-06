---
title: Mit Aspose.TeX (C#) LaTeX-Figuren in PNG rendern
linktitle: Mit Aspose.TeX (C#) LaTeX-Figuren in PNG rendern
second_title: Aspose.TeX .NET-API
description: Entdecken Sie eine umfassende Anleitung zum Rendern von LaTeX-Figuren in PNG mit Aspose.TeX in C#. Lernen Sie Schritt für Schritt anhand von Codebeispielen.
weight: 10
url: /de/net/render-latex-figures/png-latex-figure-renderer-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mit Aspose.TeX (C#) LaTeX-Figuren in PNG rendern

## Einführung

Wenn Sie in die Welt des Schriftsatzes und der Dokumenterstellung in .NET eintauchen, sind Sie wahrscheinlich mit den Herausforderungen beim Rendern von LaTeX-Figuren vertraut. In dieser Schritt-für-Schritt-Anleitung erfahren Sie, wie Sie mit Aspose.TeX für .NET LaTeX-Figuren mit C# in das PNG-Format rendern. Aspose.TeX bietet eine leistungsstarke und flexible Lösung für den Umgang mit LaTeX-Dokumenten und ist damit ein unschätzbar wertvolles Werkzeug für Entwickler, die mit der Generierung und Formatierung von Dokumenten arbeiten.

## Voraussetzungen

Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

-  Aspose.TeX für .NET-Bibliothek: Stellen Sie sicher, dass Sie die Aspose.TeX-Bibliothek für .NET installiert haben. Sie können es herunterladen[Hier](https://releases.aspose.com/tex/net/).

## Namespaces importieren

Beginnen Sie in Ihrem C#-Code mit dem Importieren der erforderlichen Namespaces. Dieser Schritt stellt sicher, dass Sie Zugriff auf die erforderlichen Klassen und Funktionalitäten haben.

```csharp
using Aspose.TeX.Features;
```

## Rendern Sie LaTeX-Figuren in PNG

### Schritt 1: Renderoptionen einrichten

Erstellen Sie zunächst Rendering-Optionen und legen Sie Parameter wie Bildauflösung, Präambel, Skalierungsfaktor, Hintergrundfarbe und mehr fest.

```csharp
FigureRendererOptions options = new PngFigureRendererOptions() { Resolution = 150 };
options.Preamble = "\\usepackage{pict2e}";
options.Scale = 3000;
options.BackgroundColor = System.Drawing.Color.White;
options.LogStream = new System.IO.MemoryStream();
options.ShowTerminal = true;
```

### Schritt 2: Definieren Sie den Ausgabestream und die Dimensionen

Erstellen Sie einen Ausgabestream für das PNG-Bild und Variablen, um die Abmessungen des resultierenden Bildes zu speichern.

```csharp
System.Drawing.SizeF size = new System.Drawing.SizeF();
using (System.IO.Stream stream = System.IO.File.Open(
   System.IO.Path.Combine("Your Output Directory", "text-and-formula.png"), System.IO.FileMode.Create))
{
    // Code zum Rendern finden Sie hier
}
```

### Schritt 3: Rendern ausführen

Implementieren Sie den Rendering-Prozess mithilfe der Aspose.TeX-Bibliothek. Geben Sie den LaTeX-Code, den Ausgabestream, die Rendering-Optionen und die Größenvariable an.

```csharp
new PngFigureRenderer().Render(@"\setlength{\unitlength}{0.8cm}
\begin{picture}(6,5)
    % LaTeX figure code goes here
\end{picture}", stream, options, out size);
```

### Schritt 4: Ergebnisse anzeigen

Zeigen Sie abschließend die Ergebnisse an, einschließlich etwaiger Fehlerberichte und der Größe des gerenderten Bildes.

```csharp
System.Console.Out.WriteLine(options.ErrorReport);
System.Console.Out.WriteLine();
System.Console.Out.WriteLine("Size: " + size);
```

## Abschluss

Mit Aspose.TeX für .NET wird das Rendern von LaTeX-Figuren in das PNG-Format zu einem nahtlosen Prozess. Dieses Tutorial hat Sie durch die wesentlichen Schritte geführt, von der Einrichtung der Rendering-Optionen bis zur Anzeige der Endergebnisse.

## FAQs

### F1: Ist Aspose.TeX mit allen LaTeX-Befehlen kompatibel?

 A1: Aspose.TeX unterstützt eine Vielzahl von LaTeX-Befehlen, es wird jedoch empfohlen, auf die zu verweisen[Dokumentation](https://reference.aspose.com/tex/net/) für detaillierte Informationen.

### F2: Kann ich Aspose.TeX vor dem Kauf testen?

 A2: Ja, Sie können eine kostenlose Testversion ausprobieren[Hier](https://releases.aspose.com/).

### F3: Wie erhalte ich Unterstützung für Aspose.TeX?

 A3: Besuchen Sie die[Aspose.TeX-Forum](https://forum.aspose.com/c/tex/47)für Community-Unterstützung und Diskussionen.

### F4: Wo finde ich temporäre Lizenzen für Aspose.TeX?

 A4: Temporäre Lizenzen sind verfügbar[Hier](https://purchase.aspose.com/temporary-license/).

### F5: Wie ist die Preisstruktur für Aspose.TeX?

A5: Informieren Sie sich über die Preisdetails und tätigen Sie einen Kauf[Hier](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
