<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=auto&height=200&section=header&text=Software%20Engineer&fontSize=70" width="100%">
</div>

### About Me
* **University**: Sejong University, Software Major 
* **Main Focus**: Web Development (Next.js, React) & AI/ML 
* **Current Interest**: Embedded Systems (ESP32) & Linux Server
* **Hobbies**: Running, Fitness, reading
* **Value**: Team-oriented development with strict coding conventions

---

### My GitHub Contributions
<p align="center">
  <img src="https://github-readme-stats-one-bice.vercel.app/api?username=yoonjaehong26&show_icons=true&count_private=true&theme=radical&hide_border=true" alt="Jaehong's GitHub Stats" />
  <img src="https://github-readme-stats-one-bice.vercel.app/api/top-langs/?username=yoonjaehong26&layout=compact&theme=vision-ary-dark&hide_border=true" alt="Top Langs" />
</p>

---


### Tech Stack

#### Frontend Development
![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![shadcn/ui](https://img.shields.io/badge/shadcn/ui-000000?style=for-the-badge&logo=shadcnui&logoColor=white)
![Styled Components](https://img.shields.io/badge/styled--components-DB7093?style=for-the-badge&logo=styled-components&logoColor=white)

#### State Management & Data Fetching
![Zustand](https://img.shields.io/badge/Zustand-443E38?style=for-the-badge&logo=react&logoColor=white)
![TanStack Query](https://img.shields.io/badge/-TanStack%20Query-FF4154?style=for-the-badge&logo=react-query&logoColor=white)
![Context API](https://img.shields.io/badge/Context%20API-61DAFB?style=for-the-badge&logo=react&logoColor=white)

#### Backend & Database
![Express](https://img.shields.io/badge/Express-000000?style=for-the-badge&logo=express&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)

#### Programming Languages & Systems
![C++](https://img.shields.io/badge/C%2B%2B-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![C#](https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=c-sharp&logoColor=white)
![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)

#### Tools & Game Dev
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)
![Netlify](https://img.shields.io/badge/Netlify-00C7B7?style=for-the-badge&logo=netlify&logoColor=white)
![Unity](https://img.shields.io/badge/Unity-FFFFFF?style=for-the-badge&logo=unity&logoColor=black)

---

### Featured Projects

---

### Manna (만나) `Web · PWA`
> **"성경 읽기의 진입 장벽을 낮춘 릴스 스타일 PWA"**

**왜 만들었나**: 성경 통독에 도전한 사람들이 중도 포기하는 가장 큰 이유는 "한 번에 읽어야 할 분량이 너무 많다"는 부담감이에요. 과자를 한 입씩 먹듯, 장 단위 대신 한 구절씩 스와이프하며 음미하는 릴스형 UX로 진입 장벽을 낮췄어요.

**핵심 UX**
* 릴스처럼 세로 스와이프로 한 구절씩 음미하며 읽는 경험
* 순수 제스처 제어로 만든 네이티브 앱 수준의 조작감
* 화면 깜빡임 없이 즉각 전환되는 탐색 경험

**Live Demo**: [https://manna-mu.vercel.app/](https://manna-mu.vercel.app/)

![화면 기록 2026-03-07 오후 4 28 44](https://github.com/user-attachments/assets/734310d0-a28c-4d1f-8d5b-7554c28eefac)

**목표**
* TWA(Trusted Web Activity)로 Google Play 스토어 출시
* 개역개정 등 여러 번역본 저작권 사용 허가 요청 진행 중
* 시작 가이드(온보딩) 추가 예정

<details>
<summary><h3>엔지니어링 하이라이트</h3></summary>

<details>
<summary><h4>화면이 갑자기 하얗게 죽어버렸는데, 범인은 유튜브였어요</h4></summary>

> **문제**: 찬양 릴스에 배경 음악을 재생하려고 YouTube IFrame API를 붙였는데, 처음엔 가장 자연스러운 방식대로 React가 렌더링한 `<div ref={containerRef}>`를 그대로 `new YT.Player()`의 타겟으로 넘겼어요. 그런데 이 API는 넘겨받은 타겟 DOM을 통째로 `<iframe>`으로 바꿔치기하는 부작용이 있었고, React의 가상 DOM은 여전히 `<div>`가 있다고 믿는데 실제 DOM은 `<iframe>`으로 바뀌어 있으니, 다음 리렌더링이나 언마운트 시점에 React가 자기가 그렸던 노드를 찾지 못하고 `insertBefore`/`removeChild` NotFoundError를 던지며 화면이 하얗게 죽었어요. 보통은 `react-youtube` 같은 래퍼 라이브러리 뒤에 가려져 잘 드러나지 않는, IFrame API를 직접 다룰 때만 마주치는 문제였어요.

> **해결**: "YouTube가 내가 렌더링한 DOM을 React 몰래 바꿔치기한다"는 원인을 짚어낸 뒤, 타겟 div를 아예 React 렌더링 흐름 밖에서 만드는 방식으로 바꿨어요. 순서는 이래요. 1) React는 빈 wrapper `<div ref={wrapperRef}>`만 렌더링하고 그 안에는 어떤 자식도 그리지 않아요. 2) 컴포넌트가 마운트되면 `wrapperRef.current`에 `document.createElement('div')` + `appendChild`로 자식 div를 직접 심어요 — JSX가 아니라 순수 DOM API 호출이라, React의 가상 DOM 트리에는 이 자식이 기록조차 되지 않아요. 3) `new YT.Player()`에는 이 수동 생성 div를 타겟으로 넘겨요. YouTube가 이걸 `<iframe>`으로 바꿔치기해도, React 입장에선 애초에 몰랐던 노드라 다음 리렌더링 때 비교할 "이전 상태"가 없으니 충돌이 날 수가 없어요. 4) 언마운트 시엔 React의 클린업이 wrapper를 지우기 전에, `while (wrapper.firstChild) wrapper.removeChild(wrapper.firstChild)`로 wrapper의 자식들을 먼저 수동으로 비워서, React가 마지막으로 기억하는 "wrapper는 비어있다"는 상태와 실제 DOM을 다시 맞춰놨어요. 레시피를 찾아 적용한 게 아니라 "React가 아예 모르는 영역을 의도적으로 만든다"는 원리부터 스스로 추론해 해결한 좋은 경험이였어요

</details>

<details>
<summary><h4>"느리다" 한 마디에 원인이 몇 개나 숨어있었을까요</h4></summary>

> 사용자에게는 그냥 "느리다"는 감각 하나지만, 실제로는 레이어마다 전혀 다른 원인이 겹쳐 있었어요. "최적화했다"고 뭉뚱그리는 대신, 어느 레이어에서 왜 지연이 나는지부터 하나씩 분리해서 진단한 뒤 레이어에 맞는 해법을 따로 적용했어요.

| 지연 유형 | 증상 | 실제 원인 | 해결 |
|---|---|---|---|
| 서버 응답 지연 (TTFB) | 첫 진입 자체가 느림 | 매 요청 동적 렌더링 | force-static + Server Component 전환 |
| 네트워크 과다 요청 | 큐레이션 열 때마다 버벅임 | 필요한 양(300bytes)보다 2,800배 큰 페이로드(840KB) | Batch API로 요청을 1회로 압축 |
| 반복 방문 지연 | 재방문해도 매번 다시 느림 | 같은 UID 조합인데도 매번 서버까지 왕복 | Service Worker CacheFirst 30일 캐싱 |
| 리렌더링 지연 | 오디오 재생 한 번에 화면 4개가 같이 흔들림 | 필요 이상으로 넓은 범위의 상태 구독 | 실제 사용처로 구독 범위 축소 |
| 번들 크기 지연 | 안 쓰는 페이지까지 초기 진입이 무거움 | 큐레이션 40여 개가 전부 정적 import로 번들에 포함 | 네이밍 컨벤션 기반 동적 import로 전환, 번들 60KB 감소 |
| 체감 지연 | 실제 지연은 그대로인데 "반응이 없다"고 느껴짐 | 지연 자체가 아니라 지연 동안 피드백 부재가 문제 | 클릭 즉시 시각 피드백(`useTransition`), 드래그 시작 시점 프리페치, 스켈레톤 UI로 대기 숨김 |

> 표의 TTFB·Batch API·SW 캐싱·리렌더링 최적화는 아래 각 항목에서 구체적인 수치와 구현으로 이어져요. 번들 최적화와 체감 지연은 "진짜 지연을 줄이는 것"과 "지연을 못 느끼게 하는 것"이 서로 다른 문제라는 걸 보여주는 사례라 여기서 함께 짚었어요.

</details>

<details>
<summary><h4>1초 넘게 걸리던 첫 로딩, 30ms까지 줄인 방법은요</h4></summary>

> **문제**: 페이지가 매 요청마다 서버리스 함수로 동적 렌더링돼 TTFB(첫 바이트 응답 시간)가 Netlify 기준 1,134ms까지 걸렸어요.

> **해결**: 한 번에 해결되지 않아서 원인을 좁혀가며 세 단계로 나눠 잡았어요. 
> 1) Next.js가 정적 최적화를 위해 공식 제공하는 `export const dynamic = 'force-static'`을 먼저 전체 페이지에 붙였는데, Netlify가 App Router의 `force-static`을 완전히 지원하지 않아 579ms(48% 개선)에서 더 줄지 않았어요. 
> 2) 사실 Netlify는 애초에 "Vercel보다 무료 플랜 bandwidth가 넉넉하다(월 100GB)"는 이유로 일부러 골랐던 플랫폼이었는데, 정작 성능에 필요한 App Router 정적 최적화 지원은 Next.js 공식 플랫폼인 Vercel보다 약하다는 게 발목을 잡았어요. 그래서 bandwidth 제한이 더 빡빡해지는 걸 감수하고 배포 플랫폼을 Vercel로 옮겼고, 265ms(4배)까지 줄었지만 응답 헤더는 여전히 `x-vercel-cache: MISS`라 CDN 정적 캐싱은 안 되고 있었어요. 
> 3) 원인을 파보니 동적 라우트(`[[...slug]]`)의 `page.tsx`가 `'use client'`로 선언돼 있어서, `force-static`을 붙여도 Next.js가 이걸 Server Component로 인식하지 않아 정적 최적화 대상에서 제외되고 있었어요. `'use client'`를 제거해 Server Component로 전환하고, styled-components를 쓰던 로딩 폴백만 별도 Client Component로 분리, `useSearchParams`를 쓰는 `ContentRouter`는 `<Suspense>` 경계로 감싸서 충돌 없이 재구성했어요.

> **결과**: 빌드 출력에서 `/[[...slug]]`가 `○ (Static)`으로 분류되어 CDN에서 정적 서빙되기 시작했고, TTFB는 1,134ms → 579ms → 265ms → 약 30ms(최대 35배)까지 줄었어요.

</details>

<details>
<summary><h4>라이브러리 없이 스와이프·탭·더블탭·롱프레스를 전부 손으로 구분했어요</h4></summary>

> **문제**: PWA 환경에서 인스타 릴스 같은 조작감을 구현하려면 스와이프(다음/이전 구절), 엣지 스와이프(뒤로가기·모드 전환), 탭(페이지 이동), 더블탭(북마크·한영전환)까지 네 가지 제스처를 직관적으로 구분해야 했어요. 처음엔 검증된 제스처 라이브러리부터 검토했는데, 후보 3개가 전부 이 프로젝트의 핵심 요구사항에서 걸렸어요.

> `react-use-gesture`는 성능을 위해 `passive: true`가 고정돼 있어 `preventDefault()` 자체가 불가능했고(iOS 시스템 제스처를 막을 방법이 없어요), `framer-motion`의 제스처 기능은 애초에 "Safari 엣지 스와이프 차단" 같은 케이스를 다루지 않았고, `hammer.js`는 PWA standalone 모드 감지가 안 돼서 "브라우저로 볼 때"와 "홈 화면에 설치해서 볼 때"를 구분할 방법이 없었어요.

> 세 라이브러리 다 "제스처 인식"은 잘하지만, 그 인식 결과로 브라우저·OS의 기본 동작(뒤로가기 등)까지 가로채야 하는 이 프로젝트의 요구는 답이 없었던 거예요.

> **해결**: 그래서 `useCardGestures`(탭·더블탭·롱프레스·스와이프업)와 `usePeekSwipe`(엣지 스와이프)를 라이브러리 없이 직접 구현했어요. 엣지 40px 이내에서 시작하는 스와이프만 감지하고, 20px 이상 움직여야 액션이 실행되게 하면서 그 사이는 진행 거리에 비례해 opacity를 점진적으로 올려 "지금 당기고 있다"는 시각 피드백을 줬어요.

> 탭은 인스타그램 스토리처럼 화면을 좌/우로 나눠 이전/다음 페이지로 연결했고(카드 실측 폭 기준 정확히 50/50 분할), 더블탭(300ms 이내 재탭)과 롱프레스(500ms)는 이동거리 10px 이내인지로 구분해 서로 오인식하지 않게 만들었어요.

> 애니메이션까지 전부 손으로 짤 필요는 없어서, 제스처 "인식"만 직접 만들고 인식 후 보여주는 애니메이션은 Framer Motion에 맡겨 역할을 나눴어요.

> **결과**: 라이브러리 없이 네 가지 제스처가 충돌 없이 공존, `react-use-gesture` 미사용으로 번들 크기 약 13KB 절약.

</details>

<details>
<summary><h4>터치는 착 붙는데, 마우스 휠은 왜 따로 코드를 짜야 했을까요</h4></summary>

> **문제**: 릴스처럼 카드 단위로 딱 맞춰 멈추는 느낌을 CSS `scroll-snap-type: y mandatory` + `scroll-snap-align: start` + `scroll-snap-stop: always`로 구현했어요. 터치 스와이프에서는 잘 맞았지만, 마우스 휠로 빠르게 여러 번 스크롤하면 두 카드 사이 중간 위치에서 스크롤이 멈춰버리는 문제가 있었어요. `scroll-snap-stop: always`가 슬라이드를 강제로 멈추려는 것과, 브라우저의 가속도 기반 휠 스크롤·`scroll-behavior: smooth`가 서로 경쟁하면서 생기는 충돌이었어요.

> **해결**: CSS snap 자체는 그대로 두고, `wheel` 이벤트만 JS로 완전히 가로챘어요. `preventDefault()`로 브라우저 기본 스크롤을 차단한 뒤 `deltaY` 부호로 방향만 읽어서 `container.scrollTo({ top: nextIndex * clientHeight, behavior: 'smooth' })`로 정확히 카드 한 장만큼만 이동시켰어요. 이전 스크롤 애니메이션이 끝나기 전(약 400ms)의 추가 휠 입력은 무시해서, 휠을 연속으로 굴려도 한 번에 한 장만 넘어가게 했어요. 결과적으로 터치는 CSS snap 그대로 쓰고 마우스 휠만 JS로 별도 제어하는, 입력 방식별로 다른 레이어에서 처리하는 구조가 됐어요.

> **결과**: 마우스 휠 중간 멈춤 현상 완전 제거, 터치·키보드 동작은 기존 그대로 유지.

</details>

<details>
<summary><h4>iOS 시스템 제스처랑 충돌하던 스와이프, 라이브러리 없이 어떻게 잡았을까요?</h4></summary>

> **문제**: iOS PWA(Standalone 모드)에서 화면 좌측 엣지 40px 이내 스와이프가 시스템 뒤로가기 제스처로 인식돼, 앱의 커스텀 스와이프와 충돌했어요.

> **해결**: `touchstart`에서 터치 시작 좌표가 엣지 영역인지 확인해 `preventDefault()`로 시스템 제스처를 차단했어요. iOS는 `{ passive: false }` 옵션 없이는 `preventDefault`가 무시돼서 이를 반드시 지정했고, `navigator.standalone`/`matchMedia('(display-mode: standalone)')`로 iOS PWA 환경에서만 동작하도록 범위를 좁혔어요.

</details>

<details>
<summary><h4>안드로이드는 왜 과감히 포기했을까요? 인스타그램도 같은 걸 겪었더라고요</h4></summary>

> **문제**: Android에서도 iOS처럼 시스템 제스처를 직접 제어하고 싶었지만, Android 제스처 내비게이션은 `preventDefault`로 막을 수 없는 시스템 레벨 동작이었어요.

> **해결**: Instagram PWA도 같은 문제로 네이티브 앱으로 회귀했던 사례를 근거로, Android는 과감히 포기하고 iOS 제스처 제어에 집중하는 전략을 의도적으로 택했어요.

</details>

<details>
<summary><h4>번역본 5개, 언어도 여러 개인데 API 호출 수는 어떻게 줄였을까요?</h4></summary>

> **문제**: 성경 데이터는 번역본별로 66권짜리 JSON(책 하나당 파일 하나)으로 저장돼 있어요. 평독 모드처럼 한 장을 순서대로 읽을 땐 이 구조로 충분했지만, 큐레이션·홈피드·북마크·Topics처럼 서로 다른 책에 흩어진 구절 몇 개만 필요한 "랜덤 접근" 상황에서는 `loadVerses()`가 구절 하나를 위해서도 그 구절이 속한 책 전체를 통째로 import했어요.

> 큐레이션 하나("소망의 빛")가 로마서·예레미야·시편에서 딱 3구절(300bytes)만 쓰는데 실제로는 책 3권(840KB)을 통째로 내려받는 식이었고, 비슷한 과다 다운로드가 Topics 페이지(10구절, 500배), 홈 구절 릴스(1구절, 500배), 북마크(3구절, 667배)에서도 반복됐어요.

> **해결**: 이 비효율을 줄일 방법을 4가지로 나눠 검토했어요. A) 장 단위로 파일을 쪼개기(66권→1,189개 장) — 840KB→12KB(70배)까지는 줄지만 여전히 40배 과다였고, HTTP 요청 횟수(왕복 시간)는 그대로였고, 파일이 5,940개로 늘어나는 관리 부담이 있었어요. B) 절 단위로 쪼개기(31,102개 구절) — 5개 번역본 기준 파일이 15만 개를 넘고, HTTP 헤더(500bytes)가 실제 데이터(100bytes)보다 커지는 역전 현상까지 있어서 바로 제외했어요. C) 필요한 구절 UID만 서버에서 추출해 응답하는 Batch API — 이걸 채택했어요. D) 큐레이션 JSON에 텍스트를 미리 박아넣기 — 840KB→5KB(168배)까지 줄지만 번역본이 바뀔 때마다 데이터를 다시 구워야 해서, 오프라인 폴백 용도로만 남겨뒀어요.

