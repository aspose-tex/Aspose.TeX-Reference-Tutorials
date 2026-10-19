---
date: 2026-10-19
description: Узнайте, как выполнять генерацию tex‑документов, создавать пользовательский
  tex‑формат и задавать каталог входных tex‑файлов с помощью Aspose.TeX для .NET.
  Пошаговое руководство с примерами кода и советами по устранению неполадок.
keywords:
- tex document generation
- create custom tex format
- set tex input directory
- custom tex macros
lastmod: 2026-10-19
linktitle: Создание пользовательских TeX‑форматов в .NET
og_description: Генерация tex‑документов с помощью Aspose.TeX позволяет создавать
  пользовательский tex‑формат и задавать каталог входных tex‑файлов в .NET. Следуйте
  этому руководству для вывода в XPS, PDF или PNG.
og_image_alt: Developer guide showing tex document generation using Aspose.TeX in
  .NET
og_title: Как выполнять генерацию tex‑документов с форматом в .NET
schemas:
- author: Aspose
  dateModified: '2026-10-19'
  description: Learn how to perform tex document generation, create custom tex format
    and set tex input directory using Aspose.TeX for .NET. Step‑by‑step guide with
    code snippets and troubleshooting tips.
  headline: How to do tex document generation with format in .NET
  type: TechArticle
- description: Learn how to perform tex document generation, create custom tex format
    and set tex input directory using Aspose.TeX for .NET. Step‑by‑step guide with
    code snippets and troubleshooting tips.
  name: How to do tex document generation with format in .NET
  steps:
  - name: '**Aspose.TeX for .NET** – download it from the [Aspose.TeX website](https://releases.aspose.com/tex/net/).'
    text: '**Aspose.TeX for .NET** – download it from the [Aspose.TeX website](https://releases.aspose.com/tex/net/).'
  - name: A **.NET development environment** (Visual Studio, VS Code, or the .NET
      CLI).
    text: A **.NET development environment** (Visual Studio, VS Code, or the .NET
      CLI).
  - name: (Optional) A valid **Aspose.TeX license** for production use.
    text: (Optional) A valid **Aspose.TeX license** for production use.
  type: HowTo
- questions:
  - answer: Absolutely. Replace `new XpsDevice()` with `new PdfDevice()` and adjust
      the output path accordingly.
    question: Can I output PDF instead of XPS?
  - answer: Yes. Any modification to macros or engine settings requires re‑running
      `tex -ini` to generate a fresh `.fmt` file.
    question: Do I need to re‑compile the format file after every change?
  type: FAQPage
second_title: Aspose.TeX .NET API
tags:
- tex document generation
- Aspose.TeX
- .NET document processing
- custom tex format
title: Как выполнять генерацию tex‑документов с форматом в .NET
url: /ru/net/custom-tex-formats/create-custom-tex-formats/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как выполнять генерацию tex‑документов с форматом в .NET

В современном .NET‑разработке **генерация tex‑документов** — это мощный способ создавать высококачественный наборный вывод без необходимости внешних установок LaTeX. Aspose.TeX for .NET предоставляет полный контроль: вы можете **создать пользовательский tex‑формат**, указать движку специальную входную папку и экспортировать в XPS, PDF, PNG или другие устройства — всё из простого кода C#.

## Быстрые ответы
- **Что означает «create custom tex format»?** Это означает определение собственной конфигурации движка TeX и скомпилированного файла формата, чтобы процессор следовал вашим макросам и настройкам.  
- **Какая библиотека мне нужна?** Aspose.TeX for .NET, которая поддерживает более 30 входных и выходных форматов.  
- **Нужно ли задавать каталог входных tex‑файлов?** Да — используйте `InputWorkingDirectory`, чтобы указать движку, где находятся вспомогательные файлы.  
- **Какой вывод я могу генерировать?** XPS, PDF, PNG, TIFF и многие другие форматы устройств.  
- **Требуется ли лицензия для продакшна?** Действительная лицензия Aspose.TeX обязательна для коммерческих развертываний.

