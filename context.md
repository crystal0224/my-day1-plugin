# my-day1 플러그인 프로젝트 컨텍스트

## 프로젝트 개요
- **목적**: 정구봉님의 AI Native Camp - Day 1을 기반으로 비개발자 친화적으로 확장한 Claude Code 온보딩 플러그인
- **타겟 사용자**: 비개발자 (HR, 디자이너, PM, 마케터 등)
- **핵심 가치**: Essential Path를 통해 1~1.5시간 만에 실무 투입 가능
- **배포**: GitHub (crystal0224/my-day1)

## 개발 컨텍스트

### 디자인 결정사항

#### 1. Essential Path vs 전체 경로
- **문제**: 원본은 13개 블록 전체 학습 (2~3시간) → 비개발자 완주율 낮음
- **해결**: 필수 7개만 선택하는 경로 추가
- **목표**: 완주율 50% → 80%
- **근거**: 실무 투입에 필요한 최소 기능만 집중 학습

#### 2. 직무별 개인화
- **문제**: 기술 용어가 비개발자에게 장벽
- **해결**: 150개 비유 (15개 기술 용어 × 10개 직업군)
- **예시**:
  - HR: "CLI는 Excel 수식처럼 텍스트로 명령하는 방법"
  - 디자이너: "CLI는 Figma 단축키의 강력 버전"
  - PM: "CLI는 프로젝트 커맨드 센터"
- **효과**: 각 직무에 익숙한 용어로 설명하여 이해도 향상

#### 3. 학습 지원 시스템
- **Help 시스템**: 막혔을 때 "help" 입력으로 4가지 상황별 도움
  1. 명령어가 안 돼요 → 화면 캡처 요청 → 진단 → 구체적 해결법
  2. 무슨 말인지 모르겠어요 → 더 쉬운 비유로 재설명
  3. 이 미션 건너뛰고 싶어요 → skip 가능 (필수는 경고)
  4. 다른 질문이 있어요 → 자유 질문
- **재진입 플로우**: 중단 후 복귀 시 진행 상황 자동 로드
- **마일스톤 배지**: 진행 상황 시각화 (🎯 기초 → 🏆 핵심 → 🚀 마스터)

### 기술 제약사항

#### 1. Claude Code 플러그인 시스템
- `.claude-plugin/plugin.json` 필수
- `skills/` 디렉토리에 스킬 파일 배치
- frontmatter 필수 (description, author, version)
- GitHub 저장소 기반 배포

#### 2. 참조 파일 구조
- 모든 참조 파일은 `skills/references/` 디렉토리에 위치
- 로컬 테스트 시 심볼릭 링크 사용 (개발 편의성)
- 파일 구조:
  ```
  skills/references/
  ├── motivation-stories.md   # 63개 동기부여 스토리
  ├── glossary.md             # 150개 용어 비유
  ├── block0-setup.md         # Setup 미션
  ├── block1-experience.md    # Experience 미션
  ├── block2-claudemd.md      # CLAUDE.md 미션
  ├── block3-1-skill.md       # Skill 미션 (필수)
  ├── block3-2-mcp.md         # MCP 미션 (심화)
  ├── block3-3-subagent.md    # Subagent 미션 (필수)
  └── ...
  ```

#### 3. 프로파일 저장소
- 사용자 프로파일: `~/.claude/memory/user-profile.md`
- 학습 진행 상황도 동일 파일에 저장
- 재진입 시 자동 로드
- 형식: YAML frontmatter + Markdown body

### 톤 및 스타일 가이드

#### 1. 친근하고 격려하는 톤
- "함께 시작해볼까요?" (명령형 X)
- "막힐 때는 help를 입력하세요!"
- 성취 시 축하 메시지 적극 활용
- 예시: "🎉 축하합니다! 기초 미션을 완료하셨어요!"

#### 2. 비개발자 친화적 언어
- 기술 용어는 항상 직무별 비유와 함께 제시
- 전문 용어보다 일상 언어 우선
- 예시는 실무 시나리오 기반
- "명령어를 실행합니다" → "명령어를 입력해보세요"

#### 3. 이모지 사용
- 진행 상황: ✓ (완료), ⏸ (중단)
- 배지: 🎯 (기초), 🏆 (핵심), 🚀 (마스터)
- 강조: 💡 (동기부여), 📖 (용어 설명), 💻 (실습)

#### 4. 협업적 톤 (중요!)
- 원본보다 "더 좋다"가 아닌 "확장했다"
- "대폭 강화" → "더해봤다"
- "차별점" → "확장한 부분"
- 원본에 대한 감사와 존중 표현

## 컨텐츠 구조

