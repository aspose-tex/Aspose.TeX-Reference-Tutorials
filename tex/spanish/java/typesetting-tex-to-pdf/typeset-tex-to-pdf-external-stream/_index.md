---
title: Componga texto de TeX a PDF en Java con flujo externo
linktitle: Componga texto de TeX a PDF en Java con flujo externo
second_title: API de Java Aspose.TeX
description: Aprenda a componer texto de TeX a PDF en Java utilizando secuencias externas con Aspose.TeX. Siga nuestra guía paso a paso para una integración perfecta.
type: docs
weight: 10
url: /es/java/typesetting-tex-to-pdf/typeset-tex-to-pdf-external-stream/
---
## Introducción

En el mundo del desarrollo de Java, la creación de archivos PDF a partir de archivos TeX es un requisito común. Aspose.TeX para Java simplifica este proceso y proporciona una solución eficiente para componer TeX en PDF. En este tutorial, lo guiaremos a través de los pasos para convertir TeX a PDF usando transmisiones externas. Al final, comprenderá claramente cómo implementar este proceso sin problemas en sus aplicaciones Java.

## Requisitos previos

Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:

- Aspose.TeX para Java: asegúrese de tener instalada la biblioteca Aspose.TeX para Java. Puedes descargarlo desde el[Documentación de Aspose.TeX para Java](https://reference.aspose.com/tex/java/).

- Directorios de entrada y salida: prepare los directorios de entrada y salida. Puede utilizar el enlace de descarga proporcionado para obtener los archivos necesarios.

## Importar paquetes

Comience importando los paquetes necesarios a su proyecto Java:

```java
package com.aspose.tex.TypesetPdfWrittenToExternalStream;

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

## Paso 1: abrir flujos de entrada y salida

Comience abriendo secuencias para el archivo ZIP de entrada (que actúa como directorio de trabajo de entrada) y el archivo ZIP de salida (que actúa como directorio de trabajo de salida). Asegúrese de reemplazar "Su directorio de entrada" y "Su directorio de salida" con las rutas de su directorio real.

```java
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "typeset-pdf-to-external-stream.zip");
```

## Paso 2: configurar TeXOptions

Cree el objeto TeXOptions y configúrelo según sus requisitos. Configure el nombre del trabajo, el directorio de trabajo de entrada, el directorio de trabajo de salida y otras opciones.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("typeset-pdf-to-external-stream");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
options.setSaveOptions(new PdfSaveOptions());
```

## Paso 3: Componga TeX en PDF

Ahora, abra una secuencia para escribir el PDF de salida en la ubicación deseada. Puede optar por escribirlo en un archivo local o directamente en el archivo ZIP de salida.

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + "file-name.pdf");
try {
    new TeXJob("hello-world", new PdfDevice(stream), options).run();
} finally {
    stream.close();
}
```

## Paso 4: Finalizar el archivo ZIP de salida

Finalice el archivo ZIP de salida para completar el proceso de composición tipográfica.

```java
((OutputZipDirectory)options.getOutputWorkingDirectory()).finish();
```

## Conclusión

¡Felicidades! Ha compuesto correctamente TeX a PDF en Java utilizando secuencias externas con Aspose.TeX. Este tutorial proporciona una base sólida para incorporar la conversión de TeX a PDF en sus aplicaciones Java sin problemas.

## Preguntas frecuentes

### P1: ¿Puedo personalizar el nombre del archivo PDF de salida?

 A1: Sí, puedes modificar el`options.setJobName("typeset-pdf-to-external-stream")` para establecer el nombre del trabajo que desee.

### P2: ¿Cómo soluciono problemas comunes durante la composición tipográfica?

 A2: Visita el[Foro Aspose.TeX](https://forum.aspose.com/c/tex/47) para el apoyo y asistencia de la comunidad.

### P3: ¿Hay una prueba gratuita disponible para Aspose.TeX para Java?

 R3: Sí, puedes acceder a la prueba gratuita[aquí](https://releases.aspose.com/).

### P4: ¿Dónde puedo encontrar documentación y ejemplos adicionales?

 A4: Explore lo completo[Documentación de Aspose.TeX](https://reference.aspose.com/tex/java/) para obtener información detallada.

### P5: ¿Puedo obtener una licencia temporal para Aspose.TeX?

 R5: Sí, puedes solicitar una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).