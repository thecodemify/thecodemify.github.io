---
title: "3. Allure reporter"
metaTitle: "How to install allure reporter"
metaDescription: "How to integrate allure reporter with WebdriverIO / WDIO"
---

## How to install allure reporter

Prerequisite: NodeJS, and WDIO framework installed on your machine

**1. Create Dockerfile - or simply use this one:**

Note: you need to create Dockerfile with no extension(no .js no .anything) in the framework directory

```shell
  npm install @wdio/allure-reporter --save-dev
```

**2. Overwrite following reporters property in your configuration file(likely wdio.conf.js)**
```javascript
  reporters: [['allure', {
        outputDir: 'allure-results',
        disableWebdriverStepsReporting: true,
        disableWebdriverScreenshotsReporting: true,
    }]],
```
**3. Run your automated tests**

**4. Generate and open report**
```shell
  allure serve
```

Bingo! Now you know how to use allure reporter. Let if you have any questions, feel free to send them by means below!


**Enjoy it!**
@Codemify - telegram, instagram, youtube