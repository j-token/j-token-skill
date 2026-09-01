# Implementation Roadmap

소프트웨어나 게임의 구현 목표를 실행 가능한 단계별 Markdown 로드맵으로 변환하는 에이전트 스킬입니다.

의존성, blocker, Mermaid 다이어그램, 검증 기준, 사용자 언어로 작성된 의사코드를 포함합니다.

## 설치

```powershell
npx skills add j-token/j-token-skill --skill implementation-roadmap
```

모든 프로젝트에서 사용하려면 전역 옵션을 추가합니다.

```powershell
npx skills add j-token/j-token-skill --skill implementation-roadmap --global
```

## 사용

에이전트에게 구현할 목표와 함께 로드맵 작성을 요청합니다.

```text
$implementation-roadmap을 사용해 이 프로젝트의 결제 기능 구현 로드맵을 작성해 주세요.
```

이 스킬은 구현 코드를 작성하지 않고, 구현 순서와 검증 기준이 담긴 Markdown 문서를 만듭니다.
