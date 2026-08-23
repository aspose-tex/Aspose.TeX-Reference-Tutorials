---
date: 2026-08-23
description: Aprenda a criar documento PDF a partir de TeX, substituir o nome do trabalho
  e gravar a saída do terminal em um arquivo ZIP usando Aspose.TeX for Java. Guia
  passo a passo para desenvolvedores Java.
keywords:
- create pdf document from tex
- Aspose.TeX Java
- TeX to PDF conversion
lastmod: 2026-08-23
linktitle: Converter TeX para PDF, Substituir Nome do Trabalho e Gravar Saída do Terminal
  em ZIP no Java
og_description: Aprenda a criar documento PDF a partir de TeX, personalizar nomes
  de trabalhos e capturar a saída do terminal em um ZIP usando Aspose.TeX for Java
  – um guia rápido de 10 minutos.
og_image_alt: Developer guide showing Java code to convert TeX to PDF and zip logs
og_title: Criar documento PDF a partir de TeX, substituir nome do trabalho e compactar
  logs em Java
schemas:
- author: Aspose
  dateModified: '2026-08-23'
  description: Learn how to create PDF document from TeX, override the job name, and
    write terminal output to a ZIP file using Aspose.TeX for Java. Step‑by‑step guide
    for Java developers.
  headline: How to create PDF document from TeX and zip logs in Java
  type: TechArticle
