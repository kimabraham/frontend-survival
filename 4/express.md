# 🟤 Express

{% hint style="info" %}
Node.js web framework

backend에 대한 이해가 필요\~!
{% endhint %}

* 굉장히 역사가 오래되었다
* Nestjs 도 바탕에는 express
* node.js로 뭔가를 만든다면 고려하는 서버
* nodemon->바뀔때마다 서버 재식작하는 라이브러리

## RestAPI

* 필딩제약조건 4가지 & Resource & HTTP Verb
* [https://webfirewood.tistory.com/116](https://webfirewood.tistory.com/116)
* C(create) R(read) U(update) D(delete)

1. Read (/products) 목록 GET
2. Read (/products/{id}) 특정정보확인 GET
3. Create (/products)  추가 POST (JSON 정보 함께 전달)
4. Update (/products/{id}) 정보변경 PUT or PATCH (JSON 정보 함께 전달)
5. Delete (/products/{id}) 삭제 DELETE

res.send(products) 알아서 json 으로 나간다.
