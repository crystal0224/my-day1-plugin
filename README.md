# my-day1: 개인화 Claude Code 온보딩 플러그인 🚀

[![Version](https://img.shields.io/badge/version-3.0.0-blue.svg)](https://github.com/crystal0224/my-day1-plugin)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

직업/전공/터미널 경험에 따라 예시와 설명을 자동으로 맞춤화하는 Claude Code 온보딩 스킬입니다.

## ✨ 주요 특징

### 🎯 Essential Path (v3.0)
- **필수 7개 미션**만 완료해도 실무 투입 가능 (1~1.5시간)
- 심화 6개는 선택적 학습
- 3가지 학습 경로: 빠른 시작 / 전체 / 커스텀

### 💡 동기부여 시스템
- **63개 스토리** (7 필수 미션 × 9 직업군)
- 각 스토리: 공감 질문 → 실제 사례 (Before/After) → 완료 혜택

### 📖 용어 장벽 제거
- **150개 비유** (15 기술 용어 × 10 직업군)
- 직업별 맞춤 설명
  - HR: CLI → "Excel 수식처럼, 텍스트로 컴퓨터에 명령"
  - 디자이너: CLI → "Figma 단축키의 강력 버전"
  - PM: CLI → "프로젝트 커맨드 센터"

### 🏆 마일스톤 배지
- 🎯 **기초 완료**: 미션 0, 1, 3-1 완료
- 🏆 **핵심 완료**: 필수 7개 완료 (실무 투입 가능)
- 🚀 **마스터**: 전체 13개 완료

### ❓ Help 시스템
막혔을 때 "help" 입력 시:
1. 명령어가 안 돼요 → 진단 + 해결법
2. 무슨 말인지 모르겠어요 → 쉬운 재설명
3. 이 미션 건너뛰고 싶어요 → skip 가능
4. 다른 질문이 있어요 → 자유 질문

### 🔄 재진입 플로우
중도 이탈 후 복귀 시:
- 진행 상황 요약 (완료 미션, 진행률, 획득 배지)
- 이어서 하기 / 처음부터 다시 / 특정 미션 선택

---

## 📦 설치 방법

### Claude Code에서 설치

```bash
# 터미널에서
claude

# Claude Code에서
/plugin install crystal0224/my-day1-plugin
```

또는 수동 설치:

```bash
git clone https://github.com/crystal0224/my-day1-plugin.git
cd my-day1-plugin
claude plugin install .
```

---

## 🚀 사용 방법

### 1. 스킬 실행

```bash
claude
/my-day1
```

### 2. 프로파일 설정 (처음이면)

3가지 질문에 답변:
1. **직업**: HR, 개발자, 디자이너, PM, 분석가, 마케터, 일반 사무, 연구원/학생
2. **전공** (선택): 전공이 있으면 입력
3. **터미널 경험**: 익숙해요 / 해본 적 있어요 / 처음이에요

### 3. 학습 경로 선택

- **빠른 시작** (필수 7개만, 1~1.5시간) ⭐ 추천
- **전체 과정** (13개 전체, 2~3시간)
- **커스텀** (필요한 미션만 선택)

### 4. 미션 진행

- 💡 동기부여 스토리 확인
- 📖 용어 출현 시 비유 확인
- 💻 실습 진행
- ✅ 퀴즈로 이해도 확인
- 🎯 실무 과제로 적용
- 막히면 "help" 입력!

---

## 📋 필수 미션 로드맵 (Essential Path)

| 미션 | 주제 | 시간 | 난이도 | 배지 |
|------|------|------|--------|------|
| 미션 0 | Setup | 5분 | ⭐ 쉬움 | |
| 미션 1 | Experience | 10분 | ⭐ 쉬움 | |
| 미션 3-1 | CLAUDE.md | 10분 | ⭐⭐ 보통 | 🎯 기초 완료 |
| 미션 3-2 | Skill | 15분 | ⭐⭐ 보통 | |
| 미션 3-4 | Subagent | 10분 | ⭐⭐ 보통 | |
| 미션 요약 | 7개 기능 요약 | 5분 | ⭐ 쉬움 | |
| 미션 4 | Basics | 10분 | ⭐⭐ 보통 | 🏆 핵심 완료 |

**총 예상 시간**: 1~1.5시간

---

## 🎯 지원 직업군

| 직업군 | 비유 예시 | 실무 과제 예시 |
|--------|-----------|----------------|
| HR/인사 담당자 | "회사 인사 규정집" | 인사 업무 규칙을 CLAUDE.md에 추가 |
| 백엔드 개발자 | ".gitignore, 설정 파일" | 코딩 컨벤션을 CLAUDE.md에 저장 |
| UI/UX 디자이너 | "디자인 시스템 가이드" | 디자인 시스템을 CLAUDE.md에 저장 |
| 제품 기획자/PM | "프로젝트 킥오프 문서" | 프로젝트 규칙을 CLAUDE.md에 저장 |
| 데이터 분석가 | "데이터 사전" | 분석 규칙을 CLAUDE.md에 저장 |
| 마케터/콘텐츠 제작자 | "브랜드 가이드라인" | 콘텐츠 규칙을 CLAUDE.md에 저장 |
| 일반 사무/관리 | "업무 매뉴얼" | 업무 규칙을 CLAUDE.md에 저장 |
| 연구원/학생 | "연구 노트 표지" | 공부 규칙을 CLAUDE.md에 저장 |

---

## 📈 성과 목표

| 지표 | 기존 | 목표 |
|------|------|------|
| 완료율 | ~50% | 80% |
| 중도 이탈률 | ~50% | 20% |
| 실무 적용 의지 | - | 70%+ |
| 용어 이해도 | - | 80%+ |

---

## 🛠 개발 정보

### 기술 스택
- Claude Code Skill System
- Markdown (skill 파일)
- YAML (참조 파일)

### 파일 구조
```
my-day1-plugin/
├── .claude-plugin/
│   └── plugin.json          # 플러그인 메타데이터
├── skills/
│   ├── my-day1.md           # 메인 스킬 파일
│   └── references/          # 미션별 콘텐츠
│       ├── motivation-stories.md  (63개)
│       ├── glossary.md            (150개)
│       └── block*.md              (미션 콘텐츠)
└── README.md                # 이 파일
```

### 버전 히스토리
- **v1.0.0** (2026-02-15): 초기 개인화 온보딩
- **v2.0.0** (2026-02-15): 전체 13개 블록 구현
- **v3.0.0** (2026-02-15): Essential Path 추가 - 비개발자 완료율 개선

---

## 🤝 기여하기

이슈와 PR을 환영합니다!

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 라이선스

MIT License - 자유롭게 사용하세요!

---

## 📞 문의

- **GitHub Issues**: https://github.com/crystal0224/my-day1-plugin/issues
- **Email**: crystal0224@example.com

---

## 🙏 감사의 말

이 플러그인은 Claude Code의 Agent Teams를 활용하여 8명의 에이전트가 병렬로 작업했습니다 (8배 효율 향상).

**Made with ❤️ by crystal0224 and Claude Sonnet 4.5**
