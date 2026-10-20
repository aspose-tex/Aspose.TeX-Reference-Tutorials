---
date: 2026-10-19
description: Erfahren Sie, wie Sie Tex-Dokumentgenerierung durchführen, ein benutzerdefiniertes
  Tex-Format erstellen und das Tex-Eingabeverzeichnis mit Aspose.TeX für .NET festlegen.
  Schritt‑für‑Schritt‑Anleitung mit Code‑Beispielen und Fehlerbehebungstipps.
keywords:
- tex document generation
- create custom tex format
- set tex input directory
- custom tex macros
lastmod: 2026-10-19
linktitle: Erstellung benutzerdefinierter TeX-Formate in .NET
og_description: Tex-Dokumentgenerierung mit Aspose.TeX ermöglicht das Erstellen benutzerdefinierter
  Tex-Formate und das Festlegen des Tex-Eingabeverzeichnisses in .NET. Folgen Sie
  dieser Anleitung für XPS-, PDF- oder PNG-Ausgabe.
og_image_alt: Developer guide showing tex document generation using Aspose.TeX in
  .NET
og_title: Wie man Tex-Dokumentgenerierung mit Format in .NET durchführt
schemas:
- author: Aspose
  dateModified: '2026-10-19'
  description: Learn how to perform tex document generation, create custom tex format
    and set tex input directory using Aspose.TeX for .NET. Step‑by‑step guide with
    code snippets and troubleshooting tips.
  headline: How to do tex document generation with format in .NET
  type: TechArticle
- description: Learn how to perform tex document generation, create custom tex format
    and set tex input directory using Aspose.TeX for .NET. Step‑by‑step guide with
    code snippets and troubleshooting tips.
  name: How to do tex document generation with format in .NET
  steps:
  - name: '**Aspose.TeX for .NET** – download it from the [Aspose.TeX website](https://releases.aspose.com/tex/net/).'
    text: '**Aspose.TeX for .NET** – download it from the [Aspose.TeX website](https://releases.aspose.com/tex/net/).'
  - name: A **.NET development environment** (Visual Studio, VS Code, or the .NET
      CLI).
    text: A **.NET development environment** (Visual Studio, VS Code, or the .NET
      CLI).
  - name: (Optional) A valid **Aspose.TeX license** for production use.
    text: (Optional) A valid **Aspose.TeX license** for production use.
  type: HowTo
- questions:
  - answer: Absolutely. Replace `new XpsDevice()` with `new PdfDevice()` and adjust
      the output path accordingly.
    question: Can I output PDF instead of XPS?
  - answer: Yes. Any modification to macros or engine settings requires re‑running
      `tex -ini` to generate a fresh `.fmt` file.
    question: Do I need to re‑compile the format file after every change?
  type: FAQPage
second_title: Aspose.TeX .NET API
tags:
- tex document generation
- Aspose.TeX
- .NET document processing
- custom tex format
title: Wie man Tex-Dokumentgenerierung mit Format in .NET durchführt
url: /de/net/custom-tex-formats/create-custom-tex-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Tex-Dokumentgenerierung mit Format in .NET durchführt

In der modernen .NET-Entwicklung ist **tex document generation** ein leistungsstarkes Mittel, um hochwertige Satzausgaben zu erzeugen, ohne externe LaTeX-Installationen zu benötigen. Aspose.TeX für .NET gibt Ihnen volle Kontrolle: Sie können **create custom tex format**, die Engine auf einen dedizierten Eingabeordner zeigen und nach XPS, PDF, PNG oder andere Geräte exportieren – alles aus einfachem C#‑Code.

## Schnelle Antworten
- **Was bedeutet “create custom tex format”?** Es bedeutet, dass Sie Ihre eigene TeX‑Engine‑Konfiguration und kompilierten Formatdatei definieren, sodass der Prozessor Ihren Makros und Einstellungen folgt.  
- **Welche Bibliothek benötige ich?** Aspose.TeX für .NET, das mehr als 30 Eingabe‑ und Ausgabeformate unterstützt.  
- **Muss ich ein tex‑Eingabeverzeichnis festlegen?** Ja – verwenden Sie `InputWorkingDirectory`, um der Engine mitzuteilen, wo Hilfsdateien liegen.  
- **Welche Ausgaben kann ich erzeugen?** XPS, PDF, PNG, TIFF und viele weitere Geräteformate.  
- **Ist für den Produktionseinsatz eine Lizenz erforderlich?** Eine gültige Aspose.TeX‑Lizenz ist für kommerzielle Bereitstellungen obligatorisch.