> 채택한 Batch API(`GET /api/verses?uids=...&version=...`)는 구절 UID 배열을 한 번에 받아 요청을 1회로 합치고, 서버가 `fs.readFileSync`로 필요한 책만 로컬 SSD에서 읽어(1ms) 요청받은 구절만 추출해 응답해요.

> 캐싱은 3단계로 쌓았어요. 클라이언트 메모리 Map(같은 구절 재요청 시 0ms), HTTP 브라우저 캐시(`Cache-Control` 1년, 같은 요청이면 서버까지 안 감), 서버 메모리 캐시(같은 책의 다른 구절을 요청해도 파일 I/O가 다시 안 일어남) 순서예요. 번역본 5개(KRV, NKRV, KJV, YLT, WEB)를 오가도 데이터가 어긋나지 않도록, 특정 번역본에 종속되지 않는 전역 UID로 구절을 식별해서 캐시 키를 통일했어요.

> 이 구조는 큐레이션 하나에만 적용한 게 아니라 홈피드·북마크·마이 큐레이션·이어읽기·읽기표(잠언·시편)까지, 구절을 "랜덤하게" 가져오는 6개 기능 전부를 Batch API로 옮겼어요. 반대로 평독 모드처럼 순서대로 읽는 화면은 그대로 장 단위 Dynamic Import + 인접 장 프리페칭을 유지해서, 접근 패턴이 다르면 로딩 전략도 다르게 가져간다는 원칙을 지켰어요.

