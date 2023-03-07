# 🟡 React Testing Library

## React Testing Library

* Node 환경에서 Dom 을 사용해서 React 상황을 연출하여 사용자로 하여금 편하게 테스트를 진행할 수 있도록 도와줌

## Given - when - then Pattern

* given=> 값을 주고(준비)
* when => 무엇무엇을 했다면
* then => 기대값 결과(화면에 뭔가 보여야 된다)

## Mocking

* 필요한 부분만 목업해서 그부분만 테스트 할떄
* backend 랑 통신하는 과정을 테스트 할때! => 이러면 근데 많아 지니까 => MSW
* MSW(Mock Service Worker) => 가라서버
* beforeAll() / afterEach() / afterAll()
* 적당히 해야지 빡세게 하면 사실 백엔드 개발이 될 수가 있다 ㅡㅡ ;;; &#x20;
* 또한 백엔드를 기다리지 않고 적당히 테스트하면서 웹브라우저로도 돌리고 하면서 하려면 좋은 툴!!
* npm i -D msw
* jest.config.js 에 추가

```javascript
module.exports = {
	testEnvironment: 'jsdom',
	setupFilesAfterEnv: [
		'@testing-library/jest-dom/extend-expect',
		'<rootDir>/src/setupTests.ts',
	],
	transform: {
		'^.+\\.(t|j)sx?$': ['@swc/jest', {
			jsc: {
				parser: {
					syntax: 'typescript',
					jsx: true,
					decorators: true,
				},
				transform: {
					react: {
						runtime: 'automatic',
					},
				},
			},
		}],
	},

```

* src/mocks/server.ts => express의 서버 파일

```javascript
import { setupServer } from 'msw/node';

import handlers from './handlers';

const server = setupServer(...handlers);

export default server;
```

* src/mocks/handlers.ts => express의 controller 파일

```javascript
import { rest } from 'msw';

const BASE_URL = 'http://localhost:3000';

const handlers = [
	rest.get(`${BASE_URL}/products`, (req, res, ctx) => {
		const products = [
			{
				category: 'Fruits', price: '$1', stocked: true, name: 'Apple',
			},
		];

		return res(
			ctx.status(200),
			ctx.json({ products }),
			);
		}),
	];

export default handlers;
```

* src/setupTest.ts => 약간 미들웨어 느낌나는데;;;;

```javascript
import server from './mocks/server';

beforeAll(() => server.listen({ onUnhandledRequest: 'error' }));
// 테스트 시작전
afterAll(() => server.close());
// 모든 테스트 끝나고 난 후
afterEach(() => server.resetHandlers());
// 각각 테스트 끝나고 난 후
```

* App.test.ts ( async => await 중요!!) 어쨌든 가라 서버 이기 때문에 기달려야 한다.!!

```typescript
import { render, screen, waitFor } from '@testing-library/react';

import App from './App';

test('App', async () => {
	render(<App />);
	
	await waitFor(() => {
		screen.getByText('Apple');
	});
});
```

## Test fixture

* 더미데이터 모음집?
