---
title: Substitua o nome do trabalho e grave a saída do terminal em Zip em Java
linktitle: Substitua o nome do trabalho e grave a saída do terminal em Zip em Java
second_title: API Java Aspose.TeX
description: Aprenda como substituir nomes de trabalhos e gravar a saída do terminal em ZIP em Java com Aspose.TeX. Um tutorial abrangente para desenvolvedores Java.
type: docs
weight: 11
url: /pt/java/customizing-output/override-job-name-zip/
---
## Introdução

No mundo do desenvolvimento Java, Aspose.TeX se destaca como uma ferramenta poderosa para lidar com formatos de arquivo TeX. Neste tutorial, nos aprofundaremos em um cenário específico – substituindo nomes de trabalhos e gravando a saída do terminal em um arquivo zip. Este guia passo a passo orientará você no processo usando Aspose.TeX para Java.

## Pré-requisitos

Antes de embarcarmos neste tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
- Conhecimento básico de programação Java.
-  Instalado Aspose.TeX para Java. Caso contrário, você pode baixá-lo no[Aspor site](https://releases.aspose.com/tex/java/).
- Uma compreensão de como configurar um ambiente de desenvolvimento Java.

## Importar pacotes

Comece importando os pacotes necessários para o seu projeto Java. Isso garante que você tenha acesso às funcionalidades do Aspose.TeX necessárias para a tarefa.

```java
package com.aspose.tex.OverridenJobNameAndTerminalOutputWrittenToZip;

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

## Etapa 1: abrir arquivos ZIP

Em primeiro lugar, abra um stream no arquivo ZIP que servirá como diretório de trabalho de entrada. Este é o arquivo a partir do qual os seus dados serão processados.

```java
// Abra um stream no arquivo ZIP de entrada
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
```

## Etapa 2: abrir arquivo ZIP de saída

Em seguida, abra um fluxo em um arquivo ZIP que servirá como diretório de trabalho de saída. É aqui que a saída do terminal será escrita.

```java
// Abra um stream no arquivo ZIP de saída
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "terminal-out-to-zip.zip");
```

## Etapa 3: definir opções de conversão

Crie opções de conversão para o formato ObjectTeX padrão na extensão do mecanismo ObjectTeX. Especifique um nome de trabalho e diretórios de trabalho de arquivo ZIP para entrada e saída.

```java
// Crie opções de TeX para o formato ObjectTeX
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("terminal-output-to-zip");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
```

## Etapa 4: Especifique a saída do terminal

 Especifique que a saída do terminal deve ser gravada em um arquivo no diretório de trabalho de saída. O nome do arquivo será`<job_name>.trm`.

```java
// Especifique as configurações de saída do terminal
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

## Etapa 5: definir opções de salvamento e executar o trabalho

Defina opções de salvamento, como opções de salvamento de PDF neste caso. Execute o trabalho TeX para executar a conversão.

```java
// Defina opções de salvamento e execute o trabalho
options.setSaveOptions(new PdfSaveOptions());
new TeXJob("hello-world", new PdfDevice(), options).run();
```

## Etapa 6: finalizar o arquivo ZIP de saída

Após a conclusão do trabalho, finalize o arquivo ZIP de saída para garantir a conclusão adequada.

```java
// Finalize o arquivo ZIP de saída
((OutputZipDirectory) options.getOutputWorkingDirectory()).finish();
```

## Conclusão

Parabéns! Você aprendeu com sucesso como substituir nomes de trabalhos e gravar a saída do terminal em um arquivo ZIP em Java usando Aspose.TeX. Essa poderosa funcionalidade adiciona flexibilidade e eficiência aos seus projetos de desenvolvimento Java.

## Perguntas frequentes

### Q1: O que é Aspose.TeX?

A1: Aspose.TeX é uma biblioteca Java que permite aos desenvolvedores trabalhar com formatos de arquivo TeX, fornecendo funcionalidades avançadas para processamento de documentos.

### Q2: Como posso obter uma licença temporária para Aspose.TeX?

 A2: Você pode obter uma licença temporária de[esse link](https://purchase.aspose.com/temporary-license/).

### Q3: Onde posso encontrar a documentação do Aspose.TeX?

 A3: A documentação está disponível[aqui](https://reference.aspose.com/tex/java/).

### Q4: Existe uma versão de teste gratuita do Aspose.TeX?

 A4: Sim, você pode encontrar a versão de avaliação gratuita[aqui](https://releases.aspose.com/).

### P5: Onde posso procurar suporte ou tirar dúvidas sobre o Aspose.TeX?

 A5: Visite o[Fórum Aspose.TeX](https://forum.aspose.com/c/tex/47) para apoio e discussões.
