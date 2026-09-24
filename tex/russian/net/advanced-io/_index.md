---
date: 2026-09-24
description: Узнайте, как настроить каталог ввода TeX, потоки, изображения и ввод
  из терминала с помощью Aspose.TeX для .NET на C#.
keywords:
- configure tex input directory
- add image stream tex
- add images from stream
lastmod: 2026-09-24
linktitle: Продвинутый ввод и вывод Aspose.TeX
og_description: Настройте каталог ввода TeX, добавьте потоки изображений и обработайте
  ввод из терминала с Aspose.TeX для .NET на C#. Узнайте пошагово.
og_image_alt: Guide showing how to configure TeX input directory and streams in Aspose.TeX
  for .NET
og_title: Настройка каталога ввода TeX – Руководство по продвинутому Aspose.TeX
schemas:
- author: Aspose
  dateModified: '2026-09-24'
  description: Learn how to configure TeX input directory, streams, images, and terminal
    input using Aspose.TeX for .NET in C#.
  headline: Configure TeX input directory – Advanced Aspose.TeX Input and Output
  type: TechArticle
- description: Learn how to configure TeX input directory, streams, images, and terminal
    input using Aspose.TeX for .NET in C#.
  name: Configure TeX input directory – Advanced Aspose.TeX Input and Output
  steps:
  - name: instantiate TeXInputOptions
    text: Assign the base folder that holds the primary TeX source.
  - name: add extra search paths
    text: If your project stores figures in a separate folder (e.g., *Images*), call
      `AddSearchPath` to include it.
  - name: hand the options to the processor
    text: Create a `TeXProcessor`, provide the configured options, and invoke `Process`
      or `Render`.
  type: HowTo
- questions:
  - answer: Yes—you can create a new `TeXInputOptions` instance with a different `BaseFolder`
      and pass it to a fresh `TeXProcessor` whenever you need to reconfigure.
    question: Can I change the input directory at runtime?
  - answer: Retrieve the image as a `byte[]`, wrap it in a `MemoryStream`, and call
      `TeXInputOptions.AddImage("image.png", stream)`. The name must match the reference
      in your `.tex` file.
    question: How do I add images that are stored in a database?
  - answer: Absolutely. Convert the incoming string to a `MemoryStream`, set it as
      the source for `TeXProcessor`, and render directly to your desired output format.
    question: Is it possible to process LaTeX code received from a web API without
      saving a file?
  - answer: Dispose of any streams you create, and for large workloads invoke `TeXProcessor.Cleanup()`
      to free native resources.
    question: Do I need to call any cleanup methods after processing?
  - answer: The two tutorial links above contain full code samples that demonstrate
      each scenario in detail, including error handling and performance tips.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.TeX .NET API
tags:
- Aspose.TeX
- input directory
- C# document processing
title: Настройка каталога ввода TeX – Продвинутый ввод и вывод Aspose.TeX
url: /ru/net/advanced-io/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Настройка каталога ввода TeX в Aspose.TeX для .NET

Aspose.TeX for .NET позволяет встраивать полнофункциональную обработку TeX непосредственно в ваши C#‑приложения. В этом руководстве вы узнаете, как **настроить каталог ввода TeX**, подавать LaTeX‑контент из потоков и добавлять изображения без обращения к файловой системе. Если вам нужен точный контроль над тем, где движок ищет файлы `.tex` и ресурсы, вы попали по адресу.

## Быстрые ответы
- **Что означает «configure tex input directory»?**  
  Он сообщает Aspose.TeX, где искать основной файл `.tex`, вспомогательные файлы и графику.
- **Какой класс определяет пути ввода?**  
  `TeXInputOptions` хранит базовую папку и любые дополнительные пути поиска.
- **Могу ли я загрузить изображение из поток памяти?**  
  Да — используйте `TeXInputOptions.AddImage` с экземпляром `Stream`.
- **Можно ли компилировать LaTeX‑код, предоставленный во время выполнения?**  
  Безусловно — передайте `MemoryStream`, содержащий исходный текст, процессору.
- **Нужна ли лицензия для использования в продакшене?**  
  Для не‑оценочных развертываний требуется действующая лицензия Aspose.TeX.

## Что такое TeXInputOptions?
`TeXInputOptions` — это объект конфигурации, определяющий базовую папку и дополнительные пути поиска ресурсов TeX. Правильная настройка устраняет ошибки «file not found» и позволяет поддерживать порядок в ресурсах.

## Как настроить каталог ввода tex?
`TeXInputOptions` — это объект конфигурации, который указывает базовую папку и дополнительные пути поиска ресурсов TeX. Загрузите основной документ и сообщите процессору, где искать всё, всего в несколько строк. Этот прямой ответ объясняет основные шаги перед любыми дополнительными деталями.

Создайте экземпляр `TeXInputOptions`, задайте `BaseFolder` в папку, содержащую ваш основной файл `.tex`, добавьте любые подпапки, где находятся изображения или вспомогательные файлы, и передайте параметры в `TeXProcessor`. Движок затем автоматически разрешит все относительные ссылки.

### Шаг 1: создать экземпляр TeXInputOptions
Назначьте базовую папку, содержащую основной источник TeX.

### Шаг 2: добавить дополнительные пути поиска
Если ваш проект хранит изображения в отдельной папке (например, *Images*), вызовите `AddSearchPath`, чтобы добавить её.

### Шаг 3: передать параметры процессору
Создайте `TeXProcessor`, передайте настроенные параметры и вызовите `Process` или `Render`.

