# 김유빈 포트폴리오

- **배포 주소:** https://home-livid-six.vercel.app/
- **GitHub 저장소:** https://github.com/dismalvin/home
- **수정 파일:** `index.html` (이 파일 하나만 수정하면 됩니다)

---

## 사이트 구조 (한눈에 보기)

| 섹션 | 파일 위치 (`index.html` 안) | 수정 예시 |
|------|-----------------------------|-----------|
| 소개 | `#about` | 자기소개 문단 |
| 연구 분야 | `#research` | 키워드 태그 |
| 학력 & 활동 | `#career` | 학력, 직책 목록 |
| 출판 | `#publications` | 논문·역서 목록 |
| 비평 | `#criticism` | 리뷰·기고 목록 |
| 번역 | `#translation` | 번역 게재·공연 |
| 심사 & 드라마투르그 | `#activities` | 활동 경력 |
| 진행 중 프로젝트 | `#current` | 현재 작업 |
| 연락처 | `#contact` | 이메일, 링크 |

에디터에서 `Ctrl + F`로 위 ID(예: `id="about"`)를 검색하면 해당 섹션으로 바로 이동할 수 있습니다.

---

## 내용 수정 방법 (가장 쉬운 방법)

### 1. GitHub 웹에서 바로 수정

코드 설치 없이 브라우저만으로 수정할 수 있습니다.

1. https://github.com/dismalvin/home 접속
2. `index.html` 클릭
3. 연필 아이콘 **Edit this file** 클릭
4. 내용 수정
5. 아래 **Commit changes** 클릭
   - 제목 예: `비평 목록 2026년 항목 추가`
6. 1~2분 후 https://home-livid-six.vercel.app/ 에 자동 반영

> Vercel이 GitHub `main` 브랜치와 연결되어 있으면, `main`에 올라간 변경은 자동 배포됩니다.

---

## 자주 하는 수정 예시

### 텍스트 한 줄 바꾸기

`<li>...</li>` 안의 글자만 바꾸면 됩니다.

```html
<li>2026 서울연극제 자유경연작 심사위원</li>
```

### 목록 항목 추가하기

같은 `<ul>` 안에 `<li>` 한 줄을 추가합니다.

```html
<ul>
  <li>기존 항목</li>
  <li>새로 추가할 항목</li>
</ul>
```

### 목록 항목 삭제하기

해당 `<li>...</li>` 줄 전체를 지웁니다.

### 연구 분야 키워드 추가 (`#research`)

```html
<span>새 키워드</span>
```

`<span>` 태그를 `<p class="tag-line">` 안에 추가하면 됩니다.

### 이메일·링크 변경 (`#contact`)

```html
<a href="mailto:dismalvin@gmail.com">dismalvin@gmail.com</a>
```

`href`와 화면에 보이는 주소를 함께 수정하세요.

### 사진 넣기 (프로필)

히어로 영역의 `portrait-frame` 안 SVG 플레이스홀더를 이미지로 교체합니다.

```html
<img src="profile.jpg" alt="김유빈" style="width:100%;height:100%;object-fit:cover;">
```

이미지 파일은 저장소에 함께 올린 뒤 `src`에 파일명을 적습니다.  
(예: `profile.jpg`를 repo에 추가 → `src="profile.jpg"`)

---

## 로컬에서 수정하는 방법 (선택)

파일을 PC에 받아서 수정한 뒤 올리는 방법입니다.

### 준비 (최초 1회)

```bash
git clone https://github.com/dismalvin/home.git
cd home
```

### 수정 후 배포 반영

```bash
# 1. index.html 수정 (메모장, VS Code 등)

# 2. 변경사항 저장 후
git add index.html
git commit -m "수정 내용 한 줄 요약"
git push origin main
```

push 후 Vercel이 자동으로 다시 배포합니다.

### 로컬에서 미리보기

```bash
npx serve .
```

브라우저에서 http://localhost:3000 으로 확인할 수 있습니다.

---

## 브랜치로 작업하는 방법 (권장)

`main`에 바로 push해도 되지만, 실수 방지를 위해 브랜치를 쓰는 것을 권장합니다.

```bash
git checkout main
git pull origin main
git checkout -b update/2026-07-비평추가

# index.html 수정 후
git add index.html
git commit -m "2026년 비평 항목 추가"
git push -u origin update/2026-07-비평추가
```

GitHub에서 **Pull Request** 생성 → **Squash and merge** → 자동 배포

---

## 주의사항

1. **수정할 파일은 `index.html` 하나**면 대부분 충분합니다.
2. `<`, `>` 기호는 HTML에서 특수문자입니다.  
   연극 제목 등에 꺾쇠가 필요하면 `&lt;제목&gt;` 형태로 적혀 있는 부분을 그대로 따라 쓰세요.
3. `</div>`, `</section>`, `</ul>` 같은 **닫는 태그를 지우지 마세요.** 레이아웃이 깨질 수 있습니다.
4. 배포 반영까지 보통 **1~2분** 걸립니다. 바로 안 바뀌면 잠시 후 새로고침(Ctrl+F5) 해보세요.
5. 큰 수정 전에는 GitHub에서 파일 **History**로 이전 버전을 볼 수 있습니다.

---

## Vercel 관련

- 배포는 **고객 Vercel 계정**에서 관리됩니다.
- GitHub `main` 브랜치에 push되면 자동 재배포됩니다.
- Vercel 대시보드: https://vercel.com/dashboard
- 도메인 변경·커스텀 도메인 연결도 Vercel 대시보드에서 설정합니다.

---

## 도움이 필요할 때

- GitHub 저장소: https://github.com/dismalvin/home
- 배포 사이트: https://home-livid-six.vercel.app/
- 담당 개발자에게 `index.html`의 몇 번째 줄 근처를 바꾸고 싶은지 알려주시면 빠르게 도와드릴 수 있습니다.

---

## 기술 정보

- 정적 HTML 단일 페이지 (프레임워크 없음)
- 호스팅: Vercel
- 소스 관리: GitHub
- 디자인: 1번 시안 기반, 목록은 1단 구성