- questions:
  - answer: Aspose.TeX is a Java library that enables developers to **create PDF document
      from TeX** sources, manipulate TeX documents, and perform advanced rendering
      without external LaTeX installations.
    question: What is Aspose.TeX?
  - answer: You can get a temporary license from the [Aspose.TeX temporary license
      page](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.TeX?
  - answer: The documentation is available on the [Aspose.TeX Java documentation page](https://reference.aspose.com/tex/java/).
    question: Where can I find the official Aspose.TeX documentation?
  - answer: Yes, you can download the free trial from the [Aspose.TeX free trial page](https://releases.aspose.com/).
    question: Is there a free trial version of Aspose.TeX?
  - answer: Visit the [Aspose.TeX forum](https://forum.aspose.com/c/tex/47) for community
      support and official assistance.
    question: Where can I ask for help if I run into problems?
  type: FAQPage
second_title: Aspose.TeX Java API
tags:
- TeX conversion
- Aspose.TeX
- Java PDF generation
title: Como criar documento PDF a partir de TeX, substituir o nome do trabalho e compactar
  logs em Java
url: /pt/java/customizing-output/override-job-name-zip/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar documento PDF a partir de TeX e compactar logs em Java

## Introdução

Se você precisar **criar documento PDF a partir de TeX** enquanto tem controle total sobre o nome do trabalho e os logs do terminal, o Aspose.TeX para Java torna isso simples. Neste tutorial, percorreremos um cenário do mundo real: sobrescrever o nome do trabalho, direcionar a saída do terminal para um arquivo ZIP e, finalmente, produzir um documento PDF. Ao final, você terá um trecho de código reutilizável que pode ser inserido em qualquer projeto Java.

## Respostas rápidas
- **Qual é o objetivo deste tutorial?** Ele mostra como criar documento PDF a partir de TeX, definir um nome de trabalho personalizado e capturar a saída do terminal em um arquivo ZIP.  
- **Qual biblioteca é necessária?** Aspose.TeX for Java (latest version).  
- **Preciso de uma licença?** Uma licença temporária funciona para avaliação; uma licença completa é necessária para produção.  
- **Quais arquivos de saída são gerados?** Um documento PDF e um log de terminal `<job_name>.trm` dentro do ZIP de saída.  
- **Quanto tempo leva a implementação?** Aproximadamente 10‑15 minutos para copiar o código e executá‑lo.

## O que é “converter TeX para PDF”?

Converter TeX para PDF significa pegar um arquivo fonte TeX (ou uma coleção de arquivos TeX) e renderizá‑lo como um documento PDF. O Aspose.TeX fornece um mecanismo de alto desempenho que lida com todo o pipeline de compilação TeX sem precisar de uma distribuição LaTeX externa.

## Por que sobrescrever o nome do trabalho e gravar a saída do terminal em um ZIP?

Sobrescrever o nome do trabalho permite marcar cada execução de compilação com um identificador significativo (por exemplo, um número de build). Gravar a saída do terminal em um ZIP mantém o log (`*.trm`) junto com o PDF gerado, o que simplifica o arquivamento, auditoria e depuração em pipelines automatizados.

## Por que isso importa

Quando você gera PDF a partir de TeX em um ambiente de produção, frequentemente precisa manter os artefatos de build organizados. Sobrescrever o nome do trabalho permite marcar cada execução com um identificador significativo (por exemplo, um número de build). Embalar o log do terminal no mesmo ZIP que o PDF fornece um pacote único e portátil que pode ser arquivado ou enviado a serviços downstream sem perder o contexto.

## Casos de uso comuns
- **Automated report generation** – um job noturno cria PDFs a partir de modelos TeX e armazena logs para fins de auditoria.  
- **CI/CD pipelines** – desenvolvedores podem visualizar as mensagens exatas de compilação quando uma build falha, sem precisar vasculhar arquivos de log separados.  
- **Cloud‑based document services** – um serviço web recebe um ZIP de fontes TeX, processa‑as e devolve um ZIP contendo o PDF e seu log de compilação.

## Pré-requisitos

Antes de começar, certifique‑se de que você tem:

- Um ambiente de desenvolvimento Java funcional (JDK 8 ou superior).  
- Aspose.TeX for Java baixado da [Aspose.TeX Java download page](https://releases.aspose.com/tex/java/).  
- Familiaridade básica com streams de I/O do Java.  

## Importar pacotes

O namespace `com.aspose.tex` contém todas as classes necessárias para a conversão, enquanto as classes padrão `java.io` lidam com streams ZIP. Importar esses pacotes fornece acesso à API Aspose.TeX e às utilidades de I/O do Java.

## Etapa 1: abrir o arquivo ZIP de entrada

A classe `InputZipDirectory` representa um arquivo ZIP que fornece arquivos fonte TeX ao mecanismo de conversão. Ela funciona como o **diretório de trabalho de entrada** para o trabalho.

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

## Etapa 2: abrir o arquivo ZIP de saída

A classe `OutputZipDirectory` cria um arquivo ZIP que receberá artefatos gerados, como o PDF e o log do terminal. Este é o **diretório de trabalho de saída**.

```java
// Open a stream on the input ZIP archive
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
```

## Etapa 3: definir opções de conversão (incluindo nome do trabalho)

`ConversionOptions` (especificamente `ObjectTeXOptions`) permite configurar o processo de compilação. Ao chamar `setJobName("MyBuild_123")` você sobrescreve o identificador de trabalho padrão, que então aparece nos nomes de arquivos de log e nos metadados internos.

```java
// Open a stream on the output ZIP archive
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "terminal-out-to-zip.zip");
```

## Etapa 4: direcionar a saída do terminal para um arquivo no ZIP

Chamar `options.setTerminalOut("MyBuild_123.trm")` indica ao Aspose.TeX que escreva a saída completa do console do compilador em um arquivo chamado `<job_name>.trm` dentro do ZIP de saída. Este arquivo contém avisos, erros e mensagens informativas essenciais para a solução de problemas.  
`setTerminalOut` especifica o nome do arquivo para o log de saída do terminal.

```java
// Create TeX options for ObjectTeX format
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("terminal-output-to-zip");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
```

## Etapa 5: definir opções de salvamento e executar o trabalho

O objeto `SavingOptions` seleciona o dispositivo de renderização — neste caso, PDF. Um objeto `Job` une o diretório de entrada, o diretório de saída e as opções de conversão e orquestra o processamento. Invocar `job.run()` executa todo o pipeline TeX‑para‑PDF, grava o PDF no ZIP de saída e cria o arquivo de log `.trm`. `run()` inicia o trabalho de conversão e bloqueia até que ele termine.

```java
// Specify terminal output settings
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

## Etapa 6: finalizar o arquivo ZIP de saída

Após o término do trabalho, você deve chamar `outputZip.finish()` para fechar o stream ZIP e garantir que o arquivo seja válido. `finish()` finaliza o arquivo ZIP e grava o diretório central. Pular esta etapa pode corromper o ZIP, tornando o PDF ou o log ilegível.

```java
// Define saving options and run the job
options.setSaveOptions(new PdfSaveOptions());
new TeXJob("hello-world", new PdfDevice(), options).run();
```

## Dicas e boas práticas

- **Reuse streams**: Se você processar muitos trabalhos TeX consecutivamente, mantenha os streams de entrada e saída abertos e altere apenas o `JobName` entre as execuções.  
- **Log inspection**: Abra o arquivo `<job_name>.trm` com qualquer editor de texto para ver avisos ou erros emitidos pelo compilador TeX.  
- **Performance**: Aspose.TeX pode processar documentos com até 500 páginas usando menos de 1 GB de memória heap em um servidor típico. Para arquivos maiores, aumente o tamanho da heap JVM (`-Xmx2g`).  
- **Security**: Ao lidar com fontes TeX não confiáveis, execute a conversão em um ambiente sandbox para mitigar macros potencialmente maliciosas.

## Problemas comuns e soluções

| Problema | Causa provável | Correção |
|----------|----------------|----------|
| **PDF vazio** | O ZIP de entrada não contém um arquivo `*.tex` válido ou o arquivo não está colocado na pasta `in`. | Verifique a estrutura do ZIP (`in/yourfile.tex`). |
| **Arquivo `.trm` ausente** | `setTerminalOut` não foi chamado ou o diretório de saída não é um `OutputZipDirectory`. | Garanta que `options.setTerminalOut(...)` seja executado antes de `run()`. |
| **`IOException` ao finalizar** | O stream de saída já foi fechado em outro lugar. | Chame `finish()` apenas uma vez, após a conclusão do trabalho. |
| **Falha na conversão com erros TeX** | A fonte TeX contém erros de sintaxe. | Abra o log `<job_name>.trm` gerado para ver mensagens de erro detalhadas. |

## Perguntas frequentes

**Q: O que é Aspose.TeX?**  
A: Aspose.TeX é uma biblioteca Java que permite aos desenvolvedores **criar documento PDF a partir de fontes TeX**, manipular documentos TeX e realizar renderização avançada sem instalações externas de LaTeX.

**Q: Como posso obter uma licença temporária para Aspose.TeX?**  
A: Você pode obter uma licença temporária na [página de licença temporária do Aspose.TeX](https://purchase.aspose.com/temporary-license/).

**Q: Onde posso encontrar a documentação oficial do Aspose.TeX?**  
A: A documentação está disponível na [página de documentação do Aspose.TeX Java](https://reference.aspose.com/tex/java/).

**Q: Existe uma versão de avaliação gratuita do Aspose.TeX?**  
A: Sim, você pode baixar a avaliação gratuita na [página de avaliação gratuita do Aspose.TeX](https://releases.aspose.com/).

**Q: Onde posso pedir ajuda se encontrar problemas?**  
A: Visite o [fórum do Aspose.TeX](https://forum.aspose.com/c/tex/47) para suporte da comunidade e assistência oficial.

## Conclusão

Agora você viu como **criar documento PDF a partir de TeX**, sobrescrever o nome do trabalho e capturar a saída do terminal dentro de um arquivo ZIP usando o Aspose.TeX para Java. Essa abordagem é especialmente útil em pipelines de build automatizados, onde manter os logs junto com os artefatos gerados simplifica a depuração e auditoria. Sinta‑se à vontade para adaptar o código à sua própria estrutura de projeto ou estendê‑lo para outros formatos de saída suportados pelo Aspose.TeX.

---

**Última atualização:** 2026-08-23  
**Testado com:** Aspose.TeX for Java 24.11 (latest at time of writing)  
**Autor:** Aspose  








```java
// Finalize the output ZIP archive
((OutputZipDirectory) options.getOutputWorkingDirectory()).finish();
```

## Tutoriais relacionados

- [Criar arquivo ZIP em Java com Aspose.TeX – Guia completo](/tex/java/zip-archives/)
- [Java gerar PDF a partir de LaTeX: Opções avançadas de conversão com Aspose.TeX](/tex/java/converting-lato-pdf/advanced-pdf-conversion/)
- [Como carregar a licença Aspose.TeX em Java – Guia passo a passo](/tex/java/managing-licenses/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}