# CSV Explore Gallery — 확장판

Midjourney Explore의 탐색 UX를 참고한 독립형 CSV 이미지 갤러리입니다. 특정 서비스의 UI/코드를 복제하지 않고 비슷한 탐색 경험을 구현했습니다.

## 실행

VS Code Live Server 또는 Python 웹서버를 권장합니다.

```bash
python -m http.server 8000
```

브라우저에서 `http://localhost:8000` 접속.

> `images.csv`는 페이지 로드 시 자동으로 읽습니다. 브라우저의 파일 선택/드래그앤드롭으로 다른 CSV를 즉시 교체할 수도 있습니다.

## CSV 형식

```csv
id,image_url,title,prompt,author,likes,type,created_at,tags
1,images/001.jpg,Mountain Lake,cinematic mountain lake,user01,128,image,2026-09-18,nature|cinematic|landscape
2,images/002.jpg,Robot,humanoid robot portrait,user02,302,image,2026-09-17,robot|ai
```

### 지원 컬럼
- `image_url` / `image` / `url` : 이미지 URL 또는 상대경로
- `video_url` : 동영상 URL
- `thumbnail_url` : 동영상/이미지 썸네일
- `title` / `name`
- `prompt` / `description`
- `author` / `username` / `user`
- `likes` / `like_count`
- `type` : `image` 또는 `video`
- `created_at` / `date`
- `tags` / `tag` : `|` 또는 `;`로 여러 태그 지정

## 확장 기능

- `images.csv` 자동 로딩
- CSV 파일 선택 / 드래그앤드롭
- Masonry 방식 이미지 배치
- 이미지 원본 비율 유지
- Top Day / Likes / Latest 정렬
- All / Images / Videos 필터
- 제목 / 프롬프트 / 작성자 / 태그 검색
- 태그 필터
- 좋아요 및 좋아요 목록(localStorage)
- 이미지/동영상 상세 모달
- 프롬프트 복사
- 원본 열기
- 무한 스크롤 방식 추가 로딩
- 반응형 화면
- 2~7열 밀도 조절
- 간격 조절
- 다크/라이트 테마
- 키보드 `/` 검색, `Esc` 모달 닫기
- 모바일 대응

## 로컬 이미지

프로젝트 아래에 이미지 폴더를 만들고 상대경로를 사용합니다.

```text
project/
├─ index.html
├─ app.js
├─ style.css
├─ images.csv
└─ images/
   ├─ 001.jpg
   └─ 002.jpg
```

CSV:

```csv
1,images/001.jpg,My Image,my prompt,user,50,image,2026-09-18,ai|test
```

브라우저 보안 때문에 `file:///C:/...` 형태의 임의 PC 경로는 사용하지 말고 웹서버를 통해 실행하세요.
