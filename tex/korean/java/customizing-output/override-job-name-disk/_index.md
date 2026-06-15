---
date: 2026-02-12
description: Aspose.TeX를 사용하여 Java에서 콘솔 출력을 캡처하고, 터미널 출력을 파일에 기록하며, 작업 이름을 재정의하는 방법을
  배웁니다. 이 단계별 가이드는 또한 Java에서 콘솔 출력을 리디렉션하는 방법을 다룹니다.
linktitle: Write Terminal Output to File and Override Job Name in Java
second_title: Aspose.TeX Java API
title: Java에서 콘솔 출력 캡처 및 작업 이름 재정의 방법
url: /ko/java/customizing-output/override-job-name-disk/
weight: 10
---

.

Will keep bold formatting.

Let's write.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 터미널 출력 파일에 저장 및 Java에서 작업 이름 재정의하기

## 소개

이 튜토리얼에서는 Aspose.TeX for Java로 TeX 파일을 처리하면서 **콘솔 출력을 캡처하는 방법**을 알아봅니다. 터미널 출력을 파일에 기록하고, 기본 작업 이름을 재정의하며, 콘솔 출력을 Java에서 리다이렉트하여 로그를 쉽게 찾고 분석할 수 있는 방법을 단계별로 안내합니다. 이러한 기술은 배치 변환이나 자동화된 문서 파이프라인에서 신뢰할 수 있는 로깅이 필요할 때 필수적입니다.

## 빠른 답변
- **작업 이름을 변경할 수 있나요?** 예, 작업을 실행하기 전에 `options.setJobName(...)`를 사용하세요.  
- **터미널 출력은 어디에 저장되나요?** 출력 작업 디렉터리의 `<job_name>.trm` 파일에 저장됩니다.  
- **이 기능에 라이선스가 필요합니까?** 유효한 Aspose.TeX 라이선스가 있으면 동작합니다; 무료 체험판도 제공됩니다.  
- **출력 파일 형식은 무엇인가요?** 콘솔 출력을 그대로 반영한 일반 텍스트 터미널 로그입니다.  
- **다른 출력 장치와 호환되나요?** 물론입니다—로그가 작성된 후에는 텍스트 파일을 읽을 수 있는 모든 도구로 처리할 수 있습니다.

## Aspose.TeX에서 **콘솔 캡처**란 무엇인가요?

콘솔 출력을 캡처한다는 것은 표준 출력 스트림(터미널)에 normally 표시되는 모든 내용을 디스크의 파일로 리다이렉트하는 것을 의미합니다. Aspose.TeX에서는 `OutputFileTerminal`을 구성하고 이를 변환 옵션에 할당함으로써 손쉽게 구현할 수 있습니다.

## 작업 이름을 재정의하는 이유는?

작업 이름을 재정의하면 각 변환 실행에 고유 식별자를 부여할 수 있습니다. 이렇게 하면 생성된 로그 파일(`*.trm`) 및 기타 아티팩트를 추적하기 쉬워지며, 특히 여러 작업을 병렬로 실행하거나 배치 프로세스를 예약할 때 유용합니다.

## 사전 요구 사항