## Что такое пользовательский tex‑формат?
Пользовательский tex‑формат — это предварительно скомпилированная коллекция макросов и настроек движка, которую процессор TeX загружает при запуске. Создавая такой формат, вы можете внедрять фирменный стиль компании, обеспечивать соблюдение стандартов макета и сокращать время компиляции повторяющихся документов. Он обеспечивает единообразный стиль во всех генерируемых документах и упрощает обслуживание сложных наборных процессов.

## Зачем задавать каталог входных tex‑файлов?
Указание **tex‑каталога входных файлов** сообщает движку, где искать вспомогательные файлы, такие как файлы стилей, пользовательские шрифты или дополнительные пакеты макросов. Это устраняет ошибки «файл не найден» и поддерживает порядок в папке проекта. Кроме того, это повышает воспроизводимость сборки, гарантируя, что все ресурсы берутся из известного места.

## Предварительные требования

Прежде чем начать, убедитесь, что у вас есть:

1. **Aspose.TeX for .NET** — скачайте его с [Aspose.TeX website](https://releases.aspose.com/tex/net/).  
2. Среда разработки **.NET** (Visual Studio, VS Code или .NET CLI).  
3. (Опционально) Действительная **лицензия Aspose.TeX** для продакшн‑использования.

## Импорт пространств имён

Следующие пространства имён предоставляют доступ к основным классам Aspose.TeX. Классы, связанные с `Document`, находятся в `Aspose.TeX`, а параметры и устройства — в `Aspose.TeX.Rendering`.

Класс `Document` — это объект верхнего уровня, представляющий один TeX‑документ в памяти.  

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using Aspose.TeX.ResourceProviders;
using System.IO;
using System.Text;
```

## Шаг 1: создать поставщик формата

`FormatProvider` указывает движку, где находится скомпилированный файл формата (`customtex.fmt`). Замените `"Your Output Directory"` на абсолютный путь, содержащий ваш пользовательский формат.

`FormatProvider` — это лёгкая оболочка, которая загружает файл `.fmt` один раз и переиспользует его для каждой конверсии, значительно повышая производительность пакетных задач.

```csharp
using (FormatProvider formatProvider =
    new FormatProvider(new InputFileSystemDirectory("Your Output Directory"), "customtex"))
{
```

## Шаг 2: настроить параметры конверсии (и задать каталог входных tex‑файлов)

Здесь мы создаём экземпляр `TeXOptions`. Свойство `InputWorkingDirectory` **задаёт каталог входных tex‑файлов**, чтобы движок мог находить любые вспомогательные файлы, такие как пользовательские пакеты или шрифты.

`TeXOptions` также позволяет указать устройство вывода, размер страницы и качество рендеринга. Для крупномасштабной генерации вы можете включить `EnableParallelProcessing`, чтобы ускорить рендеринг на многопоточных серверах.

```csharp
    TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX(formatProvider));
    options.JobName = "typeset-with-custom-format";
    options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
    options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

## Шаг 3: выполнить задачу

Теперь передайте простой TeX‑строку движку, выберите устройство вывода (XPS в этом примере) и запустите задачу. `TeXEngine` читает пользовательский формат, обрабатывает исходный код и записывает результат в выбранное устройство.

`TeXEngine` — основной процессор Aspose.TeX, который разбирает TeX‑исходник, применяет пользовательский формат и передаёт отрендеренные страницы в указанное вами устройство.

```csharp
    new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
        "Congratulations! You have successfully typeset this text with your own TeX format!\\end")),
        new XpsDevice(), options).Run();
```

## Шаг 4: улучшить вывод в терминале

Добавление пустой строки после завершения задачи делает вывод консоли более читаемым, особенно когда вы цепочкой запускаете несколько конверсий в скрипте.

`Console.WriteLine()` записывает строку текста в стандартный поток вывода. Здесь он используется исключительно для визуального разделения; он не влияет на генерируемый документ.

```csharp
    options.TerminalOut.Writer.WriteLine();
}
// ExEnd:TypesetWithCustomTeXFormat
```

Поздравляем! Вы теперь **создали пользовательский tex‑формат** и использовали его для **генерации tex‑документов** в .NET. Вы можете заменить `XpsDevice` на `PdfDevice`, `PngDevice` или любое другое поддерживаемое устройство в соответствии с вашими потребностями.

## Распространённые проблемы и решения

| Проблема | Причина | Решение |
|----------|---------|---------|
| *“Format file not found”* | Неправильный путь в `FormatProvider` | Убедитесь, что `"Your Output Directory"` содержит `customtex.fmt` и что путь абсолютный или правильно относительный к исполняемому файлу. |
| *“Cannot find input file”* | `InputWorkingDirectory` указывает на неправильную папку | Убедитесь, что `"Your Input Directory"` содержит исходный TeX‑файл или что вы передаёте источник как поток (как в примере). |
| *Terminal output garbled* | Несоответствие кодировки | Используйте `Encoding.UTF8`, если ваш TeX‑исходник содержит не‑ASCII символы. |
| *XPS file is empty* | Задача не выполнена из‑за предыдущего исключения | Проверьте консоль на наличие сообщений об ошибках; они часто указывают на отсутствующие пакеты или синтаксические ошибки в TeX‑строке. |

## Часто задаваемые вопросы

**Q1: Могу ли я использовать Aspose.TeX for .NET с другими библиотеками Aspose?**  
A: Да, Aspose.TeX легко интегрируется с Aspose.PDF, Aspose.Words и другими продуктами Aspose для сквозных конвейеров документооборота.

**Q2: Доступна ли бесплатная пробная версия Aspose.TeX for .NET?**  
A: Да, вы можете скачать пробную версию со **страницы бесплатного скачивания Aspose.TeX** (https://releases.aspose.com/tex/net/).

**Q3: Как получить поддержку для Aspose.TeX for .NET?**  
A: Посетите [форум Aspose.TeX](https://forum.aspose.com/c/tex/47) для помощи сообщества или изучите премиум‑варианты на **странице покупки премиум‑поддержки** (https://purchase.aspose.com/buy).

**Q4: Доступны ли временные лицензии для Aspose.TeX for .NET?**  
A: Да, запросите её на **странице запроса временной лицензии** (https://purchase.aspose.com/temporary-license/).

**Q5: Где можно найти официальную справку API?**  
A: Полная документация размещена в **документации справочника API** (https://reference.aspose.com/tex/net/).

### Дополнительные вопросы и ответы

**Q: Могу ли я выводить PDF вместо XPS?**  
A: Конечно. Замените `new XpsDevice()` на `new PdfDevice()` и соответственно измените путь вывода.

**Q: Нужно ли перекомпилировать файл формата после каждого изменения?**  
A: Да. Любое изменение макросов или настроек движка требует повторного запуска `tex -ini` для создания нового файла `.fmt`.

## Заключение

Aspose.TeX for .NET предоставляет **надёжное, высокопроизводительное решение для генерации tex‑документов**, позволяя вам **создавать пользовательский tex‑формат**, задавать **каталог входных tex‑файлов** и выводить на любое поддерживаемое устройство. Внедрите описанные шаги в ваш CI/CD конвейер, автоматизируйте крупномасштабную генерацию отчётов или создайте собственный движок публикации, соответствующий фирменным стандартам вашей организации.

---

**Last Updated:** 2026-10-19  
**Tested With:** Aspose.TeX 24.11 for .NET  
**Author:** Aspose

## Связанные руководства

- [Получить поток TeX‑файла (C#) с использованием Aspose.TeX API Требуемый каталог входных файлов](/tex/net/advanced-io/required-input-directory-csharp/)
- [Как создать PDF с помощью Aspose.TeX for .NET – пошагово](/tex/net/pdf-output/)
- [Как создать документ XPS в .NET – конвертировать TeX в XPS с помощью Aspose.TeX for .NET](/tex/net/xps-output/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}