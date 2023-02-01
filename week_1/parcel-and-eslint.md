# 🟡 Parcel\&EsLint

## Parcel

- 빌드 툴
- 자바스크립트로 변환해 주는 것도 포함
- SWC 라는 컴파일러를 사용해서 아주 빠르다.
- Vite도 매우 빠르다.
- <mark style="color:red;">`package.json`</mark>에 <mark style="color:red;">`"source":"./index.html"`</mark> 속성추가
- 만약에 이거 하기 싫으면

```
  npx parcel index.html --port 8080
```

PORT 만 잡아주고 싶으면 저 위에 속성 추가하고

```
  npx parcel --port 8080
```

- static file 처리하는 방법

```
static 파일 사용가능 모듈 설치

npm i -D parcel-reporter-static-files-copy

설정파일 생성

touch .parcelrc

설정
{
  "extends": ["@parcel/config-default"],
  "reporters":  ["...", "parcel-reporter-static-files-copy"]
}
```

- 빌드하고(dist 한번 지우고 빌드)

```
빌드
npx parcel build

빌드한거 실행
npx servor ./dist
```

# ESLint

- 스타일
- 문제 발견
- 좋은 습관
  vscode extension 으로 eslint 설치
  <mark style="color:red;">`.vscode/setting.json`</mark>

```
{
    "editor.codeActionsOnSave": {
        "source.fixAll.eslint": true
    }
}
```

저장시 자동으로 변경

컬럼 줄긋는거
<mark style="color:red;">`"editor.rulers":[80]`</mark>

vscode extension 으로 Trailing Spaces 설치
빈칸 없애는거

<mark style="color:red;">`"trailing-spaces.highlightCurrentLine": true`</mark>

## 이러한 세팅들을 바닥부터 만드는거를 추천!
