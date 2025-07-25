# Be-Fit 프로젝트 회고록

## 진행 기간: 2025년 6월 23일 ~ 2025년 7월 2일

---

## 1. 시작하며

이번 Be-Fit 프로젝트는 JavaScript를 배우고 나서 처음으로 기획부터 기능 구현까지 주도적으로 수행한 팀 프로젝트였다.  
첫 프로젝트였던 Nexon 클론과 달리 단순 복제가 아닌, 주제를 선정하고 UI/UX를 직접 설계하고 기능을 완성해야 했다.  

처음에는 어떤 기능을 만들지 감이 오지 않았지만, 팀원들과 논의 끝에 건강이라는 주제를 선택하게 되었고, 이 안에서 운동 루틴, 식단 추천, AI 건강 상담 등 다양한 기능을 구상하게 되었다.  
특히 Infermedica API를 통해 병원 가기 전 자가 진단 기능을 구현하려 했고, 이를 위해 번역 API까지 연동하는 복잡한 구조도 감수하기로 했다.

---

## 2. 주요 구현 기능

- 메인 페이지 구성 및 로고, 파비콘 제작
- 건강 플래너, 운동 플랜, 식단 추천 등으로 구성된 헤더 메뉴 구현
- 각 메뉴마다 hover 시 설명이 바뀌는 메가 메뉴 구조 개발
- Gemini API 기반 AI 건강 상담 챗봇 구현 (Infermedica API 대체)
- 챗봇 UI를 모달 형태로 재사용 가능하게 설계
- 공통 모달을 fetch로 외부 HTML로부터 불러오도록 구조화
- 툴팁, 버튼 애니메이션, 반응형 레이아웃 등 UI 디테일 개선

---

## 3. 어려웠던 점

- HTML, CSS만으로 상단 로고 호버 효과를 구현하려다 Flex 방향과 범위 문제로 시간을 많이 소비
- Infermedica API가 유료화 되어 갑작스럽게 Gemini API로 대체해야 했던 점
- fetch 경로 오류, 요소 미존재 오류 등 JavaScript 디버깅에 시간이 많이 소요됨
- 팀 협업 중 .gitignore에 의해 누락된 설정 파일로 인해 API 키 공유에 문제가 발생

---

## 4. 배운 점

- JavaScript를 활용한 동적 HTML 삽입, 이벤트 연결, fetch 통신 처리 방법
- 모듈화와 재사용 가능한 코드 구조의 중요성
- 외부 API 연동 시 문서를 정확히 읽고 구조를 이해하는 능력
- 콘솔 오류 메시지를 적극적으로 분석하고 해결하는 습관의 중요성
- UI 디테일이 사용자 경험에 얼마나 큰 영향을 주는지 체감함

---

## 5. 성장 포인트

- 처음으로 외부 API를 직접 연동하고, 이에 맞는 프롬프트와 처리 로직을 설계함
- 단순 구현이 아닌 사용자 입장에서 기능을 분리하고 인터랙션을 설계하는 역량이 생김
- 문제 해결을 위해 기술 문서를 찾아보고, 대체제를 스스로 찾는 경험을 통해 자립적인 개발 습관이 생김

---

## 6. 앞으로의 계획

- AI API 응답 결과의 안정성과 응답 포맷 개선
- 챗봇 UI에 대한 예외 케이스 대응 및 에러 메시지 강화
- 공통 모듈 분리 및 설정 파일 정리
- 팀원들과 역할을 명확히 나눠 전체 흐름을 정돈하고 문서화할 예정

---

## 7. 마무리

이번 프로젝트는 단순한 기능 구현을 넘어서, 사용자 경험을 고려한 UI 설계, 외부 API 연동, 에러 디버깅, 협업 시 발생하는 문제 해결 등 실무에 가까운 경험을 할 수 있는 기회였다.  
기술적인 성장도 있었지만, 무엇보다도 어떤 문제가 생겨도 끝까지 해결하고 마무리하려는 자세를 배웠다는 점에서 의미가 컸다.

---




--- 