> **결과**: 큐레이션 1개 840KB→300bytes(2,800배), 큐레이션 10개 4MB→3KB(1,333배), Topics 페이지 500KB→1KB(500배), 응답 시간 250ms→50ms.

</details>

<details>
<summary><h4>같은 구절을 또 열었는데, 두 번째부터는 서버를 아예 안 탔어요</h4></summary>

> **문제**: `/api/verses`가 이미 CDN에 캐싱되고 있었지만, 새로운 UID 조합일 때마다 서버리스 함수의 cold start(약 100~200ms)가 매번 발생했어요.

> **해결**: Service Worker에 `CacheFirst` 전략을 추가해 자주 쓰는 UID 조합을 30일간 캐싱했어요. `homeStore`가 홈 피드 상태를 localStorage에 저장해두는 덕분에 재방문 시 같은 UID 조합이 보장되고, 성경 데이터는 불변이라 30일 캐싱이 안전했어요.

> **결과**: 재방문 시 구절 로딩 약 0ms.

</details>

<details>
<summary><h4>화면 전환할 때 깜빡임이 한 번도 없었던 이유, 사실 페이지 이동을 안 했어요</h4></summary>

> **문제**: Next.js 파일 기반 라우팅으로 홈/릴스/평독 사이를 이동하면 컴포넌트가 매번 언마운트·리마운트돼 화면이 깜빡이고, 이미 불러온 데이터도 재사용할 수 없었어요. 책을 덮고 다른 책을 펴는 것과 같았어요.