## Как добавить изображения с помощью Aspose.TeX
Изображения, указанные в TeX‑файле, могут быть предоставлены либо через папку, либо напрямую из потока. Подача из потока полезна, когда изображения хранятся в базе данных или генерируются «на лету». `AddImage(string name, Stream data)` регистрирует поток изображения с заданным именем файла для использования в TeX‑документе. Этот метод позволяет избежать временных файлов и ускоряет обработку.

## Как обрабатывать потоки в Aspose.TeX
Когда ваш LaTeX‑источник генерируется динамически — возможно, из ввода пользователя или веб‑сервиса — вы можете передать его напрямую процессору без записи в файл. `TeXProcessor` обрабатывает TeX‑контент и может принимать `MemoryStream`, содержащий исходный LaTeX‑код. Оберните строку LaTeX в `MemoryStream`, укажите её как исходный поток в `TeXProcessor` и запустите конвертацию. Эта техника одинаково эффективна для облачно‑нативных сервисов, где ввод‑вывод на диск дорогой.

## Почему использовать Aspose.TeX для расширенного ввода/вывода?
Aspose.TeX поддерживает **30+ форматов ввода и вывода** (включая PDF, PNG, SVG) и может рендерить документы в сотни страниц без загрузки всего файла в память. Его поток‑ориентированный дизайн снижает накладные расходы ввода/вывода до 40 % по сравнению с файловыми рабочими процессами, делая его идеальным для высокопроизводительных серверных приложений.

## Требования
- .NET 6.0 или новее (библиотека также работает с .NET Core 3.1+ и .NET Framework 4.6.1+)
- Пакет NuGet Aspose.TeX для .NET (версия 24.11 или новее)
- Действующая лицензия Aspose.TeX для продакшн‑использования

## Изучите Aspose.TeX: шлюз к продвинутой обработке документов
Чтобы увидеть конфигурацию в действии, следуйте нашему пошаговому руководству **[Specify Required Input Directory for Aspose.TeX (C#)](./required-input-directory-csharp/)**. Этот урок проведёт вас через создание объекта `TeXInputOptions` и рендеринг PDF‑вывода.  
**[Specify Required Input Directory for Aspose.TeX (C#)](./required-input-directory-csharp/)**

## Освоение потоков, изображений и терминального ввода в Aspose.TeX для C#
Для более глубокого погружения в подачу LaTeX из памяти, добавление изображений через потоки и использование терминального ввода, ознакомьтесь с **[Master Streams, Images, & Terminal Input in Aspose.TeX for C#](./stream-input-image-output-terminal-input-csharp/)**. Он показывает, как интегрировать Aspose.TeX в веб‑API, фоновые сервисы и консольные инструменты.  
**[Master Streams, Images, & Terminal Input in Aspose.TeX for C#](./stream-input-image-output-terminal-input-csharp/)**

## Распространённые проблемы и решения
- **Ошибки «File not found»** – Убедитесь, что `BaseFolder` указывает на правильный каталог и что все дополнительные пути поиска добавлены до рендеринга.
- **Изображения не загружаются** – Убедитесь, что имя изображения в `AddImage` точно совпадает с именем, используемым в TeX‑source, включая расширение файла.
- **Резкое увеличение использования памяти** – При обработке очень больших документов вызывайте `TeXProcessor.Cleanup()` после рендеринга, чтобы освободить неуправляемые ресурсы.

## Часто задаваемые вопросы

**Q: Можно ли изменить каталог ввода во время выполнения?**  
A: Да — вы можете создать новый экземпляр `TeXInputOptions` с другим `BaseFolder` и передать его свежему `TeXProcessor`, когда понадобится переустановить конфигурацию.

**Q: Как добавить изображения, хранящиеся в базе данных?**  
A: Получите изображение как `byte[]`, оберните его в `MemoryStream` и вызовите `TeXInputOptions.AddImage("image.png", stream)`. Имя должно точно соответствовать ссылке в вашем файле `.tex`.

**Q: Можно ли обработать LaTeX‑код, полученный из веб‑API, без сохранения файла?**  
A: Безусловно. Преобразуйте полученную строку в `MemoryStream`, укажите её как источник для `TeXProcessor` и рендерите напрямую в нужный формат вывода.

**Q: Нужно ли вызывать какие‑либо методы очистки после обработки?**  
A: Освободите любые созданные потоки, а при больших нагрузках вызывайте `TeXProcessor.Cleanup()` для освобождения нативных ресурсов.

**Q: Где можно найти более продвинутые примеры?**  
A: Оба вышеуказанных учебных руководства содержат полные образцы кода, демонстрирующие каждый сценарий подробно, включая обработку ошибок и рекомендации по производительности.

---

**Последнее обновление:** 2026-09-24  
**Тестировано с:** Aspose.TeX 24.11 for .NET  
**Автор:** Aspose

## Связанные руководства

- [Получить поток TeX‑файла (C#) с использованием Aspose.TeX API Required Input Directory](/tex/net/advanced-io/required-input-directory-csharp/)
- [Создать XPS из TeX с помощью файловых систем – Aspose.TeX для .NET](/tex/net/file-input-output/filesystem-input-xps-output/)
- [Конвертировать LaTeX в PNG с использованием Aspose.TeX для .NET – обработка файловой системы и ZIP‑вводов](/tex/net/file-input-output/required-inputs-from-filesystem-and-zip/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}