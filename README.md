# brain-storming

소프트웨어 개발 아이디어를 설계 전에 대화로 정립·검증하고 아이디어 문서로 남기는 Claude Code skill입니다.

[obra/superpowers](https://github.com/obra/superpowers)의 brainstorming skill은 곧바로 설계 스펙 작성으로 이어지지만, 이 skill은 그 전 단계인 "이 아이디어를 만들 가치가 있는가, 만들 수 있는가"를 확인하는 데 집중합니다.

- 발산 → 명확화 → 검증 → 수렴 → 문서화 5단계로 진행합니다.
- 질문은 한 번에 하나씩, 가능하면 객관식으로 합니다.
- 검증 단계에서 현재 저장소와 기존 솔루션을 조사하고 MVP 범위를 제안합니다.
- 결과는 `docs/ideas/<slug>.md` 문서 하나로 저장합니다.
- 설계 스펙·구현 계획·코드는 작성하지 않습니다.
- `/brain-storming`으로 직접 호출할 때만 동작합니다.

## 설치

```bash
git clone https://github.com/isihwan/brainstorming-skill.git
mkdir -p ~/.claude/skills && cp -r brainstorming-skill/skills/brain-storming ~/.claude/skills/
```

업데이트할 때는 `git -C brainstorming-skill pull` 후 두 번째 명령을 다시 실행합니다.

## 사용 예시

```text
/brain-storming 사내 API 문서를 코드 주석에서 자동으로 만들어 주는 CLI
```

Claude가 질문을 하나씩 던지며 5단계를 진행하고, 마지막에 `docs/ideas/<slug>.md`를 저장한 뒤 종료합니다. 도중에 "정리하자"라고 하면 바로 문서화 단계로 넘어갑니다.

## 파일 구조

```text
.
├── README.md
└── skills/
    └── brain-storming/
        ├── SKILL.md      # skill 본문: 진행 규칙, 5단계, 완료 기준, 위임 규칙
        └── template.md   # 최종 아이디어 문서 골격 (필수 항목 9개)
```