25년 6월 23일 회고
- 오늘: 주제 선정, 역할 분담, 개인 - 로고이미지, 파비콘, 메인 홈페이지
- 어려웠던 점: 메인 홈페이지를 만들기위해 HTML과 CSS만으로 구현하고자 했던 스타트버튼을 호버 시 위에있는 로고가 변경 되게끔 만드는 과정이 JavaScript로 하면 편하겠지만 오기가 생겨 시간을 소비했다. AI는 스타트버튼위에있는 로고형제에게 효과를 주기위해선 CSS만으로는 안된다고 부모에게 호버를 걸어 호버 범위가 늘어나면 가능하다고만 했을뿐 스스로 Flex-direction - reverse-column 으로 바꾸기 까지 시간을 소비했다는 것이 성취감은 있었으나 효율적으로 시간을 
- 배운 점: 복습하겠다고 시간을 허비하지 말자 JavaScript가 우선적이여야 한다
- 내일: Infermedica API 활용 페이지 만들기

25년 6월 24일 회고
- 오늘: 메인 홈페이지 수정 및 버튼 추가, infermedicaAPI 연동 전까지 HTML,CSS,JS (모달창은 메신저스타일로 주고받을 수있고 입력시간까지 추가하였다) 모두 완료
- 어려웠던 점: index.html 에 모달창을 띄우기위해 infermedica.html에 요소들을 추가해 fetch 하는 과정중 주소때문에 오래 붙잡혀 있었다. 파일구조에 대해선 잘 안다고 생각했지만 폴더명과 파일명이 같았고 또 주소를 반대로 입력하고있어서 시간을 너무 소비했다. 모달창을 메신저처럼 구현하기 위해 append 하는 과정또한 순탄치 못했다.
- 배운 점: fetch .then 에 대해 좀더 공부할 수 있었고 메신저를 만드는 작업은 보여지는 것과 다르다는 점을 배웠다.
- 내일: infermedica API 연동 을 우선적으로 할 예정이다. 후에 번역 API 또한 연동할계획이다. 


25년 6월 25,26일 회고
오늘:
1. Infermedica API 연동 중단 확인 및 대체 API 조사
- 기존에 사용하려던 Infermedica API가 Closed API임을 확인함
- 이를 대체할 수 있는 공개 API를 조사하고, 챗봇 목적에 맞는 후보를 선정할 계획을 세움
2. Gemini API 연동 작업
- Google Gemini API 키 발급 및 연동 설정 완료
- fetch를 통해 요청 및 응답 테스트 환경을 구성함
3. 건강 상담 챗봇을 위한 초기 프롬프트 설계
- 챗봇의 역할과 톤을 지정하기 위한 SYSTEM_PROMPT 초안 작성
- 건강 상담에 적합한 방식으로 프롬프트를 구조화함
4. 기능 정상 작동 확인
- Gemini API와의 통신이 정상적으로 이루어지는 것을 확인
- 초기 프롬프트에 대한 응답 테스트도 성공적으로 마침
느낀 점
- 외부 API는 언제든지 중단될 수 있다는 것을 실제 사례를 통해 체감함
- 새로운 API로 빠르게 대체하고 적용하는 과정에서 API 문서 읽기와 요청 구조 이해 능력이 중요함을 느꼈다
- SYSTEM_PROMPT의 세심한 설계가 챗봇의 품질에 직접적으로 영향을 준다는 점을 확인함
내일 할 일
- Gemini API 응답 포맷 정리 및 파싱 로직 개선
- 챗봇 응답 결과의 사용자 표시 방식 개선
- 건강 정보 상담의 정확성과 신뢰성을 높이기 위한 추가 조건 설계

2025년 6월 27일
오늘 한 일:
1. UI 개선 작업
- 어사이드 버튼에 호버 시 툴팁 기능 추가
- 로그인 버튼 스타일 변경 후, 어사이드 토글 버튼을 화면 우상단에 고정
- 어사이드 버튼이 자연스럽게 펼쳐지는 spread 효과를 위해 위치 및 애니메이션 조정
2. 팀 협업 관련 정리
- PR이 완료된 `.gitignore`에 의해 제외된 `config.js` 파일을 점검
- 팀원이 사용한 API 키를 내 개인 키로 교체 완료
- 이를 통해 Gemini API 통신이 정상적으로 작동되도록 설정함
느낀 점
- UI 디테일(툴팁, 위치 고정 등)의 중요성을 다시 느꼈다
- `.gitignore`로 누락된 설정 파일은 PR 과정에서 반드시 확인할 필요가 있다
- 팀원 코드가 내 환경에서 올바르게 동작하도록 세심한 조정이 필요했다
- fetch 오류 해결과 config 설계 경험은 앞으로 실무에서도 유용할 것이다
내일 할 일
- Gemini API 결과 출력을 위한 UI 개선
- AI 응답의 예외 케이스를 고려한 에러 메시지 강화
- 공통 설정 및 유틸 함수 정리를 통한 모듈화 시도


