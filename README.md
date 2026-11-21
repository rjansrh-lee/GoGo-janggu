# 정복실과 Go! Go! 장구 — 홈페이지

공개 주소: https://rjansrh-lee.github.io/GoGo-janggu/ (저장소 `rjansrh-lee/GoGo-janggu`, `main` 브랜치, GitHub Pages)

`sites/gogo-janggu/` 폴더 구성

| 파일 | 설명 |
| --- | --- |
| `index.html` | 홈페이지 본체(공개용). 이미지·영상 외에는 이 파일 하나로 동작합니다. |
| `hero.jpg` | 첫 화면 큰 배너 (1600×901, 약 375KB) — 2026.10.23 제30회 양서면민의 날 야외 특설무대 실제 공연 사진 |
| `teacher.jpg` | 소개 섹션 선생님 사진 (1000×1503, 약 217KB) — 실제 무대 사진, 4:5 프레임 |
| `stage-yangseo-1.jpg` | 사진첩 1 — 제30회 양서면민의 날 기념식 (1400×788, 약 300KB) |
| `poster-semiwon.jpg` | 사진첩 2 — 제14회 경기정원문화박람회 포스터 (1200×1607, 약 294KB) |
| `stage-yangseo-2.jpg` | 사진첩 3 — 신명 나는 합동 무대 (1400×788, 약 297KB). 공연 영상 썸네일로도 씀 |
| `performance.mp4` | 공연 현장 영상 (57.5MB, 4분 00초, H.264 1280×720, fast-start) |
| `hero.png` · `stage.png` · `stage.jpg` | 예전 예시 그림 원본·경량본 (보관용, 배포하지 않음) |
| `live-v3-top.png` · `live-v3-teacher.png` · `live-v3-gallery.png` | 공개 주소에서 찍은 휴대폰(390px) 확인 화면 — 첫 화면 / 선생님 사진 / 사진첩 |
| `live-v4-schedule.png` · `live-v5-prep.png` · `live-v5-notice.png` | 공개 주소 휴대폰(390px) 확인 화면 — 시간표 확정 / 준비물(정규반 카드) / 준비물(공지 카드) |
| `preview-mobile.png` · `preview-desktop.png` | 로컬 파일 전체 화면 미리보기 (2026-11-21 최신판) |
| `mobile-top.png` · `mobile-mid.png` · `mobile-contact.png` | 휴대폰 화면 크기(390×844) 미리보기 — 첫 화면 / 강습 카드 / 문의 카드 |
| `render.py` | 미리보기 그림을 다시 만드는 스크립트 |
| `robots.txt` | 검색 로봇 수집 허용 안내 + 사이트맵 위치 (검색 등록용) |
| `sitemap.xml` | 검색엔진에 알려 줄 페이지 목록 (공개 주소 1개, `lastmod` 2026-11-22) |

## 2026-11-22 구글 서치 콘솔 소유 확인 태그

- **`index.html` `<head>`에 구글 소유 확인 태그 추가** — `robots`·`canonical` 바로 옆에 넣었습니다. 페이지 내용·스타일은 그대로입니다.
  `<meta name="google-site-verification" content="UFighGm5P3bdWKKVAkvUtip8eMCYNG3AZTnpkNYDaQM">`
- 구글 서치 콘솔에서 `https://rjansrh-lee.github.io/GoGo-janggu/` 를 "URL 접두어" 방식으로 소유 확인할 때 쓰는 값입니다.
  태그를 지우거나 content 값을 바꾸면 소유 확인이 해제될 수 있으니 그대로 두세요.

## 2026-11-22 검색 등록용 파일 추가

- **`index.html` `<head>`에 검색·공유용 태그 추가** — 페이지 내용·스타일·확정된 시간표는 그대로 두고 메타 태그만 넣었습니다.
  - `canonical` = `https://rjansrh-lee.github.io/GoGo-janggu/`, `robots` = `index, follow`
  - Open Graph: `og:type`(website), `og:locale`(ko_KR), `og:site_name`, `og:title`, `og:description`,
    `og:url`, `og:image`(`hero.jpg`, 1600×901), `og:image:width`/`og:image:height`, `og:image:alt`
  - Twitter 카드: `summary_large_image` + `twitter:title`/`description`/`image`
  - 구조화 데이터(JSON-LD) 1개 — `EducationalOrganization`(이름·주소·전화·지역·수상). 기존에 JSON-LD는 없었습니다.
