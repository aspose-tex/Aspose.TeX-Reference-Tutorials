---
title: .NET에서 TeX를 XPS로 조판하기
linktitle: .NET에서 TeX를 XPS로 조판하기
second_title: Aspose.TeX .NET API
description: Aspose.TeX를 사용하여 TeX 문서를 .NET의 XPS로 쉽게 변환하세요. 원활한 통합 경험을 위한 단계별 가이드를 살펴보세요.
type: docs
weight: 10
url: /ko/net/xps-output/typeset-tex-to-xps/
---
## 소개

강력한 Aspose.TeX 라이브러리를 사용하여 .NET에서 TeX를 XPS로 조판하는 방법에 대한 단계별 가이드에 오신 것을 환영합니다. .NET 응용 프로그램에서 TeX 문서를 XPS 형식으로 원활하게 변환하려는 경우 제대로 찾아오셨습니다. 이 튜토리얼에서는 원활한 구현을 보장하기 위해 각 단계를 세분화하여 전체 프로세스를 안내합니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

-  .NET용 Aspose.TeX: Aspose.TeX 라이브러리가 설치되어 있는지 확인하세요. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/tex/net/).

- 문서화: 문서를 참조하여 라이브러리에 익숙해지세요.[여기](https://reference.aspose.com/tex/net/).

- 입력 및 출력 디렉터리: 예제 코드에 지정된 대로 입력 및 출력 디렉터리를 설정합니다.

이제 모든 설정이 완료되었으므로 단계별 가이드를 진행해 보겠습니다.

## 네임스페이스 가져오기

.NET 애플리케이션에서 필요한 네임스페이스를 가져오는 것부터 시작하세요. 이렇게 하면 TeX를 XPS로 조판하는 데 필요한 Aspose.TeX 기능에 액세스할 수 있습니다.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
```

## 1단계: 변환 옵션 설정

ObjectTeX 엔진 확장 시 ObjectTeX 형식을 지정하여 변환 옵션을 정의합니다. 또한 작업 이름, 입력 및 출력 디렉터리, 터미널 출력 세부 정보를 설정합니다.

```csharp
// ObjectTeX 엔진 확장 시 기본 ObjectTeX 형식에 대한 변환 옵션을 생성합니다.
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
// 작업 이름을 지정합니다.
options.JobName = "external-file-stream";
// 입력을 위한 파일 시스템 작업 디렉터리를 지정합니다.
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
// 출력을 위한 파일 시스템 작업 디렉터리를 지정합니다.
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
// 터미널 출력이 출력 작업 디렉터리의 파일에 기록되어야 함을 지정합니다.
// 파일 이름은 <job_name>.trm입니다.
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## 2단계: XPS 문서 스트림 생성

조판 XPS 문서를 작성하려면 스트림을 엽니다. 파일 이름은 반드시 작업 이름과 동일할 필요는 없습니다.

```csharp
using (Stream stream = File.Open(Path.Combine("Your Output Directory", options.JobName + ".xps"), FileMode.Create))
```

## 3단계: TeX 작업 실행

문서 이름, XpsDevice 및 변환 옵션을 지정하여 TeX 작업을 시작하고 실행합니다.

```csharp
new TeXJob("hello-world", new XpsDevice(stream), options).Run();
```

축하해요! Aspose.TeX를 사용하여 .NET에서 TeX를 XPS로 성공적으로 조판했습니다. 특정 요구 사항에 따라 더 많은 기능과 옵션을 자유롭게 탐색해 보세요.

## 결론

이 튜토리얼에서는 Aspose.TeX를 사용하여 TeX 문서를 .NET에서 XPS 형식으로 원활하게 변환하는 필수 단계를 다루었습니다. 이 가이드를 따르면 도서관의 기능과 이를 프로젝트에 활용하는 방법에 대한 귀중한 통찰력을 얻을 수 있습니다.

## FAQ

### Q1: Aspose.TeX는 .NET Core와 호환됩니까?

A1: 예, Aspose.TeX는 .NET Core와 완벽하게 호환됩니다.

### Q2: Aspose.TeX를 상업용 프로젝트에 사용할 수 있습니까?

A2: 물론이죠! Aspose.TeX는 상업용 및 개인용으로 모두 사용할 수 있습니다.

### Q3: 추가 예시와 리소스는 어디에서 찾을 수 있나요?

 A3: Aspose.TeX 문서 살펴보기[여기](https://reference.aspose.com/tex/net/)더 많은 예시와 자세한 리소스를 확인하세요.

### Q4: Aspose.TeX에 대한 지원은 어떻게 받을 수 있나요?

 A4: Aspose.TeX 지원 포럼을 방문하세요.[여기](https://forum.aspose.com/c/tex/47) 지역사회의 도움을 받으려면.

### Q5: 무료 평가판이 제공됩니까?

 A5: 예, 무료 평가판에 액세스할 수 있습니다.[여기](https://releases.aspose.com/).