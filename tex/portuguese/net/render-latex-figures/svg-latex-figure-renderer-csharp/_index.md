---
title: Renderize figuras LaTeX para SVG com Aspose.TeX (C#)
linktitle: Renderize figuras LaTeX para SVG com Aspose.TeX (C#)
second_title: API Aspose.TeX .NET
description: Aprimore a renderização de documentos em .NET com Aspose.TeX. Aprenda como renderizar figuras LaTeX para SVG em C# para integração perfeita de expressões matemáticas.
type: docs
weight: 11
url: /pt/net/render-latex-figures/svg-latex-figure-renderer-csharp/
---
## Introdução

Se você deseja aprimorar seus recursos de renderização de documentos em .NET usando figuras LaTeX, o Aspose.TeX é a solução ideal. Neste guia passo a passo, orientaremos você na renderização de figuras LaTeX para SVG usando Aspose.TeX em C#. Ao final deste tutorial, você terá uma compreensão clara do processo, permitindo-lhe incorporar perfeitamente expressões e figuras matemáticas de alta qualidade em seus documentos.

## Pré-requisitos

Antes de mergulharmos no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:

- Conhecimento básico da linguagem de programação C#.
-  Biblioteca Aspose.TeX para .NET instalada. Você pode baixá-lo[aqui](https://releases.aspose.com/tex/net/).

## Importar namespaces

No seu código C#, certifique-se de importar os namespaces necessários:

```csharp
using Aspose.TeX.Features;
```

Agora, vamos dividir o tutorial em várias etapas:

## Etapa 1: criar opções de renderização

```csharp
FigureRendererOptions options = new SvgFigureRendererOptions();
options.Preamble = "\\usepackage{pict2e}";
options.Scale = 3000;
options.BackgroundColor = Color.White;
options.LogStream = new System.IO.MemoryStream();
options.ShowTerminal = true;
```

Aqui, configuramos opções de renderização, especificando o preâmbulo, fator de escala, cor de fundo, fluxo de log e se devemos mostrar a saída do terminal.

## Etapa 2: definir dimensões e fluxo de saída

```csharp
SizeF size = new SizeF();
using (Stream stream = File.Open(Path.Combine("Your Output Directory", "text-and-formula.svg"), FileMode.Create))
{
    // Execute a renderização.
    new SvgFigureRenderer().Render("Your LaTeX Code", stream, options, out size);
}
```

Substitua "Your Output Directory" pelo diretório desejado e forneça seu código LaTeX como uma string.

## Etapa 3: exibir resultados

```csharp
Console.Out.WriteLine(options.ErrorReport);
Console.Out.WriteLine();
Console.Out.WriteLine("Size: " + size);
```

Esta etapa exibe quaisquer relatórios de erros e o tamanho da imagem resultante.

## Conclusão

Parabéns! Você aprendeu com sucesso como renderizar figuras LaTeX para SVG usando Aspose.TeX em C#. Agora você pode integrar perfeitamente expressões matemáticas e figuras em seus aplicativos .NET.

## Perguntas frequentes

### Q1: O uso do Aspose.TeX é gratuito?

 A1: Aspose.TeX oferece um teste gratuito. Você pode acessá-lo[aqui](https://releases.aspose.com/).

### Q2: Onde posso encontrar a documentação do Aspose.TeX?

 A2: Consulte a documentação[aqui](https://reference.aspose.com/tex/net/).

### Q3: Como obtenho suporte para Aspose.TeX?

 A3: Visite o fórum de suporte[aqui](https://forum.aspose.com/c/tex/47).

### Q4: Posso comprar Aspose.TeX?

 A4: Sim, você pode comprar Aspose.TeX[aqui](https://purchase.aspose.com/buy).

### P5: Preciso de uma licença temporária?

 A5: Se necessário, você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).