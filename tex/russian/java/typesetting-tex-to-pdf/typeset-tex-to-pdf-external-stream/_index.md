---
title: Верстка TeX в PDF на Java с внешним потоком
linktitle: Верстка TeX в PDF на Java с внешним потоком
second_title: API Aspose.TeX Java
description: Узнайте, как верстать TeX в PDF на Java, используя внешние потоки с помощью Aspose.TeX. Следуйте нашему пошаговому руководству для бесшовной интеграции.
weight: 10
url: /ru/java/typesetting-tex-to-pdf/typeset-tex-to-pdf-external-stream/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Верстка TeX в PDF на Java с внешним потоком

## Введение

В мире разработки Java создание PDF-файлов из файлов TeX является обычным требованием. Aspose.TeX для Java упрощает этот процесс, предоставляя эффективное решение для верстки TeX в PDF. В этом уроке мы познакомим вас с этапами верстки TeX в PDF с использованием внешних потоков. К концу вы будете иметь четкое представление о том, как беспрепятственно реализовать этот процесс в ваших Java-приложениях.

## Предварительные условия

Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:

- Aspose.TeX для Java: убедитесь, что у вас установлена библиотека Aspose.TeX для Java. Вы можете скачать его с сайта[Документация Aspose.TeX для Java](https://reference.aspose.com/tex/java/).

- Каталоги ввода и вывода: подготовьте каталоги ввода и вывода. Вы можете использовать предоставленную ссылку для скачивания, чтобы получить необходимые файлы.

## Импортировать пакеты

Начните с импорта необходимых пакетов в ваш Java-проект:

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

## Шаг 1. Откройте потоки ввода и вывода.

Начните с открытия потоков для входного ZIP-архива (действующего как входной рабочий каталог) и выходного ZIP-архива (служащего выходным рабочим каталогом). Обязательно замените «Ваш входной каталог» и «Ваш выходной каталог» фактическими путями к каталогам.

```java
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "typeset-pdf-to-external-stream.zip");
```

## Шаг 2. Настройте TeXOptions

Создайте объект TeXOptions и настройте его в соответствии со своими требованиями. Задайте имя задания, входной рабочий каталог, выходной рабочий каталог и другие параметры.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("typeset-pdf-to-external-stream");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
options.setSaveOptions(new PdfSaveOptions());
```

## Шаг 3. Преобразование TeX в PDF

Теперь откройте поток, чтобы записать выходной PDF-файл в нужное место. Вы можете записать его в локальный файл или непосредственно в выходной ZIP-архив.

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + "file-name.pdf");
try {
    new TeXJob("hello-world", new PdfDevice(stream), options).run();
} finally {
    stream.close();
}
```

## Шаг 4. Завершите выходной ZIP-архив

Завершите выходной ZIP-архив, чтобы завершить процесс верстки.

```java
((OutputZipDirectory)options.getOutputWorkingDirectory()).finish();
```

## Заключение

Поздравляем! Вы успешно набрали TeX в PDF на Java, используя внешние потоки с помощью Aspose.TeX. Это руководство обеспечивает надежную основу для беспрепятственного внедрения преобразования TeX в PDF в ваши приложения Java.

## Часто задаваемые вопросы

### Вопрос 1: Могу ли я настроить имя выходного PDF-файла?

 A1: Да, вы можете изменить`options.setJobName("typeset-pdf-to-external-stream")` чтобы установить желаемое имя задания.

### Вопрос 2. Как устранить распространенные проблемы во время набора текста?

 A2: Посетите[Форум Aspose.TeX](https://forum.aspose.com/c/tex/47) за общественную поддержку и помощь.

### Вопрос 3: Существует ли бесплатная пробная версия Aspose.TeX для Java?

 О3: Да, вы можете получить доступ к бесплатной пробной версии.[здесь](https://releases.aspose.com/).

### Вопрос 4. Где я могу найти дополнительную документацию и примеры?

 A4: Изучите всестороннее[Документация Aspose.TeX](https://reference.aspose.com/tex/java/) для получения подробной информации.

### В5: Могу ли я получить временную лицензию на Aspose.TeX?

 О5: Да, вы можете запросить временную лицензию.[здесь](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