> **해결**: `ContentRouter`가 **스와이프 전환이 필요한 뷰(홈·릴스·평독·주제별)만** 전부 항상 마운트해두고, `view`/`back` URL 파라미터만으로 전환과 스마트 백내비게이션을 관리하게 했어요. 반대로 탐색·북마크·설정처럼 독립적인 화면은 통합하지 않고 그대로 뒀어요. 여러 뷰를 항상 메모리에 들고 있어야 하는 트레이드오프는 의도적으로 감수했어요.

> 실제 전환 방식은 캐러셀과 같은 원리예요. `ReaderViewLayers`가 4개 뷰를 전부 고정 위치 레이어로 동시에 마운트해두고, 활성 뷰만 `translateX(0)`으로 화면에 두고 나머지는 `translateX(100vw)`로 화면 밖에 밀어놔요 — 뷰를 새로 그리는 게 아니라 이미 그려진 레이어들의 위치만 옆으로 밀어서 전환하는 거예요. 화면 밖에 있는 비활성 레이어가 클릭이나 스크롤을 가로채지 않도록 `pointer-events`와 `z-index`도 뷰별로 따로 관리했고, 슬라이드 애니메이션(0.3초)이 끝난 뒤에야 새로 활성화된 뷰가 클릭을 받도록 살짝 지연(0.31초)을 줬어요.

> **결과**: 화면 깜빡임 없이 전환 시간 16ms.

> 같은 "화면을 유지한 채 필요한 것만 갈아 끼운다"는 원칙은 홈 피드의 무한 스크롤에도 적용돼요. `homeStore`는 진입 시 1개를 즉시 로드해 로딩 화면부터 빠르게 걷어낸 뒤, 백그라운드로 사용자의 콘텐츠 패턴 길이만큼(기본 설정 기준 10개)과 배치 10개를 추가로 채워 초기 피드를 두툼하게 만들어요.

> 이후 스크롤 중엔 남은 카드 수가 5개 이하로 줄어들 때마다 다음 10개를 백그라운드로 미리 불러와요. 이 조건은 카드가 전환될 때마다 체크하는 경로와 스크롤이 끝에 가까워졌을 때 감지하는 경로, 두 곳에서 동시에 걸려 있어서 사용자가 스크롤을 멈추지 않아도 항상 다음 데이터가 준비돼 있어요.

> 다만 무한정 쌓이면 메모리를 계속 먹으니, 전체 아이템 수가 40개를 넘으면 오래된 앞쪽 아이템부터 잘라내고 현재 보고 있는 인덱스도 그만큼 같이 보정해요. 다만 카드 렌더링 자체는 DOM 가상화 없이 로드된 아이템을 전부 마운트하는 구조라, 이 40개 상한은 "메모리 상한"이지 "렌더링 최적화"는 아니라는 것도 정확히 구분해요.

</details>

<details>
<summary><h4>성경 구절, 헬라어, 찬양, 기도문... 형태가 다 다른데 왜 한 화면에서 매끄럽게 넘어갈까요?</h4></summary>

> **문제**: 큐레이션 콘텐츠가 구절·헬라어·찬양가사·미디어·묵상·암송퀴즈·이벤트·읽기진행도처럼 형태가 전부 달라서, 각각 다른 렌더링 로직을 만들면 화면마다 UX가 제각각이 될 위험이 있었어요.

> **해결**: `Page`를 9종 타입(구절·텍스트·헬라어·가사·미디어·묵상·읽기진행도·암송퀴즈·이벤트)의 discriminated union으로 설계하고, `PageRenderer`가 `page.type`으로 분기해 타입별 컴포넌트에 위임하는 strategy 패턴으로 렌더링하게 했어요. 새 타입을 추가할 때 손대는 곳을 "타입 정의 1곳 + `PageRenderer` 분기 1곳"으로 고정해서, 이미 있는 타입들의 렌더링 로직은 절대 안 건드리게 만들었어요. 사전 제작된 정적 큐레이션과, 사용자 진행도·날짜 기반으로 실시간 생성되는 동적 큐레이션(이어읽기, 오늘의 잠언·시편, 마태·마가·누가·요한·사도행전·바울서신 등 465개 이상의 소제목 순차 읽기)도 같은 파이프라인에 통합했어요.

