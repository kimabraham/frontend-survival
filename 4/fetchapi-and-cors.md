# ๐ข FetchAPI\&CORS

{% hint style="info" %}

{% endhint %}

* fetch return ๊ฐ Promise ๊ทธ๋์ await or .then()
* body ๊ฐ => Readerble Stream
* ๋ค๋ฅธ METHOD

```javascript
const response = await fetch(url, {
    method:'POST',
})
```

## CORS

* ์น๋ธ๋ผ์ฐ์ ๊ฐ ๊ฐ์ง๊ณ  ์๋ ๋ณด์
* ์น๋ธ๋ผ์ฐ์ ๊ฐ ํ์ฌ์ ์นํ์ด์ง๋ ๋ค๋ฅธ ์ถ์ฒ์ ๋ฐ์ดํฐ๋ฅผ ์ป์ด์ค๊ธด ํ์ง๋ง, ์ฌ์ฉํ์ง ๋ชปํ๋๋ก ๋ง๋๋ค. ๋ธ๋ผ์ฐ์  ๋จ์์ ๋ง๋๋ค๋ ๊ฒ์ ์์์ผ ํ๋ค.&#x20;
* REST API ์๋ฒ์์ Headers "Access-Control-Allow-Origin" ์์ฑ์ ์ถ๊ฐํ๋ฉด ๋๋ค. => ์ฌ๊ธฐ์์ ์์ฒญํ์ผ๋ฉด ๊ด์ฐฎ์ ๋ผ๋ ์๋ฏธ?

```bash
npm i cors
npm i -D @types/cors
```
