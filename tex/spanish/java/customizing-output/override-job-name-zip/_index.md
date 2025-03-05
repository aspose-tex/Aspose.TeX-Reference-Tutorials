---
title: Anular el nombre del trabajo y escribir la salida del terminal en Zip en Java
linktitle: Anular el nombre del trabajo y escribir la salida del terminal en Zip en Java
second_title: API de Java Aspose.TeX
description: Aprenda a anular los nombres de los trabajos y escribir la salida del terminal en ZIP en Java con Aspose.TeX. Un tutorial completo para desarrolladores de Java.
type: docs
weight: 11
url: /es/java/customizing-output/override-job-name-zip/
---
## Introducción

En el mundo del desarrollo de Java, Aspose.TeX se destaca como una poderosa herramienta para manejar formatos de archivos TeX. En este tutorial, profundizaremos en un escenario específico: anular nombres de trabajos y escribir la salida del terminal en un archivo zip. Esta guía paso a paso lo guiará a través del proceso de uso de Aspose.TeX para Java.

## Requisitos previos

Antes de embarcarnos en este tutorial, asegúrese de tener implementados los siguientes requisitos previos:
- Conocimientos básicos de programación Java.
-  Aspose.TeX instalado para Java. Si no, puedes descargarlo desde[Aspose sitio web](https://releases.aspose.com/tex/java/).
- Comprensión de cómo configurar un entorno de desarrollo Java.

## Importar paquetes

Comience importando los paquetes necesarios a su proyecto Java. Esto garantiza que tenga acceso a las funcionalidades de Aspose.TeX necesarias para la tarea.

```java
package com.aspose.tex.OverridenJobNameAndTerminalOutputWrittenToZip;

import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.io.OutputStream;

import com.aspose.tex.InputZipDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.OutputZipDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.PdfDevice;
import com.aspose.tex.rendering.PdfSaveOptions;

import util.Utils;
```

## Paso 1: abrir archivos ZIP

En primer lugar, abra una secuencia en el archivo ZIP que servirá como directorio de trabajo de entrada. Este es el archivo desde el cual se procesarán sus datos.

```java
// Abrir una secuencia en el archivo ZIP de entrada
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
```

## Paso 2: Abra el archivo ZIP de salida

A continuación, abra una secuencia en un archivo ZIP que servirá como directorio de trabajo de salida. Aquí es donde se escribirá la salida del terminal.

```java
// Abra una secuencia en el archivo ZIP de salida
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "terminal-out-to-zip.zip");
```

## Paso 3: configurar las opciones de conversión

Cree opciones de conversión para el formato ObjectTeX predeterminado en la extensión del motor ObjectTeX. Especifique un nombre de trabajo y directorios de trabajo de archivos ZIP tanto para entrada como para salida.

```java
// Crear opciones TeX para el formato ObjectTeX
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("terminal-output-to-zip");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
```

## Paso 4: especificar la salida del terminal

 Especifique que la salida del terminal debe escribirse en un archivo en el directorio de trabajo de salida. El nombre del archivo será`<job_name>.trm`.

```java
// Especificar la configuración de salida del terminal
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

## Paso 5: Defina las opciones de guardado y ejecute el trabajo

Defina opciones de guardado, como las opciones de guardado de PDF en este caso. Ejecute el trabajo TeX para ejecutar la conversión.

```java
// Definir opciones de guardado y ejecutar el trabajo.
options.setSaveOptions(new PdfSaveOptions());
new TeXJob("hello-world", new PdfDevice(), options).run();
```

## Paso 6: Finalizar el archivo ZIP de salida

Una vez completado el trabajo, finalice el archivo ZIP de salida para garantizar una finalización adecuada.

```java
// Finalizar el archivo ZIP de salida
((OutputZipDirectory) options.getOutputWorkingDirectory()).finish();
```

## Conclusión

¡Felicidades! Ha aprendido con éxito cómo anular los nombres de los trabajos y escribir la salida del terminal en un archivo ZIP en Java usando Aspose.TeX. Esta poderosa funcionalidad agrega flexibilidad y eficiencia a sus proyectos de desarrollo Java.

## Preguntas frecuentes

### P1: ¿Qué es Aspose.TeX?

R1: Aspose.TeX es una biblioteca Java que permite a los desarrolladores trabajar con formatos de archivos TeX, proporcionando funcionalidades avanzadas para el procesamiento de documentos.

### P2: ¿Cómo puedo obtener una licencia temporal para Aspose.TeX?

 R2: Puede obtener una licencia temporal de[este enlace](https://purchase.aspose.com/temporary-license/).

### P3: ¿Dónde puedo encontrar la documentación de Aspose.TeX?

 A3: La documentación está disponible.[aquí](https://reference.aspose.com/tex/java/).

### P4: ¿Existe una versión de prueba gratuita de Aspose.TeX?

 R4: Sí, puedes encontrar la versión de prueba gratuita[aquí](https://releases.aspose.com/).

### P5: ¿Dónde puedo buscar ayuda o hacer preguntas sobre Aspose.TeX?

 A5: Visita el[Foro Aspose.TeX](https://forum.aspose.com/c/tex/47) para apoyo y discusiones.