### 동기부여 스토리 (63개)
- 형식: 7개 필수 미션 × 9개 직업군
- 구조: 공감 → 사례 → 혜택
- 예시 (HR):
  ```
  💡 매번 똑같은 채용 이메일 20개 보내는 데 지치셨나요?

  채용 담당 김OO님(HR 3년차)은 매주 지원자 20명에게
  거의 비슷한 안내 이메일을 일일이 작성했습니다.

  Claude Code의 Skill을 배운 후, 이메일 템플릿을
  /send-interview-email 명령어 하나로 자동화했습니다.
  주 5시간 절약 → 면접 전략 수립에 집중!
  ```

### 용어 비유 (150개)
- 형식: 15개 기술 용어 × 10개 직업군
- 핵심 용어:
  - CLI (Command Line Interface)
  - 터미널 (Terminal)
  - git
  - GitHub
  - CLAUDE.md
  - Skill
  - MCP (Model Context Protocol)
  - Subagent
  - Hook
  - Plugin
  - 등...

### 학습 경로

#### Essential Path (필수 7개)
1. Setup - Claude Code 설치 및 환경 구성
2. Experience - 첫 대화로 느껴보기
3. CLAUDE.md - 개인화 설정 파일 만들기
4. Skill - 반복 작업 자동화
5. Subagent - 복잡한 작업 위임
6. 요약 - 지금까지 배운 것 정리
7. Basics - CLI 기초 명령어

#### 심화 과정 (선택 6개)
8. Why - Claude Code를 왜 써야 할까?
9. MCP - 외부 도구 연결
10. Agent Teams - 여러 에이전트 협업
11. Hook - 자동화 트리거
12. Plugin - 플러그인 생성
13. Break - 휴식 및 복습

## 버전 히스토리

### v1.0.0 (2026-02-15)
- 초기 개인화 온보딩 시스템
- 직업별 프로파일링

### v2.0.0 (2026-02-15)
- 전체 13개 블록 완전 구현
- 63개 동기부여 스토리
- 150개 용어 비유
- 9개 직업군 지원

### v3.0.0 (2026-02-15)
- **Essential Path 추가** (완주율 향상 목표)
- 마일스톤 배지 시스템
- Help 시스템
- 재진입 플로우
- Claude Code 플러그인 형식으로 전환

## 개발 환경

- **개발 도구**: Claude Code with Agent Teams
- **에이전트 협업**: 8명의 에이전트가 병렬 작업 (8배 효율)
- **테스트 환경**: macOS (darwin), ~/.claude/skills/my-day1
- **배포**: GitHub → Claude Code Commands Directory

## 향후 계획

### 단기 (1-2주)
- [ ] 사용자 피드백 수집
- [ ] 완료율 지표 측정
- [ ] 베타 테스트 (10-20명)
- [ ] 스크린샷/GIF 추가

### 중기 (1-2개월)
- [ ] 직무별 실무 과제 추가 개선
- [ ] 퀴즈 뱅크 확장
- [ ] Help 시스템 강화 (프로액티브 트리거)
- [ ] 성공 사례 수집

### 장기 (3개월+)
- [ ] 다국어 지원 검토 (현재 한국어만)
- [ ] 커스텀 직업 프로필 생성기
- [ ] AI Native Camp Day 2-7과 연계

## 알려진 제약사항

1. **Korean-only content**: 글로벌 확장 제한
2. **User profile location**: `~/.claude/memory/` 의존성
3. **File-based storage**: 클라우드 동기화 미지원
4. **Manual content updates**: 자동 콘텐츠 생성 불가

## 참고 링크

- **원본**: https://github.com/ai-native-camp/camp-1
- **GitHub 저장소**: https://github.com/crystal0224/my-day1
- **로컬 설치 위치**: ~/.claude/skills/my-day1
- **Commands Directory**: https://claudecodecommands.directory/

## 기여 가이드라인

### 새 직업 프로필 추가
1. `motivation-stories.md`에 7개 스토리 추가
2. `glossary.md`에 15개 용어 비유 추가
3. 테스트 후 PR 제출

### 새 미션 추가
1. `skills/references/blockN-name.md` 생성
2. Phase A-D 구조 따르기
3. 동기부여 스토리 작성
4. 퀴즈 및 실습 포함

### 번역 기여
1. `skills/references/en/` 폴더 생성
2. 문화적 맥락 고려하여 번역
3. 직업 프로필 현지화 (예: HR → Human Resources Manager)

---

**작성자**: 배수정 (SK아카데미 RF)
**최종 업데이트**: 2026-02-15
**문서 버전**: 1.0.0
