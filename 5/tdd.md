# ๐ข TDD

{% hint style="info" %}
Test Driven Development

ํ์คํธ ์ฃผ๋๊ฐ๋ฐ
{% endhint %}

## TDD๋

* ํ์คํธ ์ฃผ๋ ๊ฐ๋ฐ -> ํ์คํธ ์ฝ๋๋ฅผ ์์ฑํ๊ณ  ์คํจ ํ๋ค์์ ๊ทธ๊ฒ์ ํต๊ณผํ๋๋ก ๊ฐ๋ฐ์ ์งํํ๋๊ฒ
* ์คํจํ๋ ํ์คํธ ์ฝ๋๋ฅผ ์์ฑํ ๋๋ ์ธํฐํ์ด์ค์ ์คํ(๊ธฐ๋๊ฐ)์ ์ง์คํ๋ค.
* ๊ทธ ํ ์ฌ๋ฐ๋ฅธ ๋ฐฉ๋ฒ์ด ์๋๋๋ผ๋ ์ฌ๋นจ๋ฆฌ ํต๊ณผํ๋๋ฐ ์ง์คํ๋ค.
* ๊ทธ๋ฆฌ๊ณ  ๋ง์ง๋ง์ผ๋ก ๋ฆฌํฉํ ๋ง์ ํตํด์ ๊ทธ๊ฑฐ๋ฅผ ๋ค๋ฌ๋ ๊ณผ์ ์ด๋ค.

> 2๋ฒ ๊ณผ์ ์์ ํต๊ณผ๋ฅผ ๋นจ๋ฆฌ ์ํค๊ณ  ์ถ์๋ฐ ์๋๋ค?&#x20;
>
> ๊ทธ๋ฌ๋ฉด ํ์คํธ ์ฝ๋๊ฐ ๋๋ฌด ๋ณต์กํ ๊ฒ!
>
> ํ์คํธ ์ฝ๋๋ฅผ ๊ฐ๋ตํ ํ ํ 2๋ฒ ๊ณผ์ ์ ํต๊ณผ ์ํค๋ฉด ๋๋ค.
>
> ๊ทผ๋ฐ 3๋ฒ๊ณผ์ ์์ 2๋ฒ๊ณผ์ ์ ์ค๋ณต์ ์ฐพ์๋ด๊ณ  ์ ๋ฆฌ๋ฅผ ํ๋ ค๊ณ  ํ๋๋ฐ ์ ๋ฆฌ๊ฐ ์๋๋ค?
>
> ์ด๊ฒ ๋ต์ด ์๋ค.(๋ด๊ฐ ๊ทธ๋ฌํ๋ค)  ์ฐ์ต์ ํ๋ฉด ๋๋ค!!&#x20;
>
> ์ฆ 2๋ฒ ๊ณผ์ ์ ์ฌ๋ฐ๋ฅด๊ฒ ํต๊ณผ์ํค๋ฉด์๋ ๊น๋ํ ์ฝ๋๋ก\~!
>
> ์์ ๊ฐ์ ๊ณผ์ ์ ๊ฐ๋๊ฒ ์๋๋ผ๋ฉด ์ฌ์ค์ TDD๋ผ๊ณ  ํ  ์ ์๋ค.

## Jest

* facebook test๋๊ตฌ

## Describe - Context - It Pattern

```typescript

function add(...numbers:number[]):number{
	if(numbers.length===0){
		return 0;
	}
	return numbers.reduce((acc, number)=>acc+number)
}

const context = describe

describe('add', () => {
	context('with two args', () => {
		it('returns sum of two numbers', () => {
			expect(add(1, 2)).toBe(3);
		});
	});
	context('with only one arg', () => {
		it('return the same number', () => {
			expect(add(2)).toBe(2);
		});
	});
	context('with no arg', () => {
		it('return the same number', () => {
			expect(add()).toBe(0);
		});
	});
	context('with three args', () => {
		it('returns sum of three numbers', () => {
			expect(add(1, 2, 3)).toBe(6);
		});
	});
});

```

## ๋จ์ํ์คํธ๋

* ์  ์์ context ํ๋ ํ๋๋ฅผ ๋ง๋ค์ด ๋ณด๋ฉด์ ํ์คํธ ํ๋๊ฒ!
