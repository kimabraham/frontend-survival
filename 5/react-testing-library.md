# ๐ก React Testing Library

## React Testing Library

* Node ํ๊ฒฝ์์ Dom ์ ์ฌ์ฉํด์ React ์ํฉ์ ์ฐ์ถํ์ฌ ์ฌ์ฉ์๋ก ํ์ฌ๊ธ ํธํ๊ฒ ํ์คํธ๋ฅผ ์งํํ  ์ ์๋๋ก ๋์์ค

## Given - when - then Pattern

* given=> ๊ฐ์ ์ฃผ๊ณ (์ค๋น)
* when => ๋ฌด์๋ฌด์์ ํ๋ค๋ฉด
* then => ๊ธฐ๋๊ฐ ๊ฒฐ๊ณผ(ํ๋ฉด์ ๋ญ๊ฐ ๋ณด์ฌ์ผ ๋๋ค)

## Mocking

* ํ์ํ ๋ถ๋ถ๋ง ๋ชฉ์ํด์ ๊ทธ๋ถ๋ถ๋ง ํ์คํธ ํ ๋
* backend ๋ ํต์ ํ๋ ๊ณผ์ ์ ํ์คํธ ํ ๋! => ์ด๋ฌ๋ฉด ๊ทผ๋ฐ ๋ง์ ์ง๋๊น => MSW
* MSW(Mock Service Worker) => ๊ฐ๋ผ์๋ฒ
* beforeAll() / afterEach() / afterAll()
* ์ ๋นํ ํด์ผ์ง ๋นก์ธ๊ฒ ํ๋ฉด ์ฌ์ค ๋ฐฑ์๋ ๊ฐ๋ฐ์ด ๋  ์๊ฐ ์๋ค ใกใก ;;; &#x20;
* ๋ํ ๋ฐฑ์๋๋ฅผ ๊ธฐ๋ค๋ฆฌ์ง ์๊ณ  ์ ๋นํ ํ์คํธํ๋ฉด์ ์น๋ธ๋ผ์ฐ์ ๋ก๋ ๋๋ฆฌ๊ณ  ํ๋ฉด์ ํ๋ ค๋ฉด ์ข์ ํด!!
* npm i -D msw
* jest.config.js ์ ์ถ๊ฐ

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

* src/mocks/server.ts => express์ ์๋ฒ ํ์ผ

```javascript
import { setupServer } from 'msw/node';

import handlers from './handlers';

const server = setupServer(...handlers);

export default server;
```

* src/mocks/handlers.ts => express์ controller ํ์ผ

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

* src/setupTest.ts => ์ฝ๊ฐ ๋ฏธ๋ค์จ์ด ๋๋๋๋๋ฐ;;;;

```javascript
import server from './mocks/server';

beforeAll(() => server.listen({ onUnhandledRequest: 'error' }));
// ํ์คํธ ์์์ 
afterAll(() => server.close());
// ๋ชจ๋  ํ์คํธ ๋๋๊ณ  ๋ ํ
afterEach(() => server.resetHandlers());
// ๊ฐ๊ฐ ํ์คํธ ๋๋๊ณ  ๋ ํ
```

* App.test.ts ( async => await ์ค์!!) ์ด์จ๋  ๊ฐ๋ผ ์๋ฒ ์ด๊ธฐ ๋๋ฌธ์ ๊ธฐ๋ฌ๋ ค์ผ ํ๋ค.!!

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

* ๋๋ฏธ๋ฐ์ดํฐ ๋ชจ์์ง?
