# 배포 가이드

## 🚀 배포 옵션별 가이드

### 1️⃣ GitHub Pages (무료, 추천)

**장점:**
- 완전 무료
- GitHub 저장소에 자동 배포
- HTTPS 기본 제공
- 커스텀 도메인 지원

**배포 방법:**

1. **GitHub에 코드 푸시**
```bash
git add .
git commit -m "Initial commit"
git push origin main
```

2. **GitHub Actions 자동 실행**
   - `.github/workflows/deploy.yml`이 자동으로 실행됨
   - 빌드 → dist 폴더 생성 → GitHub Pages 배포

3. **배포 확인**
   - Settings → Pages → 배포 URL 확인
   - `https://YOUR_USERNAME.github.io/dialect-quiz-app`

---

### 2️⃣ Vercel (무료, 매우 간단)

**장점:**
- 1-클릭 배포
- 빠른 성능
- 커스텀 도메인 지원
- 환경변수 관리 용이

**배포 방법:**

```bash
# 1. Vercel CLI 설치
npm install -g vercel

# 2. Vercel 로그인 (브라우저 팝업)
vercel

# 3. 배포 시작
vercel --prod
```

자동 배포 설정:
```bash
# GitHub 연동으로 main 푸시 시 자동 배포
vercel --prod
```

---

### 3️⃣ Netlify (무료)

**배포 방법:**

1. 빌드
```bash
npm run build
```

2. dist 폴더를 [Netlify](https://netlify.com)에 드래그앤드롭

또는 CLI:
```bash
npm install -g netlify-cli
netlify deploy --prod --dir=dist
```

---

### 4️⃣ Cloudflare Pages (무료, 고성능)

**배포 방법:**

1. [Cloudflare Pages](https://pages.cloudflare.com/)에서 GitHub 연동
2. 빌드 설정:
   - **Build command:** `npm run build`
   - **Build output directory:** `dist`
3. 자동 배포 시작

---

## 📋 배포 전 체크리스트

- [ ] `npm run build` 성공 여부 확인
- [ ] `npm run type-check` 통과
- [ ] 모든 링크가 상대 경로인지 확인
- [ ] 메타 태그 설정 (OG 이미지, 설명)
- [ ] 모바일 반응형 테스트

---

## 🔍 배포 후 검증

### 성능 측정
```bash
# Lighthouse로 성능 테스트
npm run build
npm run preview
# 브라우저에서 DevTools → Lighthouse
```

### SEO 확인
- Title 태그 ✓
- Meta description ✓
- Open Graph 메타 태그 ✓
- 모바일 반응형 ✓

---

## 🌐 커스텀 도메인 연결

### GitHub Pages
Settings → Pages → Custom domain → 도메인 입력

### Vercel
Project Settings → Domains → Add

---

## 📊 배포 후 모니터링

### Google Analytics 추가 (선택)
```html
<!-- index.html의 <head>에 추가 -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
```

---

## 🆘 문제 해결

| 문제 | 해결책 |
|------|-------|
| 빌드 실패 | `npm run type-check` 확인 후 오류 수정 |
| 배포 후 404 | `vite.config.ts`의 `base` 설정 확인 |
| 느린 로딩 | Code splitting 확인, 이미지 최적화 |
| CORS 에러 | API 요청이 없으므로 무시 |

---

## 🎯 추천 배포 순서

1. **로컬 테스트** → `npm run dev`
2. **프로덕션 빌드** → `npm run build`
3. **프리뷰** → `npm run preview`
4. **GitHub 푸시** → 자동 배포
5. **배포 확인** → 브라우저에서 접속

**총 소요 시간: 5분**
