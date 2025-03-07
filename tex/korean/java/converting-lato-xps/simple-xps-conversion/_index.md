---
title: LaTeX를 Java에서 XPS 형식으로 쉽게 변환
linktitle: LaTeX를 Java에서 XPS 형식으로 쉽게 변환
second_title: Aspose.TeX 자바 API
description: Aspose.TeX를 사용하여 Java에서 LaTeX를 XPS로 쉽게 변환하세요. 원활한 통합을 위한 단계별 가이드를 따르세요.
weight: 10
url: /ko/java/converting-lato-xps/simple-xps-conversion/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# LaTeX를 Java에서 XPS 형식으로 쉽게 변환

## 소개

Java 애플리케이션에서 LaTeX 문서를 XPS 형식으로 원활하게 변환하고 싶으십니까? Aspose.TeX for Java는 이를 쉽게 달성할 수 있는 강력한 솔루션을 제공합니다. 이 단계별 가이드에서는 Aspose.TeX를 사용하여 LaTeX를 XPS로 변환하는 과정을 안내합니다.

## 전제 조건

변환 프로세스를 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
-  Java 라이브러리용 Aspose.TeX가 다운로드되었습니다. 다운로드 링크를 찾을 수 있습니다[여기](https://releases.aspose.com/tex/java/).

## 패키지 가져오기

시작하려면 Java 프로젝트에 필요한 패키지를 가져오세요. 프로젝트 종속성에 Aspose.TeX 라이브러리를 포함했는지 확인하세요.

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

이제 제공된 코드 예제를 사용하여 변환 프로세스를 여러 단계로 나누어 보겠습니다.

## 1단계: 입력 및 출력 디렉터리 설정

```java
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

LaTeX 입력 파일이 있는 디렉터리와 변환된 XPS 파일을 저장할 디렉터리를 지정합니다.

## 2단계: TeX 옵션 구성

필요에 따라 변환 프로세스를 사용자 정의하려면 다양한 옵션을 구성하십시오.

```java
options.setInteraction(Interaction.NonstopMode);
options.setDateTime(new GregorianCalendar(2022, Calendar.DECEMBER, 18).getTime());
options.ignoreMissingPackages(true);
options.noLigatures(true);
options.repeat(true);
```

필요에 따라 상호 작용 모드, 제목 날짜, 누락된 패키지 처리, 합자 및 반복을 조정합니다.

## 3단계: XPS 저장 옵션 초기화

```java
options.setSaveOptions(new XpsSaveOptions());
```

XPS 형식으로 저장하기 위한 옵션을 초기화합니다.

## 4단계: XPS 저장 옵션 사용자 정의

```java
options.getSaveOptions().rasterizeFormulas(true);
options.getSaveOptions().rasterizeIncludedGraphics(true);
options.getSaveOptions().subsetFonts(true);
```

XPS 저장 옵션을 사용자 정의하여 수식, 포함된 그래픽 및 글꼴 하위 설정의 변환을 제어합니다.

## 5단계: LaTeX에서 XPS로 변환 실행

```java
new TeXJob("Your Input Directory" + "sample.ltx", new XpsDevice(), options).run();
```

지정된 입력 파일, 출력 장치(XpsDevice) 및 옵션을 사용하여 TeX 작업을 실행하여 변환 프로세스를 시작합니다.

## 추가 예시

다양한 입력 소스를 사용하여 추가 변환 방법을 살펴보세요.

### 입력스트림 사용

```java
new TeXJob(new ByteArrayInputStream(
    "\\documentclass{article} \\begin{document} Hello, World! \\end{document}".getBytes("ASCII")),
    new XpsDevice(), options).run();
```

### 주 입력 단자 사용

```java
new TeXJob(new XpsDevice(), options).run();
```

## 결론

Java용 Aspose.TeX를 사용하면 LaTeX를 XPS로 변환하는 것이 매우 쉽습니다. 다음 단계에 따라 옵션을 사용자 정의하고 이 기능을 Java 애플리케이션에 원활하게 통합하십시오.

## FAQ

### Q1: Aspose.TeX를 사용하여 복잡한 수식이 포함된 LaTeX 문서를 변환할 수 있나요?

A1: 물론이죠! Aspose.TeX는 변환 프로세스 중에 복잡한 수식을 원활하게 처리합니다.

### Q2: Aspose.TeX for Java에 사용할 수 있는 평가판이 있습니까?

 A2: 예, 무료 평가판을 찾을 수 있습니다.[여기](https://releases.aspose.com/).

### Q3: Aspose.TeX에 대한 지원은 어떻게 받을 수 있나요?

 A3: 다음을 방문하세요.[Aspose.TeX 포럼](https://forum.aspose.com/c/tex/47) 도움과 지역 사회 지원을 위해.

### Q4: Aspose.TeX에 임시 라이센스를 사용할 수 있습니까?

 A4: 예, 임시 라이센스를 얻을 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).

### Q5: Aspose.TeX에 대한 설명서는 어디에서 찾을 수 있습니까?

 A5: 다음을 참조하세요.[선적 서류 비치](https://reference.aspose.com/tex/java/) 종합적인 안내를 위해.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
