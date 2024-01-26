---
title: Aspose.TeX(C#)를 사용하여 LaTeX 그림을 SVG로 렌더링
linktitle: Aspose.TeX(C#)를 사용하여 LaTeX 그림을 SVG로 렌더링
second_title: Aspose.TeX .NET API
description: Aspose.TeX를 사용하여 .NET에서 문서 렌더링을 향상하세요. 수학적 표현의 원활한 통합을 위해 LaTeX 수치를 C#의 SVG로 렌더링하는 방법을 알아보세요.
type: docs
weight: 11
url: /ko/net/render-latex-figures/svg-latex-figure-renderer-csharp/
---
## 소개

LaTeX 수치를 사용하여 .NET에서 문서 렌더링 기능을 향상시키려는 경우 Aspose.TeX가 적합한 솔루션입니다. 이 단계별 가이드에서는 C#에서 Aspose.TeX를 사용하여 LaTeX 그림을 SVG로 렌더링하는 과정을 안내합니다. 이 튜토리얼을 마치면 프로세스를 명확하게 이해하게 되어 고품질 수학적 표현과 수치를 문서에 원활하게 통합할 수 있게 됩니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식.
-  .NET 라이브러리용 Aspose.TeX가 설치되었습니다. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/tex/net/).

## 네임스페이스 가져오기

C# 코드에서 필요한 네임스페이스를 가져와야 합니다.

```csharp
using Aspose.TeX.Features;
```

이제 튜토리얼을 여러 단계로 나누어 보겠습니다.

## 1단계: 렌더링 옵션 생성

```csharp
FigureRendererOptions options = new SvgFigureRendererOptions();
options.Preamble = "\\usepackage{pict2e}";
options.Scale = 3000;
options.BackgroundColor = Color.White;
options.LogStream = new System.IO.MemoryStream();
options.ShowTerminal = true;
```

여기서는 프리앰블, 배율 인수, 배경색, 로그 스트림 및 터미널 출력 표시 여부를 지정하여 렌더링 옵션을 설정합니다.

## 2단계: 차원 및 출력 스트림 정의

```csharp
SizeF size = new SizeF();
using (Stream stream = File.Open(Path.Combine("Your Output Directory", "text-and-formula.svg"), FileMode.Create))
{
    // 렌더링을 실행합니다.
    new SvgFigureRenderer().Render("Your LaTeX Code", stream, options, out size);
}
```

"Your Output Directory"를 원하는 디렉토리로 바꾸고 LaTeX 코드를 문자열로 제공하십시오.

## 3단계: 결과 표시

```csharp
Console.Out.WriteLine(options.ErrorReport);
Console.Out.WriteLine();
Console.Out.WriteLine("Size: " + size);
```

이 단계에서는 오류 보고서와 결과 이미지의 크기가 표시됩니다.

## 결론

축하해요! C#에서 Aspose.TeX를 사용하여 LaTeX 그림을 SVG로 렌더링하는 방법을 성공적으로 배웠습니다. 이제 수학적 표현과 수치를 .NET 애플리케이션에 원활하게 통합할 수 있습니다.

## FAQ

### Q1: Aspose.TeX는 무료로 사용할 수 있나요?

 A1: Aspose.TeX는 무료 평가판을 제공합니다. 당신은 그것을 액세스할 수 있습니다[여기](https://releases.aspose.com/).

### Q2: Aspose.TeX 문서는 어디서 찾을 수 있나요?

 A2: 문서를 참조하세요[여기](https://reference.aspose.com/tex/net/).

### Q3: Aspose.TeX에 대한 지원을 받으려면 어떻게 해야 합니까?

 A3: 지원 포럼을 방문하세요.[여기](https://forum.aspose.com/c/tex/47).

### Q4: Aspose.TeX를 구입할 수 있나요?

 A4: 예, Aspose.TeX를 구입할 수 있습니다.[여기](https://purchase.aspose.com/buy).

### Q5: 임시 라이센스가 필요합니까?

 A5: 필요한 경우 임시 라이센스를 취득할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).