# 배포 가이드 (정적 사이트)

이 폴더는 HTML + JSON만 있는 정적 사이트라 **빌드 없이** 그대로 올리면 됩니다.

---

## 방법 1: Netlify Drop (가장 간단, 1분)

1. **[https://app.netlify.com/drop](https://app.netlify.com/drop)** 접속
2. `aptitude-test` 폴더 전체를 드래그해서 화면에 놓기
3. 배포 완료 후 나오는 **URL**로 접속 (예: `https://random-name-123.netlify.app`)

- 계정 없이도 한 번 배포 가능 (나중에 URL이 만료될 수 있음)
- **회원가입 후** 로그인하고 드래그하면 URL이 계속 유지됨 (무료)

---

## 방법 2: GitHub Pages (무료, 영구)

1. **GitHub 계정**이 있다면:
   - [github.com](https://github.com) → New repository 생성 (이름 예: `aptitude-test`)
   - 저장소 생성 시 "Add a README" 등은 선택 안 해도 됨

2. **터미널**에서 프로젝트 폴더로 이동 후:

   ```bash
   cd c:\Users\user\Desktop\aptitude-test
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/내아이디/aptitude-test.git
   git push -u origin main
   ```
   (`내아이디`를 본인 GitHub 아이디로 바꾸기)

3. GitHub 저장소 페이지에서:
   - **Settings** → 왼쪽 메뉴 **Pages**
   - **Source**에서 "Deploy from a branch" 선택
   - **Branch**를 `main`, 폴더를 `/ (root)` 로 두고 Save

4. 1~2분 뒤 `https://내아이디.github.io/aptitude-test/` 로 접속 가능

- `index.html`이 있으면 그 주소가 메인 페이지
- `meeting_guide.html`은 `https://내아이디.github.io/aptitude-test/meeting_guide.html` 로 접속

---

## 방법 3: Vercel (무료)

1. [vercel.com](https://vercel.com) 회원가입 (GitHub로 로그인 가능)
2. **Add New** → **Project** → GitHub 저장소 연결 (방법 2에서 만든 repo)
   - 또는 **CLI**: `npx vercel` 실행 후 폴더 선택
3. 배포 완료 후 나오는 URL로 접속

---

## 요약

| 방법           | 난이도 | 특징                          |
|----------------|--------|-------------------------------|
| **Netlify Drop** | ★☆☆   | 폴더 드래그만 하면 됨, 가장 빠름 |
| **GitHub Pages** | ★★☆   | 무료·영구, URL 고정           |
| **Vercel**       | ★★☆   | GitHub 연동 시 자동 재배포    |

**지금 당장 팀원에게 링크만 공유하려면** → Netlify Drop  
**나중에 수정해도 계속 쓸 주소가 필요하면** → GitHub Pages 추천
