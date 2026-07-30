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

**왜 만들었나**: 성경 통독에 도전한 사람들이 중도 포기하는 가장 큰 이유는 "한 번에 읽어야 할 분량이 너무 많다"는 부담감 — 과자를 한 입씩 먹듯, 장 단위 대신 한 구절씩 스와이프하며 음미하는 릴스형 UX로 진입 장벽을 낮춤

**핵심 UX**
* 릴스처럼 세로 스와이프로 한 구절씩 음미하며 읽는 경험
* 순수 제스처 제어로 만든 네이티브 앱 수준의 조작감
* 화면 깜빡임 없이 즉각 전환되는 탐색 경험

**Live Demo**: [https://manna-mu.vercel.app/](https://manna-mu.vercel.app/)

![화면 기록 2026-03-07 오후 4 28 44](https://github.com/user-attachments/assets/734310d0-a28c-4d1f-8d5b-7554c28eefac)

<details>
<summary><h3>🛠️ 엔지니어링 하이라이트</h3></summary>

<details>
<summary><h4>iOS 시스템 제스처랑 충돌하던 스와이프, 라이브러리 없이 어떻게 잡았을까요?</h4></summary>

> iOS PWA(Standalone 모드)에서는 화면 좌측 엣지 40px 이내에서 시작하는 스와이프가 시스템 뒤로가기 제스처로 인식돼 앱의 커스텀 스와이프와 충돌했어요.
>
> `touchstart` 이벤트에서 터치 시작 좌표가 엣지 영역 안인지 확인해 `preventDefault()`로 시스템 제스처를 차단했어요. iOS에서 `preventDefault`가 실제로 먹히려면 리스너에 `{ passive: false }` 옵션이 필수라 이를 명시했어요.
>
> `navigator.standalone`과 `matchMedia('(display-mode: standalone)')`로 iOS PWA 여부를 감지해, 이 로직이 필요한 환경에서만 동작하도록 범위를 좁혔어요.

</details>

<details>
<summary><h4>번역본 5개, 언어도 여러 개인데 API 호출 수는 어떻게 줄였을까요?</h4></summary>

> 큐레이션을 열 때마다 책 단위 JSON을 여러 번 dynamic import 하던 방식은 요청 3회·840KB 다운로드가 필요했어요.
>
> 구절 UID 배열을 한 번에 받는 Batch API(`GET /api/verses?uids=...&version=...`)로 바꿔서 요청을 1회로 줄이고, 필요한 구절만 서버에서 추출해 응답하도록 했어요.
>
> 그 결과 다운로드량이 300bytes(약 2,800배 감소), 응답 시간이 250ms → 50ms로 줄었어요. 번역본 5개(KRV, NKRV, KJV, YLT, WEB)와 여러 언어를 오가도 같은 구절은 하나의 전역 UID로 식별해서 캐시 키를 통일했어요.

</details>

<details>
<summary><h4>기능이 계속 늘어나도 안 얽히게, 미리 선을 그어둔 게 있어요</h4></summary>

> app · components · hooks · stores · services · types · constants · utils 8개 레이어로 책임을 분리했어요.
>
> 도메인별 Zustand 스토어로 상태를 나눠, 기능이 늘어나도 레이어 간 의존성이 얽히지 않게 관리했어요.

</details>

<details>
<summary><h4>1초 넘게 걸리던 첫 로딩, 30ms까지 줄인 방법은요</h4></summary>

> 배포 플랫폼을 Netlify에서 Vercel로 옮기면서, 모든 콘텐츠를 처리하던 동적 라우트(`[[...slug]]`)에 `force-static`을 적용해 정적 생성으로 바꿨어요.
>
> Client Component 위주였던 페이지를 Server Component로 재구성해 CDN에서 정적으로 서빙되게 만들었어요.
>
> 그 결과 TTFB가 1,134ms → 265ms → 약 30ms까지 단계적으로 줄었어요(최대 35배).

</details>

<details>
<summary><h4>화면이 갑자기 하얗게 죽어버렸는데, 범인은 유튜브였어요</h4></summary>

> YouTube IFrame API가 대상 DOM을 강제로 iframe으로 치환해 React fiber tree가 깨지는(`insertBefore` 에러) 문제였어요.
>
> wrapper ref 하위에 React 관리 밖 자식 노드를 두는 방식으로, React가 그 영역을 아예 건드리지 않게 만들어 해결했어요.

</details>

<details>
<summary><h4>화면 전환할 때 깜빡임이 한 번도 없었던 이유, 사실 페이지 이동을 안 했어요</h4></summary>

> `ContentRouter` 컴포넌트가 홈/릴스/평독 3개 뷰를 전부 항상 마운트해두고, `view`/`back` URL 파라미터만으로 어떤 뷰를 보여줄지와 스마트 백내비게이션을 관리해요.
>
> 라우트 이동 없이 파라미터만 바꾸는 방식이라 화면 깜빡임 없이 전환 시간 16ms를 달성했어요.
>
> 다만 3개 뷰를 항상 메모리에 들고 있어야 하는 트레이드오프는 의도적으로 감수했어요.

</details>

<details>
<summary><h4>안드로이드는 왜 과감히 포기했을까요? 인스타그램도 같은 걸 겪었더라고요</h4></summary>

> Android의 시스템 제스처는 `preventDefault`로 막을 수 없는 시스템 레벨 동작이라는 걸 확인했어요.
>
> Instagram PWA도 같은 문제로 네이티브 앱으로 회귀했던 사례를 근거로, iOS 제스처 제어에 집중하는 전략을 의도적으로 택했어요.

</details>

<details>
<summary><h4>노래 하나 재생했을 뿐인데 화면 4개가 같이 흔들렸다면?</h4></summary>

> `ContentRouter`가 구독하던 `audioStore`를 실제로 오디오 상태를 쓰는 `ReaderPanels`로 옮겼어요.
>
> 오디오 재생 중 관련 없는 4개 뷰가 같이 리렌더되던 걸 막았고, `SettingsPanel`에 남아있던 불필요한 URL 훅도 제거했어요.
>
> 그 결과 챕터 이동 시 27.6ms의 리렌더 시간을 줄였어요.

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
