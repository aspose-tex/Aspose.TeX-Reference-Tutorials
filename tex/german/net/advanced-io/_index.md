---
date: 2026-09-24
description: Erfahren Sie, wie Sie das TeX-Eingabeverzeichnis, Streams, Bilder und
  Terminaleingaben mit Aspose.TeX für .NET in C# konfigurieren.
keywords:
- configure tex input directory
- add image stream tex
- add images from stream
lastmod: 2026-09-24
linktitle: Erweiterte Aspose.TeX Eingabe und Ausgabe
og_description: Konfigurieren Sie das TeX-Eingabeverzeichnis, fügen Sie Bildstreams
  hinzu und verarbeiten Sie Terminaleingaben mit Aspose.TeX für .NET in C#. Lernen
  Sie Schritt für Schritt.
og_image_alt: Guide showing how to configure TeX input directory and streams in Aspose.TeX
  for .NET
og_title: Konfigurieren des TeX-Eingabeverzeichnisses – Erweiterter Aspose.TeX Leitfaden
schemas:
- author: Aspose
  dateModified: '2026-09-24'
  description: Learn how to configure TeX input directory, streams, images, and terminal
    input using Aspose.TeX for .NET in C#.
  headline: Configure TeX input directory – Advanced Aspose.TeX Input and Output
  type: TechArticle
- description: Learn how to configure TeX input directory, streams, images, and terminal
    input using Aspose.TeX for .NET in C#.
  name: Configure TeX input directory – Advanced Aspose.TeX Input and Output
  steps:
  - name: instantiate TeXInputOptions
    text: Assign the base folder that holds the primary TeX source.
  - name: add extra search paths
    text: If your project stores figures in a separate folder (e.g., *Images*), call
      `AddSearchPath` to include it.
  - name: hand the options to the processor
    text: Create a `TeXProcessor`, provide the configured options, and invoke `Process`
      or `Render`.
  type: HowTo
- questions:
  - answer: Yes—you can create a new `TeXInputOptions` instance with a different `BaseFolder`
      and pass it to a fresh `TeXProcessor` whenever you need to reconfigure.
    question: Can I change the input directory at runtime?
  - answer: Retrieve the image as a `byte[]`, wrap it in a `MemoryStream`, and call
      `TeXInputOptions.AddImage("image.png", stream)`. The name must match the reference
      in your `.tex` file.
    question: How do I add images that are stored in a database?
  - answer: Absolutely. Convert the incoming string to a `MemoryStream`, set it as
      the source for `TeXProcessor`, and render directly to your desired output format.
    question: Is it possible to process LaTeX code received from a web API without
      saving a file?
  - answer: Dispose of any streams you create, and for large workloads invoke `TeXProcessor.Cleanup()`
      to free native resources.
    question: Do I need to call any cleanup methods after processing?
  - answer: The two tutorial links above contain full code samples that demonstrate
      each scenario in detail, including error handling and performance tips.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.TeX .NET API
tags:
- Aspose.TeX
- input directory
- C# document processing
title: Konfigurieren des TeX-Eingabeverzeichnisses – Erweiterte Aspose.TeX Eingabe
  und Ausgabe
url: /de/net/advanced-io/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konfigurieren des TeX-Eingabeverzeichnisses in Aspose.TeX für .NET

Aspose.TeX für .NET ermöglicht es Ihnen, die vollständige TeX-Verarbeitung direkt in Ihre C#‑Anwendungen einzubetten. In diesem Tutorial lernen Sie, wie Sie das **TeX‑Eingabeverzeichnis konfigurieren**, LaTeX‑Inhalte aus Streams bereitstellen und Bilder hinzufügen, ohne das Dateisystem zu berühren. Wenn Sie eine präzise Kontrolle darüber benötigen, wo die Engine nach `.tex`‑Dateien und Ressourcen sucht, sind Sie hier genau richtig.

## Schnelle Antworten
- **Was bedeutet „configure tex input directory“?**  
  Es teilt Aspose.TeX mit, wo die Haupt‑`.tex`‑Datei, Hilfsdateien und Grafiken zu finden sind.
- **Welche Klasse definiert die Eingabepfade?**  
  `TeXInputOptions` speichert das Basisverzeichnis und alle zusätzlichen Suchpfade.
- **Kann ich ein Bild aus einem Memory‑Stream laden?**  
  Ja – verwenden Sie `TeXInputOptions.AddImage` mit einer `Stream`‑Instanz.