- **`robots.txt`** — 모든 검색 로봇 허용, 사이트맵 주소 안내.
- **`sitemap.xml`** — 공개 주소 1개(`changefreq` weekly, `priority` 1.0). 내용이 바뀌면 `<lastmod>`를 그날 날짜로 고칩니다.
- 확인: `grep -c 1945 index.html` → 0건 유지, JSON-LD `json.loads` 통과, `sitemap.xml` XML 파싱 통과.
- 검색 등록: 네이버 서치어드바이저·구글 서치 콘솔에서 `https://rjansrh-lee.github.io/GoGo-janggu/sitemap.xml`을
  사이트맵으로 제출하고 소유 확인을 하면 수집이 빨라집니다(소유 확인은 직접 로그인 필요).

## 2026-11-21 저녁 배포본 (커밋 `a18a33f`) — 개인 장구·채 지참 안내

- **준비물 안내 수정** — 수업장에 장구·채가 갖춰져 있다는 표현을 모두 걷어내고, 회원이 개인 장구와 채를
  챙겨 오는 것으로 바꿨습니다. 수업장 여유분이 많지 않아 장구가 없으면 미리 문의하도록 안내합니다.
- 정규반 카드 `준비물`: `개인 장구·채, 편한 옷과 신발, 물` + `수업장에 여유분 장구·채가 많지 않아 개인 장구를 사용합니다. 장구가 없으신 분은 미리 문의해 주세요.` (`예시` 배지 제거)
- 공지 카드 `수업 준비물 안내`: `개인 장구와 채, 편한 옷과 신발, 물을 챙겨 오시면 됩니다. 수업장에 여유분이 많지 않으니 장구가 없으신 분은 오시기 전에 미리 문의해 주세요.`
- 확인: `grep -c 준비되어 index.html` → 0건. 공개 주소 휴대폰 390px 화면은
  `live-v5-prep.png`(정규반 카드), `live-v5-notice.png`(공지 카드).

## 2026-11-21 오후 배포본 (커밋 `c4a6f70`, `ce06f00`, `e86afe6`)

- **시간표 확정 반영** — 양서주민자치센터 정규반 `요일·시간`을 `매주 화·금 오후 1:00 ~ 3:00`으로 확정해
  `확인 후 확정 예정` 배지를 지우고 `확정된 시간표입니다.`로 바꿨습니다(커밋 `e86afe6`). 확인은
  `live-v4-schedule.png`(공개 주소 휴대폰 390px). 개인 강습·공지의 `예시` 표시는 그대로 두었습니다.

- **실제 사진 반영** — 첫 화면 배경, 소개 섹션 선생님 사진, 사진첩 3장을 실제 공연 사진으로 교체.
  `예시 이미지` 배지, `사진 준비 중`, `공연 사진 추가 예정` 자리를 모두 없앴습니다.
  첫 화면 사진 위에서도 흰 제목이 또렷하도록 스크림(어두운 그라데이션)을 보강했습니다(모바일·데스크톱).
- **선생님 사진** — 4:5 프레임, `object-position: center 15%`로 얼굴이 잘 보이게 잡았습니다.
  캡션은 `정복실 선생님 · 현역 고고장구 강사` (출생연도·나이 표기 없음).
- **포스터 카드** — 세로 포스터라 `object-fit: contain` + 크림색(`#f6ebd8`) 배경으로 글자가 잘리지 않게 했습니다.
  카드 오른쪽 위 `크게` 표시를 누르면 원본 크기(`poster-semiwon.jpg`)가 새 창에서 열립니다.
- **공연 현장 영상** — 사진첩 아래 `#performance-video` 카드에 `performance.mp4` 추가
  (poster `stage-yangseo-2.jpg`, `preload="metadata"`). 공지 카드의 비활성 `영상 보기 (준비 중)` 버튼은
  `공연 영상 보러 가기` 링크로 바꿔 이 카드로 이동합니다.
