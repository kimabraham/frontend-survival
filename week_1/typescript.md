# 🔵 Typescript

## 간단한 REPL ts-node
ts-node는 node_modules에 설치되어 있지 않다. 그래서 npx로 불러!!
```
npx ts-node
```

## type vs interface
```
type Animal = {
  name:string
}

interface Animal {
  name:string
}
```
interface는 약간 클래스 같이 생겼다
확장하는데 있어서 사용법이 약간 다르다.

우선 타입을 선호하기때문에 타입으로 강의 진행

## 배열
깐깐하게 타입 관리하고 싶을시 Tuple사용
```
let pair:[string, number]
```

타입스크립트는 전에 많이 보고 썼던 것이라서 그런지 우선 지금은 많이 적을 부분은 없는것 같다.

## 타입추론
적당히 형태들 보고 타입을 알아서 예상하기 때문에 일일히 다 타입을 적어줄 필요는 없다는 거?

## Unnion type
매개변수 처리할 때 좋다.
```
type Category = 'food'|'toy'|'bag'
```
솔직히 그동안 타입스크립트 왜쓰나 했다. 이거 좋네;

## 레거시 환경?
- ReactNode 같은게 대표적
- 지정된 타입? 같은거라고 생각된다. nest.js 쓸때 타입스크립트로 할때 적용됬던 이상한 타입들?

## Generic
- 잘 모르겠다
- 타입 안정성 있게 쓸 수 있다고 한다.

generic을 쓰지 않는다면, 1) 타입을 미리 지정하거나 2) any를 이용하여 구현할 수 있다.
1) 타입을 미리 지정하자면, 확실한 타입체크가 이뤄질 수 있겠지만 항상 number라는 타입을 받아야하므로 범용성이 떨어진다.
2) 그렇다고 any를 사용한다면 자료의 타입을 제한할 수 없을 뿐더러, 이 function을 통해 어떤 타입의 데이터가 리턴되는지 알 수 없다.

이런 경우에 사용할 수 있는 것이 제네릭이다.
[도움이 되는 영상](https://www.youtube.com/watch?v=pReXmUBjU3E)