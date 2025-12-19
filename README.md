## 현재 상황

- 이미지: 상단의 큰 이미지가 늦게 로드되며 공간 예약이 없어 콘텐츠를 아래로 밀어낸다
- 광고 영역: 상간 광고가 나중에 prepend 되어 문서 전체가 한번 더 흔들린다
- 애니메이션: left로 이동하는 배너가 레이아웃 재계산을 유발
- 폰트: 웹폰트가 늦게 도착하면 줄바꿈/높이가 변해 텍스트 블록이 흔들림

## mission 설명

- 위 문제를 직접 재현하고, CLS를 수치로 측정한 뒤,
- 원인별 최적화(이미지 자리 에약, 상단 late 삽입 방지, transform이동, 폰트 swap)를 적용하여,
- CLS < 0.10를 달성하세요
- HUD(실시간 표시) 와 DevTools Performance 탭에서 개선 효과를 시각, 수치로 검증하세요

## mission 문제 요구 사항

최종 목표: CLS <= 0.10

1. 이미지 shift 제거

- <img width height> or aspect - ratio 로 자리를 예약
- skeleton UI로 로딩 중에도 시각적 안정성 제공
- 로딩 후 onload에서 skeleton -> 실제 이미지로 교체

2. 상단 Late Inserstion 방지 / 완화

- 상단 광고/공지 등 늦게 오는 컴퍼넌트는 초기부터 고정 높이 컨테이너로 자리 확보
- 나중엔 내용만 교체 또는 position: sticky/fixed 로 문서 흐름을 밀지 않도록

3. 애니메이션 최적화

- left/top/margin 대신 transform: translate 사용

4. 웹폰트 shift 최소화

- Google Fonts Css + display=swap
- 주요 텍스 line-height 고정으로 줄바꿈 변동 최소화

5. 층정과 검증

- HUD로 실시간 CLS 표시
- DevTools Performance에서 Layout Shift 이벤트 확인(Moved from/to, impacted nodes)

## mission 문제의 의의

- UX 안정성 확보: 화면이 덜컥하지 않아 사용자 집중/조작 안정
- SEO/매출 영향: CLS 양호(≤0.10) 유지 → 검색 노출/신뢰/전환율 개선
- 재현-측정-개선-검증 사이클 훈련:실무 프로젝트에 곧바로 적용 가능
- 조직 설득력 강화:HUD 수치 + DevTools 시각 증거로 PM/디자인/경영진 설득 용이
