# 🟢 FetchAPI\&CORS

{% hint style="info" %}

{% endhint %}

* fetch return 값 Promise 그래서 await or .then()
* body 값 => Readerble Stream
* 다른 METHOD

```javascript
const response = await fetch(url, {
    method:'POST',
})
```

## CORS

* 웹브라우저가 가지고 있는 보안
* 웹브라우저가 현재의 웹페이지랑 다른 출처의 데이터를 얻어오긴 하지만, 사용하지 못하도록 막는다. 브라우저 단에서 막는다는 것을 알아야 한다.&#x20;
* REST API 서버에서 Headers "Access-Control-Allow-Origin" 속성을 추가하면 된다. => 여기에서 요청했으면 괜찮아 라는 의미?

```bash
npm i cors
npm i -D @types/cors
```
