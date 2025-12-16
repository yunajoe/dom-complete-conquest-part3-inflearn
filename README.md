## mission 설명

- 디자인 시안에서는 페이지의 메인 제목(<h1>)이 남색(#1e3a8a), 32px, bold, 아래 여백 16px로 보여야 합니다.
- 하지만 실제 화면에서는 검은색(#000), 28px, 기본 두께, 여백 없음으로 나타납니다.
- Elements / Styles / Computed 탭을 사용해 원인을 정확히 추적하고, CSS를 안전하게 수정해 시안과 일치시키세요.

## mission 문제 요구 사항

- DevTools Elements 탭에서 <h1>을 선택하고 Styles 패널에서 어떤 규칙이 적용, 무시되는지 확인하세요

- Computed 탭에서 최종 color, font-size, font-weight, margin 값을 확인하세요

- UA (User Agent) 기본 스타일의 margin-block-start/end(브라우저 기본 h1 여백) 도 체크하세요

- 시안( 남색(#1e3a8a), 32px, 굵게, 아래 여백 16px)를 만족하도록 구체성과 선언순서를 고려해 css를 수정하세요

- 전역 규칙을 완전히 제거하지 않아도 되지만, 영향 범위를 안전하게 좁히는 방식으로 해결하세요

## mission 문제의 의의

- 실무에서 시안과 화면이 다르다는 제보의 90%는 스타일 충돌이다
- 이 미션은 Styles/Computed/Box Model를 활용해 충돌 원인을 빠르게 진단하고 구체성, 캐스케이딩, UA 기본값을 고려해 부작용 없기 고치는 능력을 훈련한다

## 미션 풀이 주소

https://www.notion.so/mission-1-2cba2ed24b5e807292a8e2b583309085?source=copy_link
