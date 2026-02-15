# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [3.0.0] - 2026-02-15

### Added
- **Essential Path 시스템**: 필수 7개 + 심화 6개 미션 분류로 비개발자 완주율 향상
- **마일스톤 배지 시스템**: 🎯 기초 완료, 🏆 핵심 완료, 🚀 마스터 배지
- **Help 시스템**: 4가지 상황별 도움 (명령어 오류, 이해 부족, 미션 건너뛰기, 자유 질문)
- **재진입 플로우**: 학습 중단 후 복귀 시 진행 상황 자동 로드 및 이어하기 지원
- **학습 경로 선택**: 빠른 시작(필수만) / 전체 과정 / 커스텀 경로
- **진행 상황 추적**: user-profile.md에 학습 진행률 자동 저장

### Changed
- 전체 구조를 Claude Code 플러그인 형식으로 전환
- README 톤앤매너를 협업적이고 확장 중심으로 조정
- 정구봉님의 AI Native Camp 원본 크레딧 및 설치 방법 명시

## [2.0.0] - 2026-02-15

### Added
- 전체 13개 블록 완전 구현 (Setup부터 Basics까지)
- 63개 동기부여 스토리 (7개 필수 미션 × 9개 직업군)
- 150개 용어 비유 (15개 기술 용어 × 10개 직업군)
- 9개 직업군 지원 (HR, 개발자, 디자이너, PM, 분석가, 마케터, 일반 사무/관리, 연구원/학생, 기타)
- 전공별 맞춤 설명 (인문/사회, 자연/공학, 예체능, 경영/상경, 기타)
- 터미널 경험별 맞춤 설명 (처음, 조금, 자주)

### Changed
- 프로파일링 시스템 강화 (직업 + 전공 + 터미널 경험 3차원 개인화)
- 참조 파일 구조화 (skills/references/ 디렉토리)

## [1.0.0] - 2026-02-15

### Added
- 초기 개인화 Claude Code 온보딩 시스템
- 직업별 프로파일링 기능
- 기본 미션 구조 (Phase A-D)
- 사용자 프로필 저장 (~/.claude/memory/user-profile.md)

---

## 배포 노트

### v3.0.0 주요 개선사항
- **비개발자 완주율 목표**: 50% → 80%
- **학습 시간**: 2~3시간 → 1~1.5시간 (Essential Path 선택 시)
- **지원 시스템**: Help, 재진입, 배지로 학습 동기 강화

### 향후 계획
- 사용자 피드백 기반 컨텐츠 개선
- 영어 버전 검토
- 커뮤니티 기여 가이드 확대
