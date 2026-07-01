---
date: 2026-02-20
description: Aprende cómo convertir TeX a XPS en Java usando Aspose.TeX. Esta guía
  paso a paso te muestra cómo convertir archivos TeX y generar flujos de documentos
  XPS de manera eficiente.
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

Si necesita **convertir TeX** archivos a una salida XPS de alta calidad desde una aplicación Java, Aspose.TeX for Java hace el trabajo sencillo. En este tutorial verá exactamente **cómo convertir TeX** a un documento XPS usando un flujo de salida externo, lo cual es ideal cuando desea canalizar el resultado directamente a una respuesta, a un servicio de almacenamiento en la nube o a cualquier destino personalizado. Recorramos todo el proceso, desde la configuración del entorno hasta la escritura del archivo XPS final.

## Respuestas rápidas
- **¿Qué cubre este tutorial?** Conversión de TeX a XPS usando Aspose.TeX con un flujo externo.  
- **¿Qué biblioteca principal se requiere?** Aspose.TeX for Java.  
- **¿Necesito una licencia?** Se requiere una licencia temporal o completa para uso en producción.  
- **¿Puedo generar flujos de documentos XPS?** Sí – el ejemplo escribe el XPS directamente a un `OutputStream`.  
- **¿Qué versión de Java es compatible?** Cualquier JDK 8+ (el tutorial usa JDK 11 como referencia).

## Cómo convertir TeX a XPS usando un flujo externo

Esta sección repite la palabra clave principal en un encabezado dedicado, facilitando a los lectores y a los motores de IA localizar la solución exacta.

## Requisitos previos

Antes de sumergirse en el código, asegúrese de tener lo siguiente:

- Java Development Kit (JDK): Asegúrese de que Java esté instalado en su sistema. Puede descargarlo [aquí](https://www.oracle.com/java/technologies/javase-downloads.html).

- Aspose.TeX for Java: Descargue e instale Aspose.TeX for Java. Puede encontrar el enlace de descarga [aquí](https://releases.aspose.com/tex/java/).

## Importar paquetes

Comience importando los paquetes necesarios para iniciar su proceso de conversión de TeX a XPS. Incluya el siguiente fragmento de código en su proyecto Java:

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

Comience creando opciones de conversión para el formato ObjectTeX predeterminado usando el siguiente código:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

## Paso 2: Especificar nombre del trabajo y directorios

Defina un nombre de trabajo y establezca los directorios de trabajo de entrada y salida:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Asegúrese de reemplazar marcadores de posición como "Your Input Directory" con sus rutas de directorio reales.

## Paso 3: Configurar salida del terminal

Especifique que la salida del terminal debe escribirse en un archivo en el directorio de trabajo de salida:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

Este paso garantiza que se capturen registros detallados para depuración.

## Paso 4: Abrir flujo de salida

Abra un flujo para escribir el documento XPS maquetado:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

Reemplace "Your Output Directory" con la ruta adecuada.

## Paso 5: Ejecutar el trabajo

Ejecute el trabajo de conversión de TeX a XPS:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

Esto completa el proceso, y encontrará su documento XPS generado en el directorio de salida especificado.

## Por qué es importante

Usar un `OutputStream` externo le brinda control total sobre dónde van los datos XPS—ya sea enviándolos directamente a un cliente web, almacenándolos en la nube o encadenándolos a otra canalización de procesamiento. Elimina la necesidad de archivos intermedios y reduce la sobrecarga de E/S, lo cual es especialmente valioso en entornos de alto rendimiento o sin servidor.

## Problemas comunes y soluciones

| Problema | Por qué ocurre | Cómo solucionarlo |
|----------|----------------|-------------------|
| **FileNotFoundException** al abrir el flujo | La ruta del directorio de salida es incorrecta o no existe. | Verifique la ruta, cree el directorio previamente, o use `Files.createDirectories`. |
| **NullPointerException** en `options.getOutputWorkingDirectory()` | `setOutputWorkingDirectory` no se llamó o devolvió `null`. | Asegúrese de llamar a `options.setOutputWorkingDirectory` antes de usarlo. |
| **LicenseException** en tiempo de ejecución | Ejecutándose sin una licencia válida de Aspose.TeX. | Aplique una licencia temporal o permanente usando `License license = new License(); license.setLicense("Aspose.TeX.lic");`. |

## Preguntas frecuentes

**P: ¿Puedo usar Aspose.TeX for Java con otros formatos de documento?**  
R: Aspose.TeX se centra principalmente en el procesamiento de documentos relacionados con TeX. Para otros formatos, explore la amplia gama de productos de Aspose.

**P: ¿Hay una versión de prueba disponible?**  
R: Sí, puede probar Aspose.TeX descargando la versión de prueba gratuita [aquí](https://releases.aspose.com/).

**P: ¿Dónde puedo encontrar documentación completa?**  
R: Consulte la documentación [aquí](https://reference.aspose.com/tex/java/) para información detallada y ejemplos.

**P: ¿Cómo obtengo soporte o asistencia?**  
R: Visite el foro de Aspose.TeX [aquí](https://forum.aspose.com/c/tex/47) para soporte comunitario y discusiones.

**P: ¿Puedo obtener una licencia temporal para propósitos de prueba?**  
R: Sí, puede adquirir una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

## Conclusión

¡Felicidades! Acaba de aprender **cómo convertir TeX** a un documento XPS en Java usando Aspose.TeX y un flujo externo. Esta técnica le brinda control total sobre dónde se envía la salida XPS—ya sea al sistema de archivos, a una respuesta web o a un bucket en la nube. Siéntase libre de experimentar con diferentes fuentes TeX, ajustar `TeXOptions` para fuentes personalizadas, o conectar el flujo a una canalización de generación de documentos más grande.

---

**Última actualización:** 2026-02-20  
**Probado con:** Aspose.TeX for Java 24.11 (última versión al momento de escribir)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}