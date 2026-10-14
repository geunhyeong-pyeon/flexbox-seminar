# Flexbox 딥다이브 — 세미나 라이브 데모

CSS Flexbox 세미나에서 라이브로 시연하기 위한 인터랙티브 플레이그라운드.

## 실행

빌드/설치 없음. `index.html`을 브라우저로 열면 끝.

```bash
open index.html
```

## 데모 구성 (발표 순서)

1. **축 플레이그라운드** — flex-direction / justify-content / align-items / gap을 버튼으로 전환, 적용 CSS 실시간 표시. 하단 서브 데모 3종: "flex item은 직계 자식만"(손자의 flex: 1 무시 재현 + 중첩 flex 토글), "stretch는 auto일 때만"(명시적 height / max-height 비교), "img 비율 깨짐"(stretch로 원→타원, align-self·래퍼 해결 비교)
2. **flex-wrap** — 컨테이너를 드래그로 리사이즈하며 nowrap vs wrap 비교
3. **flex-grow × flex-basis** — 아이템별 grow/basis 값을 바꾸고 컨테이너를 리사이즈하면 free space 계산 과정(`아이템 = basis + free × growᵢ/Σgrow`)이 실시간으로 표시됨. free space가 음수가 되면 shrink로 전환된다는 안내 포함. 하단에 basis·width·min/max 3단계 파이프라인, "basis가 있으면 width 무시" 비교, max-width 동결(freeze)·재분배 토글 데모
4. **flex 단축형** — flex: 1 vs flex-grow: 1 비교 + 단축형 4종(initial/1/auto/none)을 같은 콘텐츠로 한 화면에서 리사이즈 비교
5. **flex-shrink** — 아바타 찌그러짐 재현(shrink: 0 토글) + shrink 가중치 실험(아이템별 shrink 값 변경, 실시간 너비 표시로 `줄어드는 양 ∝ shrink × basis` 확인)
6. **min-width/min-height: auto 함정** — ellipsis가 안 먹는 버그 재현(min-w-0 토글) + 같은 함정의 세 가지 증상 비교(조상 overflow가 visible이면 이웃 위로 겹침, auto면 가로 스크롤, hidden이면 말줄임 없이 잘림 — 토글 하나로 전부 해결) + column 고정 높이 레이아웃에서 내부 스크롤이 안 생기는 버그 재현(min-h-0 토글, footer 밀려남 확인) + 번외: h-full이 무시되는 이유(html/body 퍼센트 height 체인 — 무시/고정값/체인 복구 3단 비교)
7. **margin: auto** — 내비게이션 "여기부터 오른쪽 끝으로" 토글
8. **order·reverse 접근성** — 4개 버튼을 normal / row-reverse / order: 99로 전환하고 Tab을 누르면 포커스 순서가 시각 순서와 어긋나는 것을 실시간 포커스 로그로 확인
9. **실전 패턴** — sticky footer, 고정 사이드바, 반응형 카드 랩

세미나 문서(개념/계산 알고리즘/퀴즈)는 Notion 페이지 참고.