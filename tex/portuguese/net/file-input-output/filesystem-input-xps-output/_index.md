---
date: 2026-03-26
description: Aprenda a criar XPS a partir de TeX usando Aspose.TeX para .NET, gerenciar
  entrada/saída de arquivos e gerar documentos XPS de alta qualidade.
linktitle: Create XPS from TeX with Filesystems – Aspose.TeX for .NET
second_title: Aspose.TeX .NET API
title: Criar XPS a partir de TeX com Sistemas de Arquivos – Aspose.TeX para .NET
url: /pt/net/file-input-output/filesystem-input-xps-output/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar XPS a partir de TeX com Sistemas de Arquivos – Aspose.TeX para .NET

## Introdução

Bem‑vindo! Neste tutorial você aprenderá **como criar XPS a partir de TeX** trabalhando com entrada e saída de sistema de arquivos usando Aspose.TeX para .NET. Seja construindo um processador em lote, um serviço web ou um utilitário de desktop, os passos abaixo irão guiá‑lo na configuração do motor, apontando‑o para seus arquivos e produzindo documentos XPS que têm exatamente a mesma aparência do código‑fonte LaTeX original.

Dividiremos o processo em etapas claras e numeradas, explicaremos o “porquê” de cada linha de código e daremos dicas práticas que você pode aplicar imediatamente.

## Respostas Rápidas
- **O que significa “criar XPS a partir de TeX”?** Refere‑se à configuração de um job Aspose.TeX que lê arquivos TeX e grava o resultado como um documento XPS.  
- **Preciso de uma licença?** Uma licença temporária está disponível para testes; uma licença completa é necessária para produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Posso mudar o formato de saída?** Sim – substitua `XpsDevice` por outro dispositivo (PDF, PNG, etc.).  
- **A saída no console é obrigatória?** Não – você pode usar um terminal em memória para execução silenciosa.

## Como criar XPS a partir de TeX usando Aspose.TeX

Criar um job TeX que gera XPS significa inicializar o motor Aspose.TeX, indicar onde ler os arquivos fonte e direcionar as páginas renderizadas para um pacote XPS. XPS (XML Paper Specification) é um formato de layout fixo que preserva tipografia e gráficos vetoriais, tornando‑o ideal para impressão ou conversões posteriores.

## O que é “create tex job xps”?

Criar um job TeX que gera XPS significa inicializar o motor Aspose.TeX, indicar onde ler os arquivos fonte e direcionar as páginas renderizadas para um pacote XPS. XPS (XML Paper Specification) é um formato de layout fixo que preserva tipografia e gráficos vetoriais, tornando‑o ideal para impressão ou conversões posteriores.

## Por que usar Aspose.TeX para saída XPS?

- **Alta fidelidade:** O motor reproduz o layout LaTeX com precisão no XPS.  
- **Sem dependências externas:** Biblioteca .NET pura, sem necessidade de instalações nativas de LaTeX.  
- **I/O flexível:** Funciona com diretórios de sistema de arquivos, fluxos de memória ou provedores personalizados.  
- **Escalável:** Adequado para conversões de arquivo único ou pipelines de processamento em lote.

## Pré‑requisitos

Antes de começarmos, certifique‑se de que você tem o seguinte:

