---
title: C#용 Aspose.TeX의 마스터 스트림, 이미지 및 터미널 입력
linktitle: C#용 Aspose.TeX의 마스터 스트림, 이미지 및 터미널 입력
second_title: Aspose.TeX .NET API
description: C# 마스터 스트림, 이미지 및 터미널 입력을 위한 Aspose.TeX의 강력한 기능을 손쉽게 살펴보세요. 원활한 문서 처리를 위해 지금 다운로드하세요.
type: docs
weight: 11
url: /ko/net/advanced-io/stream-input-image-output-terminal-input-csharp/
---
## 소개

C#용 Aspose.TeX의 스트림, 이미지 및 터미널 입력 마스터링에 대한 포괄적인 튜토리얼에 오신 것을 환영합니다. Aspose.TeX는 개발자가 TeX 파일로 작업할 수 있도록 하는 강력한 라이브러리로, 문서 조작 및 변환을 위한 광범위한 기능을 제공합니다. 이 가이드에서는 C#용 Aspose.TeX를 사용하여 스트림 처리, 이미지 관리 및 터미널 입력 캡처에 대해 자세히 알아봅니다. 이 튜토리얼을 마치면 문서 처리의 필수 측면을 효율적으로 작업할 수 있는 지식을 갖추게 됩니다.

## 전제 조건

예제를 살펴보기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식.
-  .NET 라이브러리용 Aspose.TeX가 설치되었습니다. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/tex/net/).
- C#용 개발 환경이 설정되었습니다.

## 네임스페이스 가져오기

C# 프로젝트에서 Aspose.TeX 기능에 액세스하는 데 필요한 네임스페이스를 포함해야 합니다. 코드 시작 부분에 다음 줄을 추가합니다.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Image;
using System.IO;
using System.Text;
```

## 1단계: 변환 옵션 설정

```csharp
// ExStart:TakeMainInputFromStream-AuxFromFileSystem-TakeTerminalInputFromConsole-AlternativeImagesStorage
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
options.JobName = "stream-in-image-out";
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
options.TerminalIn = new InputConsoleTerminal();
options.TerminalOut = new OutputConsoleTerminal();
options.SaveOptions = new PngSaveOptions() { Resolution = 300 };
```

## 2단계: 이미지 장치 생성 및 작업 실행

```csharp
ImageDevice device = new ImageDevice();
TeXJob job = new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
    "\\hrule height 10pt width 95pt\\vskip10pt\\hrule height 5pt")),
    device, options);
job.Run();
```

## 3단계: 콘솔에 입력 제공

콘솔에 메시지가 표시되면 "ABC"를 입력하고 Enter 키를 누른 다음 "\end"를 입력하고 Enter 키를 다시 누릅니다.

## 4단계: 출력 미세 조정

```csharp
options.TerminalOut.Writer.WriteLine();
byte[][] result = device.Result;
// ExEnd:TakeMainInputFromStream-AuxFromFileSystem-TakeTerminalInputFromConsole-AlternativeImagesStorage
```

축하해요! C#용 Aspose.TeX를 사용하여 스트림, 관리되는 이미지 및 캡처된 터미널 입력의 TeX 입력을 성공적으로 처리했습니다. 이러한 기술은 다양한 문서 처리 시나리오에 매우 중요합니다.

## 결론

이 튜토리얼에서는 C#용 Aspose.TeX에서 스트림, 이미지 및 터미널 입력 작업의 필수 측면을 다루었습니다. 변환 옵션 설정, 이미지 장치 생성, 작업 실행 및 출력 미세 조정 방법을 배웠습니다. 이러한 지식을 바탕으로 다양한 문서 처리 작업을 효율적으로 처리할 수 있습니다.

## FAQ

### Q1: 콘솔이 아닌 응용 프로그램에서 .NET용 Aspose.TeX를 사용할 수 있습니까?

A1: 물론이죠! Aspose.TeX는 데스크톱 및 웹 애플리케이션을 포함한 다양한 유형의 애플리케이션에 완벽하게 통합될 수 있습니다.

### Q2: 출력 이미지 해상도를 어떻게 사용자 정의할 수 있습니까?

 A2: 제공된 예에서 해상도는`PngSaveOptions` 물체. 당신은 조정할 수 있습니다`Resolution` 귀하의 요구 사항에 따라 재산.

### Q3: 평가판을 사용할 수 있나요?

 A3: 예, 무료 평가판을 통해 Aspose.TeX를 탐색할 수 있습니다.[여기](https://releases.aspose.com/).

### Q4: 추가 지원은 어디서 찾을 수 있나요?

 A4: Aspose.TeX 포럼을 방문하세요.[여기](https://forum.aspose.com/c/tex/47)커뮤니티 지원 및 토론을 위해.

### Q5: Aspose.TeX에 대한 임시 라이센스를 어떻게 얻을 수 있습니까?

 A5: 임시 라이센스를 취득할 수 있습니다[여기](https://purchase.aspose.com/temporary-license/).