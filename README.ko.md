# Golden Path

[English](README.md) · [한국어 스킬](ko/SKILL.md) · [English skill](en/SKILL.md)

프로젝트의 현재 개발 기준과 개발에 사용한 스킬을 사람이 읽고 검토할 수 있는 문서로 관리하는 스킬입니다.

Golden Path에는 프로젝트에 적용되는 기술, 구조, 작업 규칙을 정리합니다. 사용 스킬은 별도 표로 정리해, 다음 사람이 어떤 스킬이 결과물에 기여했고 어디에 사용됐는지 이해할 수 있도록 합니다.

에이전트는 필요한 항목을 찾아볼 수 있습니다. 일반 개발 작업마다 문서를 읽거나 전체 내용을 상시 컨텍스트에 넣도록 요구하지 않습니다.

## 관리하는 내용

- 개발 기준: 언어, 프레임워크, 패키지 관리자, 폴더 구조, 명명 규칙, 코딩 규칙, 테스트 규칙, 주요 제약.
- 개발에 사용한 스킬: 실제 스킬 이름과 기능, 프로젝트에서 어디에 적용했는지에 대한 짧은 설명.

문서에는 현재 유효한 기준을 유지합니다. 결정·변경 이력, 대화 요약, 작업 진행 로그를 모으지 않습니다. 정해지지 않은 기준은 `미정`으로 두며, 설치만 하고 사용하지 않은 스킬은 목록에 넣지 않습니다.

## 언어 선택

```text
golden_path/
├── README.md
├── README.ko.md
├── en/
│   └── SKILL.md
└── ko/
    └── SKILL.md
```

두 언어 버전은 같은 `golden-path` 스킬입니다. 사용할 언어 하나를 선택해 해당 도구의 스킬 디렉터리에 `golden-path/SKILL.md`로 설치합니다.

## 설치

### Codex: 개인용 설치

저장소를 복제한 뒤 한국어 진입점과 라이선스를 개인 스킬 디렉터리에 복사합니다.

```sh
git clone https://github.com/shnea/golden_path.git
cd golden_path
mkdir -p "$HOME/.agents/skills/golden-path"
cp ko/SKILL.md LICENSE "$HOME/.agents/skills/golden-path/"
```

영어 버전은 복사할 원본을 `en/SKILL.md`로 바꾸면 됩니다. 기존 `golden-path` 스킬이 있다면 교체하기 전에 내용을 비교하세요.

### Codex: 프로젝트용 설치

작업 대상 프로젝트 루트에서, 복제한 저장소의 진입점을 복사합니다.

```sh
mkdir -p .agents/skills/golden-path
cp /path/to/golden_path/ko/SKILL.md /path/to/golden_path/LICENSE .agents/skills/golden-path/
```

`/path/to/golden_path`는 실제 복제한 저장소의 경로로 바꿉니다. Codex는 위 개인·프로젝트 경로에서 스킬을 탐색합니다. 자세한 내용은 [공식 스킬 문서](https://learn.chatgpt.com/docs/build-skills)를 참고하세요.

### 다른 도구

`SKILL.md` 스킬을 지원하는 도구에서는 선택한 파일을 해당 도구가 지정한 스킬 디렉터리에 `golden-path/SKILL.md`로 배치하고, 같은 폴더에 `LICENSE`도 복사합니다. 설치 경로와 호출 방식은 각 도구의 안내를 따릅니다.

## 사용

Codex에서는 `$golden-path`와 함께 다음처럼 요청할 수 있습니다.

```text
$golden-path 이 프로젝트의 개발 기준을 함께 정리해줘.
아직 합의하지 않은 항목은 미정으로 남겨줘.
```

```text
$golden-path 현재 프로젝트의 개발 기준과 사용한 스킬을 보여줘.
```

```text
$golden-path 패키지 관리자를 pnpm으로 변경하고, 사용 스킬에 skill-creator를 추가해줘.
스킬 범위 검토와 SKILL.md 지침 작성에 사용했어.
```

에이전트가 기준이나 사용 스킬의 추가·변경을 제안하면 내용을 보여주고 동의를 받은 뒤 저장합니다. 사용자가 구체적인 변경을 반영하도록 요청했다면 다시 동의를 묻지 않습니다.

## 생성되는 문서

기본 저장 위치는 작업 대상 프로젝트의 `docs/GOLDEN_PATH.md`입니다. 사용자나 프로젝트 지침이 지정한 경로를 우선하고, 별도 지정이 없으면 기존 Golden Path 문서를 사용합니다.

아래는 문서 형식을 보여주는 예시이며 특정 기술이나 스킬의 사용을 요구하지 않습니다. 실제 내용은 합의한 프로젝트 기준과 확인된 스킬 사용에 맞춰 작성합니다.

```markdown
# Golden Path

## 개발 기준

| 항목 | 적용 기준 |
| --- | --- |
| 개발 언어 | TypeScript |
| 패키지 관리자 | pnpm |
| 명명 규칙 | 미정 |

## 개발에 사용한 스킬

| 스킬명 | 역할 설명 |
| --- | --- |
| skill-creator | 스킬의 범위와 지침을 검토하는 스킬. SKILL.md 구성과 지침 정리에 사용. |
```

기준이 바뀌면 해당 항목을 갱신합니다. 같은 스킬은 한 행으로 관리하고 역할 설명을 보완하며, 실행 날짜·호출 횟수·개별 작업 내역은 누적하지 않습니다.

## 기여

동작을 변경할 때는 `en/SKILL.md`와 `ko/SKILL.md`를 함께 수정합니다. 사람이 읽는 문서, 현재 개발 기준, 실제 사용 스킬, 사용자 승인에 따른 변경이라는 범위를 유지합니다.

## 라이선스

[MIT](LICENSE).
