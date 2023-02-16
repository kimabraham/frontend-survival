# 🟡 React State

{% hint style="info" %}
리액트로 사고하기

3. 최소한 하지만 완벽한 UI의 state를 찾아라
4. 어디에 있게 할 건지
5. 역 데이터 흐름 추가?
{% endhint %}

## React state란?

* 바뀌면 다시 그린다
* 하위 컴포넌트도 다시 그린다.

## DRY 원칙

* Don't Repeat Yourself 자주하는 실수

## SSOT(Single Source of Truth)

* 일관성

## useState

* 변경되지 않는 값은 state로 다룰필요가 없다.
* props로 전달받은건 state가 아니다
* 계산가능한건 state가 아니다

## 1급 객체(first-class object)

* javascript에서는 함수가 일급객체
* 하위컴포넌트에 함수를 props로 전달 =>콜백함수라고 부른다.

## Lifting State Up

* 동시에 써야하는 컴포넌트들의 부모 컴포넌트로 state를 올리는 작업
