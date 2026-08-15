# 신나는 팔도 사투리 탐험대! 🗣️

한국의 아름다운 지역 사투리를 배우고 연습하는 학생용 웹 애플리케이션입니다.

## 🎯 주요 기능

### 1. 사투리 번역기
- 표준어를 6개 지역 사투리로 즉시 번역
- 음성 합성을 통한 발음 학습
- 클립보드 복사 기능

**지원 지역:**
- 🏙️ 표준어(서울)
- 🌲 강원도
- 🌾 충청도
- 🌊 경상도
- 🍚 전라도
- 🍊 제주도

### 2. 사투리 퀴즈
- 5개 문제로 구성된 대화형 퀴즈
- 즉각적인 정답/오답 피드백
- 최종 점수 평가 및 성취도 표시

## 🏗️ 프로젝트 구조 (개선된 아키텍처)

```
src/
├── models/          # 데이터 정의 (타입, 상수)
│   └── dialectData.ts
├── services/        # 비즈니스 로직 (번역, 퀴즈 판정)
│   ├── dialectTranslator.ts
│   └── quizService.ts
├── hooks/           # 상태 관리 (재사용 가능 로직)
│   └── useQuiz.ts
├── components/      # UI 컴포넌트 (프레젠테이션만)
│   ├── App.tsx
│   ├── Translator.tsx
│   ├── Quiz.tsx
│   ├── QuizQuestion.tsx
│   ├── QuizResult.tsx
│   └── RegionSelector.tsx
└── main.tsx
```

## 🎨 기술 스택

- **React 18** - UI 라이브러리
- **TypeScript** - 타입 안정성
- **Tailwind CSS** - 스타일링
- **Vite** - 빌드 도구
- **Lucide Icons** - 아이콘

## 📦 설치 및 실행

### 1. 저장소 클론
```bash
git clone https://github.com/YOUR_USERNAME/dialect-quiz-app.git
cd dialect-quiz-app
```

### 2. 의존성 설치
```bash
npm install
```

### 3. 개발 서버 실행
```bash
npm run dev
```
브라우저에서 `http://localhost:3000` 접속

### 4. 프로덕션 빌드
```bash
npm run build
npm run preview
```

## 🌐 배포 (GitHub Pages)

### 자동 배포 방법
1. 이 저장소를 GitHub에 fork/push
2. GitHub Actions가 자동으로 빌드 및 배포
3. `https://YOUR_USERNAME.github.io/dialect-quiz-app` 접속

### 수동 배포 (Vercel)
```bash
npm install -g vercel
vercel
```

## 📊 개선 사항 (원본 대비)

| 항목 | 원본 | 개선 후 |
|------|------|--------|
| 코드 구조 | 모놀리식 | 계층 분리 (Model/Service/Component) |
| 타입 안정성 | 미약함 | TypeScript 강화 |
| 테스트 가능성 | 낮음 | 서비스 계층 분리로 높음 |
| 확장성 | 제한적 | 데이터/로직 분리로 용이 |
| CI/CD | 없음 | GitHub Actions 자동 배포 |
| 성능 | 미최적화 | Code splitting, Tree shaking |

## 🧪 기능 테스트 예시

### 번역기 테스트
```
입력: "밥 먹었어?"
강원도 출력: "밥 먹었우과?"
충청도 출력: "밥 먹었슈?"
경상도 출력: "밥 묵었나?"
```

### 퀴즈 테스트
- 5개 문제 순차 출력 ✓
- 정답/오답 판정 ✓
- 실시간 점수 업데이트 ✓
- 최종 성취도 표시 ✓

## 📝 라이선스
MIT License

## 🤝 기여 방법
1. Fork the repo
2. Feature branch 생성 (`git checkout -b feature/amazing-feature`)
3. Changes commit (`git commit -m 'Add amazing feature'`)
4. Branch push (`git push origin feature/amazing-feature`)
5. Pull Request 열기

## 📧 문의
이메일이나 GitHub Issues로 문의해주세요.
