# 크리스탈 공원

포르투 크리스탈 공원을 닮은 3D 힐링 산책 공원이에요. 링크만 열면 누구나 함께 걸으며 대화하고, 새들에게 모이를 줄 수 있어요.

## 1. Supabase 준비 (함께 걷기용, 약 5분)

1. https://supabase.com 에 가입하고 **New project**를 만들어요. (무료 플랜이면 충분해요)
2. 프로젝트가 만들어지면 **Project Settings → API Keys**(또는 **Data API**)로 가서 두 가지를 복사해요.
   - **Project URL**: `https://xxxx.supabase.co`
   - **Publishable key** (`sb_publishable_...`) 또는 **anon public** 키
3. `config.js`를 열어 복사한 값을 넣어요.

```js
window.PARK_CONFIG = {
  supabaseUrl: 'https://xxxx.supabase.co',
  supabaseKey: 'sb_publishable_xxxx',
  roomName: 'crystal-park'
};
```

- 이 키는 웹페이지에 공개되도록 만들어진 키라 GitHub에 올려도 괜찮아요.
- **secret / service_role 키는 절대 넣지 마세요.**
- Realtime 설정에서 public 채널 접근이 막혀 있으면 연결되지 않아요. (**Realtime → Settings**에서 "Allow public access"가 켜져 있는지 확인)
- 데이터베이스 테이블은 만들 필요가 없어요. 위치·대화는 실시간으로만 오가고 저장되지 않아요.

`config.js`를 비워 두면 혼자 산책하는 모드로 열려요.

## 2. GitHub Pages에 올리기

1. GitHub에서 새 저장소를 만들어요. 예: `crystal-park` (Public)
2. 이 폴더의 파일을 모두 올려요: `index.html`, `config.js`, `.nojekyll`, `README.md`
   - 웹에서 올릴 때: 저장소 → **Add file → Upload files** → 파일 끌어다 놓기 → **Commit changes**
   - `.nojekyll`은 숨김 파일이라 안 보이면 빼도 괜찮아요.
3. 저장소 → **Settings → Pages** → Source를 **Deploy from a branch**, Branch를 `main` / `/(root)`로 두고 **Save**
4. 1~2분 뒤 `https://<내 아이디>.github.io/crystal-park/` 주소가 생겨요. 이 링크를 친구에게 보내면 끝!

## 알아 둘 점

- 로그인이 없어서 링크를 아는 사람은 누구나 들어올 수 있어요. 다른 방을 쓰고 싶으면 `roomName`을 바꾸세요.
- Supabase 무료 플랜: 동시 접속 200명, 월 메시지 200만 건 정도까지 여유 있어요.
- 무료 프로젝트를 오래(약 1주) 쓰지 않으면 일시 정지돼요. Supabase 대시보드에서 **Restore**를 누르면 다시 켜져요.

## 조작법

| 키 | 동작 |
|---|---|
| WASD / 방향키 | 이동 (Shift: 달리기) |
| 마우스 드래그 / 휠 | 시점 회전 / 확대 |
| Enter | 대화 |
| 1 2 3 4 5 | 손 흔들기 · 점프 · 하트 · 춤 · 비눗방울 |
| E | 상황별 행동: NPC와 대화 · 망원경 · 서가 둘러보기 · 앉기 |
| Q | 부탁 수첩 (NPC 퀘스트) |
| T | 공원 문고에서 책 읽기 (←/→ 쪽 넘기기) |
| L | 등불 들기 |
| F | 모이 뿌리기 |
| R | 분수에 소원 동전 (연못 근처) |
| P | 사진 찍기 |
| Tab | 공원에 있는 사람 목록 · 따라가기 |
| B | 새 친구 도감 |
| Esc | 열린 창 닫기 |

## 공원 지도

- 가운데: 돔, 장미 정원, 분수 연못, 보리수 길, 전망 테라스
- 서쪽 정원 문 너머: 책방 거리와 렐루 서점 (책을 빌려 가방에 담아요)
- 동쪽: 피크닉 잔디밭, 작은 유리 온실, 도우루 강 전망 데크와 망원경

## 시간

공원의 하루는 20분이에요(아침 → 낮 → 노을 → 밤). 모두 같은 시계를 써서 친구와 같은 하늘을 봐요. 오른쪽 위 시계 버튼을 누르면 내 화면만 낮·노을·밤·아침으로 고정할 수 있어요.
