---
date: 2025-12-20
description: Aprenda a crear salida XPS de trabajos TeX usando Aspose.TeX para .NET,
  gestione la entrada/salida del sistema de archivos y genere documentos XPS de alta
  calidad.
linktitle: Create TeX Job XPS Output with Filesystems – Aspose.TeX for .NET
second_title: Aspose.TeX .NET API
title: Crear salida XPS de trabajo TeX con sistemas de archivos – Aspose.TeX para
  .NET
url: /es/net/file-input-output/filesystem-input-xps-output/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear salida XPS de trabajo TeX con sistemas de archivos – Aspose.TeX para .NET

## Introducción

¡Bienvenido! En este tutorial aprenderá **cómo crear salida XPS de trabajo TeX** mientras trabaja con entrada y salida de sistemas de archivos usando Aspose.TeX para .NET. Ya sea que esté construyendo un procesador por lotes, un servicio web o una utilidad de escritorio, los pasos a continuación le guiarán para configurar el motor, apuntarlo a sus archivos y producir documentos XPS que se vean exactamente como el código fuente LaTeX original.

Dividiremos el proceso en pasos claros y numerados, explicaremos el “por qué” detrás de cada línea de código y le daremos consejos prácticos que podrá aplicar de inmediato.

## Respuestas rápidas
- **¿Qué significa “create tex job xps”?** Se refiere a configurar un trabajo Aspose.TeX que lee archivos TeX y escribe el resultado como un documento XPS.  
- **¿Necesito una licencia?** Hay una licencia temporal disponible para pruebas; se requiere una licencia completa para producción.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **¿Puedo cambiar el formato de salida?** Sí – reemplace `XpsDevice` con otro dispositivo (PDF, PNG, etc.).  
- **¿Se requiere salida de consola?** No – puede usar un terminal de memoria para una ejecución silenciosa.

## ¿Qué es “create tex job xps”?

Crear un trabajo TeX que genere XPS significa inicializar el motor Aspose.TeX, indicarle dónde leer los archivos fuente y dirigir las páginas renderizadas a un paquete XPS. XPS (XML Paper Specification) es un formato de diseño fijo que preserva la tipografía y los gráficos vectoriales, lo que lo hace ideal para impresión o conversiones posteriores.

## ¿Por qué usar Aspose.TeX para salida XPS?

- **Alta fidelidad:** El motor reproduce el diseño LaTeX con precisión en XPS.  
- **Sin dependencias externas:** Biblioteca .NET pura, sin necesidad de instalaciones nativas de LaTeX.  
- **E/S flexible:** Funciona con directorios de sistemas de archivos, flujos de memoria o proveedores personalizados.  
- **Escalable:** Adecuado para conversiones de un solo archivo o pipelines de procesamiento masivo.

## Requisitos previos

