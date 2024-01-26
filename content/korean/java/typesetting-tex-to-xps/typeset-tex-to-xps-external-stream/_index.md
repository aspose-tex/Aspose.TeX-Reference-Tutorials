---
title: 외부 스트림을 사용하여 Java에서 TeX를 XPS로 조판
linktitle: 외부 스트림을 사용하여 Java에서 TeX를 XPS로 조판
second_title: Aspose.TeX 자바 API
description: Aspose.TeX를 사용하여 Java에서 TeX를 XPS로 조판하는 방법을 알아보세요. 원활한 문서 처리를 위한 단계별 지침을 살펴보세요.
type: docs
weight: 10
url: /ko/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
---
## 소개

Java 개발 세계에서 Aspose.TeX는 TeX 문서를 XPS를 포함한 다양한 형식으로 조판하는 강력한 도구로 돋보입니다. Java 애플리케이션의 문서 처리 기능을 향상시키려는 경우 이 튜토리얼이 적합합니다. 이 단계별 가이드에서는 외부 스트림과 함께 Java용 Aspose.TeX를 사용하여 TeX를 XPS로 조판하는 과정을 안내합니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

-  JDK(Java Development Kit): 시스템에 Java가 설치되어 있는지 확인하십시오. 다음에서 다운로드할 수 있습니다.[여기](https://www.oracle.com/java/technologies/javase-downloads.html).

-  Java용 Aspose.TeX: Java용 Aspose.TeX를 다운로드하고 설치합니다. 다운로드 링크를 찾을 수 있습니다[여기](https://releases.aspose.com/tex/java/).

## 패키지 가져오기

TeX에서 XPS로의 변환 여정을 시작하는 데 필요한 패키지를 가져오는 것부터 시작하세요. Java 프로젝트에 다음 코드 조각을 포함합니다.

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

## 1단계: 변환 옵션 구성

다음 코드를 사용하여 기본 ObjectTeX 형식에 대한 변환 옵션을 만드는 것부터 시작하세요.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

이는 조판 프로세스의 기초를 설정합니다.

## 2단계: 작업 이름 및 디렉터리 지정

작업 이름을 정의하고 입력 및 출력 작업 디렉터리를 설정합니다.

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

"입력 디렉터리"와 같은 자리 표시자를 실제 디렉터리 경로로 바꾸십시오.

## 3단계: 터미널 출력 구성

터미널 출력이 출력 작업 디렉터리의 파일에 기록되도록 지정합니다.

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

이 단계에서는 디버깅을 위해 자세한 로그가 캡처됩니다.

## 4단계: 출력 스트림 열기

조판 XPS 문서를 작성하려면 스트림을 엽니다.

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

"Your Output Directory"를 적절한 경로로 바꾸십시오.

## 5단계: 작업 실행

TeX에서 XPS로 변환 작업을 실행합니다.

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

이것으로 프로세스가 완료되고 지정된 출력 디렉터리에서 조판된 XPS 문서를 찾을 수 있습니다.

## 결론

축하해요! Aspose.TeX를 사용하여 Java에서 TeX를 XPS로 성공적으로 조판했습니다. 이는 Java 애플리케이션에서 문서 처리에 대한 가능성의 세계를 열어줍니다. 다양한 TeX 파일을 실험하고 Aspose.TeX가 제공하는 다양한 기능을 탐색해 보세요.

## FAQ

### Q1: Aspose.TeX for Java를 다른 문서 형식과 함께 사용할 수 있습니까?

A1: Aspose.TeX는 주로 TeX 관련 문서 처리에 중점을 둡니다. 다른 형식의 경우 Aspose의 광범위한 제품 범위를 살펴보세요.

### Q2: 평가판을 사용할 수 있나요?

 A2: 예, 무료 평가판을 다운로드하여 Aspose.TeX를 경험할 수 있습니다.[여기](https://releases.aspose.com/).

### Q3: 포괄적인 문서는 어디에서 찾을 수 있습니까?

 A3: 설명서를 참조하세요[여기](https://reference.aspose.com/tex/java/) 자세한 정보와 예시를 확인하세요.

### 질문4: 지원을 받거나 도움을 구하려면 어떻게 해야 합니까?

 A4: Aspose.TeX 포럼을 방문하세요.[여기](https://forum.aspose.com/c/tex/47)커뮤니티 지원 및 토론을 위해.

### Q5: 테스트 목적으로 임시 라이선스를 얻을 수 있나요?

 A5: 예, 임시 라이센스를 취득할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).