> 페이지 사이 전환은 화면 탭 위치로 이뤄져요. 탭 좌표를 카드의 실제 렌더 폭(`getBoundingClientRect`) 기준으로 좌/우 절반으로 나눠 이전/다음 페이지를 판정하는데, `window.innerWidth`가 아니라 카드 자신의 실측 폭을 기준으로 삼은 건 데스크톱처럼 카드가 화면 전체 폭이 아닐 수 있는 레이아웃까지 고려한 거예요. 페이지가 여러 장인 콘텐츠에는 인스타그램 스토리 같은 상단 진행 바(`PageIndicator`)가 뜨고, 암송 퀴즈처럼 다음 페이지로 넘어가기 전에 조건이 있는 경우엔 `isPageLocked`로 페이지 이동 자체를 막아요.

> 페이지 전환 상태 갱신은 `startTransition`으로 감싸서 낮은 우선순위 업데이트로 처리했어요 — 무거운 `PageRenderer` 리렌더링이 탭 응답성을 막지 않게 하기 위해서예요.

> **결과**: 새 콘텐츠 타입을 추가해도 기존 화면은 안 건드림, `startTransition` 적용으로 탭 즉시 반응성 유지.

</details>

<details>
<summary><h4>혼자 만든 프로젝트인데 왜 이렇게까지 규칙을 정했을까요?</h4></summary>

> **문제**: 기능이 늘어날수록 `isActive`, `onChange`처럼 이름만 봐서는 무슨 의미인지 알 수 없는 props가 쌓이기 쉬웠고, 레이어 간 의존 방향도 흐트러지기 쉬웠어요.

> **해결**: boolean props는 `is`/`should`/`has` 접두사, 콜백은 `on + 명사 + 동사` 패턴을 강제하는 네이밍 규칙을 세웠어요. `features → shared`만 허용하고 반대 방향은 금지하는 단방향 레이어 규칙을 두고, 위반이 필요한 경우 항상 props로 주입하게 했어요. 코드를 나중에 AI 도구로 다시 훑어봐도 이름만으로 의도가 파악되게 하는 것도 목표였어요.

> **결과**: 100개 넘는 파일에서 일관된 구조 유지, 처음 보는 사람도 이름만으로 의도 파악 가능.

</details>

<details>
<summary><h4>AI한테 코드 정리를 맡겼는데, 진짜 작업은 정리가 아니었어요</h4></summary>

> **문제**: 100개 넘는 파일에 JSDoc·코드 순서·섹션 구분선을 일관되게 정리하는 작업을 AI 도구에 맡기려 했는데, 그냥 "정리해줘"라고만 시키면 위험이 두 가지 있었어요. AI가 "더 낫다"고 판단해서 기존 인라인 주석을 지우거나 로직까지 슬쩍 바꿔버릴 수 있다는 것, 그리고 파일 수가 많다 보니 한 번에 다 맡기면 중간에 타입이 깨져도 어디서부터 잘못됐는지 추적하기 어렵다는 것이었어요.

> **해결**: 그래서 "무엇을 정리할지"보다 "AI가 하면 안 되는 것"부터 문서로 못박았어요. 기존 인라인 주석 삭제 금지, 로직 변경 금지, 이미 잘 동작하는 코드 리팩토링 금지를 명시하고, 작업 전엔 반드시 `git diff`로 원본 주석 상태를 먼저 확인하게 했어요.

> 작업 순서도 의존성 방향으로 고정했어요. 의존성이 없는 `utils`부터 `core → features → components → app` 순서로 진행하고, 배치당 파일 4~6개만 건드리게 한 뒤 매 배치마다 `tsc --noEmit`으로 타입 체크를 통과해야 다음 배치로 넘어가게 했어요. 같은 디렉토리 안의 파일들은 서로 의존하지 않으니 병렬로 맡겨도 안전하다는 판단까지 문서에 남겨뒀고요.

> 이 문서는 사람이 읽는 가이드가 아니라, 맨 위에 "이 문서를 프롬프트로 사용하여 새 채팅에서 코드 정리를 진행할 수 있습니다"라고 적어둔, AI에게 그대로 복사해 붙여넣는 작업 지시서였어요.

> **결과**: 100개 넘는 파일에 일관된 JSDoc·코드 순서·주석 보존 규칙을 적용, 배치별 타입 체크로 중간에 깨지는 지점 없이 안전하게 완료.

</details>


<details>
<summary><h4>번역본을 더블탭 하나로 바로 바꿀 수 있는 이유</h4></summary>

> **문제**: 번역본(한국어 2종·영어 3종)을 전환할 때마다 새로 API를 호출하면 전환이 끊기고 느리게 느껴져요. 그리고 이 프로젝트는 화면마다 언어를 따로 설정하지 않고, 지금 보던 큐레이션에서 영어로 바꾸면 홈·북마크 등 앱 전체가 영어 성경으로 바뀌는 전역 일관성을 원칙으로 삼았어요 — 페이지별로 언어가 따로 노는 게 오히려 혼란을 준다고 판단했거든요. 다만 언어 전환의 범위는 성경 구절·책 이름·참조 표시로만 한정했고, 버튼·메뉴 같은 UI 텍스트와 큐레이션 타이틀은 한글을 유지해서 "앱 전체 번역"이 아니라 "성경 읽기 모드 전환"에 가깝게 의도적으로 좁혔어요.

> **해결**: 더블탭으로 한/영을 전환하는 UX를 만들면서, 홈 피드에 새 콘텐츠가 로드될 때마다 그 안의 구절·큐레이션·기도문 전부에 대해 반대 언어 버전을 자동으로 백그라운드에서 미리 불러와 뒀어요. 더블탭하는 순간엔 이미 캐시에 있는 데이터를 쓰기 때문에 네트워크를 안 타고, 아직 프리로드가 안 끝난 콘텐츠라면 그 자리에서 해당 언어 데이터를 로드하는 폴백도 뒀어요.

> **결과**: 캐시 히트 시 더블탭 즉시 전환(대기 시간 없음), 캐시 미스여도 100~300ms 안에 로드 완료.

</details>

<details>
<summary><h4>기능이 계속 늘어나도 안 얽히게, 미리 선을 그어둔 게 있어요</h4></summary>

> **문제**: 기능이 늘어날수록(홈 피드, 성경 읽기, 큐레이션, 오디오, 탐색, 제작 도구 등) 컴포넌트·상태·로직이 서로 뒤엉키기 쉬웠고, 특히 여러 기능이 같은 공용 UI 컴포넌트를 가져다 쓰다 보면 "이 컴포넌트가 어떤 기능의 상태까지 알아도 되는지" 경계가 흐려지기 쉬웠어요.

