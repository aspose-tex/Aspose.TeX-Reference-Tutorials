---
title: Typeset TeX para PDF em Java com fluxo externo
linktitle: Typeset TeX para PDF em Java com fluxo externo
second_title: API Java Aspose.TeX
description: Aprenda como compor TeX para PDF em Java usando fluxos externos com Aspose.TeX. Siga nosso guia passo a passo para uma integração perfeita.
type: docs
weight: 10
url: /pt/java/typesetting-tex-to-pdf/typeset-tex-to-pdf-external-stream/
---
## Introdução

No mundo do desenvolvimento Java, criar PDFs a partir de arquivos TeX é um requisito comum. Aspose.TeX para Java simplifica esse processo, fornecendo uma solução eficiente para composição tipográfica de TeX para PDF. Neste tutorial, orientaremos você nas etapas de composição de TeX para PDF usando fluxos externos. Ao final, você terá uma compreensão clara de como implementar esse processo perfeitamente em seus aplicativos Java.

## Pré-requisitos

Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:

- Aspose.TeX para Java: Certifique-se de ter a biblioteca Aspose.TeX para Java instalada. Você pode baixá-lo no[Documentação Aspose.TeX para Java](https://reference.aspose.com/tex/java/).

- Diretórios de entrada e saída: Prepare os diretórios de entrada e saída. Você pode usar o link de download fornecido para obter os arquivos necessários.

## Importar pacotes

Comece importando os pacotes necessários para o seu projeto Java:

```java
package com.aspose.tex.TypesetPdfWrittenToExternalStream;

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

## Etapa 1: abrir fluxos de entrada e saída

Comece abrindo fluxos para o arquivo ZIP de entrada (atuando como diretório de trabalho de entrada) e o arquivo ZIP de saída (servindo como diretório de trabalho de saída). Certifique-se de substituir "Seu diretório de entrada" e "Seu diretório de saída" pelos caminhos de diretório reais.

```java
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "typeset-pdf-to-external-stream.zip");
```

## Passo 2: Configurar TeXOptions

Crie o objeto TeXOptions e configure-o de acordo com suas necessidades. Defina o nome do trabalho, o diretório de trabalho de entrada, o diretório de trabalho de saída e outras opções.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("typeset-pdf-to-external-stream");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
options.setSaveOptions(new PdfSaveOptions());
```

## Etapa 3: Compor TeX em PDF

Agora, abra um stream para gravar o PDF de saída no local desejado. Você pode optar por gravá-lo em um arquivo local ou diretamente no arquivo ZIP de saída.

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + "file-name.pdf");
try {
    new TeXJob("hello-world", new PdfDevice(stream), options).run();
} finally {
    stream.close();
}
```

## Etapa 4: finalizar o arquivo ZIP de saída

Conclua o arquivo ZIP de saída para concluir o processo de composição.

```java
((OutputZipDirectory)options.getOutputWorkingDirectory()).finish();
```

## Conclusão

Parabéns! Você digitou TeX para PDF com sucesso em Java usando fluxos externos com Aspose.TeX. Este tutorial fornece uma base robusta para incorporar perfeitamente a conversão de TeX em PDF em seus aplicativos Java.

## Perguntas frequentes

### Q1: Posso personalizar o nome do arquivo do PDF de saída?

 A1: Sim, você pode modificar o`options.setJobName("typeset-pdf-to-external-stream")` para definir o nome do trabalho desejado.

### P2: Como resolvo problemas comuns durante a composição tipográfica?

 A2: Visite o[Fórum Aspose.TeX](https://forum.aspose.com/c/tex/47) para apoio e assistência comunitária.

### Q3: Existe uma avaliação gratuita disponível para Aspose.TeX para Java?

 A3: Sim, você pode acessar a avaliação gratuita[aqui](https://releases.aspose.com/).

### P4: Onde posso encontrar documentação e exemplos adicionais?

 A4: Explore o abrangente[Documentação Aspose.TeX](https://reference.aspose.com/tex/java/) para obter informações detalhadas.

### Q5: Posso obter uma licença temporária para Aspose.TeX?

 A5: Sim, você pode solicitar uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).