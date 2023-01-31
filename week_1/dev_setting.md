# 🔴 개발환경

## 개발환경세팅

개발환경세팅은 노드 환경이 지속적으로 업그레이드 됨으로 그때마다 설정이 바뀔수도 있기때문에 어렵다고 본다. 현재 노드 버전은 18.13.0 되도록 LTS 최신 버전을 사용하는 것이 좋다. fnm or nvm 등 노드 관리 프로그램을 사용하여 최신 버전 노드를 사용하여 프로젝트를 시작하는 것이 좋다고 생각된다.&#x20;

## JavaScript 개발환경 (Node.js) 세팅

* [참고문서 ](https://github.com/ahastudio/til/blob/main/javascript/20181212-setup-javascript-project.md)fnm을 통한 node version 관리
* [Node.js](https://nodejs.org/en/) 홈페이지
* [fnm](https://github.com/Schniz/fnm)(Fast Node Manager)
* [nvm](https://github.com/nvm-sh/nvm)(Node Version Manager)



## TypeScript + React + Jest + Parcel 개발환경세팅



jest 관련 모듈 설치

<pre><code>
<strong>npm i -D jest @types/jest @swc/core @swc/jest \
</strong>    jest-environment-jsdom \
    @testing-library/react @testing-library/jest-dom
    
</code></pre>



