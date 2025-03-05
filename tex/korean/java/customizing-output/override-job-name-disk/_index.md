---
title: 작업 이름 재정의 및 Java에서 터미널 출력 쓰기
linktitle: 작업 이름 재정의 및 Java에서 터미널 출력 쓰기
second_title: Aspose.TeX 자바 API
description: Java용 Aspose.TeX를 사용하여 작업 이름을 재정의하고 터미널 출력을 작성하는 방법에 대한 단계별 가이드를 살펴보세요. 강력한 사용자 정의 옵션으로 문서 처리를 강화하세요.
type: docs
weight: 10
url: /ko/java/customizing-output/override-job-name-disk/
---
## 소개

Aspose.TeX for Java는 TeX 파일 작업을 위한 강력한 기능을 제공하므로 개발자는 TeX 문서 처리를 조작하고 사용자 정의할 수 있습니다. 이 튜토리얼에서는 Java에서 Aspose.TeX를 사용하여 작업 이름을 재정의하고 터미널 출력을 파일 시스템에 쓰는 프로세스를 안내합니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- Java 프로그래밍에 대한 실무 지식.
-  Java용 Aspose.TeX가 설치되었습니다. 다음에서 다운로드할 수 있습니다.[Aspose.TeX 자바 문서](https://reference.aspose.com/tex/java/).

## 패키지 가져오기

시작하려면 필요한 패키지를 Java 프로젝트로 가져옵니다. Java 파일에 다음 가져오기를 포함합니다.

```java
package com.aspose.tex.OverridenJobNameAndTerminalOutputWrittenToDisk;

import java.io.IOException;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

## 작업 이름 재정의 및 터미널 출력 쓰기

### 1단계: 전환 옵션 생성

ObjectTeX 엔진 확장 시 기본 ObjectTeX 형식에 대한 변환 옵션을 만드는 것부터 시작하세요. 다음 코드 조각을 사용하세요.

```java
//ExStart:OverrideJobName-WriteTerminalOutputToFileSystem
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

### 2단계: 작업 이름 및 작업 디렉터리 지정

작업 이름, 입력 작업 디렉터리, 출력 작업 디렉터리를 지정합니다. 작업 이름이 지정되지 않으면 TeXJob 생성자의 첫 번째 인수가 작업 이름으로 사용됩니다. 다음 코드 조각을 사용하세요.

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### 3단계: 파일 시스템에 터미널 출력 쓰기

 터미널 출력이 출력 작업 디렉터리의 파일에 기록되어야 함을 지정합니다. 파일 이름은`<job_name>.trm`. 다음 코드를 추가하세요.

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### 4단계: 작업 실행

지정된 옵션과 작업 이름을 사용하여 TeX 작업을 실행합니다. 방법은 다음과 같습니다.

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
// ExEnd:OverrideJobName-WriteTerminalOutputToFileSystem
```

축하해요! Java에서 Aspose.TeX를 사용하여 작업 이름을 재정의하고 터미널 출력을 파일 시스템에 기록했습니다.

## 결론

이 튜토리얼에서는 Java용 Aspose.TeX를 활용하여 작업 이름을 재정의하고 터미널 출력을 캡처하는 방법을 살펴보았습니다. 이러한 기능을 통해 개발자는 TeX 문서 처리를 세밀하게 제어할 수 있어 사용자 정의 및 유연성이 향상됩니다.

## FAQ

### Q1: Aspose.TeX for Java를 다른 Java 라이브러리와 함께 사용할 수 있습니까?

A1: 예, Aspose.TeX for Java는 다른 Java 라이브러리와 원활하게 통합되어 문서 처리 기능을 향상시키도록 설계되었습니다.

### Q2: Java용 Aspose.TeX에 대한 지원은 어디서 찾을 수 있나요?

 A2: 다음을 방문하세요.[Aspose.TeX 포럼](https://forum.aspose.com/c/tex/47) 귀하가 직면할 수 있는 모든 문제에 대한 커뮤니티 지원 및 도움을 받으십시오.

### Q3: Aspose.TeX for Java에 대한 무료 평가판이 있습니까?

 A3: 예, Java용 Aspose.TeX 무료 평가판에 액세스할 수 있습니다.[여기](https://releases.aspose.com/).

### Q4: Aspose.TeX for Java에 대한 임시 라이센스를 어떻게 얻을 수 있습니까?

 A4: 이것을 따르십시오[링크](https://purchase.aspose.com/temporary-license/) 테스트 및 평가 목적으로 임시 라이센스를 취득합니다.

### Q5: Java용 Aspose.TeX를 어디서 구입할 수 있나요?

 A5: 다음을 방문하세요.[구매 페이지](https://purchase.aspose.com/buy) Java용 Aspose.TeX 라이센스를 취득합니다.