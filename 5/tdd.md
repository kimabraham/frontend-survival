# 🟢 TDD

{% hint style="info" %}
Test Driven Development

테스트 주도개발
{% endhint %}

## TDD란

* 테스트 주도 개발 -> 테스트 코드를 작성하고 실패 한다음에 그것을 통과하도록 개발을 진행하는것
* 실패하는 테스트 코드를 작성할때는 인터페이스와 스펙(기대값)에 집중한다.
* 그 후 올바른 방법이 아니더라도 재빨리 통과하는데 집중한다.
* 그리고 마지막으로 리팩토링을 통해서 그거를 다듬는 과정이다.

> 2번 과정에서 통과를 빨리 시키고 싶은데 안된다?&#x20;
>
> 그러면 테스트 코드가 너무 복잡한 것!
>
> 테스트 코드를 간략히 한 후 2번 과정을 통과 시키면 된다.
>
> 근데 3번과정에서 2번과정을 중복을 찾아내고 정리를 하려고 하는데 정리가 안된다?
>
> 이게 답이 없다.(내가 그러하다)  연습을 하면 된다!!&#x20;
>
> 즉 2번 과정을 올바르게 통과시키면서도 깔끔한 코드로\~!
>
> 위와 같은 과정을 가는게 아니라면 사실상 TDD라고 할 수 없다.

## Jest

* facebook test도구

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

## 단위테스트란

* 저 위에 context 하나 하나를 만들어 보면서 테스트 하는것!
