---
date: 2025-12-20
description: Erfahren Sie, wie Sie mit Aspose.TeX für .NET XPS‑Ausgaben für TeX‑Jobs
  erstellen, Dateisystem‑Ein‑ und‑Ausgabe verwalten und hochwertige XPS‑Dokumente
  erzeugen.
linktitle: Create TeX Job XPS Output with Filesystems – Aspose.TeX for .NET
second_title: Aspose.TeX .NET API
title: Erstellen Sie TeX-Job XPS-Ausgabe mit Dateisystemen – Aspose.TeX für .NET
url: /de/net/file-input-output/filesystem-input-xps-output/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erstellen von TeX‑Job‑XPS‑Ausgabe mit Dateisystemen – Aspose.TeX für .NET

## Einführung

Willkommen! In diesem Tutorial lernen Sie **wie man TeX‑Job‑XPS‑Ausgabe erstellt**, während Sie Eingaben und Ausgaben über das Dateisystem mit Aspose.TeX für .NET verarbeiten. Egal, ob Sie einen Batch‑Prozessor, einen Web‑Service oder ein Desktop‑Dienstprogramm bauen – die nachfolgenden Schritte führen Sie durch die Konfiguration der Engine, das Angeben Ihrer Dateien und das Erzeugen von XPS‑Dokumenten, die exakt dem ursprünglichen LaTeX‑Quelltext entsprechen.

Wir teilen den Prozess in klare, nummerierte Schritte, erklären das „Warum“ hinter jeder Code‑Zeile und geben Ihnen praktische Tipps, die Sie sofort anwenden können.

## Schnelle Antworten
- **Was bedeutet „create tex job xps“?** Es bezeichnet die Konfiguration eines Aspose.TeX‑Jobs, der TeX‑Dateien liest und das Ergebnis als XPS‑Dokument schreibt.  
- **Brauche ich eine Lizenz?** Eine temporäre Lizenz ist zum Testen verfügbar; für den Produktionseinsatz ist eine Voll‑Lizenz erforderlich.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Kann ich das Ausgabeformat ändern?** Ja – ersetzen Sie `XpsDevice` durch ein anderes Gerät (PDF, PNG usw.).  
- **Ist Konsolenausgabe erforderlich?** Nein – Sie können ein Memory‑Terminal für stille Ausführungen verwenden.

## Was ist „create tex job xps“?

Ein TeX‑Job, der XPS ausgibt, bedeutet, die Aspose.TeX‑Engine zu initialisieren, ihr mitzuteilen, wo die Quell‑Dateien zu finden sind, und die gerenderten Seiten in ein XPS‑Paket zu schreiben. XPS (XML Paper Specification) ist ein festes Layout‑Format, das Typografie und Vektorgrafiken bewahrt und sich daher ideal zum Drucken oder für weitere Konvertierungen eignet.

## Warum Aspose.TeX für XPS‑Ausgabe verwenden?

- **Hohe Treue:** Die Engine reproduziert das LaTeX‑Layout exakt in XPS.  
- **Keine externen Abhängigkeiten:** Reine .NET‑Bibliothek, keine native LaTeX‑Installation nötig.  
- **Flexibler I/O:** Arbeitet mit Dateisystem‑Verzeichnissen, Memory‑Streams oder benutzerdefinierten Providern.  
- **Skalierbar:** Geeignet für Einzeldateikonvertierungen sowie für Bulk‑Processing‑Pipelines.

## Voraussetzungen

Bevor wir starten, stellen Sie sicher, dass Sie Folgendes haben:

