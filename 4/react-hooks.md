# 🟡 React의 Hooks

{% hint style="info" %}
React 16.8 에서 hook 도입

기존의 문제점

1. 컴포넌트를 감싸줘서 다시 내려줘서 (고차컴포넌트) 복잡
2. 컴포넌트 자체가 커진다.
3. 혼란스러운 클래스
{% endhint %}

### 기존

* state쓰는 컴포넌트 class , props 쓰는 재사용 가능한 컴포넌트 function

### 현재

* 다 func컴포넌트만 사용
* 복잡한 요소를 전부 hook으로 격리

### 대표적인 훅

* useState
* useEffect
* useRef
* useContext(redux)
* useLayoutEffect(문서참조)

## UseEffect(Syncronize)

* 막 쓰지마라 라이프 사이클과 연관짓지 마라 흠
* 렌더링 이후 해야할 일,
* 의존성 배열을 통해 언제 할지 결정 할 수 있다. \[]
* 함수를 리턴!
* \[] 한번만 \[playing] playing이 바꿨을때마다.
* effect시 두번 실행되는 것은 React.strictmode 때문에 개발할때만 두번 실행한다.
* 함수를 useEffect에 써야 하는게 좋다. 일반적인 거는 상관없는데 다른 상태나 이런걸 가져오면 계속해서 실행할 수 있다.(많이 겪는 문제)
