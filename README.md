# kurimanju

가을 숲속 공터를 쿠리만주들이 돌아다니는 3D 웹페이지예요. 빌드 과정 없이 `index.html` 하나로 돌아가고, three.js(r128)는 cdnjs에서 불러와요.

## 실행

`index.html`을 브라우저로 열거나, 아무 정적 서버로 띄우면 돼요.

```bash
npx serve .
```

## 기능

- 쿠리만주 다섯 버전: 기본, 캔음료, 레모네이드, 밤만쥬 먹기, 소시지
- 오른쪽 아래 아이콘으로 낮 / 노을 / 밤 전환 (밤에는 가로등과 반딧불이)
- `+` 버튼으로 쿠리만주 추가 (내 화면에서만)
- 화면을 드래그하면 둘러보기

## 접속한 사람마다 쿠리만주 늘리기

지금 페이지를 열어 둔 사람마다 쿠리만주가 한 마리씩 같은 숲에 나타나고, 나가면 사라져요.
서버 코드나 데이터베이스 없이 Supabase Realtime(presence)만 써요. 무료 요금제로 충분해요.

1. [supabase.com](https://supabase.com)에서 무료 프로젝트를 만들어요.
2. Project Settings > API에서 `Project URL`과 `anon public` 키를 복사해요. anon 키는 브라우저에 공개해도 되는 키예요.
3. `index.html`에서 아래 줄을 찾아 두 값을 채워요.

```js
const KURI_ONLINE = { url: '', anonKey: '' };
```

값을 비워 두면 혼자 보는 모드로 동작해요. claude.ai 아티팩트 안에서 열 때는 이 설정 없이도 같이 보여요.

## 배포 (GitHub Pages)

저장소 Settings > Pages에서 배포할 브랜치와 `/ (root)` 폴더를 고르면 `https://scrawl-labs.github.io/kurimanju/` 주소로 열려요.
