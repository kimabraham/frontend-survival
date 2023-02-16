# 🟢 React Component

{% hint style="info" %}
Thicking in REACT

리액트로 사고하기

1. 컴포넌트 트리(계층구조)로 UI를쪼개
2. 하나의 component는 단순하게 하여 복잡하게 만드는  것
3. 컴포넌트화 하는 것은 사실상 데이터에 의해 강제되는 점이 있다.
{% endhint %}

## REST API 와 GraphQL

* REST API 란 무엇인가

CRUD => resource 중심으로 조작

* GraphQL은 왜 등장했는가?

하나의 endpoint에서 다양한 자료구조를 얻을 수 있다.(GET)

쓸때없는 자료 데이터 량? 낭비를 안할 수 있다.

그러나 때로는 Graphql이 더 많은 자료를 준다.

[https://www.youtube.com/watch?v=ISMVvVwmQUk](https://www.youtube.com/watch?v=ISMVvVwmQUk)

* REST API vs GraphQL

뭐가 좋다고 할 수는 없다.&#x20;

클라이언트쪽 부담이 생길 수있다.

그리고 자칫하면 서버 죽는다.

## JSON

* 데이터 형식
* JSON.parse(json)
* JSON.stringify(json)
* name value 한쌍
* 사람/기계 양쪽 모두 용이

## DSL(Domain-Specific Language)

* REACT 선언형 XML과 같은DSL을 사용하여 UI를 구성할 수 있다.
* 도메인특화언어

## 선언형 프로그래밍

## 명령형 프로그래밍

## SRP(단일 책임 원칙)

* 모든 클래스는 하나의 책임만 가지며 그건 캡슐화 해야 함
* \=> 모든 컴포넌트는 하나의 기능?만 하는 것
* 그러니까 사소한 기능을 바꾸기 위해서는 하나의 컴포넌트만 바꿀 수 있게 캡슐화를 해야한다.

## Atomic Design

* 개념적인 것.

## React component 와 props

1. 정적인 것 부터 만든다.
2. type이나 util로 빼주기
3. props의 흐름을 잘 보고 나누라
