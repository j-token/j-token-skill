# j-token Skills

## 제공 스킬

### Implementation Roadmap

소프트웨어나 게임의 구현 목표를 의존성, blocker, Mermaid 다이어그램, 검증 기준, 사용자 언어로 작성된 의사코드가 포함된 단계별 Markdown 로드맵으로 변환합니다.

### Create UI Tutorial

Computer Use로 실제 프로그램 화면을 캡처하고, 이미지가 포함된 단계별 Markdown 강의 자료를 만듭니다. 되돌릴 수 없는 작업은 변경 내용, 영향 범위, 복구 방법과 필요한 백업을 실행 전에 글로 설명합니다.

## 설치

```powershell
npx skills add j-token/j-token-skill --skill implementation-roadmap
```

UI 강의 자료 스킬을 설치합니다.

```powershell
npx skills add j-token/j-token-skill --skill create-ui-tutorial
```

모든 프로젝트에서 사용하려면 전역 옵션을 추가합니다.

```powershell
npx skills add j-token/j-token-skill --skill implementation-roadmap --global
npx skills add j-token/j-token-skill --skill create-ui-tutorial --global
```

## 사용

에이전트에게 구현할 목표와 함께 로드맵 작성을 요청합니다.

```text
$implementation-roadmap을 사용해 이 프로젝트의 결제 기능 구현 로드맵을 작성해 주세요.
```

이 스킬은 구현 코드를 작성하지 않고, 구현 순서와 검증 기준이 담긴 Markdown 문서를 만듭니다.

실제 UI를 캡처해 강의 자료를 만들려면 다음과 같이 요청합니다.

```text
$create-ui-tutorial을 사용해 Blender에서 새 애니메이션 파일을 만드는 과정을 이미지가 포함된 Markdown 강의 자료로 작성해 주세요.
```

Windows 프로그램 캡처에는 Computer Use가 필요합니다.
