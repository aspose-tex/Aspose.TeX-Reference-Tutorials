---
date: 2026-02-07
description: Aspose.TeX for Java를 사용하여 LaTeX 파일을 XPS로 변환해 인쇄 가능한 청구서를 Java로 만드는 방법을
  배워보세요. 간단하고 빠르며 완전한 Java 기반입니다.
linktitle: Step by Step Conversion - LaTeX to XPS Format in Java
second_title: Aspose.TeX Java API
title: Java로 인쇄 가능한 청구서 만들기 – Java에서 LaTeX를 XPS로 변환
url: /ko/java/converting-lato-xps/simple-xps-conversion/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java를 이용한 인쇄 가능한 송장 생성 - 단계별 변환: LaTeX 파일을 Java에서 XPS 형식으로 변환

## 소개

Java 애플리케이션에서 LaTeX 소스를 사용하여 **인쇄 가능한 송장**을 생성해야 한다면, 이 튜토리얼이 도움이 될 것입니다. **Aspose.TeX for Java**를 사용하면 LaTeX 파일을 렌더링하고, 복잡한 수식을 처리하며, 원하는 대로 인쇄되는 고품질 XPS 파일을 출력할 수 있습니다. 앞으로 몇 분 동안 전체 워크플로를 살펴보고, 이 방법이 송장 생성에 이상적인 이유를 설명하며, 보고서 파이프라인에 맞게 변환을 사용자 지정하는 방법을 보여드리겠습니다.

##빠른 답변
- **어떤 라이브러리를 사용해야 할까요?** Java용 Aspose.TeX
- **구현에 어떻게 될까요?** 기본 설정에는 약 10-15분 정도 소요됩니다.
- **필수 조건은 무엇입니까?** JDK 8+, Aspose.TeX JAR 및 IDE(Eclipse/IntelliJ)
- **복잡한 수식을 보낼 수 있나요?** 예 – Aspose.TeX는 LaTeX 수학 환경을 완벽하게 지원합니다.
- **프로덕션에 전력이 필요한가요?** 예, 평가판이 아닌 용도로 사용하려면 상용 라이선스가 필요합니다.

## LaTeX를 XPS로 변환하여 java로 인쇄하는 청구서를 작성하는 방법은 무엇입니까?

다음은 수행해야 할 각 단계를 대화식으로 안내하는 것입니다. 잠시 멈추고, 코드를 실험하고, 송장 레이아웃에 맞게 설정을 조정하세요.

## 도중에 있는 것은 무엇인가요?

*단계별 변환*은 LaTeX 소스 파일을 XPS 문서로 변환하는 등의 대규모 작업을 관리 가능한 작은 작업으로 나누는 안내식 증분 프로세스입니다. 각 단계를 수행하면 일반적인 함정을 피하고 코드를 깔끔하게 유지하며 전체 파이프라인을 다시 작성하지 않고도 개별 설정(예: 글꼴 처리 또는 이미지 래스터화)을 쉽게 조정할 수 있습니다.

## 왜 Aspose.TeX for Java LaTeX를 사랑해요?

- **완전한 LaTeX 지원** – 다양한 항목부터 사용자 정의 패키지를 사용하는 책까지 지원됩니다.
- **외부 바이너리 없음** – 순수 Java로 달리기 배포가 간편합니다.
- **세밀한 제어** – 옵션을 통해 수식, 그래픽 및 처리 처리 방식을 별도로 지정할 수 있습니다.
- **크로스 플랫폼 출력** – XPS 파일이 Windows, macOS, Linux에서 일관되게 전송됩니다.

##조건

시작하기 전에 다음 사항을 확인하세요.

