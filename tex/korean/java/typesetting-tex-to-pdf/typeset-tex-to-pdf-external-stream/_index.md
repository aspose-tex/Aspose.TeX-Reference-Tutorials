---
title: 외부 스트림을 사용하여 Java에서 TeX를 PDF로 조판
linktitle: 외부 스트림을 사용하여 Java에서 TeX를 PDF로 조판
second_title: Aspose.TeX 자바 API
description: Aspose.TeX가 포함된 외부 스트림을 사용하여 Java에서 TeX를 PDF로 조판하는 방법을 알아보세요. 원활한 통합을 위한 단계별 가이드를 따르세요.
weight: 10
url: /ko/java/typesetting-tex-to-pdf/typeset-tex-to-pdf-external-stream/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 외부 스트림을 사용하여 Java에서 TeX를 PDF로 조판

## 소개

Java 개발 세계에서는 TeX 파일에서 PDF를 생성하는 것이 일반적인 요구 사항입니다. Aspose.TeX for Java는 이 프로세스를 단순화하여 TeX를 PDF로 조판하기 위한 효율적인 솔루션을 제공합니다. 이 튜토리얼에서는 외부 스트림을 사용하여 TeX를 PDF로 조판하는 단계를 안내합니다. 결국에는 Java 애플리케이션에서 이 프로세스를 원활하게 구현하는 방법을 명확하게 이해하게 될 것입니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- Java용 Aspose.TeX: Java용 Aspose.TeX 라이브러리가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[Java 문서용 Aspose.TeX](https://reference.aspose.com/tex/java/).

- 입력 및 출력 디렉터리: 입력 및 출력 디렉터리를 준비합니다. 제공된 다운로드 링크를 사용하여 필요한 파일을 얻을 수 있습니다.

## 패키지 가져오기

필요한 패키지를 Java 프로젝트로 가져오는 것부터 시작하세요.

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

## 1단계: 입력 및 출력 스트림 열기

입력 ZIP 아카이브(입력 작업 디렉터리 역할) 및 출력 ZIP 아카이브(출력 작업 디렉터리 역할)에 대한 스트림을 여는 것부터 시작합니다. "입력 디렉터리"와 "출력 디렉터리"를 실제 디렉터리 경로로 바꾸세요.

```java
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "typeset-pdf-to-external-stream.zip");
```

## 2단계: TeXOptions 구성

TeXOptions 개체를 생성하고 요구 사항에 따라 구성합니다. 작업 이름, 입력 작업 디렉터리, 출력 작업 디렉터리 및 기타 옵션을 설정합니다.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("typeset-pdf-to-external-stream");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
options.setSaveOptions(new PdfSaveOptions());
```

## 3단계: TeX를 PDF로 조판

이제 스트림을 열어 출력 PDF를 원하는 위치에 씁니다. 로컬 파일에 쓰거나 출력 ZIP 아카이브에 직접 쓰도록 선택할 수 있습니다.

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + "file-name.pdf");
try {
    new TeXJob("hello-world", new PdfDevice(stream), options).run();
} finally {
    stream.close();
}
```

## 4단계: 출력 ZIP 아카이브 마무리

조판 프로세스를 완료하려면 출력 ZIP 아카이브를 완료하세요.

```java
((OutputZipDirectory)options.getOutputWorkingDirectory()).finish();
```

## 결론

축하해요! Aspose.TeX가 포함된 외부 스트림을 사용하여 Java에서 TeX를 PDF로 성공적으로 조판했습니다. 이 튜토리얼은 TeX에서 PDF로의 변환을 Java 애플리케이션에 원활하게 통합하기 위한 강력한 기반을 제공합니다.

## FAQ

### Q1: 출력 PDF의 파일 이름을 사용자 정의할 수 있습니까?

 A1: 예, 수정할 수 있습니다.`options.setJobName("typeset-pdf-to-external-stream")` 원하는 작업 이름을 설정하세요.

### Q2: 조판 중 일반적인 문제를 해결하려면 어떻게 해야 합니까?

 A2: 다음을 방문하세요.[Aspose.TeX 포럼](https://forum.aspose.com/c/tex/47) 지역 사회 지원 및 지원을 위해.

### Q3: Aspose.TeX for Java에 대한 무료 평가판이 있습니까?

 A3: 예, 무료 평가판에 액세스할 수 있습니다.[여기](https://releases.aspose.com/).

### Q4: 추가 문서와 예제는 어디에서 찾을 수 있습니까?

 A4: 포괄적인 탐색[Aspose.TeX 문서](https://reference.aspose.com/tex/java/) 자세한 정보를 보려면.

### Q5: Aspose.TeX에 대한 임시 라이센스를 얻을 수 있습니까?

 A5: 네, 임시 라이센스를 요청할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
