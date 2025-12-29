# 문제 상황

- 카드 레이아웃에서 스크롤 중 자주 끊긴다. (스크롤끊김)
- 카드 hover시 FPS 급락
- FOIT현상. 초기 렌더링에서 텍스트가 한동안 보이지 않았다가 폰트가 내려온 뒤에야 표시된다.
- 아이콘/스파크라인에서 잦은 Paint

# mission 문제 요구 사항

- Performance 녹화로 FPS 그래프 & Main 스레드(Style/Layout/Paint) 병목 구간 캡처
- Paint Flashing 켜고 hover/스크롤 시 초록색 반짝임 발생 지점 캡처 (Repaint)
- Network에서 Web Font 로딩(FOIT/FOUT) 확인
- 레이아웃 방식으로 인한 Reflow(많은 inline-block) 실측
- 최적화 후 다시 녹화 → FPS 55~60 근접, Paint 블록 감소, Composite 위주 확인
- 전/후 타임라인/스크린샷을 팀 공유용으로 정리

# mission 문제의 의의

- “실제 데이터가 들어간 카드/표/미니차트” 환경에서 병목을 단계별로 분해
- 시각적 결과는 유지하면서 렌더링 단계(Layout/Paint/Composite) 관점으로 최적화
- 팀 리뷰 시 DevTools 근거(Frames, Main, Bottom-Up, Network)로 설득 가능한 리포트 작성 연습