> **해결**: 코드를 `app`(라우팅 전용) · `features`(홈·성경·큐레이션·오디오·탐색·제작 등 도메인별 모듈) · `shared`(공유 레이어) 셋으로 나누고, `shared`는 다시 `core`(api·store·타입·상수) · `lib`(범용 유틸·훅) · `components`(모든 UI 컴포넌트) · `reader`(앱 진입점) 4개로 세분화했어요. 의존 방향은 `features → shared`만 허용하고 반대 방향은 금지하는 단방향 규칙을 뒀는데, `shared/reader`(`ContentRouter`)만 유일한 예외로 features를 참조할 수 있게 열어뒀어요 — 여러 기능 화면을 한 화면에서 오케스트레이션하려면 각 기능을 알아야 하니까요. 그 외 shared 컴포넌트가 기능별 상태가 필요할 땐 규칙을 어기는 대신 props/render prop으로 주입받게 했어요(예: `CardScroller`는 페이지 인덱스나 페이지 변경 콜백을 자기 상태로 갖지 않고 prop으로만 받아요).

> **결과**: "예외 없이 지켜야 할 규칙 하나 + 명시된 예외 하나"로 단순해져서, 새 기능을 추가해도 다른 기능이나 공유 컴포넌트 코드를 건드릴 일이 없어요.

</details>

<details>
<summary><h4>노래 하나 재생했을 뿐인데 화면 4개가 같이 흔들렸다면?</h4></summary>

> **문제**: 오디오(찬양 배경음악) 재생 상태가 바뀔 때마다 관련 없는 화면까지 같이 리렌더됐어요. 원인은 구독 위치였어요 — `ContentRouter`는 홈·릴스·평독·주제별 4개 뷰를 항상 동시에 마운트해두고 화면만 슬라이드시키는 구조인데(바로 위 캐러셀 방식), 이 최상위 오케스트레이터가 `useAudioStore`에서 값 6개를 직접 구독하고 있었어요. 그래서 재생 중 오디오 상태가 바뀔 때마다 `ContentRouter` 자신은 물론 그 아래 항상 마운트돼 있는 4개 뷰까지 리렌더가 전부 전파됐어요. 여기에 `SettingsPanel`도 실제로는 안 쓰는 `useSearchParams`/`usePathname` URL 훅을 구독하고 있어서, 챕터를 이동할 때마다 불필요한 리렌더가 하나 더 겹쳤어요.

> **해결**: 오디오 상태 구독을 실제로 그 값을 쓰는 `ReaderPanels`(오디오 컨트롤 UI가 있는 곳)로 옮기고, `ContentRouter`는 콜백을 prop으로 넘겨주는 역할만 남겼어요. `SettingsPanel`에 남아있던 URL 훅도 걷어내고 필요한 값은 props로 받게 바꿨어요. "이 상태를 누가 실제로 쓰는가"를 기준으로 구독 위치만 옮긴 거지만, 상위 컴포넌트가 뷰 4개를 늘 띄워두는 구조라 상위에서 구독하면 그 대가가 뷰 1개가 아니라 4개로 곱해진다는 게 핵심이었어요.

> **결과**: 오디오 재생 중 `ContentRouter`와 나머지 3개 뷰의 불필요한 리렌더 제거, 챕터 이동 시 리렌더 27.6ms 감소.

</details>

</details>

---

### react-render-board `Open Source · Dev Tool`
> **"React 앱의 실시간 렌더 구조를 한눈에 보여주는 오픈소스 개발자 도구"**

**왜 만들었나**: 기존 React DevTools는 목록 형태라 전체 구조가 한눈에 안 들어오고, 다른 시각화 도구들은 실제 화면 구조 대신 파일 import 관계만 보여줘서 실제와 다르게 그려져요. "지금 실제로 화면에 그려지고 있는 구조"를 그대로 보여주는 도구가 없다는 걸 발견하고 직접 만들었어요.

**핵심 경험**: 리서치·설계·구현 전 과정을 75개의 의사결정 기록(ADR)으로 남기며 진행했고, npm에 실제로 배포해 누구나 설치할 수 있는 오픈소스 라이브러리로 완성했어요. 유닛 테스트 346개, 실제 오픈소스 앱 3개(excalidraw 등)로 성능 검증까지 마쳤어요.