- **출생연도 문구 제거 확인** — `grep -i 1945 index.html` 결과 0건(커밋 `b59bd26`에서 제거한 것 유지).

## 이전 배포본(2026-11-21 오전)에 반영된 내용

- 출생연도 문구 제거(메타 설명·첫 화면 소개·소개 섹션·배지), 수상 카드 추가(2026-11-07 양평군 주민자치센터
  문화프로그램 경연대회 양서면 ‘복실언니와 신바람 고고장구’ 팀 우수상, 보도 기사 링크),
  이미지 경량화, 공개용 문구 정리, 제목 자간 보정.

## 실제 정보로 바꿀 곳 (index.html 안에서 아래 문구를 찾아 수정)

1. **수업 요일·시간** — 2026-11-21에 `매주 화·금 오후 1:00 ~ 3:00`으로 확정해 `확인 후 확정 예정` 표시를
   지웠습니다. 시간이 다시 바뀌면 `index.html`의 `매주 화·금 오후 1:00 ~ 3:00`을 찾아 함께 고칩니다.
2. **준비물·수강 신청** — 준비물은 2026-11-21에 `개인 장구·채, 편한 옷과 신발, 물`(개인 지참, 여유분 적음·미리 문의)으로
   확정했습니다. `index.html`에서 `개인 장구·채`와 `개인 장구와 채` 두 곳을 찾아 함께 고치고, 수강 신청은
   `주민자치센터 프로그램 접수 기간에 신청` 부분을 봅니다.
3. **개인 강습** — `평일·주말 협의`, `협의 — 연습실 또는 방문`, `인원·횟수에 따라 협의`.
4. **연락처** — `010-5412-7183` 이 이미 `tel:`/`sms:` 링크로 연결되어 있습니다. 번호를 바꿀 때는
   `tel:01054127183`, `sms:01054127183`, 화면에 보이는 숫자 세 곳(문의 칸 큰 번호·강습 카드 아래 문구·푸터)을 함께 고칩니다.
5. **이달 공연 일정** — `예: 12월 6일(토) 양서면 마을축제` 부분.
6. **사진·영상 교체** — 사진첩은 `.gallery` 안 `figure.shot` 세 개, 영상은 `#performance-video` 카드입니다.
   같은 파일 이름으로 바꿔 넣으면 나머지 코드는 그대로 둬도 됩니다.

확인된 실제 정보로 넣어 둔 것: 양서면 주민자치센터 주소 `경기도 양평군 양서면 양수로 110`,
센터 대표번호 `031-772-3782` (양서면 주민자치센터 안내 기준. 강습 문의 번호가 아닙니다.),
강사 연락처 `010-5412-7183` (전화 `tel:` · 문자 `sms:` 링크로 연결), 2026-11-07 경연대회 우수상 수상.

## 미리보기 다시 만들기

```bash
export PATH=$PATH:/workspace/.local/bin
export PLAYWRIGHT_BROWSERS_PATH=/workspace/.playwright
export TMPDIR=/workspace/tmpdir
export LD_LIBRARY_PATH=/workspace/syslibs/root/usr/lib/x86_64-linux-gnu
cd /workspace/sites/gogo-janggu && python3 render.py
```

## 배포하기

```bash
cd /workspace/tmpdir/gogo_deploy            # 저장소 복제본
cp /workspace/sites/gogo-janggu/index.html /workspace/sites/gogo-janggu/robots.txt /workspace/sites/gogo-janggu/sitemap.xml .
cp /workspace/sites/gogo-janggu/*.jpg /workspace/sites/gogo-janggu/performance.mp4 .
git add -A && git commit -m "..." && git push origin main
gh api repos/rjansrh-lee/GoGo-janggu/pages/builds/latest --jq '.commit,.status'   # built 확인
```

`performance.mp4`(57.5MB)는 GitHub 권장 50MB를 넘어 push할 때 경고가 뜨지만, 100MB 하드 리밋 아래라 그대로 올라갑니다.
