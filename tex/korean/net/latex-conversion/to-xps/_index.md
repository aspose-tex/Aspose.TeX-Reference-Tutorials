---
title: .NET에서 LaTeX를 XPS로 - Aspose.TeX를 사용하여 쉽게 변환
linktitle: .NET에서 LaTeX를 XPS로 - Aspose.TeX를 사용하여 쉽게 변환
second_title: Aspose.TeX .NET API
description: Aspose.TeX를 사용하여 .NET에서 LaTeX를 XPS로 쉽게 변환하세요. 고품질, 사용자 정의 가능, 효율적입니다.
type: docs
weight: 13
url: /ko/net/latex-conversion/to-xps/
---
## 소개

.NET 응용 프로그램에서 LaTeX 문서를 XPS 형식으로 변환하는 원활한 방법을 찾고 계십니까? .NET용 Aspose.TeX는 이 작업을 위한 강력한 솔루션을 제공하여 변환 프로세스를 간단하고 효율적으로 만듭니다. 이 단계별 가이드는 Aspose.TeX를 사용하여 LaTeX를 XPS로 변환하는 과정을 안내하여 정확하고 고품질의 결과를 얻을 수 있도록 보장합니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- C# 및 .NET 개발에 대한 실무 지식.
-  .NET 라이브러리용 Aspose.TeX가 설치되었습니다. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/tex/net/).
- LaTeX 구문 및 구조에 대한 이해.

## 네임스페이스 가져오기

.NET 애플리케이션에 필요한 네임스페이스를 가져오는 것부터 시작해 보겠습니다. 이러한 네임스페이스는 Aspose.TeX 기능과 상호 작용하는 데 중요합니다.

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;
using System.Text;
```

## 1단계: 변환 옵션 설정

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectLaTeX);
options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
```

여기서는 변환 옵션을 초기화하고 LaTeX 파일의 입력 작업 디렉터리를 설정합니다.

## 2단계: 상호작용 모드 설정

```csharp
options.Interaction = Interaction.NonstopMode;
```

중단 없는 변환을 위해 논스톱 모드로 설정하는 상호 작용 모드를 지정합니다.

## 3단계: 작업 이름 설정(선택 사항)

```csharp
// options.JobName = "내 작업 이름";
```

필요한 경우 사용자 정의 작업 이름을 설정할 수 있습니다.

## 4단계: 제목에 날짜 설정(선택 사항)

```csharp
// options.DateTime = new System.DateTime(2022, 12, 18);
```

TeX 엔진이 제목에 특정 날짜를 출력하도록 강제합니다.

## 5단계: 누락된 패키지 무시

```csharp
options.IgnoreMissingPackages = true;
```

엔진이 오류 없이 누락된 패키지를 건너뛰도록 하려면 true로 설정하십시오.

## 6단계: 합자 비활성화

```csharp
options.NoLigatures = true;
```

엔진이 합자를 구성하지 않도록 하려면 true로 설정합니다.

## 7단계: 작업 반복(선택 사항)

```csharp
// 옵션.반복 = true;
```

필요한 경우 엔진에 작업을 반복하도록 요청하세요.

## 8단계: 출력 작업 디렉터리 지정

```csharp
options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
```

변환된 XPS 파일의 출력 작업 디렉터리를 설정합니다.

## 9단계: XPS용 저장 옵션 초기화

```csharp
options.SaveOptions = new XpsSaveOptions(); // 기본값. 임의 할당.
```

XPS 형식으로 저장하기 위한 옵션을 초기화합니다.

## 10단계: 수식 래스터화(선택 사항)

```csharp
options.SaveOptions.RasterizeFormulas = true;
```

수학 공식을 래스터 이미지로 변환하려면 true로 설정하세요.

## 11단계: 포함된 그래픽 래스터화(선택 사항)

```csharp
options.SaveOptions.RasterizeIncludedGraphics = true;
```

벡터 요소가 포함된 그래픽을 래스터 이미지로 변환하려면 true로 설정하십시오.

## 12단계: 하위 집합 글꼴

```csharp
options.SaveOptions.SubsetFonts = true;
```

문서에 사용되는 장치 하위 집합 글꼴을 만들려면 true로 설정합니다.

## 13단계: LaTeX에서 XPS로 변환 실행

```csharp
new TeXJob(Path.Combine("Your Input Directory", "sample.ltx"), new XpsDevice(), options).Run();
```

LaTeX에서 XPS로의 변환 프로세스를 시작합니다.

## 14단계: MemoryStream을 사용하여 LaTeX에서 XPS로 변환 실행(대안)

```csharp
// new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(@"\documentclass{article} \begin{document} Hello, World! \end{document}")),
// 새로운 XpsDevice(), 옵션).Run();
```

입력 LaTeX 콘텐츠에 대해 MemoryStream을 사용하여 변환을 실행할 수도 있습니다.

## 15단계: 기본 입력 터미널을 사용하여 LaTeX에서 XPS로 변환 실행(대체)

```csharp
// new TeXJob(new XpsDevice(), options).Run();
```

기본 입력 터미널에서 직접 변환을 실행합니다.

## 결론

이러한 간단한 단계를 따르면 Aspose.TeX for .NET을 사용하여 LaTeX 문서를 XPS 형식으로 쉽게 변환할 수 있습니다. 이 강력한 라이브러리는 특정 요구 사항을 충족하는 유연성과 사용자 정의 옵션을 제공합니다.

## FAQ

### Q1: Aspose.TeX는 최신 .NET 프레임워크와 호환됩니까?

A1: 예, Aspose.TeX는 최신 .NET 프레임워크와의 호환성을 보장하기 위해 정기적으로 업데이트됩니다.

### Q2: XPS 이외의 출력 형식을 사용자 정의할 수 있습니까?

 A2: Aspose.TeX는 다양한 출력 형식을 지원합니다. 문서를 참조하세요[여기](https://reference.aspose.com/tex/net/) 자세한 내용은.

### Q3: Aspose.TeX에 대한 임시 라이선스를 어떻게 얻나요?

 A3: 임시 라이센스를 얻을 수 있습니다[여기](https://purchase.aspose.com/temporary-license/).

### Q4: 어디에서 Aspose.TeX에 대한 도움을 구하거나 내 경험을 공유할 수 있습니까?

 A4: Aspose.TeX 포럼을 방문하세요.[여기](https://forum.aspose.com/c/tex/47) 지역 사회 지원을 위해.

### Q5: 테스트에 사용할 수 있는 샘플 문서가 있습니까?

 A5: Aspose.TeX 예제 살펴보기[여기](https://github.com/aspose-tex/Aspose.TeX-for-.NET).