# 어울림 미슐랭 가이드 — 사이트 사용 안내

## 📁 파일 구성

```
michelin_guide/
├── index.html       # 교사 화면 (실시간 카드 누적·발간식)
└── student.html     # 학생 화면 (개인 카드 작성·모둠 큐레이션)
```

## 🚀 설치 (GitHub Pages — 4·5월 방식 그대로)

1. 기존 `courage_spoon` 리포지토리와 같은 GitHub 계정에 새 리포지토리 `michelin_guide` 생성
2. 위 두 파일(`index.html`, `student.html`)을 리포지토리 루트에 업로드
3. **Settings → Pages → Source: main branch / root** 로 설정
4. 약 1분 후 접속:
   - 교사 화면: `https://eunnjin-ssam.github.io/michelin_guide/`
   - 학생 화면: `https://eunnjin-ssam.github.io/michelin_guide/student.html`

## 🔥 Firebase 설정 (가장 중요!)

**4·5월 사이트(`namsan_eats`, `courage_spoon`)와 동일한 Firebase 프로젝트를 그대로 사용합니다.**

`index.html`과 `student.html` 양쪽 파일에 동일한 `firebaseConfig` 블록이 있습니다.
4·5월 사이트의 config를 그대로 복사해 7개 `REPLACE_WITH_YOUR_*` 자리에 붙여넣으세요.

```javascript
const firebaseConfig = {
  apiKey: "...",                    // ← 4·5월 사이트와 동일
  authDomain: "...firebaseapp.com",
  databaseURL: "https://...firebaseio.com",
  projectId: "...",
  storageBucket: "...appspot.com",
  messagingSenderId: "...",
  appId: "..."
};
```

**데이터 저장 경로**: Firebase 안에 `michelin_guide/` 하위 노드로 자동 분리 저장됩니다. (4·5월 데이터와 섞이지 않음)

## 📋 수업 진행 순서

### 1단계: 평론가 등록 (도입)
- 교사 화면에서 학생용 QR 노출
- 학생들은 디벗으로 접속하여 이름·모둠 입력

### 2단계: 레시피 수집 (전개1)
- 교사 화면 **'▶ 레시피 수집 시작'** 버튼 클릭
- 학생들이 가치 재료 → 카테고리 → 레시피 카드 작성·제출
- 교사 화면에서 4개 모둠 카드가 실시간으로 모이는 모습 시연

### 3단계: 모둠 큐레이션 (전개2)
- 교사 화면 **'▶ 모둠 큐레이션 단계로'** 버튼 클릭
- 학생 화면에 **'모둠 큐레이션 시작'** 버튼이 자동 노출됨
- 모둠별로 토의하여 ★★★ 대표 레시피 1개 선정·투표
- 교사 화면에서 최다 득표 카드에 ★★★ 강조 표시

### 4단계: 가이드 발간식 (전개3·정리)
- 교사 화면 **'🏆 어울림 미슐랭 가이드 발간!'** 버튼 클릭
- 검은 배경의 가이드북 화면에 4모둠 대표 레시피가 발간됨
- QR 코드로 참관 선생님께 공유
- '인쇄/PDF 저장' 버튼으로 가이드북을 PDF로 출력 가능

## 🔄 데이터 초기화

수업 시작 전에 교사 화면 첫 페이지의 **'🗑 데이터 초기화'** 버튼으로 이전 데이터 삭제 가능합니다.

## 🎨 디자인

- 4월 「남산이츠」와 5월 「용기 한 스푼」의 베이지·갈색 톤을 계승
- 미슐랭 컨셉 강조를 위한 골드(★) 포인트
- Gowun Dodum / Jua 폰트로 따뜻한 손글씨 느낌 유지

## 📝 비고

- 모바일 우선 디자인 (학생 디벗)
- Firebase Realtime Database 사용 (무료 티어로 충분)
- 인터넷 연결 필수
