---
title: Набор текста TeX в XPS на Java с внешним потоком
linktitle: Набор текста TeX в XPS на Java с внешним потоком
second_title: API Aspose.TeX Java
description: Узнайте, как верстать TeX в XPS на Java с помощью Aspose.TeX. Ознакомьтесь с пошаговыми инструкциями по бесперебойной обработке документов.
weight: 10
url: /ru/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Набор текста TeX в XPS на Java с внешним потоком

## Введение

В мире разработки Java Aspose.TeX выделяется как мощный инструмент для верстки документов TeX в различные форматы, включая XPS. Если вы хотите расширить возможности обработки документов в своем Java-приложении, это руководство специально для вас. В этом пошаговом руководстве мы покажем вам процесс верстки TeX в XPS с использованием Aspose.TeX для Java с внешним потоком.

## Предварительные условия

Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:

-  Комплект разработки Java (JDK): убедитесь, что в вашей системе установлена Java. Вы можете скачать его с[здесь](https://www.oracle.com/java/technologies/javase-downloads.html).

-  Aspose.TeX для Java: Загрузите и установите Aspose.TeX для Java. Вы можете найти ссылку для скачивания[здесь](https://releases.aspose.com/tex/java/).

## Импортировать пакеты

Начните с импорта необходимых пакетов, чтобы начать процесс преобразования TeX в XPS. Включите следующий фрагмент кода в свой проект Java:

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

## Шаг 1. Настройте параметры преобразования

Начните с создания параметров преобразования для формата ObjectTeX по умолчанию, используя следующий код:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

Это закладывает основу для процесса набора текста.

## Шаг 2. Укажите имя задания и каталоги.

Определите имя задания и установите входные и выходные рабочие каталоги:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Обязательно замените заполнители, такие как «Ваш входной каталог», фактическими путями к каталогам.

## Шаг 3. Настройте выход терминала

Укажите, что вывод терминала должен быть записан в файл в выходном рабочем каталоге:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

Этот шаг обеспечивает сбор подробных журналов для отладки.

## Шаг 4: Откройте выходной поток

Откройте поток для записи верстаемого документа XPS:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

Замените «Ваш выходной каталог» соответствующим путем.

## Шаг 5. Запустите задание

Выполните задание преобразования TeX в XPS:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

На этом процесс завершается, и вы найдете набранный документ XPS в указанном выходном каталоге.

## Заключение

Поздравляем! Вы успешно набрали TeX в XPS на Java с помощью Aspose.TeX. Это открывает мир возможностей для обработки документов в ваших Java-приложениях. Поэкспериментируйте с различными файлами TeX и изучите разнообразные функции, предлагаемые Aspose.TeX.

## Часто задаваемые вопросы

### Вопрос 1: Могу ли я использовать Aspose.TeX для Java с другими форматами документов?

A1: Aspose.TeX в первую очередь ориентирован на обработку документов, связанных с TeX. Для других форматов изучите обширный ассортимент продукции Aspose.

### В2: Доступна ли пробная версия?

 О2: Да, вы можете испытать Aspose.TeX, загрузив бесплатную пробную версию.[здесь](https://releases.aspose.com/).

### В3: Где я могу найти подробную документацию?

 A3: обратитесь к документации[здесь](https://reference.aspose.com/tex/java/) для получения подробной информации и примеров.

### Вопрос 4: Как мне получить поддержку или обратиться за помощью?

 A4: Посетите форум Aspose.TeX.[здесь](https://forum.aspose.com/c/tex/47)за поддержку сообщества и обсуждения.

### Вопрос 5: Могу ли я получить временную лицензию для целей тестирования?

 О5: Да, вы можете приобрести временную лицензию.[здесь](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
