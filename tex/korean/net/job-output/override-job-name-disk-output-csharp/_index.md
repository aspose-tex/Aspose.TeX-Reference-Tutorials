---
date: 2025-12-21
description: Aspose.TeX를 사용하여 C#에서 콘솔 출력을 캡처하고, 작업 이름을 재정의하며, TeX 입력 디렉터리를 설정하고, 터미널
  출력을 파일에 기록하는 방법을 배웁니다.
linktitle: Capture Console Output C# – Override Job Name & Write Output to Disk
second_title: Aspose.TeX .NET API
title: 콘솔 출력 캡처 C# – 작업 이름 재정의 및 출력 디스크에 저장
url: /ko/net/job-output/override-job-name-disk-output-csharp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 콘솔 출력 캡처 C# – 작업 이름 재정의 및 터미널 출력을 디스크에 기록 (C#)

## 소개

이 단계별 가이드에서는 Aspose.TeX for .NET을 사용할 때 **콘솔 출력 캡처 C#** 방법을 배웁니다. 작업 이름을 재정의하고 터미널 출력을 파일로 지정함으로써 TeX 처리 파이프라인을 완전히 제어할 수 있습니다—자동 빌드, CI/CD 시나리오 또는 콘솔 스트림을 나중에 분석하기 위해 로그가 필요한 모든 상황에 적합합니다.

## 빠른 답변
- **“capture console output C#”는 무엇을 의미합니까?** Aspose.TeX에서 생성되는 표준 터미널 스트림을 지정한 파일로 리디렉션합니다.  
- **왜 작업 이름을 재정의합니까?** 재정의하면 파일 이름이 예측 가능해지고 여러 작업을 동시에 실행할 때 충돌을 방지할 수 있습니다.  
- **어떤 Aspose.TeX 클래스가 출력을 기록합니까?** `OutputFileTerminal` (`options.TerminalOut`을 통해 사용).  
- **사용자 지정 TeX 입력 폴더를 설정할 수 있나요?** 예—`options.InputWorkingDirectory`를 사용하여 **TeX 입력 디렉터리**를 설정합니다.  
- **이 방법이 .NET Core와 호환되나요?** 물론입니다; 동일한 API가 .NET Framework와 .NET Core 모두에서 작동합니다.

## Aspose.TeX 컨텍스트에서 “capture console output C#”란 무엇인가요?

콘솔 출력을 캡처한다는 것은 터미널 창에 일반적으로 표시되는 모든 내용(로그 메시지, 경고, 컴파일 세부 정보)을 가져와 영구 파일에 기록하는 것을 의미합니다. 이는 대규모 TeX 프로젝트 디버깅이나 TeX 처리를 자동화된 워크플로에 통합할 때 특히 유용합니다.

## 왜 작업 이름을 재정의하고 터미널 출력을 파일에 기록해야 할까요?

- **예측 가능한 파일 이름:** 작업 이름을 재정의하면 생성된 파일들의 기본 이름을 결정할 수 있어 후처리 스크립트를 작성하기가 쉬워집니다.  
- **감사 가능성:** 터미널 로그를 저장하면 TeX 컴파일 과정에 대한 완전한 감사 기록을 확보할 수 있습니다.  
- **병렬 실행:** 여러 작업을 동시에 실행할 때 고유한 작업 이름은 파일 충돌을 방지합니다.

## 전제 조건

시작하기 전에 다음 항목이 준비되어 있는지 확인하십시오:

- Aspose.TeX for .NET 라이브러리: Aspose.TeX for .NET 라이브러리가 설치되어 있는지 확인하십시오. [Aspose.TeX 웹사이트](https://releases.aspose.com/tex/net/)에서 다운로드할 수 있습니다.  
- .NET 개발 환경: Visual Studio와 같은 통합 개발 환경(IDE)을 포함한 .NET 개발 환경이 준비되어 있어야 합니다.  
- 기본 C# 지식: C# 프로그래밍 언어의 기본에 익숙해야 합니다.  
- 입력 및 출력 디렉터리: TeX 파일을 위한 입력 및 출력 디렉터리를 준비하십시오.

## 네임스페이스 가져오기

C# 코드에서 Aspose.TeX 기능에 접근하기 위해 필요한 네임스페이스를 포함하십시오:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

## 1단계: 변환 옵션 생성

먼저, Aspose.TeX에 콘솔 애플리케이션 시나리오에서 실행 중임을 알리는 `TeXOptions` 인스턴스를 생성합니다.

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

`ConsoleAppOptions`와 함께 `TeXOptions`를 생성하고, `TeXConfig`로 `ObjectTeX`를 지정합니다.

## 2단계: 작업 이름 지정 (기본값 재정의)

작업 이름을 재정의하면 모든 생성된 아티팩트의 기본 이름을 제어할 수 있습니다.

```csharp
options.JobName = "overridden-job-name";
```

기본 이름을 재정의하기 위해 작업 이름을 지정합니다.

## 3단계: TeX 입력 디렉터리 설정

Aspose.TeX에 소스 `.tex` 파일이 위치한 경로를 알려줍니다. 이것이 **TeX 입력 디렉터리 설정** 단계입니다.

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

TeX 파일에 대한 입력 작업 디렉터리를 설정합니다.

## 4단계: 출력 작업 디렉터리 지정

처리된 파일과 캡처된 콘솔 로그가 저장될 위치를 정의합니다.

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

처리된 TeX 파일을 저장할 출력 작업 디렉터리를 정의합니다.

## 5단계: 터미널 출력을 파일에 기록

이제 콘솔 스트림을 출력 디렉터리의 실제 파일로 전달합니다. 이는 **터미널 출력을 파일에 기록** 요구사항을 구현합니다.

```csharp
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

터미널 출력을 출력 디렉터리의 파일에 기록하도록 구성합니다.

## 6단계: 작업 실행

마지막으로, 재정의된 작업 이름, XPS 출력 장치, 그리고 구성한 옵션을 사용해 `TeXJob`을 생성합니다. 작업을 실행하면 XPS 파일이 생성되고 콘솔 로그가 캡처됩니다.

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

`TeXJob`을 생성하고 작업 이름, 출력 장치(`XpsDevice`), 옵션을 지정합니다. 마지막으로 작업을 실행합니다.

## 일반적인 문제 및 해결 방법

| 증상 | 가능한 원인 | 해결 방법 |
|------|------------|----------|
| 출력 파일이 생성되지 않음 | 출력 디렉터리 경로가 잘못되었거나 쓰기 권한이 없음 | `options.OutputWorkingDirectory`가 유효한 폴더를 가리키고 프로세스에 쓰기 권한이 있는지 확인하십시오. |
| 터미널 로그가 비어 있음 | `TerminalOut`이 설정되지 않았거나 나중에 덮어쓰기됨 | `options.TerminalOut = new OutputFileTerminal(...);`가 `job.Run();` 전에 실행되었는지 확인하십시오. |
| “파일을 찾을 수 없습니다” 오류로 작업 실패 | 입력 디렉터리가 올바르게 설정되지 않음 | `InputFileSystemDirectory`에 전달된 경로와 해당 디렉터리에 `.tex` 파일이 존재하는지 다시 확인하십시오. |

## 자주 묻는 질문

### Q1: Aspose.TeX for .NET을 다른 .NET 라이브러리와 함께 사용할 수 있나요?

A1: 예, Aspose.TeX for .NET은 다른 .NET 라이브러리와 원활하게 통합될 수 있습니다.

### Q2: Aspose.TeX for .NET에 대한 무료 체험판이 있나요?

A2: 예, 무료 체험 버전을 [여기](https://releases.aspose.com/)에서 다운로드할 수 있습니다.

### Q3: Aspose.TeX for .NET에 대한 지원을 어떻게 받을 수 있나요?

A3: 커뮤니티와 지원을 받으려면 [Aspose.TeX 포럼](https://forum.aspose.com/c/tex/47)을 방문하십시오.

### Q4: Aspose.TeX for .NET에 대한 임시 라이선스가 제공되나요?

A4: 예, 임시 라이선스를 [여기](https://purchase.aspose.com/temporary-license/)에서 받을 수 있습니다.

### Q5: Aspose.TeX for .NET 문서는 어디에서 찾을 수 있나요?

A5: 문서는 [여기](https://reference.aspose.com/tex/net/)에서 확인할 수 있습니다.

## 결론

축하합니다! 작업 이름을 재정의하고 TeX 입력 디렉터리를 설정하며 Aspose.TeX for .NET을 사용해 터미널 출력을 파일에 기록하는 방법으로 **콘솔 출력 캡처 C#**을 성공적으로 배웠습니다. 이 기술은 로깅을 간소화하고 추적성을 향상시키며 자동화된 TeX 처리 파이프라인을 보다 견고하게 만듭니다.

---

**마지막 업데이트:** 2025-12-21  
**테스트 환경:** Aspose.TeX 24.11 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}