- **Ist es möglich, LaTeX‑Code zur Laufzeit zu kompilieren?**  
  Absolut – übergeben Sie einen `MemoryStream`, der den Quelltext enthält, an den Prozessor.
- **Benötige ich eine Lizenz für den Produktionseinsatz?**  
  Eine gültige Aspose.TeX‑Lizenz ist für den produktiven Einsatz erforderlich.

## Was ist TeXInputOptions?
`TeXInputOptions` ist das Konfigurationsobjekt, das das Basisverzeichnis und zusätzliche Suchpfade für TeX‑Ressourcen definiert. Eine korrekte Einrichtung eliminiert „Datei nicht gefunden“-Fehler und ermöglicht eine organisierte Verwaltung der Assets.

## Wie konfiguriere ich das TeX‑Eingabeverzeichnis?
`TeXInputOptions` ist ein Konfigurationsobjekt, das das Basisverzeichnis und zusätzliche Suchpfade für TeX‑Ressourcen angibt. Laden Sie Ihr Hauptdokument und teilen Sie dem Prozessor in wenigen Zeilen mit, wo alles zu finden ist. Diese direkte Antwort erklärt die wesentlichen Schritte, bevor weitere Details folgen.

Erstellen Sie eine `TeXInputOptions`‑Instanz, setzen Sie `BaseFolder` auf das Verzeichnis, das Ihre primäre `.tex`‑Datei enthält, fügen Sie alle Unterordner hinzu, die Bilder oder Hilfsdateien enthalten, und übergeben Sie die Optionen an `TeXProcessor`. Die Engine löst dann automatisch alle relativen Verweise auf.

### Schritt 1: TeXInputOptions instanziieren
Legen Sie das Basisverzeichnis fest, das die primäre TeX‑Quelle enthält.

### Schritt 2: zusätzliche Suchpfade hinzufügen
Wenn Ihr Projekt Abbildungen in einem separaten Ordner speichert (z. B. *Images*), rufen Sie `AddSearchPath` auf, um ihn einzubeziehen.

### Schritt 3: Optionen an den Prozessor übergeben
Erstellen Sie einen `TeXProcessor`, übergeben Sie die konfigurierten Optionen und rufen Sie `Process` oder `Render` auf.

## Wie füge ich Bilder mit Aspose.TeX hinzu
Bilder, die in einer TeX‑Datei referenziert werden, können entweder über einen Ordner oder direkt aus einem Stream bereitgestellt werden. Das Bereitstellen eines Streams ist nützlich, wenn Bilder in einer Datenbank gespeichert oder on‑the‑fly generiert werden. `AddImage(string name, Stream data)` registriert einen Bild‑Stream mit dem angegebenen Dateinamen zur Verwendung im TeX‑Dokument. Diese Methode ermöglicht es, temporäre Dateien zu vermeiden und beschleunigt die Verarbeitung.

## Wie verarbeite ich Streams in Aspose.TeX
Wenn Ihre LaTeX‑Quelle dynamisch erzeugt wird – beispielsweise aus Benutzereingaben oder einem Web‑Service – können Sie sie direkt an den Prozessor übergeben, ohne eine Datei zu schreiben. `TeXProcessor` verarbeitet TeX‑Inhalte und kann einen `MemoryStream` akzeptieren, der den Quell‑LaTeX‑Code enthält. Verpacken Sie den LaTeX‑String in einen `MemoryStream`, setzen Sie ihn als Quell‑Stream in `TeXProcessor` und führen Sie die Konvertierung aus. Diese Technik funktioniert ebenso gut für cloud‑native Dienste, bei denen Festplatten‑I/O teuer ist.

## Warum Aspose.TeX für fortgeschrittene I/O verwenden?
Aspose.TeX unterstützt **30+ Eingabe‑ und Ausgabeformate** (einschließlich PDF, PNG, SVG) und kann mehrseitige Dokumente rendern, ohne die gesamte Datei in den Speicher zu laden. Sein Stream‑first‑Design reduziert den I/O‑Overhead um bis zu 40 % im Vergleich zu dateibasierten Workflows und ist damit ideal für hochdurchsatzfähige Serveranwendungen.

## Voraussetzungen
- .NET 6.0 oder höher (die Bibliothek funktioniert auch mit .NET Core 3.1+ und .NET Framework 4.6.1+)
- Aspose.TeX für .NET NuGet‑Paket (Version 24.11 oder neuer)
- Eine gültige Aspose.TeX‑Lizenz für den Produktionseinsatz

