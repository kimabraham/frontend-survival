# 🔵 Playwright

E2E 자동화 도구 (웹브라우저 기반)

* 설치

```bash
npm i -D @playwright/test eslint-plugin-playwright
```

* `playwright.config.ts 파일 생성`

```javascript
import {type PlaywrightTestConfig} from '@playwright/test';

const config: PlaywrightTestConfig = {
	testDir: './tests',
	retries: 0,
	use: {
		channel: 'chrome',
		baseURL: 'http://localhost:3000',
		headless: Boolean(process.env.CI),
		screenshot: 'only-on-failure',
	},
};

export default config;
```

* tests 폴더를 만들고 `eslintrc.js 와 테스트 파일(xxx.spec.ts)을 만든다.`

```javascript
module.exports = {
	env: {
		jest: false,
	},
	extends: ['plugin:playwright/playwright-test'],
	rules: {
		'import/no-extraneous-dependencies': 'off',
	},
};
```

* npx playwright test
* /test-results/ 실패했을때 이미지=> .gitignore에 추가

```javascript
import { test, expect } from '@playwright/test';

test('Filter products', async ({ page }) => {
	await page.goto('/');

	await expect(page.getByText('Apple')).toBeVisible();

	const searchInput = page.getByLabel('Search');

	await searchInput.fill('a');

	await expect(page.getByText('Apple')).toBeVisible();

	await searchInput.fill('aa');

	await expect(page.getByText('Apple')).toBeHidden();
});

test('Click the “Increase” button', async ({ page }) => {
	await page.goto('/');

	const count = 13;

	await Promise.all((
		[...Array(count)].map(async () => {
			await page.getByText('Increase').click();
		})
	));

	await expect(page.getByText(`${count}`)).toBeVisible();
});
```

## CodeceptJS

* 단순한 서비스는 이걸로 커버가 가능하다.
* 인간 친화적인 테스트 도구
* [https://codecept.io/](https://codecept.io/)
