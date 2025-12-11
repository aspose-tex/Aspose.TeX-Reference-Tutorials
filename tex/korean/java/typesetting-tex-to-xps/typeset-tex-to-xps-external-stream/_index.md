---
date: 2025-12-11
description: Aspose.TeX를 사용하여 Java에서 TeX를 XPS로 변환하는 방법을 배워보세요. 이 단계별 가이드는 XPS 문서 스트림을
  효율적으로 생성하는 방법을 보여줍니다.
linktitle: How to Convert TeX to XPS in Java with External Stream
second_title: Aspose.TeX Java API
title: Java에서 외부 스트림을 사용하여 TeX를 XPS로 변환하는 방법
url: /ko/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java에서 외부 스트림을 사용하여 TeX를 XPS로 변환하는 방법

## 소개

Java 애플리케이션에서 **TeX** 파일을 고품질 XPS 출력으로 **변환**해야 한다면 Aspose.TeX for Java가 작업을 간단하게 만들어 줍니다. 이 튜토리얼에서는 외부 출력 스트림을 사용하여 **TeX를 XPS 문서**로 변환하는 정확한 방법을 보여줍니다. 결과를 바로 응답, 클라우드 스토리지 서비스 또는 사용자 정의 대상에 파이프하고 싶을 때 이상적입니다. 환경 설정부터 최종 XPS 파일 작성까지 전체 과정을 단계별로 살펴보겠습니다.

## 빠른 답변
- **이 튜토리얼은 무엇을 다루나요? Aspose.TeX와 외부 스트림을 이용한 TeX → XPS 변환.  
- **필요한 주요 라이브러리는?** Aspose.TeX for Java.  
- **라이선스가 필요합니까?** 프로덕션 사용을 위해 임시 또는 정식 라이선스가 필요합니다.  
- **XPS 문서 스트림을 생성할 수 있나요?** 예 – 예제에서는 XPS를 `OutputStream`에 직접 씁니다.  
- **지원되는 Java 버전은?** JDK 8 이상 (튜토리얼은 JDK 11을 기준으로 작성).

## 사전 요구 사항

코드 작성을 시작하기 전에 다음 항목이 준비되어 있는지 확인하세요.

- Java Development Kit (JDK): 시스템에 Java가 설치되어 있어야 합니다. [여기](https://www.oracle.com/java/technologies/javase-downloads.html)에서 다운로드할 수 있습니다.

- Aspose.TeX for Java: Aspose.TeX for Java를 다운로드하고 설치합니다. 다운로드 링크는 [여기](https://releases.aspose.com/tex/java/)에 있습니다.

## 패키지 가져오기

TeX → XPS 변환을 시작하기 위해 필요한 패키지를 가져옵니다. 다음 코드를 Java 프로젝트에 포함시키세요.

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

## 단계 1: 변환 옵션 구성

다음 코드를 사용하여 기본 ObjectTeX 형식에 대한 변환 옵션을 생성합니다.

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

이 코드는 조판 프로세스의 기반을 설정합니다.

## 단계 2: 작업 이름 및 디렉터리 지정

작업 이름을 정의하고 입력 및 출력 작업 디렉터리를 설정합니다:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

"Your Input Directory"와 같은 자리표시자를 실제 디렉터리 경로로 교체하세요.

## 단계 3: 터미널 출력 구성

터미널 출력을 출력 작업 디렉터리의 파일에 기록하도록 지정합니다:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

이 단계는 디버깅을 위한 상세 로그를 캡처합니다.

## 단계 4: 출력 스트림 열기

조판된 XPS 문서를 기록할 스트림을 엽니다:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

"Your Output Directory"를 적절한 경로로 교체하세요.

## 단계 5: 작업 실행

TeX → XPS 변환 작업을 실행합니다:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

이로써 과정이 완료되며, 지정한 출력 디렉터리에서 생성된 XPS 문서를 확인할 수 있습니다.

## 일반적인 문제와 해결 방법

| 문제 | 발생 원인 | 해결 방법 |
|------|-----------|-----------|
| **FileNotFoundException** 발생 시 스트림 열기 | 출력 디렉터리 경로가 잘못되었거나 존재하지 않음 | 경로를 확인하고, 미리 디렉터리를 생성하거나 `Files.createDirectories`를 사용 |
| **NullPointerException** 발생 시 `options.getOutputWorkingDirectory()` | `setOutputWorkingDirectory`를 호출하지 않았거나 `null` 반환 | `options.setOutputWorkingDirectory`를 사용 후 호출 |
| **LicenseException** 발생 시 런타임 | 유효한 Aspose.TeX 라이선스 없이 실행 | `License license = new License(); license.setLicense("Aspose.TeX.lic");`와 같이 임시 또는 정식 라이선스 적용 |

## 자주 묻는 질문

**Q: Aspose.TeX for Java를 다른 문서 형식과 함께 사용할 수 있나요?**  
A: Aspose.TeX는 주로 TeX 관련 문서 처리에 초점을 맞추고 있습니다. 다른 형식은 Aspose의 다양한 제품군을 살펴보세요.

**Q: 체험판 버전을 제공하나요?**  
A: 예, 무료 체험판을 [여기](https://releases.aspose.com/)에서 다운로드할 수 있습니다.

**Q: 포괄적인 문서는 어디서 찾을 수 있나요?**  
A: 자세한 정보와 예제는 문서 페이지 [여기](https://reference.aspose.com/tex/java/)를 참고하세요.

**Q: 지원을 받거나 도움을 요청하려면 어떻게 해야 하나요?**  
A: Aspose.TeX 포럼 [여기](https://forum.aspose.com/c/tex/47)에서 커뮤니티 지원 및 토론을 확인하세요.

**Q: 테스트용 임시 라이선스를 받을 수 있나요?**  
A: 예, 임시 라이선스는 [여기](https://purchase.aspose.com/temporary-license/)에서 획득할 수 있습니다.

## 결론

축하합니다! 이제 Aspose.TeX와 외부 스트림을 활용해 Java에서 **TeX를 XPS 문서**로 변환하는 방법을 배웠습니다. 이 기술을 사용하면 XPS 출력이 파일 시스템이든 웹 응답이든 클라우드 버킷이든 원하는 위치로 자유롭게 전달할 수 있습니다. 다양한 TeX 소스를 실험하고, `TeXOptions`를 조정해 사용자 정의 폰트를 적용하거나, 스트림을 더 큰 문서 생성 파이프라인에 연결해 보세요.

---

**마지막 업데이트:** 2025-12-11  
**테스트 환경:** Aspose.TeX for Java 24.11 (작성 시 최신 버전)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}