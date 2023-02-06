# 🔴 JSX

{% hint style="info" %}
JSX는  XML처럼  작성된 JavaScript를 확장한 문법이다. HTML도 아니고 문자열도 아니다.
{% endhint %}

* JSX 는 React에서 React.createElement로 변화되서 Javascript로 변환되서 사용된다

```javascript
<Test />
React.createElement("Test", null)

<Greeting name="kimkr" />
React.createElement("Greeting", {name="kimkr"})

<Button type="submit">Send</Button>
React.createElement("Button", {type="submit"}, "Send")

<div className="test">
    <p>Hello, world!</p>
    <Button type="submit">Send</Button>
</div>
React.createElement("div", {className="test"}, 
    React.createElement("p", null, "Hello, world!"),
    React.createElement("Button", {type="submit"}, "Send")
);

<>
    <p>Hello, world!</p>
    <Button type="submit">Send</Button>
</>
React.createElement(React.Fragment, null, 
    React.createElement("p", null, "Hello, world!"),
    React.createElement("Button", {type="submit"}, "Send")
);

<div>
    <p>Count:{count}!</p>
    <button type="button" onClick={()=>setCount(count+1)}>Increase</buttton>
</div>

React.createElement("div", null, 
    React.createElement("p", null, "Count:", count, "!"),
    React.createElement("button", {type="button", onClick={()=>setCount(count+1)},
                        "Increase")
);
```

* JSX 는 React.createElement를 쉽게 사용하게 변환해 주는 것
* 그래서 필수가 아니다. "JSX로 할수 있는 모든 것은 순수 JavaScript로 할 수 있다."
* JSX Runtime은 \_jsx 함수를 이용(짧다)
* Preact는 h를 이용...

### VDOM(Virtual DOM)

* 가상의 DOM
* 매번 작은 VDOM을 만든다.
* 동기화를 효율적으로 하는 것.
* 특정기술이라기 보다는 패턴에 가깝다.
* 유지/보수 하기 좋은 DOM
*
