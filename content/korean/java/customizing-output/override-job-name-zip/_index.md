---
title: 작업 이름을 재정의하고 터미널 출력을 Java의 Zip에 쓰기
linktitle: 작업 이름을 재정의하고 터미널 출력을 Java의 Zip에 쓰기
second_title: Aspose.TeX 자바 API
description: Aspose.TeX를 사용하여 작업 이름을 재정의하고 Java에서 ZIP에 터미널 출력을 작성하는 방법을 알아보세요. Java 개발자를 위한 포괄적인 튜토리얼입니다.
type: docs
weight: 11
url: /ko/java/customizing-output/override-job-name-zip/
---
## 소개

Java 개발 세계에서 Aspose.TeX는 TeX 파일 형식을 처리하는 강력한 도구로 돋보입니다. 이 튜토리얼에서는 작업 이름을 재정의하고 터미널 출력을 zip 파일에 쓰는 특정 시나리오를 자세히 살펴보겠습니다. 이 단계별 가이드는 Aspose.TeX for Java를 사용하는 프로세스를 안내합니다.

## 전제 조건

이 튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- Java 프로그래밍에 대한 기본 지식.
-  Java용 Aspose.TeX를 설치했습니다. 그렇지 않은 경우 다음에서 다운로드할 수 있습니다.[Aspose 웹 사이트](https://releases.aspose.com/tex/java/).
- Java 개발 환경을 설정하는 방법에 대한 이해.

## 패키지 가져오기

필요한 패키지를 Java 프로젝트로 가져오는 것부터 시작하세요. 이렇게 하면 작업에 필요한 Aspose.TeX 기능에 액세스할 수 있습니다.

```java
package com.aspose.tex.OverridenJobNameAndTerminalOutputWrittenToZip;

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

## 1단계: ZIP 아카이브 열기

먼저 입력 작업 디렉터리 역할을 할 ZIP 아카이브에서 스트림을 엽니다. 이는 귀하의 데이터가 처리될 아카이브입니다.

```java
// 입력 ZIP 아카이브에서 스트림 열기
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
```

## 2단계: 출력 ZIP 아카이브 열기

다음으로, 출력 작업 디렉터리 역할을 할 ZIP 아카이브에서 스트림을 엽니다. 여기에 터미널 출력이 기록됩니다.

```java
// 출력 ZIP 아카이브에서 스트림 열기
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "terminal-out-to-zip.zip");
```

## 3단계: 변환 옵션 설정

ObjectTeX 엔진 확장 시 기본 ObjectTeX 형식에 대한 변환 옵션을 생성합니다. 입력과 출력 모두에 대해 작업 이름과 ZIP 아카이브 작업 디렉터리를 지정합니다.

```java
// ObjectTeX 형식에 대한 TeX 옵션 만들기
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("terminal-output-to-zip");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
```

## 4단계: 터미널 출력 지정

 터미널 출력이 출력 작업 디렉터리의 파일에 기록되어야 함을 지정합니다. 파일 이름은`<job_name>.trm`.

```java
// 터미널 출력 설정 지정
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

## 5단계: 저장 옵션 정의 및 작업 실행

이 경우 PDF 저장 옵션과 같은 저장 옵션을 정의하십시오. TeX 작업을 실행하여 변환을 실행합니다.

```java
// 저장 옵션 정의 및 작업 실행
options.setSaveOptions(new PdfSaveOptions());
new TeXJob("hello-world", new PdfDevice(), options).run();
```

## 6단계: 출력 ZIP 아카이브 마무리

작업이 완료된 후 출력 ZIP 아카이브를 마무리하여 올바르게 완료되었는지 확인하세요.

```java
// 출력 ZIP 아카이브 마무리
((OutputZipDirectory) options.getOutputWorkingDirectory()).finish();
```

## 결론

축하해요! Aspose.TeX를 사용하여 작업 이름을 재정의하고 Java에서 ZIP 파일에 터미널 출력을 쓰는 방법을 성공적으로 배웠습니다. 이 강력한 기능은 Java 개발 프로젝트에 유연성과 효율성을 추가합니다.

## FAQ

### Q1: Aspose.TeX이 무엇인가요?

A1: Aspose.TeX는 개발자가 TeX 파일 형식으로 작업할 수 있게 해 주고 문서 처리를 위한 고급 기능을 제공하는 Java 라이브러리입니다.

### Q2: Aspose.TeX에 대한 임시 라이센스를 어떻게 얻을 수 있습니까?

 A2: 다음에서 임시 라이센스를 받을 수 있습니다.[이 링크](https://purchase.aspose.com/temporary-license/).

### Q3: Aspose.TeX 문서는 어디서 찾을 수 있나요?

 A3: 문서를 사용할 수 있습니다.[여기](https://reference.aspose.com/tex/java/).

### Q4: Aspose.TeX의 무료 평가판이 있습니까?

 A4: 예, 무료 평가판을 찾을 수 있습니다.[여기](https://releases.aspose.com/).

### Q5: Aspose.TeX에 대한 지원을 받거나 질문을 할 수 있는 곳은 어디입니까?

 A5: 다음을 방문하세요.[Aspose.TeX 포럼](https://forum.aspose.com/c/tex/47) 지원과 토론을 위해.
