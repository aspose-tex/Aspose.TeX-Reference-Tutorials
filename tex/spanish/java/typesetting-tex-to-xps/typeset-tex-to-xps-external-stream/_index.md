---
date: 2025-12-11
description: Aprende a convertir TeX a XPS en Java usando Aspose.TeX. Esta guía paso
  a paso te muestra cómo generar flujos de documentos XPS de manera eficiente.
linktitle: How to Convert TeX to XPS in Java with External Stream
second_title: Aspose.TeX Java API
title: Cómo convertir TeX a XPS en Java con flujo externo
url: /es/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo convertir TeX a XPS en Java con flujo externo

## Introducción

Si necesitas **convertir archivos TeX** a una salida XPS de alta calidad desde una aplicación Java, Aspose.TeX for Java hace el trabajo sencillo. En este tutorial verás exactamente **cómo convertir TeX** a un documento XPS usando un flujo de salida externo, lo cual es ideal cuando deseas canalizar el resultado directamente a una respuesta, a un servicio de almacenamiento en la nube o a cualquier destino personalizado. Repasemos todo el proceso, desde la configuración del entorno hasta la escritura del archivo XPS final.

## Respuestas rápidas
- **¿Qué cubre este tutorial?** Conversión de TeX a XPS usando Aspose.TeX con un flujo externo.  
- **¿Qué biblioteca principal se requiere?** Aspose.TeX for Java.  
- **¿Necesito una licencia?** Se requiere una licencia temporal o completa para uso en producción.  
- **¿Puedo generar flujos de documentos XPS?** Sí – el ejemplo escribe el XPS directamente a un `OutputStream`.  
- **¿Qué versión de Java es compatible?** Cualquier JDK 8+ (el tutorial usa JDK 11 como referencia).

## Requisitos previos

Antes de sumergirte en el código, asegúrate de contar con lo siguiente:

- Java Development Kit (JDK): Asegúrate de que Java esté instalado en tu sistema. Puedes descargarlo [aquí](https://www.oracle.com/java/technologies/javase-downloads.html).

- Aspose.TeX for Java: Descarga e instala Aspose.TeX for Java. Puedes encontrar el enlace de descarga [aquí](https://releases.aspose.com/tex/java/).

## Importar paquetes

Comienza importando los paquetes necesarios para iniciar tu proceso de conversión de TeX a XPS. Incluye el siguiente fragmento de código en tu proyecto Java:

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

## Paso 1: Configurar opciones de conversión

Crea opciones de conversión para el formato predeterminado ObjectTeX usando el siguiente código:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

Esto establece la base para el proceso de composición tipográfica.

## Paso 2: Especificar nombre del trabajo y directorios

Define un nombre de trabajo y establece los directorios de trabajo de entrada y salida:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Asegúrate de reemplazar marcadores como "Your Input Directory" con las rutas reales de tus directorios.

## Paso 3: Configurar salida de terminal

Indica que la salida de la terminal debe escribirse en un archivo dentro del directorio de trabajo de salida:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

Este paso garantiza que se capturen registros detallados para depuración.

## Paso 4: Abrir flujo de salida

Abre un flujo para escribir el documento XPS compuesto:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

Reemplaza "Your Output Directory" con la ruta correspondiente.

## Paso 5: Ejecutar el trabajo

Ejecuta el trabajo de conversión de TeX a XPS:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

Esto completa el proceso, y encontrarás tu documento XPS generado en el directorio de salida especificado.

## Problemas comunes y soluciones

| Problema | Por qué ocurre | Cómo solucionarlo |
|----------|----------------|-------------------|
| **FileNotFoundException** al abrir el flujo | La ruta del directorio de salida es incorrecta o no existe. | Verifica la ruta, crea el directorio con antelación, o usa `Files.createDirectories`. |
| **NullPointerException** en `options.getOutputWorkingDirectory()` | No se llamó a `setOutputWorkingDirectory` o devolvió `null`. | Asegúrate de llamar a `options.setOutputWorkingDirectory` antes de usarlo. |
| **LicenseException** en tiempo de ejecución | Se está ejecutando sin una licencia válida de Aspose.TeX. | Aplica una licencia temporal o permanente usando `License license = new License(); license.setLicense("Aspose.TeX.lic");`. |

## Preguntas frecuentes

**P: ¿Puedo usar Aspose.TeX for Java con otros formatos de documento?**  
R: Aspose.TeX se centra principalmente en el procesamiento de documentos relacionados con TeX. Para otros formatos, explora la amplia gama de productos de Aspose.

**P: ¿Existe una versión de prueba disponible?**  
R: Sí, puedes probar Aspose.TeX descargando la versión de prueba gratuita [aquí](https://releases.aspose.com/).

**P: ¿Dónde puedo encontrar documentación completa?**  
R: Consulta la documentación [aquí](https://reference.aspose.com/tex/java/) para obtener información detallada y ejemplos.

**P: ¿Cómo obtengo soporte o asistencia?**  
R: Visita el foro de Aspose.TeX [aquí](https://forum.aspose.com/c/tex/47) para soporte comunitario y discusiones.

**P: ¿Puedo obtener una licencia temporal para propósitos de prueba?**  
R: Sí, puedes adquirir una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

## Conclusión

¡Felicidades! Acabas de aprender **cómo convertir TeX** a un documento XPS en Java usando Aspose.TeX y un flujo externo. Esta técnica te brinda control total sobre dónde se envía la salida XPS—ya sea al sistema de archivos, a una respuesta web o a un bucket en la nube. Siéntete libre de experimentar con diferentes fuentes TeX, ajustar `TeXOptions` para fuentes personalizadas, o conectar el flujo a una canalización más grande de generación de documentos.

---

**Última actualización:** 2025-12-11  
**Probado con:** Aspose.TeX for Java 24.11 (última versión al momento de escribir)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}