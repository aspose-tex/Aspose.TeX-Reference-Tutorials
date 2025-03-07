---
title: Renderice figuras de LaTeX a SVG con Aspose.TeX (C#)
linktitle: Renderice figuras de LaTeX a SVG con Aspose.TeX (C#)
second_title: API Aspose.TeX .NET
description: Mejore la representación de documentos en .NET con Aspose.TeX. Aprenda a renderizar figuras de LaTeX a SVG en C# para una integración perfecta de expresiones matemáticas.
weight: 11
url: /es/net/render-latex-figures/svg-latex-figure-renderer-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Renderice figuras de LaTeX a SVG con Aspose.TeX (C#)

## Introducción

Si está buscando mejorar sus capacidades de representación de documentos en .NET utilizando figuras LaTeX, Aspose.TeX es su solución preferida. En esta guía paso a paso, lo guiaremos a través de la representación de figuras LaTeX a SVG usando Aspose.TeX en C#. Al final de este tutorial, comprenderá claramente el proceso, lo que le permitirá incorporar sin problemas expresiones y cifras matemáticas de alta calidad en sus documentos.

## Requisitos previos

Antes de sumergirnos en el tutorial, asegúrese de tener implementados los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#.
-  Aspose.TeX para la biblioteca .NET instalada. Puedes descargarlo[aquí](https://releases.aspose.com/tex/net/).

## Importar espacios de nombres

En su código C#, asegúrese de importar los espacios de nombres necesarios:

```csharp
using Aspose.TeX.Features;
```

Ahora, dividamos el tutorial en varios pasos:

## Paso 1: crear opciones de renderizado

```csharp
FigureRendererOptions options = new SvgFigureRendererOptions();
options.Preamble = "\\usepackage{pict2e}";
options.Scale = 3000;
options.BackgroundColor = Color.White;
options.LogStream = new System.IO.MemoryStream();
options.ShowTerminal = true;
```

Aquí, configuramos las opciones de representación, especificando el preámbulo, el factor de escala, el color de fondo, el flujo de registro y si se muestra la salida del terminal.

## Paso 2: definir dimensiones y flujo de salida

```csharp
SizeF size = new SizeF();
using (Stream stream = File.Open(Path.Combine("Your Output Directory", "text-and-formula.svg"), FileMode.Create))
{
    // Ejecute el renderizado.
    new SvgFigureRenderer().Render("Your LaTeX Code", stream, options, out size);
}
```

Reemplace "Su directorio de salida" con el directorio que desee y proporcione su código LaTeX como una cadena.

## Paso 3: Mostrar resultados

```csharp
Console.Out.WriteLine(options.ErrorReport);
Console.Out.WriteLine();
Console.Out.WriteLine("Size: " + size);
```

Este paso muestra los informes de error y el tamaño de la imagen resultante.

## Conclusión

¡Felicidades! Ha aprendido con éxito cómo renderizar figuras de LaTeX a SVG usando Aspose.TeX en C#. Ahora puede integrar sin problemas expresiones y figuras matemáticas en sus aplicaciones .NET.

## Preguntas frecuentes

### P1: ¿Aspose.TeX es de uso gratuito?

 R1: Aspose.TeX ofrece una prueba gratuita. Puedes acceder a él[aquí](https://releases.aspose.com/).

### P2: ¿Dónde puedo encontrar la documentación de Aspose.TeX?

 A2: consulte la documentación[aquí](https://reference.aspose.com/tex/net/).

### P3: ¿Cómo obtengo soporte para Aspose.TeX?

 A3: Visita el foro de soporte[aquí](https://forum.aspose.com/c/tex/47).

### P4: ¿Puedo comprar Aspose.TeX?

 R4: Sí, puedes comprar Aspose.TeX[aquí](https://purchase.aspose.com/buy).

### P5: ¿Necesito una licencia temporal?

 R5: Si es necesario, puede obtener una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
