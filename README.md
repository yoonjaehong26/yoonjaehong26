<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=auto&height=200&section=header&text=Software%20Engineer&fontSize=70" width="100%">
</div>

### 💫 About Me
* 🎓 **University**: Sejong University, Software Major 
* 🛠 **Main Focus**: Web Development (Next.js, React) & AI/ML 
* 📟 **Current Interest**: Embedded Systems (ESP32) & Linux Server
* 🏃 **Hobbies**: Running, Fitness, reading
* 🤝 **Value**: Team-oriented development with strict coding conventions

---

### 📊 My GitHub Contributions
<p align="center">
  <img src="https://github-readme-stats-one-bice.vercel.app/api?username=yoonjaehong26&show_icons=true&count_private=true&theme=radical&hide_border=true" alt="Jaehong's GitHub Stats" />
  <img src="https://github-readme-stats-one-bice.vercel.app/api/top-langs/?username=yoonjaehong26&layout=compact&theme=vision-ary-dark&hide_border=true" alt="Top Langs" />
</p>

---


### 💻 Tech Stack

#### 🌐 Frontend Development
![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![shadcn/ui](https://img.shields.io/badge/shadcn/ui-000000?style=for-the-badge&logo=shadcnui&logoColor=white)
![Styled Components](https://img.shields.io/badge/styled--components-DB7093?style=for-the-badge&logo=styled-components&logoColor=white)

#### 🔄 State Management & Data Fetching
![Zustand](https://img.shields.io/badge/Zustand-443E38?style=for-the-badge&logo=react&logoColor=white)
![TanStack Query](https://img.shields.io/badge/-TanStack%20Query-FF4154?style=for-the-badge&logo=react-query&logoColor=white)
![Context API](https://img.shields.io/badge/Context%20API-61DAFB?style=for-the-badge&logo=react&logoColor=white)

#### ⚙️ Backend & Database
![Express](https://img.shields.io/badge/Express-000000?style=for-the-badge&logo=express&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)

#### 🚀 Programming Languages & Systems
![C++](https://img.shields.io/badge/C%2B%2B-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![C#](https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=c-sharp&logoColor=white)
![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)

#### 🛠️ Tools & Game Dev
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)
![Netlify](https://img.shields.io/badge/Netlify-00C7B7?style=for-the-badge&logo=netlify&logoColor=white)
![Unity](https://img.shields.io/badge/Unity-FFFFFF?style=for-the-badge&logo=unity&logoColor=black)

---

### 🔭 Featured Projects

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

<details>
<summary><h3>🛠️ 엔지니어링 하이라이트</h3></summary>

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

> **문제**: 한 화면에서 스와이프(다음/이전 구절), 엣지 스와이프(뒤로가기·모드 전환), 탭(페이지 이동), 더블탭(북마크), 롱프레스(공유)까지 다섯 가지 제스처를 구분해야 했고, 잘못 인식하면 원치 않는 동작이 발생해요.

> **해결**: 엣지 40px 이내에서 시작하는 스와이프만 감지하고, 20px 이상 움직여야 액션이 실행되게 하면서 그 사이는 진행 거리에 비례해 opacity를 점진적으로 올려 "지금 당기고 있다"는 시각 피드백을 줬어요. 탭은 인스타그램 스토리처럼 화면 좌측 1/3·우측 2/3으로 영역을 나눠 이전/다음 페이지로 연결했고, 더블탭(300ms 이내 재탭)과 롱프레스(500ms)는 이동거리 10px 이내인지로 구분해 서로 오인식하지 않게 만들었어요.

> **결과**: 라이브러리 없이 다섯 가지 제스처가 충돌 없이 공존.

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

> **문제**: 큐레이션을 열 때마다 책 단위 JSON을 여러 번 나눠 불러와, 요청 3회·840KB 다운로드가 필요했어요.

> **해결**: 구절 UID 배열을 한 번에 받는 Batch API(`GET /api/verses?uids=...&version=...`)로 바꿔 요청을 1회로 합치고, 필요한 구절만 서버에서 추출해 응답하게 했어요. 번역본 5개(KRV, NKRV, KJV, YLT, WEB)와 여러 언어를 오가도 같은 구절은 하나의 전역 UID로 식별해서 캐시 키를 통일했어요.

> **결과**: 다운로드량 300bytes(약 2,800배 감소), 응답 시간 250ms → 50ms.

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

> **결과**: 화면 깜빡임 없이 전환 시간 16ms.

</details>

<details>
<summary><h4>성경 구절, 헬라어, 찬양, 기도문... 형태가 다 다른데 왜 한 화면에서 매끄럽게 넘어갈까요?</h4></summary>

> **문제**: 큐레이션 콘텐츠가 구절·헬라어·찬양가사·미디어·묵상·읽기진행도처럼 형태가 전부 달라서, 각각 다른 렌더링 로직을 만들면 화면마다 UX가 제각각이 될 위험이 있었어요.

> **해결**: `Page`를 7종 타입의 discriminated union으로 설계하고, `PageRenderer`가 strategy 패턴으로 타입별 컴포넌트에 위임하게 했어요. 사전 제작된 정적 큐레이션과, 사용자 진행도·날짜 기반으로 실시간 생성되는 동적 큐레이션(이어읽기, 오늘의 잠언·시편, 마태·마가·누가·요한·사도행전·바울서신 등 465개 이상의 소제목 순차 읽기)을 같은 파이프라인에 통합했어요.

> **결과**: 새 콘텐츠 타입을 추가해도 기존 화면은 안 건드림, 페이지 전환에 `startTransition`을 적용해 체감 렉을 30~50% 줄임.

</details>

<details>
<summary><h4>혼자 만든 프로젝트인데 왜 이렇게까지 규칙을 정했을까요?</h4></summary>

> **문제**: 기능이 늘어날수록 `isActive`, `onChange`처럼 이름만 봐서는 무슨 의미인지 알 수 없는 props가 쌓이기 쉬웠고, 레이어 간 의존 방향도 흐트러지기 쉬웠어요.

> **해결**: boolean props는 `is`/`should`/`has` 접두사, 콜백은 `on + 명사 + 동사` 패턴을 강제하는 네이밍 규칙을 세웠어요. `features → shared`만 허용하고 반대 방향은 금지하는 단방향 레이어 규칙을 두고, 위반이 필요한 경우 항상 props로 주입하게 했어요. 코드를 나중에 AI 도구로 다시 훑어봐도 이름만으로 의도가 파악되게 하는 것도 목표였어요.

> **결과**: 100개 넘는 파일에서 일관된 구조 유지, 처음 보는 사람도 이름만으로 의도 파악 가능.

</details>

<details>
<summary><h4>번역본이 4개인데 퀴즈 문제는 하나만 만들면 됐어요</h4></summary>

> **문제**: 번역본마다 빈칸 퀴즈를 따로 만들면 콘텐츠가 4배로 늘고, 정답 단어가 실수로 오답 보기에 노출될 위험도 있었어요.

> **해결**: 번역에 무관한 헬라어 원어의 Strong's 번호를 공통 키로 써서 4개 번역본이 단어장 하나를 공유하도록 설계했어요. 오프라인 생성 → 검증 스크립트 → 런타임 필터, 3중 방어로 정답 노출을 차단했어요.

> **결과**: 설계 및 구현 진행 중 (현재 데이터 약 34% 채움).

</details>

<details>
<summary><h4>번역본을 더블탭 하나로 바로 바꿀 수 있는 이유</h4></summary>

> **문제**: 번역본을 전환할 때마다 새로 API를 호출하면 전환이 끊기고 느리게 느껴져요.

> **해결**: 더블탭으로 한/영 번역을 전환하는 UX를 만들면서, 현재 보고 있는 구절의 반대 언어 버전을 백그라운드에서 미리 불러와 뒀어요.

> **결과**: 더블탭 즉시 전환, 대기 시간 없음.

</details>

<details>
<summary><h4>기능이 계속 늘어나도 안 얽히게, 미리 선을 그어둔 게 있어요</h4></summary>

> **문제**: 기능이 늘어날수록 컴포넌트·상태·로직이 서로 얽히기 쉬웠어요.

> **해결**: app · components · hooks · stores · services · types · constants · utils 8개 레이어로 책임을 분리하고, 도메인별 Zustand 스토어로 상태를 나눠 레이어 간 의존성이 얽히지 않게 관리했어요.

</details>

<details>
<summary><h4>노래 하나 재생했을 뿐인데 화면 4개가 같이 흔들렸다면?</h4></summary>

> **문제**: 오디오 재생 중 관련 없는 뷰 4개가 같이 리렌더됐어요.

> **해결**: `ContentRouter`가 구독하던 `audioStore`를 실제로 쓰는 `ReaderPanels`로 옮기고, `SettingsPanel`에 남아있던 불필요한 URL 훅도 제거했어요.

> **결과**: 챕터 이동 시 리렌더 27.6ms 감소.

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
<summary>엔지니어링 하이라이트</summary>

* **다른 개발자 도구와 안전하게 공존하게 만들었어요**: React DevTools 확장이나 react-scan 같은 다른 분석 도구가 먼저 켜져 있어도 서로 방해하지 않고 함께 동작하도록 설계했어요. 처음엔 여러 도구를 한 번에 지원하려고 욕심을 냈다가 무한 재귀로 실제 페이지가 멈추는 사고를 냈고, 원인을 정확히 찾아내 기존 동작을 보존한 채 딱 한 번만 연결하는 더 안전한 방식으로 다시 설계했어요.
* **4가지 빌드 도구를 전부 자동으로 지원했어요**: Vite, webpack, Rspack, Next.js(Turbopack)처럼 실무에서 널리 쓰이는 빌드 도구 4종을 설치 한 줄(`npm install`)만으로 자동 연결되게 만들었어요. 도구마다 내부 동작 방식이 달라 각각 다른 연결 방법이 필요했고, 4가지 경로 전부 실제로 화면이 뜨는지 자동화 테스트로 하나하나 확인했어요.
* **느려지는 원인을 직접 찾아 최대 28배 빠르게 개선했어요**: 컴포넌트가 5,000개까지 늘어나면 반응 속도가 최대 28배까지 느려지는 성능 문제가 있었어요. 코드를 직접 분석해서 "화면에 안 보이는 요소까지 전부 그리고 있었다"는 진짜 원인을 찾아냈고, 화면 밖 요소는 아예 그리지 않는 방식으로 바꿔서 거의 그대로(1배 수준)까지 개선했어요.
* **배포된 버전에서 한 번도 작동한 적 없던 기능을 발견해서 고쳤어요**: 빌드 최적화 과정에서 특정 기능의 코드 전체가 통째로 사라지는 버그가 있었어요. 그래서 배포된 모든 버전에서 그 기능이 실제로는 한 번도 정상 동작한 적이 없었다는 걸 실사용 중 발견해서 수정했고, 같은 실수가 나중에 다른 파일에서 다시 발생한 것도 재발 방지 테스트를 추가해서 잡아냈어요.

</details>

---

### doogoodoogoo(두구두구) `Web · Team` ![최근 30일 방문자](http://152.67.211.137:3000/badge?v=2)
> **"세종대 일정 정리 및 ics를 통한 캘린더 일정등록 자동화 서비스"**

**핵심 경험**: 사용자 경험과 니즈를 고려하여 프론트 2명, 백엔드 3명과 함께 진행한 협업 프로젝트

**Live Demo**: [https://doogoodoogoo.kr/](https://doogoodoogoo.kr/)

![화면 기록 2026-03-20 오후 3 45 59](https://github.com/user-attachments/assets/cd5c7f65-eec5-4568-b3d7-6837f53f56f2)

<details>
<summary>엔지니어링 하이라이트</summary>

* **기술보다는 사용자의 경험 우선 개발**: 각 개발단계에서 사용자에게 필요한 니즈에 맞추어 개발을 진행하도록 노력(디자인, 레이아웃, UI)
* **체계화된 개발 과정 공개**: git flow 전략과 함께 공개된 오픈소스 환경에서 중간 개발요소를 커밋 단위로 문서화
* **팀 활동**: swagger를 통한 API 명세와 함께 프로젝트 아이디어 도출부터 배포까지 전 과정을 팀과 함께 개발

</details>

---

### UnJ (언제) `Web · Collab` w.claude
> **"복잡한 약속 시간을 한눈에, 드래그 기반 일정 조율 플랫폼"**

**핵심 경험**: 30분 단위 그리드 드래그 인터랙션을 통해 다수의 참여자가 가능한 시간을 시각적으로 집계

**Live Demo**: [https://unj.kr/](https://unj.kr/)

![화면 기록 2026-03-07 오후 4 59 27](https://github.com/user-attachments/assets/d5392223-9994-4707-a9ab-3a99336e2ce0)

<details>
<summary>엔지니어링 하이라이트</summary>

* **Interactive Grid**: 마우스/터치 드래그 인덱스 계산 알고리즘을 통한 다중 슬롯 일괄 선택 구현
* **Heatmap Logic**: 참여 인원 및 상태(가능/조정가능)에 따른 투명도/분할 그라데이션 동적 렌더링 로직 설계
* **Optimization**: 500ms 디바운스 및 `sendBeacon`을 활용한 안정적인 가용시간 자동 저장 시스템 구축

</details>

---

### Last Chance `Game Dev`
> **"유니티 2D 진영기반 뱀서 게임 구현"**

**핵심 경험**: 수업 팀 프로젝트로 4개월간 유니티로 게임을 제작

**Plat Demo**: [게임 발표 자료](https://sejonguniversity-my.sharepoint.com/:p:/r/personal/23011810_sju_ac_kr/Documents/%E1%84%8C%E1%85%AE%E1%86%BC%E1%84%80%E1%85%A1%E1%86%AB%E1%84%87%E1%85%A1%E1%86%AF%E1%84%91%E1%85%AD%20%E1%84%8C%E1%85%A1%E1%84%85%E1%85%AD%201.pptx?d=w478a9b0fe7564f9d8258998b7de3bc15&csf=1&web=1&e=B0O4xA) · [플레이 영상](https://drive.google.com/drive/folders/1x_EcGXgb-4HY_vahjJP4I5gNfEsXRbU4)

![화면 기록 2026-03-09 오후 9 37 32](https://github.com/user-attachments/assets/dab7f1fc-d3a1-485e-ab0b-1dd4ed7e23c3)

<details>
<summary>엔지니어링 하이라이트</summary>

* **독창적인 게임 시스템 설계**: 다른 게임들과의 차별성을 위한 뱀서라이크 + 진영시스템 + AOS식 플레이어 조작을 조화롭게 융합하여 새로운 게임 장르 융합
* **Unity Tag**: 아군/상대진영을 tag 시스템으로 분류하여 기존의 로그라이크에 진영시스템 부여
* **물리엔진 최적화**: 아군-200 + 1 vs 적군-200 x 3의 대규모 전투를 위한 (충돌·거리) 물리엔진, 렌더링 최적화

</details>

---

### self-driving (clone-coding) `ML · Simulation`
> **"Canvas 2D를 활용한 머신러닝-유전적알고리즘 자동차 구현"**

**핵심 경험**: JS로 머신러닝 구현, Canvas 2D를 활용하여 자동차 객체 및 배경 구현, FPS 업데이트 주기에 따른 실시간 비주얼 변경 요소 구현

**Live Demo**: [https://resplendent-selkie-2e1e63.netlify.app/](https://resplendent-selkie-2e1e63.netlify.app/)

![화면 기록 2026-03-07 오후 5 14 38](https://github.com/user-attachments/assets/959c9102-856c-4daf-83fd-2a6066e43cb1)

---

### endCard `Web · Full-stack` (OCI + Docker로 배포)
> **"에빙하우스의 망각 곡선에 따른 복습 시스템을 이용한 AI 예문기반 영단어 암기 웹사이트"**

**핵심 경험**: 기획부터 개발, 배포까지 처음으로 혼자 완주한 첫 개인 프로젝트

**Plat Demo**: [사이트 보기](http://152.67.211.137:8001/)

![화면 기록 2026-03-20 오후 3 25 21](https://github.com/user-attachments/assets/410f2b11-f6c6-48fa-bcf3-9d90b0eb5849)

<details>
<summary>엔지니어링 하이라이트</summary>

* **전체적인 설계 경험**: 처음으로 혼자 만들어본 첫 프로젝트이며, UI/UX 설계, 기술 선정, 사용자 플로우 등을 고려하고 배포까지 끝마친 프로젝트
* **다양한 라이브러리 사용**: 당시 개발 지식과 경험이 없어서 도서관에서 책을 읽고 강의를 통해 배운 지식으로 EJS + JS, Express, MongoDB, CSS에 대해 알아가며 기능을 구현, AWS 배포까지 경험
* **로그인 기능 구현**: session을 바탕으로 로그인 기능 구현
* **Gemini API 활용**: API를 활용하여 프롬프트에 따른 예문을 호출

</details>

---

### 🛣️ LoadMap

* **ESP32 & Linux Server**: e-Ink 디스플레이를 활용한 개인용 대시보드 구축
  * (진행중) 맥북에 리눅스 서버를 구축하여 ESP로 Manna 웹 비주얼 렌더링 및 외부장비로 조작 구현 예정
  * 최종적으로, 어느 디스플레이에서도 ESP 칩만 있으면 Manna 웹 갤러리처럼 구현할 예정
  * => 구현 완료, 문서화 중

* **ESP32 & Linux Server & Python**: 초음파 센서를 Lidar 형태로 배치 후, 머신러닝 학습을 통하여 가위바위보 분석 시스템 구축

* **ESP32 & Linux Server & Python**: 가속도 센서를 활용하여 복싱 임팩트에 대하여 머신러닝 학습 및 임팩트 가이드 제공
