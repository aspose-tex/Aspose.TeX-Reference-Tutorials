---
title: Renderujte obrázky z LaTeXu do SVG pomocí Aspose.TeX (C#)
linktitle: Renderujte obrázky z LaTeXu do SVG pomocí Aspose.TeX (C#)
second_title: Aspose.TeX .NET API
description: Vylepšete vykreslování dokumentů v .NET pomocí Aspose.TeX. Naučte se vykreslovat obrázky z LaTeXu do SVG v C# pro bezproblémovou integraci matematických výrazů.
weight: 11
url: /cs/net/render-latex-figures/svg-latex-figure-renderer-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Renderujte obrázky z LaTeXu do SVG pomocí Aspose.TeX (C#)

## Úvod

Pokud chcete vylepšit své možnosti vykreslování dokumentů v .NET pomocí obrázků LaTeX, Aspose.TeX je vaším řešením. V tomto podrobném průvodci vás provedeme vykreslováním obrázků z LaTeXu do SVG pomocí Aspose.TeX v C#. Na konci tohoto výukového programu budete mít jasnou představu o procesu, který vám umožní bezproblémově začlenit vysoce kvalitní matematické výrazy a čísla do vašich dokumentů.

## Předpoklady

Než se pustíme do výukového programu, ujistěte se, že máte splněny následující předpoklady:

- Základní znalost programovacího jazyka C#.
-  Nainstalovaná knihovna Aspose.TeX for .NET. Můžete si jej stáhnout[tady](https://releases.aspose.com/tex/net/).

## Importovat jmenné prostory

V kódu C# nezapomeňte importovat potřebné jmenné prostory:

```csharp
using Aspose.TeX.Features;
```

Nyní si tutoriál rozdělíme do několika kroků:

## Krok 1: Vytvořte možnosti vykreslování

```csharp
FigureRendererOptions options = new SvgFigureRendererOptions();
options.Preamble = "\\usepackage{pict2e}";
options.Scale = 3000;
options.BackgroundColor = Color.White;
options.LogStream = new System.IO.MemoryStream();
options.ShowTerminal = true;
```

Zde nastavíme možnosti vykreslování, určíme preambuli, faktor měřítka, barvu pozadí, tok protokolu a zda se má zobrazit výstup terminálu.

## Krok 2: Definujte rozměry a výstupní proud

```csharp
SizeF size = new SizeF();
using (Stream stream = File.Open(Path.Combine("Your Output Directory", "text-and-formula.svg"), FileMode.Create))
{
    // Spusťte vykreslování.
    new SvgFigureRenderer().Render("Your LaTeX Code", stream, options, out size);
}
```

Nahraďte "Váš výstupní adresář" požadovaným adresářem a zadejte svůj kód LaTeXu jako řetězec.

## Krok 3: Zobrazení výsledků

```csharp
Console.Out.WriteLine(options.ErrorReport);
Console.Out.WriteLine();
Console.Out.WriteLine("Size: " + size);
```

Tento krok zobrazí chybová hlášení a velikost výsledného obrázku.

## Závěr

Gratulujeme! Úspěšně jste se naučili vykreslovat obrázky z LaTeXu do SVG pomocí Aspose.TeX v C#. Nyní můžete bez problémů integrovat matematické výrazy a čísla do svých aplikací .NET.

## FAQ

### Q1: Je Aspose.TeX zdarma k použití?

 A1: Aspose.TeX nabízí bezplatnou zkušební verzi. Můžete k němu přistupovat[tady](https://releases.aspose.com/).

### Q2: Kde najdu dokumentaci Aspose.TeX?

 A2: Viz dokumentace[tady](https://reference.aspose.com/tex/net/).

### Q3: Jak získám podporu pro Aspose.TeX?

 A3: Navštivte fórum podpory[tady](https://forum.aspose.com/c/tex/47).

### Q4: Mohu si koupit Aspose.TeX?

 A4: Ano, můžete si zakoupit Aspose.TeX[tady](https://purchase.aspose.com/buy).

### Q5: Potřebuji dočasnou licenci?

 A5: V případě potřeby můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
