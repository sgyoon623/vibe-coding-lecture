# 교사를 위한 바이브코딩 첫걸음 — 배포용 폴더

이 폴더 하나를 Vercel에 올리면 두 페이지가 함께 배포됩니다.

| 주소 | 내용 |
|---|---|
| `https://(프로젝트 이름).vercel.app` | 강의 슬라이드 (22장, 마지막 1장은 선택용 보너스) |
| `https://(프로젝트 이름).vercel.app/helper` | 앱 만들기 프롬프트 도우미 |

슬라이드 17번의 QR코드와 주소는 `https://vibe-coding-lecture-bay.vercel.app/helper` 로 고정되어 있습니다. Vercel 주소를 바꾸면 index.html 안의 이 주소도 함께 바꿔야 합니다.

## 폴더 구성

```
vibe-coding-lecture/
├─ index.html        ← 강의 슬라이드
├─ helper/
│  └─ index.html     ← 프롬프트 도우미
├─ assets/
│  └─ qrcode.js      ← QR코드를 그려 주는 작은 프로그램 (MIT 라이선스)
└─ README.md         ← 지금 이 안내문
```

## 배포 방법 A — 터미널 없이 (GitHub + Vercel 웹)

1. **GitHub에 새 저장소 만들기**
   - github.com에 로그인 → 오른쪽 위 `+` → `New repository`
   - Repository name에 `vibe-coding-lecture` 입력 → `Create repository`
2. **파일 올리기**
   - 만들어진 저장소 화면에서 `uploading an existing file` 링크를 누릅니다.
   - 압축을 푼 `vibe-coding-lecture` 폴더 **안에 있는 것들**(index.html, helper 폴더, assets 폴더, README.md)을 한꺼번에 끌어다 놓습니다.
   - 아래 `Commit changes` 를 누릅니다.
3. **Vercel에서 가져오기**
   - vercel.com에 로그인 → `Add New…` → `Project`
   - 방금 만든 `vibe-coding-lecture` 저장소 옆 `Import`
   - Framework Preset은 `Other` 그대로 두고 `Deploy`
4. **확인**
   - 1분 정도 뒤 나오는 주소를 열면 슬라이드가 보입니다.
   - 주소 뒤에 `/helper` 를 붙여 휴대폰으로 열어 봅니다.
   - 슬라이드 17번의 QR코드를 휴대폰으로 찍어 도우미가 열리는지 확인합니다.

> 나중에 내용을 고치면 GitHub 저장소에 파일을 다시 올리기만 하면 Vercel이 자동으로 새로 배포합니다.

## 배포 방법 B — Vercel CLI를 써 본 경우

이 폴더에서 터미널을 열고 아래를 입력합니다.

```
npx vercel --prod
```

## 슬라이드 조작법

| 동작 | 방법 |
|---|---|
| 다음 / 이전 | → / ← 키, 스페이스바, 화면 오른쪽·왼쪽 클릭, 휴대폰은 좌우로 밀기 |
| 발표 메모 보기 | `N` 키 또는 아래 `발표 메모` 버튼 |
| 전체 화면 | `F` 키 또는 아래 `전체 화면` 버튼 |
| 특정 슬라이드 바로 열기 | 주소 끝에 `#slide-17` 처럼 번호 붙이기 |

## 주의

- 발표 메모는 페이지 안에 들어 있어서, 주소를 아는 사람은 메모를 볼 수 있습니다. 메모에 공개하기 어려운 내용이 있으면 배포 전에 지워 주세요.
- 프롬프트 도우미는 입력한 내용을 서버로 보내지 않습니다. 각자의 브라우저에만 임시로 저장됩니다.
