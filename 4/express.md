# π€ Express

{% hint style="info" %}
Node.js web framework

backendμ λν μ΄ν΄κ° νμ\~!
{% endhint %}

* κ΅μ₯ν μ­μ¬κ° μ€λλμλ€
* Nestjs λ λ°νμλ express
* node.jsλ‘ λ­κ°λ₯Ό λ§λ λ€λ©΄ κ³ λ €νλ μλ²
* nodemon->λ°λλλ§λ€ μλ² μ¬μμνλ λΌμ΄λΈλ¬λ¦¬

## RestAPI

* νλ©μ μ½μ‘°κ±΄ 4κ°μ§ & Resource & HTTP Verb
* [https://webfirewood.tistory.com/116](https://webfirewood.tistory.com/116)
* C(create) R(read) U(update) D(delete)

1. Read (/products) λͺ©λ‘ GET
2. Read (/products/{id}) νΉμ μ λ³΄νμΈ GET
3. Create (/products)  μΆκ° POST (JSON μ λ³΄ ν¨κ» μ λ¬)
4. Update (/products/{id}) μ λ³΄λ³κ²½ PUT or PATCH (JSON μ λ³΄ ν¨κ» μ λ¬)
5. Delete (/products/{id}) μ­μ  DELETE

res.send(products) μμμ json μΌλ‘ λκ°λ€.
