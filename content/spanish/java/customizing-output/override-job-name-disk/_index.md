---
title: Anular el nombre del trabajo y escribir la salida del terminal en Java
linktitle: Anular el nombre del trabajo y escribir la salida del terminal en Java
second_title: API de Java Aspose.TeX
description: Explore la guía paso a paso sobre cómo anular nombres de trabajos y escribir resultados de terminal usando Aspose.TeX para Java. Mejore el procesamiento de sus documentos con potentes opciones de personalización.
type: docs
weight: 10
url: /es/java/customizing-output/override-job-name-disk/
---
## Introducción

Aspose.TeX para Java proporciona potentes funciones para trabajar con archivos TeX, lo que permite a los desarrolladores manipular y personalizar el procesamiento de documentos TeX. En este tutorial, lo guiaremos a través del proceso de anular el nombre del trabajo y escribir la salida del terminal en el sistema de archivos usando Aspose.TeX en Java.

## Requisitos previos

Antes de sumergirnos en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:

- Un conocimiento práctico de la programación Java.
-  Aspose.TeX para Java instalado. Puedes descargarlo desde el[Documentación Java de Aspose.TeX](https://reference.aspose.com/tex/java/).

## Importar paquetes

Para comenzar, importe los paquetes necesarios a su proyecto Java. En su archivo Java, incluya las siguientes importaciones:

```java
package com.aspose.tex.OverridenJobNameAndTerminalOutputWrittenToDisk;

import java.io.IOException;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

## Anular el nombre del trabajo y escribir la salida del terminal

### Paso 1: crear opciones de conversión

Comience creando opciones de conversión para el formato ObjectTeX predeterminado en la extensión del motor ObjectTeX. Utilice el siguiente fragmento de código:

```java
//ExStart: Anular nombre de trabajo-Escribir salida de terminal a sistema de archivos
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

### Paso 2: especificar el nombre del trabajo y los directorios de trabajo

Especifique un nombre de trabajo, un directorio de trabajo de entrada y un directorio de trabajo de salida. Si no se especifica el nombre del trabajo, el primer argumento del constructor TeXJob se tomará como nombre del trabajo. Utilice el siguiente fragmento de código:

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### Paso 3: escribir la salida del terminal en el sistema de archivos

 Especifique que la salida del terminal debe escribirse en un archivo en el directorio de trabajo de salida. El nombre del archivo será`<job_name>.trm`. Agregue el siguiente código:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### Paso 4: ejecutar el trabajo

Ejecute el trabajo TeX usando las opciones y el nombre del trabajo especificados. Así es como puedes hacerlo:

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
// ExEnd:OverrideJobName-WriteTerminalOutputToFileSystem
```

¡Felicidades! Ha anulado con éxito el nombre del trabajo y escrito la salida del terminal en el sistema de archivos utilizando Aspose.TeX en Java.

## Conclusión

En este tutorial, exploramos cómo utilizar Aspose.TeX para Java para anular el nombre del trabajo y capturar la salida del terminal. Estas características permiten a los desarrolladores tener un control detallado sobre el procesamiento de documentos TeX, mejorando la personalización y la flexibilidad.

## Preguntas frecuentes

### P1: ¿Puedo usar Aspose.TeX para Java con otras bibliotecas de Java?

R1: Sí, Aspose.TeX para Java está diseñado para integrarse perfectamente con otras bibliotecas de Java para mejorar sus capacidades de procesamiento de documentos.

### P2: ¿Dónde puedo encontrar soporte para Aspose.TeX para Java?

 A2: Visita el[Foro Aspose.TeX](https://forum.aspose.com/c/tex/47) para obtener apoyo y asistencia de la comunidad con cualquier problema que pueda encontrar.

### P3: ¿Hay una prueba gratuita disponible para Aspose.TeX para Java?

 R3: Sí, puede acceder a la versión de prueba gratuita de Aspose.TeX para Java[aquí](https://releases.aspose.com/).

### P4: ¿Cómo puedo obtener una licencia temporal de Aspose.TeX para Java?

 A4: sigue esto[enlace](https://purchase.aspose.com/temporary-license/) obtener una licencia temporal para fines de prueba y evaluación.

### P5: ¿Dónde puedo comprar Aspose.TeX para Java?

 A5: Visita el[pagina de compra](https://purchase.aspose.com/buy) para adquirir una licencia de Aspose.TeX para Java.