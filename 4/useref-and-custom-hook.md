# ๐ด useRef\&Custom Hook

{% hint style="info" %}
์ ๋ชจ๋ฅด๋ ๋ถ๋ถ ์์!!!
{% endhint %}

## useRef

* ์ปดํฌ๋ํธ ์์ ์ฃผ๊ธฐ ์ ์ฒด์ ๊ฑธ์ณ์ ์ ์ง๋๋ ๊ฐ์ฒด(ํ ... ์ปดํฌ๋ํธ๊ฐ ์์ด์ง๋๊น์ง ๋์ผํ ๊ฐ์ฒด๊ฐ ์ ์ง๋๋ค.) ์ํ๋ ์๊ด์์ด ์ ์งํ๊ณ  ์ถ๋ค.

```javascript
const ref = useRef(1);
ref.current += 1
์๋ current๊ฐ์ ๋นผ์จ๋ค.
```

* useState๋ ๋ญ๊ฐ ๋ค๋ฅด๋? ํด๋น ๋ฐ ํ์ ์ปดํฌ๋ํธ๋ฅผ ์ฌ๋ ๋๋ง ์ํ๋ค.
* ๋์ค์ ๋ ๋๋ง ๋ฌ์๋ ๊ทธ ๊ฐ์ด ๋์จ๋ค. ์ ๊ธฐ!
* ์ธ์ ์ฐ๋?
* input ๋ฑ์ ID
* state๋ฅผ ๋ณ๊ฒฝํ๋ฉด ์ฌ ๋ ๋๋ง ํ๋๊น ์ฌ๋ ๋๋ง์ด ํ์์๋ ๊ฐ์ ์ง์ ํ๋ฉด ์ฌ๋๋๋ง๋ ์ํ๊ณ  ์ข ๊ฐ๋ณ๊ฒ ํด์ ๋ฉ๋ชจ๋ฆฌ์ ์ข์ง ์์๊น?

## Custom Hook

* ์ ์ผ ์์ ํธ์ถ
* ํจ์ํ ์ปดํฌ๋ํธ ๋ ์ปค์คํํ์์๋ง ํธ
* ์กฐ๊ฑด๋ฌธ์ด๋ ์ฝ๋ฐฑํจ์์์ ํธ์ถํ๋ฉด ์๋๋ค.