## Was ist ein custom tex format?
Ein custom tex format ist eine vorab kompilierte Sammlung von Makros und Engine‑Einstellungen, die der TeX‑Prozessor beim Start lädt. Durch das Erstellen eines solchen Formats können Sie Corporate Branding einbetten, Layout‑Standards durchsetzen und die Kompilierzeit für wiederkehrende Dokumente reduzieren. Es ermöglicht einheitliches Styling für alle erzeugten Dokumente und vereinfacht die Wartung komplexer Satz‑Workflows.

## Warum ein tex‑Eingabeverzeichnis festlegen?
Das Festlegen des **tex input directory** teilt der Engine mit, wo Hilfsdateien wie Stil‑Dateien, benutzerdefinierte Schriften oder zusätzliche Makro‑Pakete zu finden sind. Dies eliminiert „Datei nicht gefunden“-Fehler und hält Ihren Projektordner übersichtlich. Außerdem verbessert es die Wiederholbarkeit von Builds, indem sichergestellt wird, dass alle Ressourcen aus einem bekannten Ort aufgelöst werden.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Aspose.TeX für .NET** – laden Sie es von der [Aspose.TeX-Website](https://releases.aspose.com/tex/net/) herunter.  
2. Eine **.NET‑Entwicklungsumgebung** (Visual Studio, VS Code oder die .NET‑CLI).  
3. (Optional) Eine gültige **Aspose.TeX‑Lizenz** für den Produktionseinsatz.

## Namespaces importieren

Die folgenden Namespaces geben Ihnen Zugriff auf die Kernklassen von Aspose.TeX.  
Klassen, die sich auf `Document` beziehen, befinden sich unter `Aspose.TeX`, während Optionen und Geräte in `Aspose.TeX.Rendering` liegen.

Die Klasse `Document` ist das oberste Objekt, das ein einzelnes TeX‑Dokument im Speicher repräsentiert.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using Aspose.TeX.ResourceProviders;
using System.IO;
using System.Text;
```

## Schritt 1: Format‑Provider erstellen

Der `FormatProvider` teilt der Engine mit, wo sich die kompilierte Formatdatei (`customtex.fmt`) befindet. Ersetzen Sie `"Your Output Directory"` durch den absoluten Pfad, der Ihr benutzerdefiniertes Format enthält.

`FormatProvider` ist ein leichtgewichtiger Wrapper, der die `.fmt`‑Datei einmal lädt und für jede Konvertierung wiederverwendet, wodurch die Leistung bei Batch‑Jobs erheblich verbessert wird.

```csharp
using (FormatProvider formatProvider =
    new FormatProvider(new InputFileSystemDirectory("Your Output Directory"), "customtex"))
{
```

## Schritt 2: Konvertierungsoptionen konfigurieren (und tex‑Eingabeverzeichnis festlegen)

Hier erstellen wir eine Instanz von `TeXOptions`. Die Eigenschaft `InputWorkingDirectory` **setzt das tex‑Eingabeverzeichnis**, sodass die Engine alle unterstützenden Dateien wie benutzerdefinierte Pakete oder Schriften finden kann.

`TeXOptions` ermöglicht außerdem die Angabe des Ausgabegeräts, der Seitengröße und der Renderqualität. Für groß angelegte Generierung können Sie `EnableParallelProcessing` aktivieren, um das Rendern auf Mehrkern‑Servern zu beschleunigen.

```csharp
    TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX(formatProvider));
    options.JobName = "typeset-with-custom-format";
    options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
    options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

## Schritt 3: Job ausführen

Jetzt übergeben Sie der Engine einen einfachen TeX‑String, wählen ein Ausgabegerät (XPS in diesem Beispiel) und führen den Job aus. Die `TeXEngine` liest das custom format, verarbeitet die Quelle und schreibt das Ergebnis an das ausgewählte Gerät.

`TeXEngine` ist der Kernprozessor von Aspose.TeX, der den TeX‑Quelltext analysiert, das custom format anwendet und die gerenderten Seiten an das von Ihnen angegebene Gerät streamt.

```csharp
    new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
        "Congratulations! You have successfully typeset this text with your own TeX format!\\end")),
        new XpsDevice(), options).Run();
```

## Schritt 4: Terminalausgabe verfeinern

Das Hinzufügen einer Leerzeile nach Abschluss des Jobs macht Konsolenprotokolle leichter lesbar, insbesondere wenn Sie mehrere Konvertierungen in einem Skript hintereinander ausführen.

`Console.WriteLine()` schreibt eine Textzeile in den Standardausgabestream. Es wird hier ausschließlich zur visuellen Trennung verwendet; es hat keinen Einfluss auf das erzeugte Dokument.

```csharp
    options.TerminalOut.Writer.WriteLine();
}
// ExEnd:TypesetWithCustomTeXFormat
```

Herzlichen Glückwunsch! Sie haben nun **create custom tex format** erstellt und es für **tex document generation** in .NET verwendet. Sie können das `XpsDevice` durch `PdfDevice`, `PngDevice` oder ein anderes unterstütztes Gerät ersetzen, um Ihren Auslieferungsanforderungen gerecht zu werden.

## Häufige Probleme und Lösungen

| Problem | Grund | Lösung |
|---------|-------|--------|
| *“Format file not found”* | Falscher Pfad im `FormatProvider` | Überprüfen Sie, dass `"Your Output Directory"` die Datei `customtex.fmt` enthält und dass der Pfad absolut oder korrekt relativ zur ausführbaren Datei ist. |
| *“Cannot find input file”* | `InputWorkingDirectory` zeigt auf den falschen Ordner | Stellen Sie sicher, dass `"Your Input Directory"` die TeX‑Quelldatei enthält oder dass Sie die Quelle als Stream übergeben (wie im Beispiel). |
| *Terminal output garbled* | Kodierungsinkompatibilität | Verwenden Sie `Encoding.UTF8`, wenn Ihre TeX‑Quelle nicht‑ASCII‑Zeichen enthält. |
| *XPS file is empty* | Job wurde aufgrund einer vorherigen Ausnahme nicht ausgeführt | Prüfen Sie die Konsole auf Fehlermeldungen; diese weisen häufig auf fehlende Pakete oder Syntaxfehler im TeX‑String hin. |

## Häufig gestellte Fragen

**Q1: Kann ich Aspose.TeX für .NET mit anderen Aspose‑Bibliotheken verwenden?**  
A: Ja, Aspose.TeX lässt sich nahtlos in Aspose.PDF, Aspose.Words und andere Aspose‑Produkte für End‑to‑End‑Dokumenten‑Pipelines integrieren.

**Q2: Gibt es eine kostenlose Testversion von Aspose.TeX für .NET?**  
A: Ja, Sie können eine Testversion von der **Aspose.TeX‑Kostenlos‑Test‑Download‑Seite** (https://releases.aspose.com/tex/net/) herunterladen.

**Q3: Wie kann ich Support für Aspose.TeX für .NET erhalten?**  
A: Besuchen Sie das [Aspose.TeX‑Forum](https://forum.aspose.com/c/tex/47) für Community‑Hilfe oder prüfen Sie Premium‑Optionen auf der **Premium‑Support‑Kaufseite** (https://purchase.aspose.com/buy).

**Q4: Gibt es temporäre Lizenzen für Aspose.TeX für .NET?**  
A: Ja, beantragen Sie eine auf der **temporären Lizenz‑Anfrageseite** (https://purchase.aspose.com/temporary-license/).

**Q5: Wo finde ich die offizielle API‑Referenz?**  
A: Die umfassende Dokumentation ist auf der **API‑Referenz‑Dokumentationsseite** (https://reference.aspose.com/tex/net/) verfügbar.

### Zusätzliche Fragen & Antworten

**Q: Kann ich PDF statt XPS ausgeben?**  
A: Absolut. Ersetzen Sie `new XpsDevice()` durch `new PdfDevice()` und passen Sie den Ausgabepfad entsprechend an.

**Q: Muss ich die Formatdatei nach jeder Änderung neu kompilieren?**  
A: Ja. Jede Änderung an Makros oder Engine‑Einstellungen erfordert das erneute Ausführen von `tex -ini`, um eine neue `.fmt`‑Datei zu erzeugen.

## Fazit

Aspose.TeX für .NET bietet eine **robuste, leistungsstarke Lösung für tex document generation**, mit der Sie **create custom tex format** erstellen, das **tex input directory** festlegen und zu jedem unterstützten Gerät ausgeben können. Integrieren Sie die obigen Schritte in Ihre CI/CD‑Pipeline, automatisieren Sie die großflächige Berichtserstellung oder bauen Sie eine benutzerdefinierte Publishing‑Engine, die den Markenstandards Ihrer Organisation entspricht.

---

**Letzte Aktualisierung:** 2026-10-19  
**Getestet mit:** Aspose.TeX 24.11 für .NET  
**Autor:** Aspose

## Verwandte Tutorials

- [TeX-Datei-Stream (C#) mit Aspose.TeX API erforderliches Eingabeverzeichnis erhalten](/tex/net/advanced-io/required-input-directory-csharp/)
- [Wie man PDF mit Aspose.TeX für .NET erstellt – Schritt für Schritt](/tex/net/pdf-output/)
- [Wie man XPS-Dokument in .NET erstellt – TeX in XPS-Ausgabe mit Aspose.TeX für .NET konvertiert](/tex/net/xps-output/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}