---
title: Substituir o nome do trabalho e gravar a saída do terminal em Java
linktitle: Substituir o nome do trabalho e gravar a saída do terminal em Java
second_title: API Java Aspose.TeX
description: Explore o guia passo a passo sobre como substituir nomes de trabalhos e escrever saída de terminal usando Aspose.TeX para Java. Aprimore o processamento de documentos com poderosas opções de personalização.
type: docs
weight: 10
url: /pt/java/customizing-output/override-job-name-disk/
---
## Introdução

Aspose.TeX for Java fornece recursos poderosos para trabalhar com arquivos TeX, permitindo aos desenvolvedores manipular e personalizar o processamento de documentos TeX. Neste tutorial, iremos guiá-lo através do processo de substituição do nome do trabalho e gravação da saída do terminal no sistema de arquivos usando Aspose.TeX em Java.

## Pré-requisitos

Antes de mergulharmos no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:

- Conhecimento prático de programação Java.
-  Aspose.TeX para Java instalado. Você pode baixá-lo no[Documentação Java Aspose.TeX](https://reference.aspose.com/tex/java/).

## Importar pacotes

Para começar, importe os pacotes necessários para o seu projeto Java. No seu arquivo Java, inclua as seguintes importações:

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

## Substituir nome do trabalho e gravar saída do terminal

### Etapa 1: crie opções de conversão

Comece criando opções de conversão para o formato ObjectTeX padrão na extensão do mecanismo ObjectTeX. Use o seguinte trecho de código:

```java
//ExStart:OverrideJobName-WriteTerminalOutputToFileSystem
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

### Etapa 2: Especifique o nome do trabalho e os diretórios de trabalho

Especifique um nome de tarefa, um diretório de trabalho de entrada e um diretório de trabalho de saída. Se o nome do trabalho não for especificado, o primeiro argumento do construtor TeXJob será considerado o nome do trabalho. Use o seguinte trecho de código:

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### Etapa 3: gravar a saída do terminal no sistema de arquivos

 Especifique que a saída do terminal deve ser gravada em um arquivo no diretório de trabalho de saída. O nome do arquivo será`<job_name>.trm`. Adicione o seguinte código:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### Etapa 4: execute o trabalho

Execute o trabalho TeX usando as opções e o nome do trabalho especificados. Veja como você pode fazer isso:

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
// ExEnd:OverrideJobName-WriteTerminalOutputToFileSystem
```

Parabéns! Você substituiu com êxito o nome do trabalho e gravou a saída do terminal no sistema de arquivos usando Aspose.TeX em Java.

## Conclusão

Neste tutorial, exploramos como utilizar Aspose.TeX for Java para substituir o nome do trabalho e capturar a saída do terminal. Esses recursos permitem que os desenvolvedores tenham controle refinado sobre o processamento de documentos TeX, melhorando a personalização e a flexibilidade.

## Perguntas frequentes

### Q1: Posso usar Aspose.TeX para Java com outras bibliotecas Java?

A1: Sim, o Aspose.TeX for Java foi projetado para se integrar perfeitamente com outras bibliotecas Java para aprimorar seus recursos de processamento de documentos.

### P2: Onde posso encontrar suporte para Aspose.TeX para Java?

 A2: Visite o[Fórum Aspose.TeX](https://forum.aspose.com/c/tex/47) para suporte da comunidade e assistência com quaisquer problemas que você possa encontrar.

### Q3: Existe uma avaliação gratuita disponível para Aspose.TeX para Java?

 A3: Sim, você pode acessar a versão de teste gratuita do Aspose.TeX para Java[aqui](https://releases.aspose.com/).

### P4: Como posso obter uma licença temporária do Aspose.TeX para Java?

 A4: Siga isto[link](https://purchase.aspose.com/temporary-license/) para obter uma licença temporária para fins de teste e avaliação.

### Q5: Onde posso comprar Aspose.TeX para Java?

 A5: Visite o[página de compra](https://purchase.aspose.com/buy) para adquirir uma licença para Aspose.TeX para Java.