# 🔴 JSX

{% hint style="info" %}
JSX는  XML처럼  작성된 JavaScript를 확장한 문법이다. HTML도 아니고 문자열도 아니다.
{% endhint %}

* JSX 는 React에서 React.createElement로 변화되서 Javascript로 변환되서 사용된다

> React에서 JSX를 사용하는 목적
>
> * 결국 HTML 처럼 Javascript를 작성할 수 있기 때문에...
> * 하지만 당연히 HTML 은 아니고 XML이다.
> * 변환기 중 제일 유명한건 Babel\~! 온라인에서 바로바로 변화된 결과를 볼수 있다.
> * 필수는 아니다 빌드할때 컴파일 하기 싫으면 그냥 React.createElement쓰면되!

> Syntactic sugar
>
> * JSX 가 직관적이고 쓰기 편하다.

> React.createElement
>
> * 말 그대로 Element를 만드는 거
> * 어떻게 보면 JSX 를 만든다고 생각할 수도 있을 것 같다
> * 사실 VDOM의 노드를 생성하는 것
> * 이걸 쓰면 React Element 트리를 갱신
>
> ```javascript
> <Test />
> React.createElement("Test", null)
>
> <Greeting name="kimkr" />
> React.createElement("Greeting", {name="kimkr"})
>
> <Button type="submit">Send</Button>
> React.createElement("Button", {type="submit"}, "Send")
>
> <div className="test">
>     <p>Hello, world!</p>
>     <Button type="submit">Send</Button>
> </div>
> React.createElement("div", {className="test"}, 
>     React.createElement("p", null, "Hello, world!"),
>     React.createElement("Button", {type="submit"}, "Send")
> );
>
> <>
>     <p>Hello, world!</p>
>     <Button type="submit">Send</Button>
> </>
> React.createElement(React.Fragment, null, 
>     React.createElement("p", null, "Hello, world!"),
>     React.createElement("Button", {type="submit"}, "Send")
> );
>
> <div>
>     <p>Count:{count}!</p>
>     <button type="button" onClick={()=>setCount(count+1)}>Increase</buttton>
> </div>
>
> React.createElement("div", null, 
>     React.createElement("p", null, "Count:", count, "!"),
>     React.createElement("button", {type="button", onClick={()=>setCount(count+1)},
>                         "Increase")
> );
> ```

> React Element
>
> * 반드시 JSX를 말하는게 아니다.
> * React.createElement를 통해서도 생성 가능하고,
> * react runtime으로도 가능하며,
> * preact 로도 가능하다.

> React StrictMode
>
> * 문제를 발견하기 위한 도구
> * 개발 모드에서만 활성
>
> ```javascript
> import React from 'react';
>
> function ExampleApplication() {
>   return (
>     <div>
>       <Header />
>       <React.StrictMode>
>         <div>
>           <ComponentOne />
>           <ComponentTwo />
>         </div>
>       </React.StrictMode>
>       <Footer />
>     </div>
>   );
> }
> ```

> VDOM(Virtual DOM)이란?
>
> 1. DOM이란?
>    * 문서 객체 모델(The Document Object Model)
>    * 객체들로 이루어진 형태를 의미?
>    * 그 형태는 트리 구조라는것이 중요
> 2. DOM과 Virtual DOM의 차이
>    * VDOM은 유지보수가 편리한게 우선
>    * 속도는 빠르긴 하지만 뭐 속도만 따질만큼 빠르다고 할 건 아니다(이런저런 상황)
>    * 메모리 상에서 움직이기 때문에 빠르다.
>    * 또한 실제로 렌더링이 되지 않기 때문에도 속도적인 면에 앞서다.
>    * 하지만 바뀌는 부분만 변화되기때문에 유지 보수에 편하다
>    * DOM은 바꾸면 다 전체 노드가 싹다 바뀌서 비 효율적
>    * Fragment는 DOM에 없다(이런 몇몇가지 차이점이 있다.)

> Reconciliation(재조정) 과정은 무엇인가?
>
> * 바뀐 것만 업데이트를 하고 있는데, 그거를 직접 해주고 있는 것은 하지 않는다.
> * VDOM 트리만 바꾸고 있는데 그걸 DOM과 비교를 하고 있고 바뀐 것만 업데이트를 해준다.
> * “실제” DOM과 동기화하는 과정
