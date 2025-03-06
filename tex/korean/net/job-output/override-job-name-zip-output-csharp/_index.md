---
title: 작업 이름 재정의 및 터미널 출력을 Zip에 쓰기(C#)
linktitle: 작업 이름 재정의 및 터미널 출력을 Zip에 쓰기(C#)
second_title: Aspose.TeX .NET API
description: .NET용 Aspose.TeX를 사용하여 작업 이름을 재정의하고 터미널 출력을 ZIP 파일에 쓰는 방법을 알아보세요. C# 예제가 포함된 단계별 가이드입니다.
weight: 11
url: /ko/net/job-output/override-job-name-zip-output-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 작업 이름 재정의 및 터미널 출력을 Zip에 쓰기(C#)

## 소개

이 튜토리얼에서는 작업 이름을 재정의하고 .NET용 Aspose.TeX를 사용하여 ZIP 파일에 터미널 출력을 쓰는 방법을 살펴보겠습니다. Aspose.TeX는 개발자가 .NET 애플리케이션에서 TeX 문서로 작업할 수 있게 해주는 강력한 라이브러리입니다. 이 특정 예에서는 작업 이름을 재정의하는 기능을 사용하여 터미널 출력을 ZIP 파일에 쓰는 일반적인 작업에 중점을 둘 것입니다.

## 전제 조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- C#에 대한 실무 지식
- .NET용 Aspose.TeX가 설치되었습니다.
- 작업 디렉터리에 대한 ZIP 아카이브 입력
- 터미널 출력을 위한 출력 ZIP 아카이브

## 네임스페이스 가져오기

코드를 살펴보기 전에 C# 프로젝트에 필요한 네임스페이스를 포함했는지 확인하세요.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Pdf;
using System.IO;
```

이제 프로세스를 안내하기 위해 예제를 여러 단계로 나누어 보겠습니다.

## 1단계: 입력 및 출력 ZIP 스트림 열기

```csharp
using (Stream inZipStream = File.Open(Path.Combine("Your Input Directory", "zip-in.zip"), FileMode.Open))
using (Stream outZipStream = File.Open(Path.Combine("Your Output Directory", "terminal-out-to-zip.zip"), FileMode.Create))
{
    // 1단계 코드는 여기에 있습니다.
}
```

## 2단계: 변환 옵션 설정

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
options.JobName = "terminal-output-to-zip";
options.InputWorkingDirectory = new InputZipDirectory(inZipStream, "in");
options.OutputWorkingDirectory = new OutputZipDirectory(outZipStream);
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## 3단계: 저장 옵션 정의

```csharp
options.SaveOptions = new PdfSaveOptions();
```

## 4단계: TeX 작업 실행

```csharp
new TeXJob("hello-world", new PdfDevice(), options).Run();
```

## 5단계: 출력 ZIP 아카이브 마무리

```csharp
((OutputZipDirectory)options.OutputWorkingDirectory).Finish();
```

## 결론

축하해요! .NET용 Aspose.TeX를 사용하여 작업 이름을 재정의하고 터미널 출력을 ZIP 파일에 쓰는 방법을 성공적으로 배웠습니다. 이 기술은 C# 애플리케이션에서 TeX 문서를 처리할 때 매우 유용할 수 있습니다.

## FAQ

### Q1: VB.NET과 같은 다른 .NET 언어와 함께 .NET용 Aspose.TeX를 사용할 수 있습니까?

A1: 예, .NET용 Aspose.TeX는 모든 .NET 언어와 호환됩니다.

### Q2: .NET용 Aspose.TeX에 대한 추가 문서는 어디에서 찾을 수 있습니까?

 A2: 다음을 방문하세요.[선적 서류 비치](https://reference.aspose.com/tex/net/) 자세한 정보를 보려면.

### Q3: Aspose.TeX에 대한 임시 라이선스를 어떻게 얻을 수 있나요?

 A3:[임시 면허증](https://purchase.aspose.com/temporary-license/) 테스트 목적으로.

### Q4: Aspose.TeX 지원을 위한 커뮤니티 포럼이 있습니까?

 A4: 그렇습니다.[Aspose.TeX 포럼](https://forum.aspose.com/c/tex/47) 지역 사회 지원을 위해.

### Q5: .NET용 Aspose.TeX를 어디서 구입할 수 있나요?

 A5: Aspose.TeX를 구입할 수 있습니다.[여기](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
