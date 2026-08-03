# 당구 게임 (4구 / 3쿠션)

Three.js + Rapier3D 기반 웹 당구 프로토타입입니다.  
CDN만 사용하므로 **빌드 없이** 정적 호스팅으로 배포할 수 있습니다.

## 로컬 실행

```bash
# 방법 1) 루트 index.html
npx --yes serve -p 8080 .

# 방법 2) public 폴더
cd public && python3 -m http.server 8080
```

브라우저: http://localhost:8080

## 기능

- 4구 / 3쿠션 모드
- 마우스 조준 + 드래그 파워
- 물리 엔진 (Rapier)
- 로컬 2인, 코인 토스 선공, 알(비드) 스코어
- 방 코드 · 승리 점수 설정 로비

## GitHub Pages 배포

### 1) 새 저장소 만들기

GitHub에서 빈 저장소를 생성합니다. 예: `billiards-game`

### 2) 코드 푸시

```bash
cd billiards-game
git init
git add index.html docs/ README.md .gitignore favicon.svg public/index.html
git commit -m "Deploy billiards game"
git branch -M main
git remote add origin https://github.com/YOUR_ID/billiards-game.git
git push -u origin main
```

### 3) Pages 설정

1. 저장소 **Settings → Pages**
2. **Source**: Deploy from a branch
3. **Branch**: `main` / 폴더 **`/docs`** (또는 `/ (root)` 후 루트 `index.html` 사용)
4. Save

몇 분 후 접속:

```
https://YOUR_ID.github.io/billiards-game/
```

`/docs`를 쓰면: `https://YOUR_ID.github.io/billiards-game/` 에 `docs/index.html`이 루트로 제공됩니다.

## 다음 단계 (온라인)

- Supabase Realtime으로 방 코드 기반 동기화
- Render / Supabase Edge로 매치메이킹

## 조작

| 조작 | 설명 |
|------|------|
| 큐볼 근처 클릭 후 드래그 | 조준 + 파워 |
| ESC | 충전 취소 |
| R | 공 리셋 |
| 드래그 / 휠 | 카메라 |
