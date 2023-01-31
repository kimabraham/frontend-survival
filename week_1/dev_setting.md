# 🔴 개발환경

## 서론

{% hint style="info" %}
_어느 환경에서든지 자기가 쓰는 개발 환경을 세팅할 수 있어야 한다.자주 세팅하지 않기 때문에 항상 할때마다 생각보다 많은 시간과 오류를 경험하는 구간이라고 생각하기 때문에 이 부분을 명확하고 오류 없이 순서대로 할 수 있어야 하며 개념을 잘 잡아 놓아야 된다고 생각한다. 물론 시작부분에서 모든 과정을 이해할 수는 없겠지만, 어느정도는 알고 있어야 나중에 개발 환경에 대해서 첨삭이 가능할 것이라고 생각한다. 특히 cofing 파일 같은 부분에 있어서 상세히 알아두고 기록할 필요가 있다고 생각한다._
{% endhint %}

## 목차

1. [개발환경세팅](dev\_setting.md#undefined-2)
2. [JavaScript 개발환경 (Node.js) 세팅](dev\_setting.md#javascript-node.js)
3. [TypeScript + React + Jest + ESLint + Parcel 개발 환경 세팅](dev\_setting.md#typescript-+-react-+-jest-+-parcel)



## 개발환경세팅

개발환경세팅은 노드 환경이 지속적으로 업그레이드 됨으로 그때마다 설정이 바뀔수도 있기때문에 어렵다고 본다. 현재 노드 버전은 18.13.0 되도록 LTS 최신 버전을 사용하는 것이 좋다. fnm or nvm 등 노드 관리 프로그램을 사용하여 최신 버전 노드를 사용하여 프로젝트를 시작하는 것이 좋다고 생각된다.&#x20;

&#x20;



## JavaScript 개발환경 (Node.js) 세팅

* [참고문서 ](https://github.com/ahastudio/til/blob/main/javascript/20181212-setup-javascript-project.md)fnm을 통한 node version 관리
* [Node.js](https://nodejs.org/en/) 홈페이지
* [fnm](https://github.com/Schniz/fnm)(Fast Node Manager)
* [nvm](https://github.com/nvm-sh/nvm)(Node Version Manager)

_<mark style="color:green;">****</mark>_



## TypeScript + React + Jest + Parcel 개발환경세팅

1. 프로젝트 폴더 만들고 npm 초기화 해준다.
2. 당연히 <mark style="color:red;">`.gitignore`</mark> 만들어 주고 vscode extention을 이용한다.
3. 타입스크립트 설치 dev로

```

npm i -D typescript

npx tsc --init

```

4. npx 라는건 dev로 혹은 글로벌로 설치된 typescript 에서 tsc를 가져와서 typescript를 초기 설정하는 것을 의미한다. 이거 하면 <mark style="color:red;">`tsconfig.json`</mark> 이라는 파일이 생성되는데, 여기서 jsx 속성 변경한다.
5. ESLint 설정

```

npm i -D eslint

npx eslint --init

```

6. <mark style="color:red;">`.eslintrc.js`</mark> 수정한다. <mark style="color:red;">`jest:true`</mark>
7. 여기도 <mark style="color:red;">`.eslintignore`</mark> 파일을 생성한다.
8. 리액트설치

```

npm i react react-dom

npm i -D @types/react @types/react-dom

```

9. jest 관련 모듈 설치

```

npm i -D jest @types/jest @swc/core @swc/jest \
    jest-environment-jsdom \
    @testing-library/react @testing-library/jest-dom
    
```

10. &#x20;<mark style="color:red;">`jest.config.js`</mark> 파일을 작성해 설치한 swc를 사용한다. confing 파일 내용 [참고](https://github.com/ahastudio/CodingLife/blob/main/20220726/react/jest.config.js)
11. &#x20;기본 코드 작성하여 테스트 및  내용

작성 파일들

* <mark style="color:red;">`index.html`</mark>
* <mark style="color:red;">`src/main.tsx`</mark>
* <mark style="color:red;background-color:yellow;">`src/App.tsx`</mark>
* <mark style="color:red;background-color:yellow;">`src/App.test.tsx`</mark>
* <mark style="color:red;background-color:yellow;">`src/components/Greeting.test.tsx`</mark>
* <mark style="color:red;background-color:yellow;">`src/components/Greeting.tsx`</mark>

&#x20;_<mark style="color:green;">****</mark>_ :arrow\_up:_<mark style="color:green;">****</mark>_



