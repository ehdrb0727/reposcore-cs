# C# CLI 프로그램 개발을 위한 라이브러리 (Octokit & Cocona)

## 1. Cocona

가장 쉽고 빠르게 C# CLI 애플리케이션을 만들 수 있게 해주는 프레임워크입니다.
### 특징
- 최소한의 코드로 강력한 CLI 구현 (Minimal API 스타일)
- 명령어, 옵션, 인자 파싱 및 유효성 검사 자동화
- `--help` 메시지 및 쉘 자동완성 지원
- 의존성 주입(Dependency Injection) 및 로깅 등 엔터프라이즈 기능 통합

### 설치 방법
아래 명령어를 터미널에 입력합니다.
```
dotnet add package Cocona
```

### 사용 예시
아래는 `Cocona`를 사용해 `--token` 옵션을 받아 실행하는 예시입니다.
```csharp
using Cocona;

var app = CoconaApp.Create();

// 명령어를 메서드 형태로 정의
app.AddCommand((string token) => 
{
    Console.WriteLine($"입력된 토큰: {token}");
});

app.Run();
```

실행 및 결과 확인
터미널에서 dotnet run 명령어 뒤에 --를 붙여 애플리케이션에 인자를 전달할 수 있습니다
```Bash
$ dotnet run -- --token "my-secret-key"
입력된 토큰: my-secret-key
```
---


## 참고 링크

- [Cocona GitHub Repository](https://github.com/mayuki/Cocona)

