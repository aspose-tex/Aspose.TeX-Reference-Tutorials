---
date: 2025-12-20
description: Aspose.TeX for .NET를 사용해 TeX 작업의 XPS 출력을 만드는 방법을 배우고, 파일 시스템 입출력을 관리하며,
  고품질 XPS 문서를 생성하세요.
linktitle: Create TeX Job XPS Output with Filesystems – Aspose.TeX for .NET
second_title: Aspose.TeX .NET API
title: 파일 시스템을 사용한 TeX 작업 XPS 출력 생성 – Aspose.TeX for .NET
url: /ko/net/file-input-output/filesystem-input-xps-output/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 파일 시스템을 사용한 TeX 작업 XPS 출력 생성 – Aspose.TeX for .NET

## 소개

안녕하세요! 이 튜토리얼에서는 Aspose.TeX for .NET을 사용하여 파일 시스템 입력 및 출력을 처리하면서 **TeX 작업 XPS 출력 생성** 방법을 배우게 됩니다. 배치 프로세서, 웹 서비스 또는 데스크톱 유틸리티를 구축하든 관계없이 아래 단계에 따라 엔진을 구성하고, 파일을 지정하고, 원본 LaTeX 소스와 동일한 XPS 문서를 생성할 수 있습니다.

이 과정은 명확하게 번호가 매겨진 단계별로 설명되며, 각 코드 줄의 "이유"를 설명하고, 바로 적용할 수 있는 실용적인 팁을 제공합니다.

## 빠른 답변
- **"TeX 작업 XPS 생성"이란 무엇을 의미합니까?** TeX 파일을 읽고 결과를 XPS 문서로 작성하는 Aspose.TeX 작업을 구성하는 것을 의미합니다.
- **라이선스가 필요합니까?** 테스트용 임시 라이선스가 제공되며, 프로덕션 환경에서는 정식 라이선스가 필요합니다.
- **지원되는 .NET 버전은 무엇인가요?** .NET Framework 4.5 이상, .NET Core 3.1 이상, .NET 5/6/7.
- **출력 형식을 변경할 수 있나요?** 네, `XpsDevice`를 다른 장치(PDF, PNG 등)로 바꾸면 됩니다.
- **콘솔 출력이 필요한가요?** 아니요, 메모리 터미널을 사용하여 조용히 실행할 수 있습니다.

## "create tex job xps"란 무엇인가요?

XPS 형식으로 출력하는 TeX 작업을 생성한다는 것은 Aspose.TeX 엔진을 초기화하고, 소스 파일을 읽을 위치를 지정하고, 렌더링된 페이지를 XPS 패키지에 저장하는 것을 의미합니다. XPS(XML Paper Specification)는 고정 레이아웃 형식으로, 타이포그래피와 벡터 그래픽을 그대로 유지하므로 인쇄나 추가 변환에 적합합니다.

## XPS 출력에 Aspose.TeX를 사용하는 이유는 무엇인가요?

- **높은 품질:** 엔진은 LaTeX 레이아웃을 XPS 형식으로 정확하게 재현합니다.
- **외부 종속성 없음:** 순수 .NET 라이브러리이므로 네이티브 LaTeX 설치가 필요하지 않습니다.
- **유연한 I/O:** 파일 시스템 디렉터리, 메모리 스트림 또는 사용자 지정 공급자와 함께 작동합니다.
- **확장성:** 단일 파일 변환 또는 대량 처리 파이프라인에 적합합니다.

## 필수 조건

시작하기 전에 다음 사항을 확인하십시오.