[![npm version](https://img.shields.io/npm/v/react-render-board.svg?style=for-the-badge&logo=npm&logoColor=white)](https://www.npmjs.com/package/react-render-board) [![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/yoonjaehong26/react-render-board)

<!-- 스크린샷·데모 영상 추가 예정 -->

<details>
<summary><h3>엔지니어링 하이라이트</h3></summary>

<details>
<summary><h4>다른 개발자 도구랑 같이 켜놨다가 페이지를 통째로 멈춘 적이 있어요</h4></summary>

> **문제**: React DevTools 확장이나 react-scan처럼 이미 훅을 쓰고 있는 다른 분석 도구와 함께 켜도 서로 방해하지 않게 만들려고 했는데, 실제로 두 번 다른 방식으로 문제가 터졌어요. 먼저 `onCommitFiberRoot`를 여러 리스너가 동시에 걸릴 수 있는 getter/setter 구조로 바꿔서 react-scan과 완전히 공존시키려 했는데, 실사용 중 무한 재귀로 페이지가 완전히 멈추는 사고가 났어요. 원인은 "현재 dispatch 함수를 캡처해서 감싸 재대입"하는 흔한 패턴을 쓰면, 그 래퍼 자신이 리스너 목록에 다시 등록돼서 dispatch가 자기 자신을 다시 부르는 무한 루프가 만들어진다는 거였어요.

> 이후 실사용자가 직접 원인까지 규명해서 제보한 두 번째 문제도 있었어요. 브라우저 확장(React DevTools/Scan)은 `document_start` 시점에 페이지의 `<head>` 스크립트보다도 먼저 자기 훅을 심어버려서, "훅이 없을 때만 우리 훅을 설치한다"는 조건이 항상 거짓이 됐어요. 그 결과 Next.js처럼 하이드레이션이 런타임 부팅보다 먼저 끝나는 환경에서는 커밋을 하나도 못 잡고 노드가 영구히 0개로 보이는 문제가 있었어요.

> **해결**: 무한 재귀 사고가 난 직후엔 즉시 되돌렸어요 — 실사용 프로젝트에 건 핫픽스와 라이브러리 소스 코드 수정을 같은 시점에 짝지어야 한다는 교훈도 남겼고요(따로 고치다 소스 쪽 위험한 코드를 놓칠 뻔했거든요). 다중 리스너라는 욕심을 버리고 안전한 단일 슬롯 구조로 돌아갔어요.

> 두 번째 문제는 기존 훅이 있어도 무시하지 않고, `onCommitFiberRoot`를 "원본을 보존한 채 딱 한 번만 재할당"하는 방식으로 고쳤어요. 중복 방지 플래그를 두고, 우리 로직이 끝나면 원본 핸들러를 그대로 이어 호출해서 확장의 기능도 그대로 살아있게 했어요. 첫 번째 사고와 다른 점은, 여러 리스너를 관리하는 getter/setter 구조가 아니라 함수 프로퍼티 하나를 안전하게 딱 한 번 감싸는 것뿐이라 애초에 재귀할 여지가 없다는 거예요. 검증은 Playwright로 "확장이 먼저 훅을 심어놓은 상황"을 흉내 내서(가짜 훅을 `document_start`에 미리 주입), 보드가 정상적으로 노드를 그리고 원본 훅도 그대로 체이닝되는지까지 자동화 테스트로 확인했어요.

> **결과**: 다른 devtools 도구와 안전하게 공존(단, react-scan과의 완전한 양방향 공존은 무한 재귀 위험 때문에 의도적으로 보류), 확장 선점 케이스를 포함한 자동화 검증 통과.

</details>

<details>
<summary><h4>4가지 빌드 도구를 전부 자동으로 지원했어요</h4></summary>

* Vite, webpack, Rspack, Next.js(Turbopack)처럼 실무에서 널리 쓰이는 빌드 도구 4종을 설치 한 줄(`npm install`)만으로 자동 연결되게 만들었어요. 도구마다 내부 동작 방식이 달라 각각 다른 연결 방법이 필요했고, 4가지 경로 전부 실제로 화면이 뜨는지 자동화 테스트로 하나하나 확인했어요.

</details>

<details>
<summary><h4>느려지는 원인을 직접 찾아 최대 28배 빠르게 개선했어요</h4></summary>

* 컴포넌트가 5,000개까지 늘어나면 반응 속도가 최대 28배까지 느려지는 성능 문제가 있었어요. 코드를 직접 분석해서 "화면에 안 보이는 요소까지 전부 그리고 있었다"는 진짜 원인을 찾아냈고, 화면 밖 요소는 아예 그리지 않는 방식으로 바꿔서 거의 그대로(1배 수준)까지 개선했어요.

</details>

<details>
<summary><h4>배포된 버전에서 한 번도 작동한 적 없던 기능을 발견해서 고쳤어요</h4></summary>

* 빌드 최적화 과정에서 특정 기능의 코드 전체가 통째로 사라지는 버그가 있었어요. 배포된 모든 버전에서 그 기능이 실제로는 한 번도 정상 동작한 적이 없었다는 걸 실사용 중 발견해서 수정했고, 같은 실수가 나중에 다른 파일에서 다시 발생한 것도 재발 방지 테스트를 추가해서 잡아냈어요.

</details>

</details>

---

### doogoodoogoo(두구두구) `Web · Team` ![최근 30일 방문자](http://152.67.211.137:3000/badge?v=2)
> **"세종대 일정 정리 및 ics를 통한 캘린더 일정등록 자동화 서비스"**

**왜 만들었나**: 세종대 학사 일정을 확인할 때마다 수기로 캘린더에 옮겨 적어야 하는 번거로움이 있어서, ics 파일로 캘린더에 자동 등록까지 되는 서비스를 만들었어요.

**핵심 경험**: 사용자 경험과 니즈를 고려하여 프론트 2명, 백엔드 3명과 함께 진행한 협업 프로젝트

**Live Demo**: [https://doogoodoogoo.kr/](https://doogoodoogoo.kr/)

![화면 기록 2026-03-20 오후 3 45 59](https://github.com/user-attachments/assets/cd5c7f65-eec5-4568-b3d7-6837f53f56f2)

<details>
<summary><h3>엔지니어링 하이라이트</h3></summary>

<details>
<summary><h4>기능 구현보다 먼저 확인한 게 있어요</h4></summary>

> 각 개발 단계에서 디자인·레이아웃·UI를 기술적 구현보다 먼저 사용자 니즈에 맞추는 것을 우선순위로 뒀어요.

</details>

<details>
<summary><h4>중간 개발 과정 자체를 커밋 단위로 남겼어요</h4></summary>

> git flow 전략을 따르면서, 공개된 오픈소스 저장소에 중간 개발 요소를 커밋 단위로 문서화했어요.

</details>

<details>
<summary><h4>프론트 2명·백엔드 3명, API 명세부터 맞추고 시작했어요</h4></summary>

> swagger로 API 명세를 정리하고, 아이디어 도출부터 배포까지 전 과정을 팀과 함께 진행했어요.

</details>

</details>

---

### UnJ (언제) `Web · Collab · AI-assisted`
> **"복잡한 약속 시간을 한눈에, 드래그 기반 일정 조율 플랫폼"**

**왜 만들었나**: 여러 명이 가능한 시간을 맞추려면 채팅방에서 각자 되는 시간을 하나하나 대조해야 하는 번거로움이 있어서, 드래그 한 번으로 가능한 시간을 표시하고 겹치는 시간을 한눈에 볼 수 있는 플랫폼을 만들었어요.

**핵심 경험**: 30분 단위 그리드 드래그 인터랙션을 통해 다수의 참여자가 가능한 시간을 시각적으로 집계

**Live Demo**: [https://unj.kr/](https://unj.kr/)

![화면 기록 2026-03-07 오후 4 59 27](https://github.com/user-attachments/assets/d5392223-9994-4707-a9ab-3a99336e2ce0)

<details>
<summary><h3>엔지니어링 하이라이트</h3></summary>

<details>
<summary><h4>여러 칸을 한 번에 선택하는 드래그, 인덱스 계산부터 직접 짰어요</h4></summary>

> 마우스/터치 드래그로 다중 슬롯을 일괄 선택하는 인터랙션을 인덱스 계산 알고리즘으로 직접 구현했어요.

</details>

<details>
<summary><h4>참여 인원이 저마다 다른데, 한 화면에서 어떻게 다 보여줄지 고민했어요</h4></summary>

> 참여 인원 수와 상태(가능/조정가능)에 따라 투명도와 분할 그라데이션이 동적으로 달라지는 히트맵 렌더링 로직을 설계했어요.

</details>

<details>
<summary><h4>가용 시간을 매번 저장하면 안 될 것 같았어요</h4></summary>

> **문제**: 드래그할 때마다 가용 시간을 바로 저장하면 요청이 너무 잦아지고, 사용자가 페이지를 벗어나는 순간 마지막 변경 사항이 저장되지 않고 씹힐 위험이 있었어요.

> **해결**: 500ms 디바운스로 저장 요청 빈도를 줄이고, 페이지 이탈 시점의 저장은 `sendBeacon`으로 처리해 요청이 끊기지 않고 안정적으로 전송되게 했어요.

</details>

</details>

---

### Last Chance `Game Dev · Team`
> **"유니티 2D 진영기반 뱀서 게임 구현"**

**왜 만들었나**: 기존 뱀서라이크 장르와 차별화하기 위해, 진영 시스템과 AOS식 조작을 결합한 게임을 수업 팀 과제로 기획했어요.

**핵심 경험**: 수업 팀 프로젝트로 4개월간 유니티로 게임을 제작

**Demo**: [게임 발표 자료](https://sejonguniversity-my.sharepoint.com/:p:/r/personal/23011810_sju_ac_kr/Documents/%E1%84%8C%E1%85%AE%E1%86%BC%E1%84%80%E1%85%A1%E1%86%AB%E1%84%87%E1%85%A1%E1%86%AF%E1%84%91%E1%85%AD%20%E1%84%8C%E1%85%A1%E1%84%85%E1%85%AD%201.pptx?d=w478a9b0fe7564f9d8258998b7de3bc15&csf=1&web=1&e=B0O4xA) · [플레이 영상](https://drive.google.com/drive/folders/1x_EcGXgb-4HY_vahjJP4I5gNfEsXRbU4)

![화면 기록 2026-03-09 오후 9 37 32](https://github.com/user-attachments/assets/dab7f1fc-d3a1-485e-ab0b-1dd4ed7e23c3)

<details>
<summary><h3>엔지니어링 하이라이트</h3></summary>

<details>
<summary><h4>뱀서라이크에 진영전을 얹으면 어떨까 싶었어요</h4></summary>

> 다른 게임들과의 차별성을 위해 뱀서라이크 장르에 진영 시스템과 AOS식 플레이어 조작을 함께 녹여서 새로운 장르 조합을 시도했어요.

</details>

<details>
<summary><h4>Tag 하나로 로그라이크에 없던 진영 개념을 만들었어요</h4></summary>

> Unity의 Tag 시스템으로 아군/상대 진영을 분류해서, 기존 로그라이크 장르에 없던 진영전 개념을 부여했어요.

</details>

<details>
<summary><h4>아군 201 vs 적군 600, 이 규모의 전투를 버티게 만들어야 했어요</h4></summary>

> **문제**: 아군 200+1 대 적군 200×3 규모의 대규모 동시 전투에서 물리 충돌·거리 계산과 렌더링 부하가 감당하기 어려운 수준이었어요.

> **해결**: 이 정도 물량의 동시 전투를 버틸 수 있게 물리 엔진의 충돌·거리 계산과 렌더링을 최적화했어요.

</details>

</details>

---

### self-driving (clone-coding) `ML · Simulation`
> **"Canvas 2D를 활용한 머신러닝-유전적알고리즘 자동차 구현"**

**왜 만들었나**: 머신러닝을 이론으로만 이해하고 넘어가는 대신, Canvas 2D 위에서 유전 알고리즘으로 자동차가 스스로 주행을 학습해가는 과정을 직접 구현하며 익히고 싶었어요.

**핵심 경험**: JS로 머신러닝 구현, Canvas 2D를 활용하여 자동차 객체 및 배경 구현, FPS 업데이트 주기에 따른 실시간 비주얼 변경 요소 구현

**Live Demo**: [https://resplendent-selkie-2e1e63.netlify.app/](https://resplendent-selkie-2e1e63.netlify.app/)

![화면 기록 2026-03-07 오후 5 14 38](https://github.com/user-attachments/assets/959c9102-856c-4daf-83fd-2a6066e43cb1)

---

### endCard `Web · Full-stack` (OCI + Docker로 배포)
> **"에빙하우스의 망각 곡선에 따른 복습 시스템을 이용한 AI 예문기반 영단어 암기 웹사이트"**

**왜 만들었나**: 영단어를 외워도 금방 잊어버리는 문제를, 에빙하우스 망각 곡선에 맞춰 복습 주기를 자동으로 잡아주고 AI가 그때그때 새 예문을 만들어주는 서비스로 풀어보고 싶었어요.

**핵심 경험**: 기획부터 개발, 배포까지 처음으로 혼자 완주한 첫 개인 프로젝트

**Live Demo**: [사이트 보기](http://152.67.211.137:8001/)

![화면 기록 2026-03-20 오후 3 25 21](https://github.com/user-attachments/assets/410f2b11-f6c6-48fa-bcf3-9d90b0eb5849)

<details>
<summary><h3>엔지니어링 하이라이트</h3></summary>

<details>
<summary><h4>기획부터 배포까지 혼자 완주한 첫 프로젝트예요</h4></summary>

> UI/UX 설계, 기술 선정, 사용자 플로우까지 전부 혼자 고려하며 배포까지 끝마쳤어요.

</details>

<details>
<summary><h4>책과 강의로 배워가며 스택을 하나씩 붙였어요</h4></summary>

> 개발 지식과 경험이 없는 상태에서 도서관 책과 강의로 배워가며 EJS+JS, Express, MongoDB, CSS로 기능을 구현하고 AWS 배포까지 경험했어요.

</details>

<details>
<summary><h4>세션 기반으로 로그인 기능을 직접 구현했어요</h4></summary>

> session을 바탕으로 로그인 기능을 구현했어요.

</details>

<details>
<summary><h4>Gemini API로 예문을 그때그때 생성하게 했어요</h4></summary>

> Gemini API를 호출해 프롬프트 기반으로 단어 예문을 생성하게 했어요.

</details>

</details>

---

### LoadMap

* **ESP32 & Linux Server**: e-Ink 디스플레이를 활용한 개인용 대시보드 구축
  * (진행중) 맥북에 리눅스 서버를 구축하여 ESP로 Manna 웹 비주얼 렌더링 및 외부장비로 조작 구현 예정
  * 최종적으로, 어느 디스플레이에서도 ESP 칩만 있으면 Manna 웹 갤러리처럼 구현할 예정
  * => 구현 완료, 문서화 중

* **ESP32 & Linux Server & Python**: 초음파 센서를 Lidar 형태로 배치 후, 머신러닝 학습을 통하여 가위바위보 분석 시스템 구축

* **ESP32 & Linux Server & Python**: 가속도 센서를 활용하여 복싱 임팩트에 대하여 머신러닝 학습 및 임팩트 가이드 제공
