# 교외체험학습 결과보고서 작성 페이지

「학교장 허가 교외체험학습」 결과보고서를 웹에서 작성하고 PDF로 저장하는 페이지입니다.
학생이 기본 정보, 일자별 체험 내용, 증빙 사진을 입력하면 원본 양식과 같은 배치의 A4 PDF가 만들어집니다.

## 파일 구성

```
index.html                  페이지 전체 (화면, 양식, PDF 생성 코드)
vendor/html2canvas.min.js   양식을 이미지로 그리는 라이브러리 (MIT)
vendor/jspdf.umd.min.js     PDF 파일을 만드는 라이브러리 (MIT)
.nojekyll                   GitHub Pages가 파일을 그대로 쓰도록 하는 빈 파일
```

라이브러리를 저장소 안에 함께 두었기 때문에, 외부 CDN이 막힌 학교 네트워크에서도 PDF 저장이 동작합니다.

## GitHub Pages로 배포하기

1. GitHub에서 새 저장소를 만듭니다. (예: `trip-report`, **Public**)
2. 저장소 화면에서 **Add file → Upload files**를 누르고, 이 폴더의 파일과 `vendor` 폴더를 통째로 끌어다 놓은 뒤 **Commit changes**를 누릅니다.
3. **Settings → Pages**로 이동합니다.
4. **Build and deployment**의 Source를 **Deploy from a branch**로, Branch를 **main / (root)**로 고르고 **Save**를 누릅니다.
5. 1~2분 뒤 같은 화면 위쪽에 주소가 나타납니다.
   `https://<GitHub 아이디>.github.io/trip-report/`
6. 이 주소를 학생들에게 공유합니다.

> `.nojekyll`은 이름이 점(.)으로 시작해서 업로드 창에서 안 보일 수 있습니다. 빠져도 동작에는 문제없습니다.

## 학교 이름 바꾸기

`index.html`에서 아래 줄을 찾아 학교 이름을 고치면, 양식 하단의 "○○○장 귀하"가 바뀝니다.

```js
const SCHOOL = '문정여자고등학교장';
```

## 학생 안내용 메모

- 입력한 내용과 사진은 **학생 기기의 브라우저에만 자동 저장**되고, 서버로 전송되지 않습니다. 같은 기기·같은 브라우저로 다시 열면 이어서 쓸 수 있습니다.
- 내용이 첫 장(21줄)을 넘으면 **별지**가 자동으로 붙고, 사진은 한 쪽에 8장씩 들어갑니다.
- **제출일과 보호자·학생 서명**은 PDF를 인쇄한 뒤 직접 적습니다.
- 카카오톡 같은 앱 안에서 링크를 열면 PDF 저장이 안 될 수 있습니다. 페이지 위쪽 안내에 따라 기본 브라우저(크롬, 사파리 등)로 열어 주세요.
- 아이폰의 HEIC 사진이 안 올라가면 JPG로 바꿔서 올려 주세요.

## 라이선스

- html2canvas 1.4.1 — MIT License, © Niklas von Hertzen
- jsPDF 2.5.1 — MIT License, © James Hall, yWorks GmbH 외
