# ๐ก Parcel\&EsLint

### Parcel

* ๋น๋ ํด
* ์๋ฐ์คํฌ๋ฆฝํธ๋ก ๋ณํํด ์ฃผ๋ ๊ฒ๋ ํฌํจ
* SWC ๋ผ๋ ์ปดํ์ผ๋ฌ๋ฅผ ์ฌ์ฉํด์ ์์ฃผ ๋น ๋ฅด๋ค.
* Vite๋ ๋งค์ฐ ๋น ๋ฅด๋ค.
* <mark style="color:red;">`package.json`</mark>์ <mark style="color:red;">`"source":"./index.html"`</mark> ์์ฑ์ถ๊ฐ
* ๋ง์ฝ์ ์ด๊ฑฐ ํ๊ธฐ ์ซ์ผ๋ฉด

```
  npx parcel index.html --port 8080
```

PORT ๋ง ์ก์์ฃผ๊ณ  ์ถ์ผ๋ฉด ์  ์์ ์์ฑ ์ถ๊ฐํ๊ณ 

```
  npx parcel --port 8080
```

* static file ์ฒ๋ฆฌํ๋ ๋ฐฉ๋ฒ

```
static ํ์ผ ์ฌ์ฉ๊ฐ๋ฅ ๋ชจ๋ ์ค์น

npm i -D parcel-reporter-static-files-copy

์ค์ ํ์ผ ์์ฑ

touch .parcelrc

์ค์ 
{
  "extends": ["@parcel/config-default"],
  "reporters":  ["...", "parcel-reporter-static-files-copy"]
}
```

* ๋น๋ํ๊ณ (dist ํ๋ฒ ์ง์ฐ๊ณ  ๋น๋)

```
๋น๋
npx parcel build

๋น๋ํ๊ฑฐ ์คํ
npx servor ./dist
```

* static file ์ฌ์ฉํ๊ธฐ ์ํด์

`npm i -D parcel-reporter-static-files-copy`

* `.parcelrc` ์์ฑ

```json
{
  "extends": ["@parcel/config-default"],
  "reporters":  ["...", "parcel-reporter-static-files-copy"]
}
```

* `static/images(ํด๋) ๋ฑ ์์ ํ์ผ ์ฌ์ฉ ๊ฐ๋ฅ`

## ESLint

* ์คํ์ผ
* ๋ฌธ์  ๋ฐ๊ฒฌ
* ์ข์ ์ต๊ด vscode extension ์ผ๋ก eslint ์ค์น <mark style="color:red;">`.vscode/setting.json`</mark>

```
{
    "editor.codeActionsOnSave": {
        "source.fixAll.eslint": true
    }
}
```

์ ์ฅ์ ์๋์ผ๋ก ๋ณ๊ฒฝ

์ปฌ๋ผ ์ค๊ธ๋๊ฑฐ <mark style="color:red;">`"editor.rulers":[80]`</mark>

vscode extension ์ผ๋ก Trailing Spaces ์ค์น ๋น์นธ ์์ ๋๊ฑฐ

<mark style="color:red;">`"trailing-spaces.highlightCurrentLine": true`</mark>

### ์ด๋ฌํ ์ธํ๋ค์ ๋ฐ๋ฅ๋ถํฐ ๋ง๋๋๊ฑฐ๋ฅผ ์ถ์ฒ!
