서브모듈 연결

```bash
git submodule update --init
```

서브모듈 빌드

```bash
git submodule update --init

cd module
#npm ci
npm run build
npm pack ./packages/playwright-core
npm pack ./packages/playwright-test
```

패키지 설치하기

```bash
cd src
npm remove @playwright/test
npm remove playwright-core
npm i -D ../packs/playwright-core-1.33.0-next.tgz
npm i -D ../packs/playwright-test-1.33.0-next.tgz
#PLAYWRIGHT_BROWSERS_PATH=$HOME/pw-browsers npx playwright install
PLAYWRIGHT_BROWSERS_PATH=$HOME/pw-browsers npx playwright test
```