- **Aspose.TeX für .NET** – laden Sie die neueste Version von der [Aspose‑Website](https://releases.aspose.com/tex/net/) herunter.  
- **.NET‑Entwicklungsumgebung** – Visual Studio, Rider oder VS Code mit dem .NET‑SDK.  
- **Eingabe‑ & Ausgabeverzeichnisse** – erstellen Sie zwei Ordner auf Ihrem Rechner (z. B. `C:\TeX\Input` und `C:\TeX\Output`).  
- **Lizenz (optional zum Testen)** – Sie können eine temporäre Lizenz im Aspose‑Portal erhalten.

## Namespaces importieren

Zuerst bringen Sie die benötigten Namespaces in den Gültigkeitsbereich, damit Sie auf Dateisystem‑Hilfsfunktionen und das XPS‑Device zugreifen können.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

Diese Namespaces stellen `InputFileSystemDirectory`, `OutputFileSystemDirectory` und `XpsDevice` bereit, die für den **create tex job xps**‑Workflow unverzichtbar sind.

## Schritt 1: Konvertierungsoptionen erstellen

Wir beginnen damit, ein `TeXOptions`‑Objekt zu bauen, das der Engine mitteilt, die ObjectTeX‑Konfiguration zu verwenden (die Standardeinstellung für die meisten LaTeX‑Quellen).

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

> **Pro‑Tipp:** `ConsoleAppOptions` setzt sinnvolle Vorgaben für Konsolen‑Anwendungen, Sie können die Optionen später bei Bedarf anpassen.

## Schritt 2: Eingabe‑ und Ausgabeverzeichnisse angeben

Weisen Sie die Engine auf die zuvor angelegten Ordner. Ersetzen Sie die Platzhalter‑Strings durch die tatsächlichen Pfade auf Ihrem System.

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Jetzt weiß der TeX‑Job, wo er `.tex`‑Dateien findet und wohin die erzeugten XPS‑Dateien abgelegt werden.

## Schritt 3: Ausgabeterminal wählen

Das Terminal bestimmt, wohin Statusmeldungen geschrieben werden. Für schnelles Debugging bleiben wir bei der Konsole, Sie können jedoch zu einem Memory‑Terminal für stille Durchläufe wechseln.

```csharp
options.TerminalOut = new OutputConsoleTerminal(); // Default value. Arbitrary assignment.
```

> **Warum das wichtig ist:** Ein Konsolen‑Terminal liefert sofortiges Feedback zu Kompilierungs‑Warnungen oder -Fehlern, was die Fehlersuche beschleunigt.

## Schritt 4: TeX‑Job ausführen

Erzeugen Sie eine `TeXJob`‑Instanz, geben Sie ihr einen aussagekräftigen Namen, hängen Sie das `XpsDevice` an und führen Sie den Job aus.

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

Wenn `Run()` abgeschlossen ist, finden Sie eine `hello-world.xps`‑Datei im Ausgabeverzeichnis.

## Schritt 5: Konsolenausgabe feinjustieren

Das Hinzufügen einer Leerzeile nach Abschluss des Jobs macht das Konsolen‑Log leichter lesbar, besonders wenn Sie mehrere Jobs in einem Batch ausführen.

```csharp
options.TerminalOut.Writer.WriteLine();
```

## Häufige Probleme und Lösungen

| Problem | Ursache | Lösung |
|---------|----------|--------|
| **XPS‑Datei ist leer** | Pfad zum Ausgabeverzeichnis ist falsch oder nicht beschreibbar. | Prüfen Sie den Pfad, der an `OutputFileSystemDirectory` übergeben wird, und stellen Sie sicher, dass der Prozess Schreibrechte hat. |
| **Kompilierungsfehler** | LaTeX‑Quelltext verwendet Pakete, die nicht in ObjectTeX enthalten sind. | Wechseln Sie zu einer vollständigen TeX‑Engine‑Konfiguration (`TeXConfig.FullTeX()`) oder fügen Sie fehlende Paketdateien dem Eingabeverzeichnis hinzu. |
| **Konsole hängt** | Terminal wartet auf Eingaben wegen interaktiver Eingabeaufforderungen. | Verwenden Sie `OutputMemoryTerminal`, um interaktive Eingaben in automatisierten Skripten zu unterdrücken. |

## Häufig gestellte Fragen

**F1: Kann ich ein anderes Ausgabeformat als XPS verwenden?**  
A1: Ja, Aspose.TeX unterstützt PDF, PNG, SVG und weitere Formate. Ersetzen Sie `new XpsDevice()` durch die passende Device‑Klasse (z. B. `new PdfDevice()`).

**F2: Gibt es eine temporäre Lizenz für Testzwecke?**  
A2: Ja, Sie können eine temporäre Testlizenz über [diesen Link](https://purchase.aspose.com/temporary-license/) erhalten.

**F3: Wo finde ich zusätzliche Dokumentation?**  
A3: Siehe die [Aspose.TeX für .NET‑Dokumentation](https://reference.aspose.com/tex/net/) für detaillierte Informationen.

**F4: Wie bekomme ich Community‑Support oder kann Fragen stellen?**  
A4: Besuchen Sie das [Aspose.TeX‑Forum](https://forum.aspose.com/c/tex/47) für Community‑Support und Diskussionen.

**F5: Gibt es Beispielprojekte?**  
A5: Durchstöbern Sie das Aspose.TeX‑GitHub‑Repository für Beispielprojekte und Code‑Snippets.

## Fazit

Wenn Sie die obigen Schritte befolgt haben, wissen Sie jetzt, **wie man TeX‑Job‑XPS‑Ausgabe** mit Aspose.TeX für .NET erstellt, Ihre Eingabe‑ und Ausgabeverzeichnisse verwaltet und den Prozess sowohl für Entwicklungs‑ als auch für Produktionsszenarien feinjustiert. Experimentieren Sie gern mit anderen Ausgabegeräten, integrieren Sie diese Logik in größere Workflows oder automatisieren Sie Batch‑Konvertierungen.

---

**Zuletzt aktualisiert:** 2025‑12‑20  
**Getestet mit:** Aspose.TeX 24.11 für .NET (zum Zeitpunkt der Erstellung)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}