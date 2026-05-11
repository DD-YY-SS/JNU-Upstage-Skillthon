# JNU × Upstage Skillthon

> **전남대학교 소프트웨어중심대학 × 업스테이지**  
> 2026 교내 디지털 경진대회 (SW부문)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Powered by Upstage](https://img.shields.io/badge/Powered%20by-Upstage%20Solar-blue)](https://upstage.ai)
[![Built for Codex](https://img.shields.io/badge/Built%20for-Codex-black)](https://openai.com/)

## Skillthon이란?

**하나의 Skill을 만드는 대회**입니다.

> **Skills for Your Daily Life**  
> 일상의 문제를 해결하는 AI Agent용 모듈을 만듭니다.

Skill은 AI Agent가 필요할 때 꺼내 쓰는 단일 목적 도구입니다. 사용자가 직접 세부 절차를 기억하지 않아도, 에이전트가 상황을 보고 적절한 Skill을 선택해 활용할 수 있도록 만드는 것이 목표입니다.

## 크레딧 지원

대회 참가자 전원에게 **Upstage API 크레딧 $70**을 무료로 지원합니다.

1. [console.upstage.ai](https://console.upstage.ai) 가입 또는 로그인
2. `Dashboard` 탭으로 이동
3. 좌측 `Billing -> Credit` 선택
4. `Redeem code` 클릭
5. 아래 코드 입력

```text
UPWAVE-KOH
```

![Upstage 크레딧 리딤 방법](assets/referral_code.jpg)

## 사전 요구사항

| 도구 | 용도 |
|------|------|
| Codex | Skill 개발 및 실행 |
| Git | Fork / Clone |
| Upstage API 키 | Solar API 호출 |

## Codex에서 시작하기

### 1. 저장소 가져오기

```bash
git clone https://github.com/[내-username]/JNU-Upstage-Skillthon
cd JNU-Upstage-Skillthon
```

### 2. Codex용 skill 설치

이 저장소의 핵심 스킬은 `skills/solar-skill-creator/`에 들어 있습니다. Codex에서 바로 쓰려면 이 폴더를 Codex skills 디렉터리로 복사하면 됩니다.

Windows PowerShell:

```powershell
New-Item -ItemType Directory -Force "$HOME\\.codex\\skills" | Out-Null
Copy-Item -Recurse ".\\skills\\solar-skill-creator" "$HOME\\.codex\\skills\\solar-skill-creator"
```

macOS / Linux:

```bash
mkdir -p ~/.codex/skills
cp -R ./skills/solar-skill-creator ~/.codex/skills/solar-skill-creator
```

이 저장소에는 Codex 플러그인 메타데이터도 포함되어 있어, 필요하면 repo-local plugin 형태로 확장해서 쓸 수 있습니다.

### 3. Codex에서 저장소 열기

현재 작업 중인 리포지토리를 Codex에서 연 뒤, 아래처럼 요청하면 `solar-skill-creator`가 동작하도록 설계되어 있습니다.

```text
내 주변의 버터떡을 파는 곳을 가져오는 스킬을 만들고 싶어요
```

이 스킬은 보통 다음 순서로 진행합니다.

1. Upstage API 키 확인과 `.env` 설정 안내
2. 만들고 싶은 스킬의 목적과 트리거 문구 인터뷰
3. 필요한 Upstage API 선택
4. `SKILL.md`, 참고 자료, 예시 자산 구조 작성

## 저장소 구조

```text
JNU-Upstage-Skillthon/
|-- .codex-plugin/
|   `-- plugin.json
|-- .agents/
|   `-- plugins/
|       `-- marketplace.json
|-- skills/
|   `-- solar-skill-creator/
|       |-- SKILL.md
|       |-- assets/
|       `-- references/
`-- assets/
```

참가자가 제출할 스킬도 같은 형식을 따르면 됩니다.

```text
skills/
`-- [내-스킬-이름]/
    |-- SKILL.md
    |-- scripts/      # 선택
    |-- references/   # 선택
    `-- assets/       # 선택
```

`SKILL.md`의 최소 frontmatter 예시는 아래와 같습니다.

```yaml
---
name: my-skill-name
description: 이 스킬이 무엇을 하고, 어떤 요청에서 반드시 사용해야 하는지 설명합니다.
---
```

## 체크리스트

- [ ] `SKILL.md`에 `name`, `description`이 들어 있다.
- [ ] Codex 환경에서 스킬이 의도대로 동작한다.
- [ ] 실제 API 키는 `.env`에만 넣고 커밋하지 않는다.

## References

| 문서 | 설명 |
|------|------|
| [Upstage Console Docs](https://console.upstage.ai/docs/capabilities) | Solar LLM, Embeddings, Document Parse API 레퍼런스 |
| [Upstage API Spec](https://console.upstage.ai/api/docs/for-agents/raw) | 에이전트 친화적인 Upstage API 원본 스펙 |

## 문의

- 담당: 조아라 연구원 / 고범수
- 전화: 062-530-5364 / 010-4012-1143
- 이메일: [rha852@jnu.ac.kr](mailto:rha852@jnu.ac.kr) / [gobeumsu@gmail.com](mailto:gobeumsu@gmail.com)
