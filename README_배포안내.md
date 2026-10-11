# 월요일에 우리, 월미도! — GitHub Pages 배포 및 수정 안내

행사일: 2026년 10월 12일

## 1. 구성 파일

| 이름 | 용도 | 수정 빈도 |
|---|---|---|
| `index.html` | 참가자가 카카오톡 링크로 여는 모바일 미션지 | 최초 배포 뒤 거의 수정하지 않음 |
| `editor.html` | 운영진이 한글 입력칸으로 행사 정보를 변경하는 편집 화면 | 수정할 때 사용 |
| `settings.js` | 장소·시간·공지·필수 미션 개수·28개 미션 등의 설정 | **내용을 바꿀 때 교체하는 파일** |
| `assets/park-map.webp` | 월미공원 산책로 안내도 | 지도 교체 시 |
| `assets/attractions-map.webp` | 월미공원 8경·나무9경 안내도 | 지도 교체 시 |
| `assets/kakao-preview.png` | 카카오톡 공유 미리보기용 자체 제작 이미지 | 특별한 경우만 |
| `.nojekyll` | GitHub Pages 정적 파일 배포용 | 수정하지 않음 |

> 참가자 명단, 연락처, 사진과 법인카드 정보는 넣지 않았습니다. GitHub 공개 저장소에 개인 정보를 올리지 마세요.

## 2. GitHub Pages 최초 공개 (PC 기준)

