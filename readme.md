최초 실행 시에만
```bash
git submodule update --init

cd module
npm ci
npm run build
npm pack ./packages/playwright-core
npm pack ./packages/playwright-test

cd ../src
npm i -D ../module/playwright-core-1.33.0-next.tgz
npm i -D ../module/playwright-test-1.33.0-next.tgz

# e2e-poc/src/node_modules/playwright-core/.local-browsers 경로에 브라우저 설치
PLAYWRIGHT_BROWSERS_PATH=0 npx playwright install
```

서브모듈만 빌드 후 재설치
```bash
cd module
npm run build
npm pack ./packages/playwright-core
npm pack ./packages/playwright-test

cd ../src
npm uninstall @playwright/test
npm uninstall playwright-core
npm i -D ../module/playwright-core-1.33.0-next.tgz
npm i -D ../module/playwright-test-1.33.0-next.tgz
```
