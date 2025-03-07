---
title: Substituir o nome do trabalho e gravar a saída do terminal em Zip (C#)
linktitle: Substituir o nome do trabalho e gravar a saída do terminal em Zip (C#)
second_title: API Aspose.TeX .NET
description: Aprenda como substituir nomes de trabalhos e gravar a saída do terminal em um arquivo ZIP usando Aspose.TeX para .NET. Guia passo a passo com exemplos de C#.
weight: 11
url: /pt/net/job-output/override-job-name-zip-output-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Substituir o nome do trabalho e gravar a saída do terminal em Zip (C#)

## Introdução

Neste tutorial, exploraremos como substituir o nome do trabalho e gravar a saída do terminal em um arquivo ZIP usando Aspose.TeX para .NET. Aspose.TeX é uma biblioteca poderosa que permite aos desenvolvedores trabalhar com documentos TeX em seus aplicativos .NET. Neste exemplo específico, vamos nos concentrar em uma tarefa comum – gravar a saída do terminal em um arquivo ZIP com a capacidade de substituir o nome do trabalho.

## Pré-requisitos

Antes de começarmos, certifique-se de ter os seguintes pré-requisitos em vigor:

- Um conhecimento prático de C#
- Aspose.TeX para .NET instalado
- Insira o arquivo ZIP para o diretório de trabalho
- Arquivo ZIP de saída para saída do terminal

## Importar namespaces

Antes de mergulhar no código, certifique-se de incluir os namespaces necessários em seu projeto C#:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Pdf;
using System.IO;
```

Agora, vamos dividir o exemplo em várias etapas para guiá-lo durante o processo.

## Etapa 1: abrir fluxos ZIP de entrada e saída

```csharp
using (Stream inZipStream = File.Open(Path.Combine("Your Input Directory", "zip-in.zip"), FileMode.Open))
using (Stream outZipStream = File.Open(Path.Combine("Your Output Directory", "terminal-out-to-zip.zip"), FileMode.Create))
{
    // O código para a etapa 1 vai aqui
}
```

## Etapa 2: definir opções de conversão

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
options.JobName = "terminal-output-to-zip";
options.InputWorkingDirectory = new InputZipDirectory(inZipStream, "in");
options.OutputWorkingDirectory = new OutputZipDirectory(outZipStream);
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## Etapa 3: definir opções de salvamento

```csharp
options.SaveOptions = new PdfSaveOptions();
```

## Etapa 4: execute o trabalho TeX

```csharp
new TeXJob("hello-world", new PdfDevice(), options).Run();
```

## Etapa 5: finalizar o arquivo ZIP de saída

```csharp
((OutputZipDirectory)options.OutputWorkingDirectory).Finish();
```

## Conclusão

Parabéns! Você aprendeu com sucesso como substituir o nome do trabalho e gravar a saída do terminal em um arquivo ZIP usando Aspose.TeX para .NET. Essa técnica pode ser extremamente útil ao lidar com documentos TeX em seus aplicativos C#.

## Perguntas frequentes

### Q1: Posso usar Aspose.TeX for .NET com outras linguagens .NET como VB.NET?

A1: Sim, Aspose.TeX for .NET é compatível com todas as linguagens .NET.

### Q2: Onde posso encontrar mais documentação para Aspose.TeX for .NET?

 A2: Visite o[documentação](https://reference.aspose.com/tex/net/) para obter informações detalhadas.

### Q3: Como posso obter uma licença temporária para Aspose.TeX?

 A3: Obtenha um[licença temporária](https://purchase.aspose.com/temporary-license/) para fins de teste.

### Q4: Existe um fórum da comunidade para suporte do Aspose.TeX?

 A4: Sim, junte-se ao[Fórum Aspose.TeX](https://forum.aspose.com/c/tex/47) para apoio comunitário.

### Q5: Onde posso comprar Aspose.TeX para .NET?

 A5: Você pode comprar Aspose.TeX[aqui](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
