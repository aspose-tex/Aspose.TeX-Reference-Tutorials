---
title: Anular el nombre del trabajo y escribir la salida del terminal en el disco (C#)
linktitle: Anular el nombre del trabajo y escribir la salida del terminal en el disco (C#)
second_title: API Aspose.TeX .NET
description: Explore cómo usar Aspose.TeX para .NET para anular los nombres de los trabajos y capturar la salida del terminal. Siga nuestra guía completa para una gestión perfecta de archivos TeX.
type: docs
weight: 10
url: /es/net/job-output/override-job-name-disk-output-csharp/
---
## Introducción

Bienvenido a esta guía paso a paso sobre el uso de Aspose.TeX para .NET para anular nombres de trabajos y escribir la salida del terminal en el disco en el lenguaje de programación C#. Aspose.TeX para .NET es una biblioteca poderosa que le permite trabajar sin problemas con archivos TeX y en este tutorial nos centraremos en una tarea específica: anular los nombres de los trabajos y capturar la salida del terminal.

## Requisitos previos

Antes de sumergirnos en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:

-  Biblioteca Aspose.TeX para .NET: asegúrese de tener instalada la biblioteca Aspose.TeX para .NET. Puedes descargarlo desde el[Sitio web de Aspose.TeX](https://releases.aspose.com/tex/net/).

- Entorno de desarrollo .NET: tenga un entorno de desarrollo .NET que funcione, incluido un entorno de desarrollo integrado (IDE) como Visual Studio.

- Conocimientos básicos de C#: familiarícese con los conceptos básicos del lenguaje de programación C#.

- Directorios de entrada y salida: prepare los directorios de entrada y salida para sus archivos TeX.

## Importar espacios de nombres

En su código C#, asegúrese de incluir los espacios de nombres necesarios para acceder a las funcionalidades de Aspose.TeX:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

## Paso 1: crear opciones de conversión

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

Cree TeXOptions con ConsoleAppOptions, especificando ObjectTeX como TeXConfig.

## Paso 2: especificar el nombre del trabajo

```csharp
options.JobName = "overridden-job-name";
```

Especifique el nombre del trabajo para anular el nombre predeterminado.

## Paso 3: especificar el directorio de trabajo de entrada

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

Configure el directorio de trabajo de entrada para sus archivos TeX.

## Paso 4: especificar el directorio de trabajo de salida

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Defina el directorio de trabajo de salida para guardar los archivos TeX procesados.

## Paso 5: escribir la salida del terminal en el disco

```csharp
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

Configure la salida del terminal para que se escriba en un archivo en el directorio de salida.

## Paso 6: ejecutar el trabajo

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

Cree un TeXJob, especificando un nombre de trabajo, un dispositivo de salida (XpsDevice) y opciones. Finalmente, ejecute el trabajo.

## Conclusión

¡Felicidades! Ha aprendido con éxito cómo anular los nombres de los trabajos y escribir la salida del terminal en el disco usando Aspose.TeX para .NET en C#. Esta capacidad es valiosa para administrar sus tareas de procesamiento TeX de manera eficiente.

## Preguntas frecuentes

### P1: ¿Puedo usar Aspose.TeX para .NET con otras bibliotecas .NET?

R1: Sí, Aspose.TeX para .NET se puede integrar perfectamente con otras bibliotecas .NET.

### P2: ¿Hay una prueba gratuita disponible para Aspose.TeX para .NET?

 R2: Sí, puedes descargar una versión de prueba gratuita[aquí](https://releases.aspose.com/).

### P3: ¿Cómo puedo obtener soporte para Aspose.TeX para .NET?

 A3: Visita el[Foro Aspose.TeX](https://forum.aspose.com/c/tex/47) para conseguir comunidad y apoyo.

### P4: ¿Hay licencias temporales disponibles para Aspose.TeX para .NET?

 R4: Sí, puedes obtener una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).

### P5: ¿Dónde puedo encontrar la documentación de Aspose.TeX para .NET?

 A5: La documentación está disponible.[aquí](https://reference.aspose.com/tex/net/).