- **Aspose.TeX for .NET** – descargue la última versión desde el [sitio web de Aspose](https://releases.aspose.com/tex/net/).  
- **Entorno de desarrollo .NET** – Visual Studio, Rider o VS Code con el SDK de .NET.  
- **Carpetas de entrada y salida** – cree dos directorios en su máquina (p. ej., `C:\TeX\Input` y `C:\TeX\Output`).  
- **Licencia (opcional para pruebas)** – puede obtener una licencia temporal desde el portal de Aspose.

## Importar espacios de nombres

Primero, importe los espacios de nombres requeridos para que pueda acceder a los auxiliares del sistema de archivos y al dispositivo XPS.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

Estos espacios de nombres exponen `InputFileSystemDirectory`, `OutputFileSystemDirectory` y `XpsDevice`, que son esenciales para el flujo de trabajo **create tex job xps**.

## Paso 1: Crear opciones de conversión

Comenzamos creando un objeto `TeXOptions` que indica al motor usar la configuración ObjectTeX (la predeterminada para la mayoría de fuentes LaTeX).

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

> **Consejo profesional:** `ConsoleAppOptions` establece valores predeterminados sensatos para aplicaciones de tipo consola, pero puede personalizar las opciones más adelante si es necesario.

## Paso 2: Especificar directorios de entrada y salida

Apunte el motor a las carpetas que preparó anteriormente. Reemplace las cadenas de marcador de posición con las rutas reales en su máquina.

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Ahora el trabajo TeX sabe dónde encontrar archivos `.tex` y dónde colocar los archivos XPS generados.

## Paso 3: Elegir un terminal de salida

El terminal controla dónde se escriben los mensajes de estado. Para una depuración rápida nos quedaremos con la consola, pero puede cambiar a un terminal de memoria para ejecuciones silenciosas.

```csharp
options.TerminalOut = new OutputConsoleTerminal(); // Default value. Arbitrary assignment.
```

> **Por qué es importante:** Usar un terminal de consola le brinda retroalimentación inmediata sobre advertencias o errores de compilación, lo que acelera la solución de problemas.

## Paso 4: Ejecutar el trabajo TeX

Cree una instancia de `TeXJob`, asígnele un nombre amigable, adjunte el `XpsDevice` y ejecútelo.

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

Cuando `Run()` finalice, encontrará un archivo `hello-world.xps` en el directorio de salida.

## Paso 5: Ajustar la salida de consola

Agregar una línea en blanco después de que el trabajo termine hace que el registro de consola sea más fácil de leer, especialmente cuando ejecuta varios trabajos en lote.

```csharp
options.TerminalOut.Writer.WriteLine();
```

## Problemas comunes y soluciones

| Problema | Causa | Solución |
|----------|-------|----------|
| **El archivo XPS está vacío** | La ruta del directorio de salida es incorrecta o no tiene permisos de escritura. | Verifique la ruta pasada a `OutputFileSystemDirectory` y asegúrese de que el proceso tenga permisos de escritura. |
| **Errores de compilación** | El código fuente LaTeX usa paquetes que no están incluidos en ObjectTeX. | Cambie a una configuración de motor TeX completa (`TeXConfig.FullTeX()`) o añada los archivos de paquetes faltantes al directorio de entrada. |
| **La consola se bloquea** | El terminal espera entrada debido a prompts interactivos. | Use `OutputMemoryTerminal` para suprimir los prompts interactivos en scripts automatizados. |

## Preguntas frecuentes

**P1: ¿Puedo usar un formato de salida diferente en lugar de XPS?**  
R1: Sí, Aspose.TeX admite PDF, PNG, SVG y otros formatos. Reemplace `new XpsDevice()` con la clase de dispositivo apropiada (p. ej., `new PdfDevice()`).

**P2: ¿Está disponible una licencia temporal para propósitos de prueba?**  
R2: Sí, puede obtener una licencia temporal para pruebas desde [este enlace](https://purchase.aspose.com/temporary-license/).

**P3: ¿Dónde puedo encontrar documentación adicional?**  
R3: Consulte la [documentación de Aspose.TeX para .NET](https://reference.aspose.com/tex/net/) para información detallada.

**P4: ¿Cómo puedo obtener soporte de la comunidad o hacer preguntas?**  
R4: Visite el [foro de Aspose.TeX](https://forum.aspose.com/c/tex/47) para soporte comunitario y discusiones.

**P5: ¿Hay proyectos de ejemplo disponibles?**  
R5: Explore el repositorio de Aspose.TeX en GitHub para proyectos de ejemplo y fragmentos de código.

## Conclusión

Al seguir los pasos anteriores, ahora sabe cómo **crear salida XPS de trabajo TeX** usando Aspose.TeX para .NET, gestionar sus carpetas de entrada y salida, y ajustar el proceso tanto para escenarios de desarrollo como de producción. Siéntase libre de experimentar con otros dispositivos de salida, integrar esta lógica en flujos de trabajo más grandes o automatizar conversiones por lotes.

---

**Última actualización:** 2025-12-20  
**Probado con:** Aspose.TeX 24.11 para .NET (última versión al momento de escribir)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}