- JDK(Java Development Kit) 8 또는 그 이후 버전을 설치해야 합니다.
- Java용 Aspose.TeX 라이브러리(공식 [Aspose.TeX Java 다운로드 페이지](https://releases.aspose.com/tex/java/)에서 다운로드).
- 프로젝트 클래스 패스트에 JAR을 추가할 수 있는 Java IDE 또는 빌드 도구(Maven/Gradle).

##체인을 가져오기

첫 번째 단계는 필요한 클래스를 가져오는 것입니다. import 블록을 표시된 대로 정확하게 유지하십시오. 이렇게 하면 코드가 수정 없이 컴파일됩니다.

```java
package com.aspose.tex.LaTeXXpsConversionSimplest;

import java.io.ByteArrayInputStream;
import java.io.IOException;
import java.util.Calendar;
import java.util.GregorianCalendar;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.Interaction;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;
import com.aspose.tex.rendering.XpsSaveOptions;

import util.Utils;
```

이제 변환 단계를 하나씩 살펴보면서 각 코드 조각의 용도를 설명하겠습니다.

## 1단계: 입력 및 출력 디렉터리 설정

Aspose.TeX에 원본 `.ltx` 파일의 위치와 결과 XPS 파일의 저장 위치를 ​​알려줘야 합니다.

```java
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

*팁:* `"입력 디렉터리"`와 `"출력 디렉터리"`를 컴퓨터의 실제 절대 경로 또는 상대 경로로 바꾸세요.

## 2단계: TeX 옵션 구성

이 옵션은 변환 과정에서 LaTeX 엔진의 동작 방식을 제어합니다. 문서 요구 사항에 맞게 조정하세요.

```java
options.setInteraction(Interaction.NonstopMode);
options.setDateTime(new GregorianCalendar(2022, Calendar.DECEMBER, 18).getTime());
options.ignoreMissingPackages(true);
options.noLigatures(true);
options.repeat(true);
```

- **Interaction mode** – `NonstopMode`는 오류가 발생해도 계속 처리합니다.  
- **DateTime** – 문서 표지에 표시될 날짜를 설정합니다.  
- **ignoreMissingPackages** – 패키지를 찾지 못해도 작업이 실패하지 않도록 합니다.  
- **noLigatures** – 일반 문자만 원한다면 활자 결합(ligatures)을 비활성화합니다.  
- **repeat** – 교차 참조를 위해 엔진을 재실행할 수 있게 합니다.

## 3단계: XPS 저장 옵션 초기화

XPS 관련 설정을 저장할 `XpsSaveOptions` 인스턴스를 생성합니다.

```java
options.setSaveOptions(new XpsSaveOptions());
```

## 4단계: XPS 저장 옵션 사용자 지정

XPS 출력에서 ​​수식, 그래픽 및 글꼴을 처리하는 방식을 세부적으로 조정합니다.

```java
options.getSaveOptions().rasterizeFormulas(true);
options.getSaveOptions().rasterizeIncludedGraphics(true);
options.getSaveOptions().subsetFonts(true);
```

- **rasterizeFormulas** – 수학 표현식을 이미지로 변환하여 모든 XPS 뷰어에서 올바르게 표시됩니다.  
- **rasterizeIncludedGraphics** – 포함된 그래픽을 강제로 래스터화하여 호환성을 높일 수 있습니다.  
- **subsetFonts** – 문서에 사용된 글리프만 포함시켜 파일 크기를 줄입니다.

## 5단계: LaTeX를 XPS로 변환 실행

마지막으로 변환 작업을 실행합니다. `TeXJob`은 입력 파일, 출력 장치(`XpsDevice`) 및 구성한 모든 옵션을 연결합니다.

```java
new TeXJob("Your Input Directory" + "sample.ltx", new XpsDevice(), options).run();
```

`run()` 호출이 완료되면 이전에 지정한 출력 디렉터리에 `sample.xps` 파일이 생성됩니다. 이 XPS 파일은 프린터로 직접 전송하거나 PDF 청구서 묶음에 포함할 수 있습니다.

## 추가 예제

### InputStream 사용 (LaTeX 문자열 직접 변환)

파일 대신 메모리에서 LaTeX 소스를 입력하려면 소스를 `ByteArrayInputStream`으로 묶습니다.

```java
new TeXJob(new ByteArrayInputStream(
    "\\documentclass{article} \\begin{document} Hello, World! \\end{document}".getBytes("ASCII")),
    new XpsDevice(), options).run();
```

### 기본 입력 터미널 사용 (Aspose.TeX가 파일을 자동으로 찾도록 함)

파일 경로를 명시적으로 지정할 필요가 없는 경우 기본 입력 터미널을 사용할 수 있습니다.

```java
new TeXJob(new XpsDevice(), options).run();
```

## 일반적인 사용 사례 및 팁

| 시나리오 | 이 접근 방식이 도움이 되는 이유 |
|----------|-------------|
| **인쇄물 청구서 생성** | XPS는 Windows 프린터에 작은 블록 정확성을 유지하므로 고품질의 충전기 출력에 소수입니다. |
| **학술적으로 적용되는 해석** | 최종 API를 사용하면 고유의 코드로 문자열의 `.ltx` 파일을 반복 처리할 수 있습니다. |
| ** 보고 도구에 LaTeX 등록** | 식을 새스터화하면 저울 장치에도 조치를 취할 수 있습니다. |

**전문가 팁:** 애플리케이션의 여러 모듈에서 재사용할 수 있도록 변환 논리를 유틸리티 메서드로 래핑합니다.

## 자주 묻는 질문

**Q: Aspose.TeX를 활용하여 LaTeX 문서를 변환할 수 있나요?**
답: 물론이죠. 엔진은 AMS 수학 패키지를 완벽하게 지원하며 `rasterizeFormulas(true)`가 설정된 경우 수식을 래스터화합니다.

**Q: Aspose.TeX for Java에 대한 체험판이 있습니까?**
A: 예, [Aspose.TeX Java 다운로드 페이지](https://releases.aspose.com/tex/java/)에서 무료 평가판을 다운로드할 수 있습니다.

**Q: Aspose.TeX에 대한 지원을 받을 수 있을까요?**
A: 커뮤니티 지원을 받으려면 [Aspose.TeX 포럼](https://forum.aspose.com/c/tex/47)을 방문하거나 Aspose 계정을 통해 지원 티켓을 개설하세요.

**Q: Aspose.TeX에 임시 기계를 제공합니까?**
A: 네, 임시 라이선스는 [Aspose 임시 라이선스 페이지](https://purchase.aspose.com/temporary-license/)를 통해 얻을 수 있습니다.

**Q: Aspose.TeX 문서는 유일하게 찾을 수 없나요?**
A: 종합적인 API 문서는 [Aspose.TeX Java 참조](https://reference.aspose.com/tex/java/)에서 확인할 수 있습니다.

---

**마지막 업데이트:** 2026-02-07
**테스트 환경:** Java용 Aspose.TeX 24.11
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}