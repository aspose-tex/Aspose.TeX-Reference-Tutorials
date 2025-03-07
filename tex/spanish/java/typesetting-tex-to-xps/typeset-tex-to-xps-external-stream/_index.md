---
title: Componga TeX a XPS en Java con transmisión externa
linktitle: Componga TeX a XPS en Java con transmisión externa
second_title: API de Java Aspose.TeX
description: Aprenda a componer TeX a XPS en Java usando Aspose.TeX. Explore la guía paso a paso para un procesamiento de documentos fluido.
weight: 10
url: /es/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Componga TeX a XPS en Java con transmisión externa

## Introducción

En el mundo del desarrollo de Java, Aspose.TeX se destaca como una poderosa herramienta para componer documentos TeX en varios formatos, incluido XPS. Si busca mejorar las capacidades de procesamiento de documentos de su aplicación Java, este tutorial está diseñado para usted. En esta guía paso a paso, lo guiaremos a través del proceso de composición tipográfica de TeX a XPS usando Aspose.TeX para Java con una transmisión externa.

## Requisitos previos

Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:

-  Kit de desarrollo de Java (JDK): asegúrese de tener Java instalado en su sistema. Puedes descargarlo desde[aquí](https://www.oracle.com/java/technologies/javase-downloads.html).

-  Aspose.TeX para Java: descargue e instale Aspose.TeX para Java. Puedes encontrar el enlace de descarga.[aquí](https://releases.aspose.com/tex/java/).

## Importar paquetes

Comience importando los paquetes necesarios para iniciar su viaje de conversión de TeX a XPS. Incluya el siguiente fragmento de código en su proyecto Java:

```java
package com.aspose.tex.TypesetXpsWrittenToExternalStream;

import java.io.FileOutputStream;
import java.io.IOException;
import java.io.OutputStream;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

## Paso 1: configurar las opciones de conversión

Comience creando opciones de conversión para el formato ObjectTeX predeterminado usando el siguiente código:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

Esto sienta las bases para el proceso de composición tipográfica.

## Paso 2: especificar el nombre del trabajo y los directorios

Defina un nombre de trabajo y configure los directorios de trabajo de entrada y salida:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Asegúrese de reemplazar marcadores de posición como "Su directorio de entrada" con las rutas de directorio reales.

## Paso 3: configurar la salida del terminal

Especifique que la salida del terminal debe escribirse en un archivo en el directorio de trabajo de salida:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

Este paso garantiza que se capturen registros detallados para la depuración.

## Paso 4: abrir flujo de salida

Abra una secuencia para escribir el documento XPS tipográfico:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

Reemplace "Su directorio de salida" con la ruta adecuada.

## Paso 5: ejecutar el trabajo

Ejecute el trabajo de conversión de TeX a XPS:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

Esto completa el proceso y encontrará su documento XPS tipográfico en el directorio de salida especificado.

## Conclusión

¡Felicidades! Ha compuesto correctamente TeX a XPS en Java utilizando Aspose.TeX. Esto abre un mundo de posibilidades para el procesamiento de documentos en sus aplicaciones Java. Experimente con diferentes archivos TeX y explore las diversas funciones que ofrece Aspose.TeX.

## Preguntas frecuentes

### P1: ¿Puedo usar Aspose.TeX para Java con otros formatos de documentos?

R1: Aspose.TeX se centra principalmente en el procesamiento de documentos relacionados con TeX. Para otros formatos, explore la amplia gama de productos de Aspose.

### P2: ¿Hay una versión de prueba disponible?

 R2: Sí, puedes experimentar Aspose.TeX descargando la versión de prueba gratuita[aquí](https://releases.aspose.com/).

### P3: ¿Dónde puedo encontrar documentación completa?

 A3: consulte la documentación[aquí](https://reference.aspose.com/tex/java/) para obtener información detallada y ejemplos.

### P4: ¿Cómo obtengo apoyo o busco asistencia?

 R4: Visite el foro Aspose.TeX[aquí](https://forum.aspose.com/c/tex/47)para apoyo y debates de la comunidad.

### P5: ¿Puedo obtener una licencia temporal para realizar pruebas?

 R5: Sí, puedes adquirir una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