2025년 6월 28일
오늘의 목표
- 공통 모달(챗봇)을 여러 페이지에서 재사용하기
- fetch로 외부 HTML 불러오기 및 Gemini API 연동
- JS 동작 오류 디버깅 및 경로 문제 해결

오늘 배운 것 / 시도한 것
1. window.location.href 사용법 학습
- 버튼 클릭 시 다른 페이지로 이동하는 코드 작성
- window.location.href = 'main.html'은 현재 창을 해당 경로로 이동시킨다는 의미
2. 이벤트 리스너 연결 방식 학습
- onclick 속성 대신 addEventListener 사용
- DOMContentLoaded 이벤트 안에서 안전하게 연결하는 법 익힘
3. JS 실행 오류 해결
- addEventListener에서 null 오류 발생 원인 파악: 요소 미존재 또는 DOM 로딩 전 실행
- 해결: 요소 존재 여부 확인(if 문) 및 DOMContentLoaded 사용
4. fetch 경로 오류 디버깅 (404 Not Found)
- HTML 기준 경로와 JS 기준 경로 차이 이해
- fetch("src/infermedica/infermedica.html") → ../infermedica/infermedica.html 로 수정
5. 동적으로 삽입된 HTML 요소 접근 시 주의사항
- scrollHeight 오류 발생: 아직 삽입되지 않은 DOM 요소에 접근해서 생김
- 해결: 요소 존재 여부 확인 및 append 이후 호출 보장

오늘 리팩토링한 것
- infermedica.js 전체 리팩토링
  - 경로 자동 감지
  - 요소 존재 체크
  - 모달 삽입 후 이벤트 연결 방식 변경
- 공통 모달 재사용 구조 설계 시작

어려웠던 점
- 경로 문제: JS 기준이 아닌 HTML 기준 경로 설정에 혼란
- 요소 존재 여부 확인 없이 이벤트 연결 시 오류가 자주 발생함

느낀 점
- fetch와 공통 모듈 구조를 이해하며 코드가 유연해지는 느낌을 받음
- 콘솔 오류 메시지를 정확히 읽고 해석하는 습관이 중요함을 깨달음
- 여러 페이지에서 모듈을 공유하는 구조는 실제 프로젝트에서 매우 유용하다는 걸 느낌>

2025년 7월 1일
오늘 한 일
- 건강 관련 웹페이지 상단 헤더 메뉴 구조를 3개(nav-item)로 구성하였다.
- 건강 플래너: 일정, 분석, 목표 설정 항목 구성
- 운동 플랜: 운동 영상 추천, 상품 검색, AI 건강 상담 항목 구성
- More: 식단 추천, 커뮤니티, 진행 현황 항목 구성
- 각 메뉴 항목에 마우스를 올리면 오른쪽에 해당 설명이 바뀌는 메가 메뉴 인터랙션을 구현하였다.
- data-target 속성과 id 매칭 방식으로 동작 구현
- JavaScript로 hover 이벤트 처리하여 설명 노출
- .mega-header 구조를 정리하고, 반응형 CSS 일부 적용함

느낀 점
- 처음에는 메가 메뉴 구조와 hover 기능을 어떻게 연동할지 어려웠지만, data-target을 활용한 방식으로 간결하게 구현할 수 있어서 유익했다.
- CSS 배경색 조합을 고민하면서 색상 간의 조화나 대비의 중요성을 다시 느꼈다.
- 인터랙션과 디자인을 조합하여 하나의 구조로 완성하는 과정이 점점 익숙해지고 있다는 것을 체감했다.
