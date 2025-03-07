---
title: Anular el nombre del trabajo y escribir la salida del terminal en Zip (C#)
linktitle: Anular el nombre del trabajo y escribir la salida del terminal en Zip (C#)
second_title: API Aspose.TeX .NET
description: Aprenda a anular los nombres de los trabajos y escribir la salida del terminal en un archivo ZIP usando Aspose.TeX para .NET. Guía paso a paso con ejemplos de C#.
weight: 11
url: /es/net/job-output/override-job-name-zip-output-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Anular el nombre del trabajo y escribir la salida del terminal en Zip (C#)

## Introducción

En este tutorial, exploraremos cómo anular el nombre del trabajo y escribir la salida del terminal en un archivo ZIP usando Aspose.TeX para .NET. Aspose.TeX es una poderosa biblioteca que permite a los desarrolladores trabajar con documentos TeX en sus aplicaciones .NET. En este ejemplo particular, nos centraremos en una tarea común: escribir la salida del terminal en un archivo ZIP con la capacidad de anular el nombre del trabajo.

## Requisitos previos

Antes de comenzar, asegúrese de contar con los siguientes requisitos previos:

- Un conocimiento práctico de C#
- Aspose.TeX para .NET instalado
- Ingrese el archivo ZIP para el directorio de trabajo
- Archivo ZIP de salida para salida de terminal

## Importar espacios de nombres

Antes de profundizar en el código, asegúrese de incluir los espacios de nombres necesarios en su proyecto C#:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Pdf;
using System.IO;
```

Ahora, dividamos el ejemplo en varios pasos para guiarlo a través del proceso.

## Paso 1: abrir secuencias ZIP de entrada y salida

```csharp
using (Stream inZipStream = File.Open(Path.Combine("Your Input Directory", "zip-in.zip"), FileMode.Open))
using (Stream outZipStream = File.Open(Path.Combine("Your Output Directory", "terminal-out-to-zip.zip"), FileMode.Create))
{
    // El código para el paso 1 va aquí.
}
```

## Paso 2: configurar las opciones de conversión

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
options.JobName = "terminal-output-to-zip";
options.InputWorkingDirectory = new InputZipDirectory(inZipStream, "in");
options.OutputWorkingDirectory = new OutputZipDirectory(outZipStream);
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## Paso 3: definir opciones de ahorro

```csharp
options.SaveOptions = new PdfSaveOptions();
```

## Paso 4: ejecute el trabajo TeX

```csharp
new TeXJob("hello-world", new PdfDevice(), options).Run();
```

## Paso 5: Finalizar el archivo ZIP de salida

```csharp
((OutputZipDirectory)options.OutputWorkingDirectory).Finish();
```

## Conclusión

¡Felicidades! Ha aprendido con éxito cómo anular el nombre del trabajo y escribir la salida del terminal en un archivo ZIP usando Aspose.TeX para .NET. Esta técnica puede resultar increíblemente útil cuando se trata de documentos TeX en sus aplicaciones C#.

## Preguntas frecuentes

### P1: ¿Puedo usar Aspose.TeX para .NET con otros lenguajes .NET como VB.NET?

R1: Sí, Aspose.TeX para .NET es compatible con todos los lenguajes .NET.

### P2: ¿Dónde puedo encontrar más documentación sobre Aspose.TeX para .NET?

 A2: Visita el[documentación](https://reference.aspose.com/tex/net/) para obtener información detallada.

### P3: ¿Cómo puedo obtener una licencia temporal para Aspose.TeX?

 A3: Obtener un[licencia temporal](https://purchase.aspose.com/temporary-license/) con fines de prueba.

### P4: ¿Existe un foro comunitario para soporte de Aspose.TeX?

 A4: Sí, únete al[Foro Aspose.TeX](https://forum.aspose.com/c/tex/47) para el apoyo de la comunidad.

### P5: ¿Dónde puedo comprar Aspose.TeX para .NET?

 R5: Puedes comprar Aspose.TeX[aquí](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