## Entdecken Sie Aspose.TeX: ein Tor zur fortgeschrittenen Dokumentenverarbeitung
Um die Konfiguration in Aktion zu sehen, folgen Sie unserer Schritt‑für‑Schritt‑Anleitung **[Erforderliches Eingabeverzeichnis für Aspose.TeX festlegen (C#)](./required-input-directory-csharp/)**.  
**[Erforderliches Eingabeverzeichnis für Aspose.TeX festlegen (C#)](./required-input-directory-csharp/)**

## Beherrschung von Streams, Bildern und Terminal‑Eingaben in Aspose.TeX für C#
Für ein tieferes Eintauchen in das Einspeisen von LaTeX aus dem Speicher, das Hinzufügen von Bildern über Streams und die Verwendung von terminalähnlichen Eingaben, schauen Sie sich **[Streams, Bilder & Terminal‑Eingaben in Aspose.TeX für C# meistern](./stream-input-image-output-terminal-input-csharp/)** an. Es zeigt, wie Aspose.TeX in Web‑APIs, Hintergrunddienste und Konsolen‑Tools integriert wird.  
**[Streams, Bilder & Terminal‑Eingaben in Aspose.TeX für C# meistern](./stream-input-image-output-terminal-input-csharp/)**

## Häufige Probleme und Lösungen
- **„File not found“-Fehler** – Stellen Sie sicher, dass `BaseFolder` auf das richtige Verzeichnis zeigt und dass alle zusätzlichen Suchpfade vor dem Rendern hinzugefügt wurden.
- **Bilder werden nicht geladen** – Stellen Sie sicher, dass der Bildname in `AddImage` exakt dem im TeX‑Quelltext verwendeten Namen entspricht, einschließlich Dateierweiterung.
- **Speicherverbrauch steigt** – Rufen Sie bei der Verarbeitung sehr großer Dokumente nach dem Rendern `TeXProcessor.Cleanup()` auf, um nicht verwaltete Ressourcen freizugeben.

## Häufig gestellte Fragen

**Q: Kann ich das Eingabeverzeichnis zur Laufzeit ändern?**  
A: Ja – Sie können eine neue `TeXInputOptions`‑Instanz mit einem anderen `BaseFolder` erstellen und sie bei Bedarf an einen neuen `TeXProcessor` übergeben, um die Konfiguration zu ändern.

**Q: Wie füge ich Bilder hinzu, die in einer Datenbank gespeichert sind?**  
A: Rufen Sie das Bild als `byte[]` ab, verpacken Sie es in einen `MemoryStream` und rufen Sie `TeXInputOptions.AddImage("image.png", stream)` auf. Der Name muss mit der Referenz in Ihrer `.tex`‑Datei übereinstimmen.

**Q: Ist es möglich, LaTeX‑Code, der von einer Web‑API empfangen wurde, zu verarbeiten, ohne eine Datei zu speichern?**  
A: Absolut. Konvertieren Sie den eingehenden String in einen `MemoryStream`, setzen Sie ihn als Quelle für `TeXProcessor` und rendern Sie direkt in das gewünschte Ausgabeformat.

**Q: Muss ich nach der Verarbeitung Aufräummethoden aufrufen?**  
A: Entsorgen Sie alle erstellten Streams und rufen Sie bei großen Arbeitslasten `TeXProcessor.Cleanup()` auf, um native Ressourcen freizugeben.

**Q: Wo finde ich weiterführende Beispiele?**  
A: Die beiden oben genannten Tutorial‑Links enthalten vollständige Code‑Beispiele, die jedes Szenario im Detail demonstrieren, einschließlich Fehlerbehandlung und Performance‑Tipps.

---

**Zuletzt aktualisiert:** 2026-09-24  
**Getestet mit:** Aspose.TeX 24.11 für .NET  
**Autor:** Aspose

## Verwandte Tutorials

- [TeX‑Datei‑Stream erhalten (C#) mit Aspose.TeX API Erforderliches Eingabeverzeichnis](/tex/net/advanced-io/required-input-directory-csharp/)
- [XPS aus TeX mit Dateisystemen erstellen – Aspose.TeX für .NET](/tex/net/file-input-output/filesystem-input-xps-output/)
- [LaTeX zu PNG konvertieren mit Aspose.TeX für .NET – Dateisystem‑ & ZIP‑Eingaben verarbeiten](/tex/net/file-input-output/required-inputs-from-filesystem-and-zip/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}