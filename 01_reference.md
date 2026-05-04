# 리서치 종합: 비개발자를 위한 Claude 활용 정적 사이트 구축

> 대상: 비개발자 | 저자: 김상기 | 문체: 존댓말(해요체)
> 예시 프로젝트: 포트폴리오(GitHub Pages) + 컨퍼런스 후기(Vercel)
> 수집일: 2026-05-04

---

## 1. 시대 배경 — 코딩 없이 사이트를 만드는 시대

### 1.1 바이브 코딩의 등장
- AI에게 자연어로 설명하면 코드를 생성하는 개발 방식
- Vercel v0 사용자의 63%가 비개발자
- "코딩 문법 몰라도, 느낌(Vibe)과 논리만 전달하면 된다"

### 1.2 핵심 도구 생태계

| 도구 | 역할 | 비용 |
|------|------|------|
| Claude (claude.ai) | AI 대화로 코드 생성, Artifacts로 미리보기 | 무료/Pro |
| Claude Code | CLI 기반 자동 개발, 배포 | Pro 이상 |
| GitHub | 코드 저장소 + GitHub Pages 무료 호스팅 | 무료 |
| Vercel | 자동 배포 + 커스텀 도메인 | 무료 Hobby |
| v0 (v0.app) | 자연어로 React 컴포넌트 생성 | 무료 시작 |

### 1.3 Claude Artifacts의 가능성
- 웹페이지를 대화로 생성하고 즉시 미리보기
- 디자이너+개발자와 동시에 작업하는 경험
- HTML/CSS/React 코드를 복사해서 바로 배포 가능
- 파일 업로드(이력서, 사진)로 콘텐츠 자동 반영

---

## 2. GitHub Pages — 무료 포트폴리오 호스팅

### 2.1 개요
- GitHub이 제공하는 무료 정적 웹사이트 호스팅
- `username.github.io` 도메인 자동 제공
- 정적 파일(HTML/CSS/JS) 업로드만으로 사이트 운영
- 커스텀 도메인 연결 가능

### 2.2 배포 과정 (비개발자 관점)
1. GitHub 계정 생성
2. `username.github.io` 이름의 레포지토리 생성
3. HTML 파일 업로드 (Claude가 생성한 코드)
4. Settings → Pages에서 활성화
5. 몇 분 후 사이트 접속 가능

### 2.3 실제 사례
- 김상기 포트폴리오: ksangki.github.io (React 기반)
- 디자이너 포트폴리오 이전 사례 (Medium 블로그)
- "10분 만에 포트폴리오 만들기" (시리얼 블로그)

---

## 3. Vercel — 자동 배포 플랫폼

### 3.1 개요
- GitHub 연동 → 코드 푸시 시 자동 빌드+배포
- `project-name.vercel.app` 도메인 무료 제공
- React/Next.js 프로젝트 최적 지원
- 약 90초 만에 변경사항 반영

### 3.2 배포 과정 (비개발자 관점)
1. vercel.com 가입 (GitHub 계정으로 로그인)
2. GitHub 레포지토리 Import
3. Deploy 클릭
4. 자동으로 빌드+배포 완료
5. 이후 GitHub에 변경 사항 push하면 자동 재배포

### 3.3 v0.app과의 연계
- v0에서 자연어로 페이지 디자인
- 생성된 React 코드를 프로젝트에 추가
- Vercel에 자동 배포

### 3.4 실제 사례
- HR Exchange 2026: hr-exchange-2026.vercel.app (React 기반 컨퍼런스 사이트)

---

## 4. Claude로 사이트 만드는 워크플로우

### 4.1 Artifacts 방식 (가장 쉬움)
1. Claude에게 원하는 페이지 설명
2. Artifacts에서 실시간 미리보기
3. 코드 복사 → HTML 파일로 저장
4. GitHub Pages에 업로드

### 4.2 Claude Code 방식 (더 강력)
1. Claude Code에서 프로젝트 생성
2. 자연어로 사이트 구조/디자인 지시
3. 자동으로 파일 생성, 수정
4. GitHub에 푸시 → Vercel 자동 배포

### 4.3 효과적인 프롬프트 패턴
- 역할 + 목적 + 구체적 요구사항
- "저는 마케터입니다. 개인 포트폴리오 사이트를 만들고 싶어요. 깔끔한 디자인으로..."
- 이력서/경력 정보를 직접 붙여넣기
- 참고 사이트 URL 제시
- 반복적 수정: "헤더 색상을 파란색으로", "섹션 순서를 바꿔주세요"

---

## 5. 프로젝트 1 — 포트폴리오 사이트

### 5.1 구성 요소
- 히어로 섹션 (이름, 직함, 한 줄 소개)
- About Me (자기소개, 사진)
- Skills/경력 (타임라인 또는 카드)
- Projects/포트폴리오 (작업물 갤러리)
- Contact (연락처, 소셜 링크)
- 반응형 디자인 (모바일 대응)

### 5.2 기술 선택지
- **초급:** 순수 HTML/CSS (1파일, GitHub Pages 직접 배포)
- **중급:** React (Claude Code로 생성, Vercel 배포)
- **고급:** Next.js + 애니메이션 (v0 활용)

---

## 6. 프로젝트 2 — 컨퍼런스/이벤트 후기 사이트

### 6.1 구성 요소
- 이벤트 배너/히어로
- 프로그램/세션 목록
- 발표자 프로필
- 사진 갤러리
- 후기/하이라이트
- 다음 이벤트 안내

### 6.2 실전 예시
- HR Exchange 2026 (hr-exchange-2026.vercel.app)
- React 기반, Vercel 배포

---

## 7. 비개발자가 알아야 할 최소 지식

### 7.1 Git/GitHub 기초
- 레포지토리 = 프로젝트 폴더
- 커밋 = 저장
- 푸시 = 업로드
- GitHub Desktop (GUI) 사용 추천

### 7.2 HTML/CSS 기본 개념 (읽을 수 있는 수준)
- HTML: 구조 (제목, 문단, 이미지, 링크)
- CSS: 스타일 (색상, 크기, 위치)
- 직접 작성하지 않지만, Claude가 만든 코드를 이해할 수 있어야 함

### 7.3 터미널 기초 (Claude Code 사용 시)
- 폴더 이동, 명령 실행
- Claude Code가 대부분 안내

---

## 8. 참고 자료

### 한국어
- "10분 만에 포트폴리오 웹사이트 만들기: 코딩 없이 AI로" (시리얼 블로그)
- "GitHub Pages로 웹사이트 무료 호스팅하기" (Dale Seo 블로그)
- "Github Pages로 디자인 포트폴리오 이사하는 중기" (Medium)

### 영어
- "How to Build and Deploy a Website With Claude AI — No Code, Free Hosting" (Medium)
- "How I Built a Full Website With AI and Zero Code in 2026" (Substack)
- "Build and Deploy a Website Using Claude Code (From Zero to Live)" (Medium)
- "In 5 Steps: Launch a Dynamic Landing Page with Vercel v0" (FlexOS)
- "Claude Artifacts: Build Interactive Apps Without Coding" (QWE AI Academy)

### 공식 문서
- GitHub Pages 문서: pages.github.com
- Vercel 문서: vercel.com/docs
- Claude Artifacts 가이드: claude.com/resources
- v0 by Vercel: v0.app
