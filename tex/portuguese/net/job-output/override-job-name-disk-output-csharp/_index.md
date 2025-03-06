---
title: Substituir o nome do trabalho e gravar a saída do terminal no disco (C#)
linktitle: Substituir o nome do trabalho e gravar a saída do terminal no disco (C#)
second_title: API Aspose.TeX .NET
description: Explore como usar o Aspose.TeX for .NET para substituir nomes de trabalhos e capturar a saída do terminal. Siga nosso guia completo para gerenciamento perfeito de arquivos TeX.
weight: 10
url: /pt/net/job-output/override-job-name-disk-output-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Substituir o nome do trabalho e gravar a saída do terminal no disco (C#)

## Introdução

Bem-vindo a este guia passo a passo sobre como usar Aspose.TeX para .NET para substituir nomes de trabalhos e gravar a saída do terminal em disco na linguagem de programação C#. Aspose.TeX for .NET é uma biblioteca poderosa que permite trabalhar perfeitamente com arquivos TeX e, neste tutorial, nos concentraremos em uma tarefa específica: substituir nomes de trabalhos e capturar a saída do terminal.

## Pré-requisitos

Antes de mergulharmos no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:

-  Biblioteca Aspose.TeX for .NET: Certifique-se de ter a biblioteca Aspose.TeX for .NET instalada. Você pode baixá-lo no[Site Aspose.TeX](https://releases.aspose.com/tex/net/).

- Ambiente de desenvolvimento .NET: tenha um ambiente de desenvolvimento .NET funcional, incluindo um ambiente de desenvolvimento integrado (IDE), como o Visual Studio.

- Conhecimento básico de C#: Familiarize-se com os fundamentos da linguagem de programação C#.

- Diretórios de entrada e saída: prepare os diretórios de entrada e saída para seus arquivos TeX.

## Importar namespaces

Em seu código C#, certifique-se de incluir os namespaces necessários para acessar as funcionalidades do Aspose.TeX:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

## Etapa 1: crie opções de conversão

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

Crie TeXOptions com ConsoleAppOptions, especificando ObjectTeX como TeXConfig.

## Etapa 2: Especifique o nome do trabalho

```csharp
options.JobName = "overridden-job-name";
```

Especifique o nome do trabalho para substituir o nome padrão.

## Etapa 3: especificar o diretório de trabalho de entrada

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

Defina o diretório de trabalho de entrada para seus arquivos TeX.

## Etapa 4: especificar o diretório de trabalho de saída

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Defina o diretório de trabalho de saída para salvar os arquivos TeX processados.

## Etapa 5: gravar a saída do terminal no disco

```csharp
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

Configure a saída do terminal para ser gravada em um arquivo no diretório de saída.

## Etapa 6: execute o trabalho

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

Crie um TeXJob, especificando um nome de trabalho, dispositivo de saída (XpsDevice) e opções. Finalmente, execute o trabalho.

## Conclusão

Parabéns! Você aprendeu com sucesso como substituir nomes de trabalhos e gravar a saída do terminal em disco usando Aspose.TeX para .NET em C#. Esse recurso é valioso para gerenciar suas tarefas de processamento TeX com eficiência.

## Perguntas frequentes

### Q1: Posso usar Aspose.TeX for .NET com outras bibliotecas .NET?

A1: Sim, o Aspose.TeX for .NET pode ser integrado perfeitamente com outras bibliotecas .NET.

### Q2: Existe uma avaliação gratuita disponível para Aspose.TeX for .NET?

 A2: Sim, você pode baixar uma versão de avaliação gratuita[aqui](https://releases.aspose.com/).

### Q3: Como posso obter suporte para Aspose.TeX para .NET?

 A3: Visite o[Fórum Aspose.TeX](https://forum.aspose.com/c/tex/47) para obter comunidade e apoio.

### Q4: As licenças temporárias estão disponíveis para Aspose.TeX for .NET?

 A4: Sim, você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).

### Q5: Onde posso encontrar a documentação do Aspose.TeX for .NET?

 A5: A documentação está disponível[aqui](https://reference.aspose.com/tex/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