- Java 프로그래밍에 대한 기본 지식.  
- Aspose.TeX for Java 설치 ([Aspose.TeX Java 문서](https://reference.aspose.com/tex/java/)에서 다운로드).  
- 샘플을 컴파일하고 실행할 수 있는 Java IDE 또는 빌드 도구(Maven/Gradle).

## 패키지 가져오기

시작하려면 Java 프로젝트에 필요한 패키지를 가져옵니다. Java 파일에 다음 import 문을 포함하세요:

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

> **Pro tip:** Aspose 샘플 유틸리티의 헬퍼 메서드가 필요하지 않다면 `util.Utils` import를 제거하여 코드를 깔끔하게 유지하세요.

## Java에서 콘솔 출력 캡처하기

아래 단계별 가이드는 변환 옵션을 구성하고, 작업 이름을 재정의하며, 터미널 출력을 디스크 파일에 기록하는 방법을 정확히 보여줍니다.

### 단계 1: 변환 옵션 생성

먼저 기본 ObjectTeX 구성을 사용하는 `TeXOptions` 인스턴스를 생성합니다. 이 객체는 변환 프로세스의 모든 설정을 보관합니다.

```java
// ExStart:OverrideJobName-WriteTerminalOutputToFileSystem
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
// ExEnd:OverrideJobName-WriteTerminalOutputToFileSystem
```

### 단계 2: 작업 이름 및 작업 디렉터리 지정

다음으로 사용자 정의 작업 이름을 설정하고 입력·출력 파일이 위치할 디렉터리를 정의합니다. 작업 이름을 지정하지 않으면 `TeXJob` 생성자의 첫 번째 인수가 자동으로 작업 이름이 됩니다.

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

> **작업 이름을 재정의하는 이유**  
> 작업 이름을 재정의하면 로그 파일 및 생성된 아티팩트를 쉽게 식별할 수 있어, 여러 작업을 병렬로 실행하거나 배치 처리를 자동화할 때 특히 유용합니다.

### 단계 3: 터미널 출력을 파일 시스템에 기록

Aspose.TeX에 콘솔에 normally 표시되는 모든 내용을 캡처하여 파일에 기록하도록 지시합니다. 파일 이름은 `<job_name>.trm`이며, 앞서 정의한 출력 작업 디렉터리에 저장됩니다.

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### 단계 4: 작업 실행

마지막으로 원하는 입력 파일(여기서는 간단한 “hello‑world” 예시)과 XPS 렌더링 장치를 사용해 `TeXJob`을 생성합니다. 그런 다음 `run()`을 호출하여 변환을 실행합니다.

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
```

작업이 완료되면 **Your Output Directory** 안에 `overridden-job-name.trm` 파일이 생성되어 전체 터미널 로그를 확인할 수 있습니다.

## 일반적인 함정 및 문제 해결

| 문제 | 원인 | 해결 방법 |
|------|------|-----------|
| **`.trm` 파일이 생성되지 않음** | `setTerminalOut`을 호출하지 않았거나 출력 디렉터리가 없음 | 출력 디렉터리가 존재하는지 확인하고 `options.setTerminalOut(...)`가 `job.run()` 전에 실행되었는지 검증하세요. |
| **파일 이름이 재정의된 이름이 아님** | 작업 이름이 올바르게 설정되지 않음 | `options.setJobName("your‑desired‑name")`를 `TeXJob` 생성 **이전**에 호출했는지 확인하세요. |
| **로그 파일이 비어 있음** | 로깅 시작 전에 예외가 발생 | `job.run()`을 try‑catch 블록으로 감싸고, 누락된 폰트나 잘못된 TeX 소스와 같은 예외 스택 트레이스를 확인하세요. |

## 자주 묻는 질문

**Q: Aspose.TeX for Java를 다른 Java 라이브러리와 함께 사용할 수 있나요?**  
A: 예, Aspose.TeX는 다른 Java 라이브러리와 원활히 통합되도록 설계되어 PDF, 이미지, 데이터베이스 유틸리티 등을 동일 워크플로우에서 결합할 수 있습니다.

**Q: Aspose.TeX for Java에 대한 지원은 어디서 받을 수 있나요?**  
A: 커뮤니티 도움을 원하면 [Aspose.TeX 포럼](https://forum.aspose.com/c/tex/47)을 방문하거나 Aspose 지원 포털을 통해 지원 티켓을 열 수 있습니다.

**Q: Aspose.TeX for Java의 무료 체험판이 있나요?**  
A: 물론입니다. [Aspose.TeX 무료 체험 페이지](https://releases.aspose.com/)에서 완전 기능 체험판을 다운로드할 수 있습니다.

**Q: 테스트용 임시 라이선스를 어떻게 받을 수 있나요?**  
A: [Aspose 임시 라이선스](https://purchase.aspose.com/temporary-license/) 양식을 통해 30일 평가 라이선스를 신청하세요.

**Q: 영구 라이선스는 어디서 구매하나요?**  
A: [Aspose.TeX 구매 페이지](https://purchase.aspose.com/buy)에서 직접 라이선스를 구매할 수 있습니다.

---

**마지막 업데이트:** 2026-02-12  
**테스트 환경:** Aspose.TeX 24.11 for Java  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}