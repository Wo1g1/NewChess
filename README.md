# Ishenoy Vinoy Laquir

이셰노이 비나([Ishenoy Vinah](https://jwiki.kr/wiki/index.php/%EC%9D%B4%EC%85%B0%EB%85%B8%EC%9D%B4_%EB%B9%84%EB%82%98)) 세계관에서 파생된 변형 체스 4종을 브라우저에서 즐길 수 있는 정적 웹페이지.

**플레이**: https://wo1g1.github.io/NewChess/

## 구성

- `index.html` — 허브. 홈 화면(게임 선택) ↔ 게임 화면 전환, 테마(심플/클래식) 관리, 하단 라이선스/Info/Links 푸터를 담당한다.
- `games/` — 게임 4종의 개별 html 파일.
  - **Synergy Chess** (`support-chess.html`) — 기물 배치 및 인접 기물에 따라 행마가 강화되는 변형 체스.
  - **Pirate Chess** (`pirate-chess.html`) — 바다/육지 타일 속성에 따라 기물 행마가 달라지는 변형 체스.
  - **Demotion Chess** (`demotion-chess.html`) — 승급이 아닌 강급 개념을 적용한 변형 체스. 6x6(기본)/8x8(확장) 두 버전.
  - **Stack & Seal** (`stack-and-seal.html`) — 현실 보드게임에 대응되지 않는, 이셰노이 비나만의 독창적인 게임.
- `info.html` — 세계관 소개 및 게임별 설명을 담은 About 페이지. 허브 하단 "Info → About"으로 접근.
- `assets/` — 로고 SVG 등 정적 리소스.

## 기술 노트

- 공용 AI: negamax + 알파베타 가지치기 기반의 고정 깊이(4/5) 정적 탐색, 3초 제한. 각 게임 html에 개별 구현.
- 허브와 게임은 `<iframe>` + `postMessage`로 통신(테마 동기화, 높이 자동 조절, 모달 열림 시 배경 딤 처리 등).
- 테마 값은 `localStorage`(`newchess-theme`)로 허브·게임 전체가 공유.

## 라이선스

© 2022–2026 월기. [CC BY-ND 3.0](https://creativecommons.org/licenses/by-nd/3.0/)으로 배포됩니다. 자세한 내용과 세계관 설명은 사이트 내 [About 페이지](https://wo1g1.github.io/NewChess/info.html)를 참고하세요.
