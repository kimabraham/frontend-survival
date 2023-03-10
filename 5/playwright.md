# ๐ต Playwright

E2E ์๋ํ ๋๊ตฌ (์น๋ธ๋ผ์ฐ์  ๊ธฐ๋ฐ)

* ์ค์น

```bash
npm i -D @playwright/test eslint-plugin-playwright
```

* `playwright.config.ts ํ์ผ ์์ฑ`

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

* tests ํด๋๋ฅผ ๋ง๋ค๊ณ  `eslintrc.js ์ ํ์คํธ ํ์ผ(xxx.spec.ts)์ ๋ง๋ ๋ค.`

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
* /test-results/ ์คํจํ์๋ ์ด๋ฏธ์ง=> .gitignore์ ์ถ๊ฐ

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

test('Click the โIncreaseโ button', async ({ page }) => {
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

* ๋จ์ํ ์๋น์ค๋ ์ด๊ฑธ๋ก ์ปค๋ฒ๊ฐ ๊ฐ๋ฅํ๋ค.
* ์ธ๊ฐ ์นํ์ ์ธ ํ์คํธ ๋๊ตฌ
* [https://codecept.io/](https://codecept.io/)