- **Aspose.TeX for .NET** – [Aspose 웹사이트](https://releases.aspose.com/tex/net/)에서 최신 버전을 다운로드하십시오.
- **.NET 개발 환경** – .NET SDK가 설치된 Visual Studio, Rider 또는 VS Code.
- **입력 및 출력 폴더** – 컴퓨터에 두 개의 디렉터리를 생성하십시오(예: `C:\TeX\Input` 및 `C:\TeX\Output`).
- **라이선스(테스트용 선택 사항)** – Aspose 포털에서 임시 라이선스를 발급받을 수 있습니다.

## 네임스페이스 가져오기

먼저 파일 시스템 도우미와 XPS 장치에 접근할 수 있도록 필요한 네임스페이스를 범위 내로 가져옵니다.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
```

이 네임스페이스는 **tex 작업 XPS 생성** 워크플로에 필수적인 `InputFileSystemDirectory`, `OutputFileSystemDirectory` 및 `XpsDevice`를 노출합니다.

## 1단계: 변환 옵션 생성

먼저 엔진에 ObjectTeX 구성(대부분의 LaTeX 소스의 기본값)을 사용하도록 지시하는 `TeXOptions` 객체를 생성합니다.

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
```

> **팁:** `ConsoleAppOptions`는 콘솔 스타일 애플리케이션에 적합한 기본값을 설정하지만, 필요에 따라 나중에 옵션을 사용자 지정할 수 있습니다.

## 2단계: 입력 및 출력 디렉터리 지정

이전에 준비한 폴더를 엔진에 지정합니다. 자리 표시자 문자열을 컴퓨터의 실제 경로로 바꿉니다.

```csharp
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

이제 TeX 작업은 `.tex` 파일을 찾을 위치와 생성된 XPS 파일을 저장할 위치를 알게 되었습니다.

## 3단계: 출력 터미널 선택

터미널은 상태 메시지가 출력되는 위치를 제어합니다. 빠른 디버깅을 위해 콘솔을 사용하지만, 조용한 실행을 위해서는 메모리 터미널로 전환할 수 있습니다.

```csharp
options.TerminalOut = new OutputConsoleTerminal(); // Default value. Arbitrary assignment.
```

> **중요한 이유:** 콘솔 터미널을 사용하면 컴파일 경고나 오류에 대한 즉각적인 피드백을 받을 수 있어 문제 해결 속도를 높일 수 있습니다.

## 4단계: TeX 작업 실행

`TeXJob` 인스턴스를 생성하고, 알아보기 쉬운 이름을 지정한 다음, `XpsDevice`를 연결하고 실행합니다.

```csharp
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.Run();
```

`Run()`이 완료되면 출력 디렉터리에 `hello-world.xps` 파일이 생성됩니다.

## 5단계: 콘솔 출력 세부 조정

작업이 완료된 후 빈 줄을 추가하면 특히 여러 작업을 일괄 실행할 때 콘솔 로그를 더 쉽게 읽을 수 있습니다.

```csharp
options.TerminalOut.Writer.WriteLine();
```

## 일반적인 문제 및 해결 방법

| 문제 | 원인 | 해결 방법 |
|-------|-------|-----|
| **XPS 파일이 비어 있음** | 출력 디렉터리 경로가 잘못되었거나 쓰기 권한이 없습니다. | `OutputFileSystemDirectory`에 전달된 경로를 확인하고 프로세스에 쓰기 권한이 있는지 확인하십시오. |
| **컴파일 오류** | LaTeX 소스에서 ObjectTeX에 포함되지 않은 패키지를 사용합니다. | 전체 TeX 엔진 구성(`TeXConfig.FullTeX()`)으로 전환하거나 누락된 패키지 파일을 입력 디렉터리에 추가하십시오. |
| **콘솔이 멈춤** | 대화형 프롬프트로 인해 터미널이 입력을 기다리고 있습니다. | 자동화된 스크립트에서 대화형 프롬프트를 억제하려면 `OutputMemoryTerminal`을 사용하십시오. |

## 자주 묻는 질문

**Q1: ​​XPS 대신 다른 출력 형식을 사용할 수 있습니까?**
A1: 예, Aspose.TeX는 PDF, PNG, SVG 및 기타 형식을 지원합니다. `new XpsDevice()`를 적절한 장치 클래스(예: `new PdfDevice()`)로 바꾸세요.

**Q2: 테스트용 임시 라이선스를 받을 수 있나요?**
A2: 네, [이 링크](https://purchase.aspose.com/temporary-license/)에서 테스트용 임시 라이선스를 받을 수 있습니다.

**Q3: 추가 문서는 어디에서 찾을 수 있나요?**
A3: 자세한 내용은 [Aspose.TeX for .NET 문서](https://reference.aspose.com/tex/net/)를 참조하세요.

**Q4: 커뮤니티 지원을 받거나 질문을 하려면 어떻게 해야 하나요?**
A4: 커뮤니티 지원 및 토론을 위해 [Aspose.TeX 포럼](https://forum.aspose.com/c/tex/47)을 방문하세요.

**Q5: 사용 가능한 샘플 프로젝트가 있습니까?**
A5: Aspose.TeX GitHub 저장소에서 샘플 프로젝트와 코드 스니펫을 찾아보세요.

## 결론

위의 단계를 따르면 Aspose.TeX for .NET을 사용하여 **TeX 작업 XPS 출력 생성**, 입력 및 출력 폴더 관리, 개발 및 프로덕션 시나리오에 맞게 프로세스 최적화 방법을 알 수 있습니다. 다른 출력 장치를 사용해 보거나, 이 로직을 더 큰 워크플로에 통합하거나, 일괄 변환을 자동화해 보세요.

---

**최종 업데이트:** 2025년 12월 20일
**테스트 환경:** Aspose.TeX 24.11 for .NET (작성 시점 기준 최신 버전)
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}