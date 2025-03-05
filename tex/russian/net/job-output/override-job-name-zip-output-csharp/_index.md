---
title: Переопределить имя задания и записать вывод терминала в ZIP (C#)
linktitle: Переопределить имя задания и записать вывод терминала в ZIP (C#)
second_title: API Aspose.TeX .NET
description: Узнайте, как переопределить имена заданий и записать вывод терминала в ZIP-файл с помощью Aspose.TeX для .NET. Пошаговое руководство с примерами C#.
type: docs
weight: 11
url: /ru/net/job-output/override-job-name-zip-output-csharp/
---
## Введение

В этом уроке мы рассмотрим, как переопределить имя задания и записать вывод терминала в ZIP-файл, используя Aspose.TeX для .NET. Aspose.TeX — мощная библиотека, которая позволяет разработчикам работать с документами TeX в своих .NET-приложениях. В этом конкретном примере мы сосредоточимся на общей задаче — записи вывода терминала в ZIP-файл с возможностью переопределения имени задания.

## Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:

- Рабочее знание C#
- Установлен Aspose.TeX для .NET.
- Входной ZIP-архив для рабочего каталога.
- Выходной ZIP-архив для вывода через терминал

## Импортировать пространства имен

Прежде чем углубиться в код, обязательно включите в свой проект C# необходимые пространства имен:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Pdf;
using System.IO;
```

Теперь давайте разобьем пример на несколько шагов, которые помогут вам пройти весь процесс.

## Шаг 1. Откройте входные и выходные ZIP-потоки

```csharp
using (Stream inZipStream = File.Open(Path.Combine("Your Input Directory", "zip-in.zip"), FileMode.Open))
using (Stream outZipStream = File.Open(Path.Combine("Your Output Directory", "terminal-out-to-zip.zip"), FileMode.Create))
{
    // Код для шага 1 находится здесь
}
```

## Шаг 2. Установите параметры преобразования

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
options.JobName = "terminal-output-to-zip";
options.InputWorkingDirectory = new InputZipDirectory(inZipStream, "in");
options.OutputWorkingDirectory = new OutputZipDirectory(outZipStream);
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## Шаг 3: Определите параметры сохранения

```csharp
options.SaveOptions = new PdfSaveOptions();
```

## Шаг 4. Запустите задание TeX

```csharp
new TeXJob("hello-world", new PdfDevice(), options).Run();
```

## Шаг 5. Завершите выходной ZIP-архив

```csharp
((OutputZipDirectory)options.OutputWorkingDirectory).Finish();
```

## Заключение

Поздравляем! Вы успешно научились переопределять имя задания и записывать вывод терминала в ZIP-файл с помощью Aspose.TeX для .NET. Этот метод может быть невероятно полезен при работе с документами TeX в ваших приложениях C#.

## Часто задаваемые вопросы

### Вопрос 1: Могу ли я использовать Aspose.TeX для .NET с другими языками .NET, такими как VB.NET?

О1: Да, Aspose.TeX для .NET совместим со всеми языками .NET.

### Вопрос 2. Где я могу найти дополнительную документацию по Aspose.TeX для .NET?

 A2: Посетите[документация](https://reference.aspose.com/tex/net/) для получения подробной информации.

### В3: Как я могу получить временную лицензию на Aspose.TeX?

 A3: Получите[временная лицензия](https://purchase.aspose.com/temporary-license/) в целях тестирования.

### Вопрос 4: Существует ли форум сообщества для поддержки Aspose.TeX?

 A4: Да, присоединяйтесь к[Форум Aspose.TeX](https://forum.aspose.com/c/tex/47) для поддержки сообщества.

### Вопрос 5: Где я могу приобрести Aspose.TeX для .NET?

 A5: Вы можете купить Aspose.TeX.[здесь](https://purchase.aspose.com/buy).