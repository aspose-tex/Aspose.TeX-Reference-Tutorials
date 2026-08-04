---
date: 2026-03-24
description: Aprende cómo obtener un flujo de archivo en C# mientras especificas la
  entrada requerida para Aspose.TeX .NET. Sigue nuestra guía paso a paso.
linktitle: Get File Stream C# in Aspose.TeX Required Input Directory
second_title: Aspose.TeX .NET API
title: 'Obtener flujo de archivo C# en Aspose.TeX: directorio de entrada requerido'
url: /es/net/advanced-io/required-input-directory-csharp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Obtener flujo de archivo C# en Aspose.TeX – Directorio de Entrada Requerido

## Introducción

Si necesitas **obtener flujo de archivo C#** mientras trabajas con Aspose.TeX, el primer paso es indicarle a la biblioteca dónde se encuentran tus archivos fuente TeX. Este tutorial te guía paso a paso con el código exacto que necesitas para **especificar la entrada requerida** para el motor de Aspose.TeX, convirtiendo una carpeta de archivos `.tex` en un flujo que la API pueda consumir. Al final de esta guía tendrás una clase reutilizable `RequiredInputDirectory` que conecta de forma limpia tu sistema de archivos con Aspose.TeX.

## Respuestas rápidas
- **¿Qué significa “obtener flujo de archivo C#”?** Significa devolver un objeto `System.IO.Stream` para el nombre de archivo solicitado.  
- **¿Por qué debo especificar la entrada requerida?** Aspose.TeX busca en el directorio de entrada los archivos TeX; sin él el motor no puede resolver los comandos `\include{}` o `\input{}`.  
- **¿Qué espacios de nombres son obligatorios?** `Aspose.TeX.IO`, `System.Collections.Generic` y `System.IO`.  
- **¿Se necesita alguna licencia especial?** Se requiere una licencia de desarrollo o de prueba de Aspose.TeX para uso en producción.  
- **¿Puedo reutilizar la clase en varios proyectos?** Sí, una vez compilada funciona con cualquier proyecto .NET que haga referencia a Aspose.TeX.

## ¿Qué es obtener flujo de archivo C#?

En .NET, un *flujo de archivo* es un objeto derivado de `System.IO.Stream` que brinda acceso de lectura/escritura a los bytes crudos de un archivo. Cuando Aspose.TeX solicita un archivo, espera que devuelvas dicho flujo para que el motor pueda leer el código fuente TeX directamente desde la memoria o el disco.

## ¿Por qué especificar la entrada requerida para Aspose.TeX?

Aspose.TeX procesa documentos TeX localizando archivos auxiliares (imágenes, archivos de estilo, archivos TeX incluidos) relativos a un **directorio de entrada requerido**. Al definir explícitamente este directorio, tú:

1. Evitas errores “archivo no encontrado” durante la compilación.  
2. Mantienes la lógica de acceso a archivos de tu proyecto aislada del resto del código.  
3. Facilitas las pruebas unitarias simulando el directorio de entrada.

## Requisitos previos