- **Aspose.TeX for .NET** – faça o download da versão mais recente no [site da Aspose](https://releases.aspose.com/tex/net/).  
- **Ambiente de desenvolvimento .NET** – Visual Studio, Rider ou VS Code com o .NET SDK.  
- **Pastas de entrada e saída** – crie dois diretórios na sua máquina (por exemplo, `C:\TeX\Input` e `C:\TeX\Output`).  
- **Licença (opcional para testes)** – você pode obter uma licença temporária no portal da Aspose.

## Importar Namespaces

Primeiro, traga os namespaces necessários para o escopo para que você possa acessar os auxiliares de sistema de arquivos e o dispositivo XPS.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

Esses namespaces expõem `InputFileSystemDirectory`, `OutputFileSystemDirectory` e `XpsDevice`, que são essenciais para o fluxo de trabalho **create XPS from TeX**.

## Etapa 1: Criar Opções de Conversão

Começamos construindo um objeto `TeXOptions` que indica ao motor usar a configuração ObjectTeX (o padrão para a maioria das fontes LaTeX).

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

> **Dica profissional:** `ConsoleAppOptions` define padrões sensatos para aplicações estilo console, mas você pode personalizar as opções posteriormente, se necessário.

## Etapa 2: Especificar Diretórios de Entrada e Saída

Aponte o motor para as pastas que você preparou anteriormente. Substitua as strings de espaço reservado pelos caminhos reais na sua máquina.

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

Agora o job TeX sabe onde encontrar arquivos `.tex` e onde colocar os arquivos XPS gerados.

## Etapa 3: Escolher um Terminal de Saída

O terminal controla onde as mensagens de status são escritas. Para depuração rápida, permaneceremos com o console, mas você pode mudar para um terminal em memória para execuções silenciosas.

```csharp
options.TerminalOut = new OutputConsoleTerminal(); // Default value. Arbitrary assignment.
```

> **Por que isso importa:** Usar um terminal de console fornece feedback imediato sobre avisos ou erros de compilação, o que acelera a solução de problemas.

## Etapa 4: Executar o Job TeX

Crie uma instância `TeXJob`, dê‑lhe um nome amigável, anexe o `XpsDevice` e execute‑a.

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

Quando `Run()` for concluído, você encontrará um arquivo `hello-world.xps` no diretório de saída.

## Etapa 5: Ajustar a Saída do Console

Adicionar uma linha em branco após a conclusão do job torna o log do console mais fácil de ler, especialmente ao executar vários jobs em lote.

```csharp
options.TerminalOut.Writer.WriteLine();
```

## Casos de Uso Comuns

| Cenário | Por que XPS? | Como o trecho ajuda |
|----------|--------------|----------------------|
| **Conversão em lote de artigos acadêmicos** | Preservar o layout exato para impressão de arquivo. | A abordagem baseada em sistema de arquivos permite apontar para uma pasta de arquivos `.tex` e gerar um conjunto correspondente de arquivos XPS. |
| **Serviço web que renderiza LaTeX em tempo real** | XPS pode ser transmitido diretamente para navegadores que o suportam. | Ao trocar `XpsDevice` por um fluxo de memória, você pode retornar o documento sem tocar no disco. |
| **Ferramenta de editoração desktop** | Necessita de uma pré‑visualização de layout fixo antes da conversão para PDF. | O mesmo job pode ser encadeado a um dispositivo PDF posteriormente para distribuição final. |

## Problemas Comuns e Soluções

| Problema | Causa | Correção |
|----------|-------|----------|
| **O arquivo XPS está vazio** | O caminho do diretório de saída está incorreto ou não é gravável. | Verifique o caminho passado para `OutputFileSystemDirectory` e assegure que o processo tem permissões de gravação. |
| **Erros de compilação** | O código‑fonte LaTeX usa pacotes que não estão incluídos no ObjectTeX. | Mude para uma configuração de motor TeX completa (`TeXConfig.FullTeX()`) ou adicione os arquivos de pacotes ausentes ao diretório de entrada. |
| **Console trava** | Terminal aguardando entrada devido a prompts interativos. | Use `OutputMemoryTerminal` para suprimir prompts interativos em scripts automatizados. |

## Perguntas Frequentes

**Q1: Posso usar um formato de saída diferente de XPS?**  
R1: Sim, Aspose.TeX suporta PDF, PNG, SVG e outros formatos. Substitua `new XpsDevice()` pela classe de dispositivo apropriada (por exemplo, `new PdfDevice()`).

**Q2: Uma licença temporária está disponível para fins de teste?**  
R2: Sim, você pode obter uma licença temporária para teste neste [link](https://purchase.aspose.com/temporary-license/).

**Q3: Onde posso encontrar documentação adicional?**  
R3: Consulte a [documentação do Aspose.TeX para .NET](https://reference.aspose.com/tex/net/) para informações detalhadas.

**Q4: Como posso obter suporte da comunidade ou fazer perguntas?**  
R4: Visite o [fórum Aspose.TeX](https://forum.aspose.com/c/tex/47) para suporte da comunidade e discussões.

**Q5: Existem projetos de exemplo disponíveis?**  
R5: Explore o repositório Aspose.TeX no GitHub para projetos de exemplo e trechos de código.

## Conclusão

Seguindo as etapas acima, você agora sabe como **criar XPS a partir de TeX** usando Aspose.TeX para .NET, gerenciar suas pastas de entrada e saída e ajustar o processo para cenários de desenvolvimento e produção. Sinta‑se à vontade para experimentar outros dispositivos de saída, integrar essa lógica em fluxos de trabalho maiores ou automatizar conversões em lote.

---

**Última atualização:** 2026-03-26  
**Testado com:** Aspose.TeX 24.11 for .NET (latest at time of writing)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}