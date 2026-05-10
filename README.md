# PD 인터뷰 스튜디오

당신만의 AI PD가 한국어로 인터뷰합니다. 채널 톤에 맞춰 영상 대본 초안까지.

---

## 🚀 GitHub Pages 배포 (5분)

### 1. GitHub 저장소 만들기

1. [github.com](https://github.com) 로그인
2. 우상단 **+** → **New repository**
3. Repository name: `pd-studio` (또는 원하는 이름)
4. **Public** 선택
5. **Create repository**

### 2. 파일 업로드

저장소 페이지에서:

1. **Add file** → **Upload files**
2. 이 폴더(`pd-studio/`)의 **모든 파일 11개를 드래그 앤 드롭**:
   - `index.html` — 메인 앱
   - `react.min.js`, `react-dom.min.js` — ⚠️ React 라이브러리 (꼭 같이 올려야 앱이 뜸)
   - `manifest.json` — PWA 매니페스트
   - `sw.js` — 서비스 워커
   - `icon.svg`, `icon-192.png`, `icon-512.png`, `apple-touch-icon.png` — 아이콘
   - `.nojekyll` — 숨김 파일 (꼭 같이)
3. 아래 **Commit changes** 클릭

`.nojekyll`이 안 올라가면 **Add file → Create new file → 파일명 `.nojekyll`** 으로 직접 만들고 빈 채로 커밋하세요.

### 3. GitHub Pages 활성화

저장소 페이지에서:

1. **Settings** 탭
2. 좌측 메뉴 **Pages**
3. **Source** → **Deploy from a branch**
4. **Branch** → `main` (또는 `master`) → `/(root)` → **Save**
5. 1~2분 후 페이지 상단에 표시되는 URL이 배포 주소  
   예: `https://username.github.io/pd-studio/`

---

## 🔑 첫 사용 (사용자 본인의 API 키 등록)

배포된 URL로 접속하면 가장 먼저 **API 키 입력 화면**이 떠요.

### Anthropic API 키 발급

1. [console.anthropic.com](https://console.anthropic.com/settings/keys) 가입 (무료, 신규 가입 시 **$5 크레딧** 지급)
2. 좌측 메뉴 **API Keys** → **Create Key**
3. 키 복사 (보통 `sk-ant-api03-...`로 시작)
4. 앱 화면에 붙여넣고 **저장하고 시작하기**

### 비용 감각

- 인터뷰 1회 (질문 5~10개 + 대본 생성): 약 **₩30~100** (Sonnet 4.5 기준)
- 신규 가입 $5 크레딧으로 **수십 회** 가능
- 키는 **이 기기 브라우저에만** 저장되고 외부로 전송되지 않아요

---

## 📱 휴대폰 홈 화면에 추가 (PWA)

배포된 URL에서:

**iOS Safari**: 공유 버튼 → **홈 화면에 추가**  
**Android Chrome**: 메뉴 (⋮) → **앱 설치** 또는 **홈 화면에 추가**

설치하면 일반 앱처럼 홈에서 바로 실행 가능해요.

---

## 🎙️ 사용 흐름

1. **내 채널 등록** — 채널 이름, 톤, 금지어 등을 입력
2. **주제 입력** + **진행 방식 선택** (AI / 질문지 모드)
3. **인터뷰** — PD가 질문 → 음성 또는 텍스트로 답변 → 다음 질문
4. **대본 초안** — 채널 구조에 맞춰 자동 정리. 다운로드/공유 가능

모든 데이터는 사용자 본인 브라우저에만 저장됩니다.

---

## 🔄 업데이트 방법

코드를 수정하고 GitHub에 새로 업로드하면 끝. 1~2분 후 새 버전이 자동 반영돼요.

---

## ❓ 문제 해결

**"API 키가 잘못됐어요"** → 설정(⚙)에서 다시 입력. 키 앞뒤 공백 주의.

**"모델을 찾을 수 없어요"** → 설정에서 다른 모델 선택 (예: Sonnet 4 또는 Haiku 4.5).

**음성 인식이 안 됨** → 휴대폰 설정에서 브라우저의 마이크 권한 허용. iOS는 Safari에서, Android는 Chrome에서 가장 잘 작동.

**저장된 데이터가 사라짐** → 브라우저의 사이트 데이터를 삭제하면 채널/세션도 함께 삭제됩니다. 시크릿 모드에서는 저장되지 않아요.

---

## 📂 파일 구조

```
pd-studio/
├── index.html          # 메인 앱 (React 컴파일된 JS 포함)
├── react.min.js        # React 18 (로컬, CDN 의존 제거)
├── react-dom.min.js    # ReactDOM 18 (로컬)
├── manifest.json       # PWA 매니페스트
├── sw.js               # 서비스 워커
├── icon.svg            # 아이콘 원본
├── icon-192.png        # PWA 아이콘 (작음)
├── icon-512.png        # PWA 아이콘 (큼)
├── apple-touch-icon.png # iOS용 아이콘
├── .nojekyll           # GitHub Pages용 (Jekyll 처리 비활성화)
└── README.md           # 이 파일
```

---

Made with Claude · 인생2막 라디오 · 수명해커 · 마더클럽
