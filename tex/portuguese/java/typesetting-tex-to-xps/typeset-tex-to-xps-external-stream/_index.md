---
title: Typeset TeX para XPS em Java com fluxo externo
linktitle: Typeset TeX para XPS em Java com fluxo externo
second_title: API Java Aspose.TeX
description: Aprenda como compor TeX para XPS em Java usando Aspose.TeX. Explore orientações passo a passo para um processamento de documentos perfeito.
weight: 10
url: /pt/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Typeset TeX para XPS em Java com fluxo externo

## Introdução

No mundo do desenvolvimento Java, Aspose.TeX se destaca como uma ferramenta poderosa para composição tipográfica de documentos TeX em vários formatos, incluindo XPS. Se você deseja aprimorar os recursos de processamento de documentos do seu aplicativo Java, este tutorial foi feito sob medida para você. Neste guia passo a passo, orientaremos você no processo de composição tipográfica de TeX para XPS usando Aspose.TeX para Java com um fluxo externo.

## Pré-requisitos

Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:

-  Java Development Kit (JDK): Certifique-se de ter o Java instalado em seu sistema. Você pode baixá-lo em[aqui](https://www.oracle.com/java/technologies/javase-downloads.html).

-  Aspose.TeX para Java: Baixe e instale Aspose.TeX para Java. Você pode encontrar o link para download[aqui](https://releases.aspose.com/tex/java/).

## Importar pacotes

Comece importando os pacotes necessários para iniciar sua jornada de conversão de TeX em XPS. Inclua o seguinte trecho de código em seu projeto Java:

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

## Etapa 1: configurar opções de conversão

Comece criando opções de conversão para o formato ObjectTeX padrão usando o seguinte código:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

Isso estabelece a base para o processo de composição tipográfica.

## Etapa 2: Especifique o nome do trabalho e os diretórios

Defina um nome de trabalho e defina os diretórios de trabalho de entrada e saída:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Certifique-se de substituir espaços reservados como "Seu diretório de entrada" pelos caminhos de diretório reais.

## Etapa 3: configurar a saída do terminal

Especifique que a saída do terminal deve ser gravada em um arquivo no diretório de trabalho de saída:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

Esta etapa garante que logs detalhados sejam capturados para depuração.

## Etapa 4: fluxo de saída aberto

Abra um fluxo para escrever o documento XPS composto:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

Substitua “Seu diretório de saída” pelo caminho apropriado.

## Etapa 5: execute o trabalho

Execute o trabalho de conversão de TeX para XPS:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

Isso conclui o processo e você encontrará seu documento XPS composto no diretório de saída especificado.

## Conclusão

Parabéns! Você digitou TeX para XPS com sucesso em Java usando Aspose.TeX. Isto abre um mundo de possibilidades para processamento de documentos em suas aplicações Java. Experimente diferentes arquivos TeX e explore os diversos recursos oferecidos pelo Aspose.TeX.

## Perguntas frequentes

### Q1: Posso usar Aspose.TeX para Java com outros formatos de documento?

A1: Aspose.TeX concentra-se principalmente no processamento de documentos relacionados ao TeX. Para outros formatos, explore a extensa linha de produtos da Aspose.

### Q2: Existe uma versão de teste disponível?

 A2: Sim, você pode experimentar o Aspose.TeX baixando a versão de avaliação gratuita[aqui](https://releases.aspose.com/).

### P3: Onde posso encontrar documentação abrangente?

 A3: Consulte a documentação[aqui](https://reference.aspose.com/tex/java/) para obter informações detalhadas e exemplos.

### P4: Como obtenho suporte ou procuro assistência?

 A4: Visite o fórum Aspose.TeX[aqui](https://forum.aspose.com/c/tex/47)para apoio e discussões da comunidade.

### P5: Posso obter uma licença temporária para fins de teste?

 A5: Sim, você pode adquirir uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