1. [GitHub](https://github.com/new)에서 새 저장소를 만듭니다. 저장소명 예: `wolmido-mission-2026`, 공개 범위 **Public**. 빈 저장소라면 `README` 자동 추가 여부는 무관합니다.
2. 이 ZIP을 압축 해제합니다. **압축파일 자체를 GitHub에 올리지 말고**, 안에 있는 `index.html`, `editor.html`, `settings.js`, `.nojekyll`, `assets` 폴더를 저장소의 **최상위 폴더**에 업로드합니다. (저장소 > Add file > Upload files > Commit changes)
3. 저장소에서 `Settings` > `Pages` > `Build and deployment`를 엽니다. `Source`: **Deploy from a branch**, `Branch`: **main**, 폴더: **/(root)**를 선택하고 저장합니다.
4. 배포가 완료되면 GitHub Pages 주소를 엽니다. 예: `https://내계정.github.io/wolmido-mission-2026/`.
5. 카카오톡에서 링크를 직접 열어 제목·지도·코스 4개·미션 28개가 정상 출력되는지 확인합니다.

실제 GitHub Pages 주소는 사용자 계정명과 저장소명에 따라 달라집니다. **이 ZIP 자체는 웹에 게시되지 않았습니다.**

## 3. 카카오톡으로 배포할 주소

- 전체 코스 선택: `https://내계정.github.io/wolmido-mission-2026/`
- 1코스 전통정원: 위 주소에 `?course=1` 추가
- 2코스 월미산: 위 주소에 `?course=2` 추가
- 3코스 유람선: 위 주소에 `?course=3` 추가
- 4코스 등대: 위 주소에 `?course=4` 추가

코스 추첨 전에 전체 주소 하나를 전달해도 됩니다. 참가자는 화면에서 코스를 선택하고 미션을 고릅니다. **선택 내역은 해당 휴대폰에만 저장**되며, 사진 업로드나 운영진 자동 채점 기능은 없습니다.

## 4. 장소·시간·미션 개수·문구를 수정하는 방법

1. 운영진 편집 화면을 엽니다: `https://내계정.github.io/wolmido-mission-2026/editor.html`.
2. 한글 입력칸에서 집결 장소·시간, 미션 개수(1~7개), 미션명·성공 조건, 공지 문구 등을 수정합니다.
3. 아래의 **설정 코드 복사** 버튼을 누릅니다. 설정을 검증한 뒤 `settings.js` 전체 내용을 복사합니다. 모바일 기기에서 복사가 차단되면 **설정 파일 다운로드**를 사용합니다.
4. 같은 화면의 **GitHub 파일 편집** 버튼을 눌러 로그인된 GitHub의 `settings.js` 편집 화면으로 이동합니다. 저장소 계정명이 자동 인식되지 않으면 `계정명/저장소명`을 한 번 입력합니다.
5. 기존 내용을 모두 선택해 새 코드로 바꾸고 **Commit changes**를 누릅니다.
6. 참가자들은 **기존 링크 그대로** 새로고침하면 수정된 내용을 볼 수 있습니다. 배포 갱신에 다소 시간이 걸릴 수 있습니다.

**중요:** 편집 화면의 입력만으로 홈페이지가 곧바로 수정되지는 않습니다. 누구나 이 화면을 열 수 있지만, GitHub 저장소에 커밋할 수 있는 권한이 있어야 실제 수정됩니다. 접속 암호나 개인 GitHub 토큰을 이 사이트에 입력하는 기능은 없습니다.

## 5. 카카오톡 미리보기 이미지 (최초 1회 설정 권장)

GitHub 주소가 정해지면 `index.html`에 있는 아래 줄의 `content` 값을 **배포된 이미지의 완전한 HTTPS 주소**로 바꾸면 미리보기가 더 안정적입니다.

```html
<meta property="og:image" content="https://내계정.github.io/wolmido-mission-2026/assets/kakao-preview.png">
```

배포 후 카카오톡 링크 미리보기가 바로 갱신되지 않는다면, 카카오 디벨로퍼스의 **카카오톡 URL 메타데이터(OG) 관리 도구**에서 해당 주소의 캐시를 초기화할 수 있습니다.

행사 *시간·장소*는 방문자가 페이지를 열어야 최신 내용을 확인할 수 있습니다. 카카오톡 미리보기 문구는 정적 HTML에 있으므로 `settings.js` 변경과 자동 연동되지 않습니다. 따라서 미리보기에 구체적인 집결시각을 넣지 않았습니다.

## 6. 행사 실무 주의사항

- 현재 필수 미션은 코스별 7개 중 **3개**, 성공 1개당 10점입니다. 필수 미션 수를 4개로 바꾸면 코스 점수의 최대치가 30점에서 40점으로 변하므로 **엑셀 운영시트 배점도 조정**해야 합니다.
- 지도 이미지의 저작권·공개 재배포 조건을 확인한 뒤 외부 공개하세요. 자료 제공자가 공개 재배포 권리를 보유하지 않았다면 `assets` 지도 파일을 공개하지 말고 지도 원문 링크로 대체해야 합니다.
- 집결 시간이나 장소를 당일 변경할 경우에는 **홈페이지 수정과 별개로 카카오톡 단톡방에도 직접 공지**하세요. 참가자들은 페이지를 새로고침하기 전까지 바뀐 내용을 알지 못할 수 있습니다.
- 위급한 상황은 웹페이지를 거치지 말고 팀 리더 또는 운영진에게 바로 연락하도록 안내하세요.

## 7. 문제 해결

- **지도가 보이지 않음:** `assets` 폴더가 `index.html`과 같은 저장소 루트에 업로드되었는지 확인. `assets/park-map.webp`, `assets/attractions-map.webp` 주소를 직접 열어 확인.
- **수정했는데 옛 시간이 표시됨:** 커밋 여부 및 GitHub Pages 배포 완료 여부를 확인하고 페이지에서 새로고침. 사이트는 접속할 때마다 `settings.js`를 새 주소로 불러와 캐시를 회피합니다.
- **편집 화면에서 수정이 사라짐:** '임시 수정본 복원' 버튼을 눌러 해당 브라우저의 편집 내용을 불러옵니다.
- **GitHub 편집 버튼이 엉뚱한 저장소를 엶:** 편집 화면 맨 아래의 `계정명/저장소명`을 정확하게 입력합니다.

공식 문서: [GitHub Pages 게시 설정](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site), [GitHub 파일 편집](https://docs.github.com/en/repositories/working-with-files/managing-files/editing-files), [카카오 디벨로퍼스 OG 관리](https://developers.kakao.com/docs/en/tool/common).