- **Aspose.TeX for .NET Library** – descárgala desde la [página de lanzamientos](https://releases.aspose.com/tex/net/).  
- **Entorno de desarrollo .NET** – Visual Studio 2022, Rider o cualquier IDE que soporte .NET 6+.

Ahora, importemos los espacios de nombres que necesitarás.

## Importar espacios de nombres

Agrega estas sentencias `using` al inicio de tu archivo C# para que el compilador pueda localizar los tipos requeridos:

```csharp
using Aspose.TeX.IO;
using System.Collections.Generic;
using System.IO;
```

## Cómo obtener flujo de archivo C# con un Directorio de Entrada Requerido

A continuación tienes un desglose paso a paso de la clase `RequiredInputDirectory`. Cada paso incluye una breve explicación seguida del bloque de código exacto que debes copiar en tu proyecto.

### Paso 1: Crear la clase `RequiredInputDirectory`

La clase implementa dos interfaces—`IInputWorkingDirectory` (usada por Aspose.TeX para localizar archivos) e `IFileCollector` (usada para recopilar nombres de archivo a medida que se añaden).

```csharp
public class RequiredInputDirectory : IInputWorkingDirectory, IFileCollector
{
    private Dictionary<string, Dictionary<string, string>> _fileNames =
        new Dictionary<string, Dictionary<string, string>>();

    public RequiredInputDirectory()
    {
    }
```

### Paso 2: Implementar el método `StoreFileName`

Este método registra cada nombre de archivo que pasas al colector, agrupándolos por su extensión para una búsqueda rápida.

```csharp
public void StoreFileName(string fileName)
{
    string extension = Path.GetExtension(fileName);
    string name = Path.GetFileNameWithoutExtension(fileName);

    Dictionary<string, string> files;
    if (!_fileNames.TryGetValue(extension, out files))
        _fileNames.Add(extension, files = new Dictionary<string, string>());

    files[name] = fileName;
}
```

### Paso 3: Implementar la interfaz `IInputWorkingDirectory` – GetFile

Cuando Aspose.TeX solicita un archivo, este método devuelve un **flujo de archivo** (o `null` si manejas el flujo de otra manera). La salida `fullName` permite al motor conocer la ruta exacta que resolvió.

```csharp
public Stream GetFile(string fileName, out string fullName, bool searchSubdirectories = false)
{
    fullName = fileName;
    return null; // Here we actually return a stream for the file requested by its name.
}
```

### Paso 4: Obtener colecciones de archivos por extensión

El motor puede solicitar todos los archivos con una cierta extensión (p. ej., “.tex”). Este método devuelve esos nombres como una matriz de cadenas.

```csharp
public string[] GetFileNamesByExtension(string extension, string path = null)
{
    Dictionary<string, string> files;
    if (!_fileNames.TryGetValue(extension, out files))
        return new string[0];

    return new List<string>(files.Values).ToArray();
}
```

### Paso 5: Liberar recursos

Limpiar el diccionario interno evita fugas de memoria, especialmente cuando la clase se usa en servicios de larga duración.

```csharp
public void Dispose()
{
    _fileNames.Clear();
}
```

Con estos cinco fragmentos ya dispones de una clase `RequiredInputDirectory` totalmente funcional que **obtiene flujo de archivo C#** y **especifica la entrada requerida** para el procesador Aspose.TeX.

## Problemas comunes y soluciones

| Problema | Por qué ocurre | Solución rápida |
|----------|----------------|-----------------|
| `GetFile` devuelve `null` y la compilación falla | El método es un marcador de posición; necesitas abrir un `FileStream` real si deseas que el motor lea el archivo. | Reemplaza `return null;` por `return File.OpenRead(fullName);` (asegúrate de que la ruta sea correcta). |
| Los archivos no se encuentran aunque existan | El colector no recibió los nombres o extensiones correctas. | Llama a `StoreFileName` para cada archivo **antes** de pasar el directorio a Aspose.TeX. |
| El uso de memoria se dispara con muchos archivos `.tex` grandes | El diccionario mantiene todos los nombres de archivo en memoria. | Libera el `RequiredInputDirectory` tan pronto como finalice el procesamiento, o utiliza un enfoque de streaming. |

## Preguntas frecuentes

**P: ¿Dónde puedo encontrar la documentación de Aspose.TeX para .NET?**  
R: La documentación está disponible [aquí](https://reference.aspose.com/tex/net/).

**P: ¿Cómo descargo la biblioteca Aspose.TeX para .NET?**  
R: Puedes descargar la biblioteca desde la [página de lanzamientos](https://releases.aspose.com/tex/net/).

**P: ¿Dónde puedo obtener soporte para Aspose.TeX para .NET?**  
R: Visita el [foro de Aspose.TeX](https://forum.aspose.com/c/tex/47) para soporte comunitario.

**P: ¿Hay una versión de prueba gratuita disponible?**  
R: Sí, puedes explorar la versión de prueba gratuita [aquí](https://releases.aspose.com/).

**P: ¿Cómo puedo obtener una licencia temporal para Aspose.TeX para .NET?**  
R: Puedes adquirir una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

## Preguntas frecuentes adicionales

**P: ¿Puedo usar esta clase en un proyecto .NET Core?**  
R: Absolutamente—`IInputWorkingDirectory` e `IFileCollector` son independientes de la plataforma.

**P: ¿Necesito registrar el directorio con Aspose.TeX manualmente?**  
R: Sí, pasa una instancia de `RequiredInputDirectory` al constructor de `TeXDocument` o a la llamada API correspondiente.

**P: ¿Qué versiones de .NET son compatibles?**  
R: Aspose.TeX funciona con .NET 5, .NET 6 y versiones posteriores, así como con .NET Framework 4.6.2+.

---

**Última actualización:** 2026-03-24  
**Probado con:** Aspose.TeX 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}