---
title: "4. Video reporter"
metaTitle: "How to install video reporter"
metaDescription: "How to integrate video reporter with WebdriverIO / WDIO"
---

## How to install video reporter

Prerequisite: NodeJS, WDIO, and allure reporter installed

**1. Install video reporter**
```shell
  npm install wdio-video-reporter
```

**2. Add following import to your configuration file**
```javascript
    const video = require('wdio-video-reporter');
```
**3. Overwrite reporters property in your configuration file(likely wdio.conf.js)**
```javascript
    reporters: [
    [video, {
      saveAllVideos: false,       // If true, also saves videos for successful test cases
      videoSlowdownMultiplier: 3, // Higher to get slower videos, lower for faster videos [Value 1-100]
    }],
    ['allure', {
      outputDir: './_results_/allure-raw',
      disableWebdriverStepsReporting: true,
      disableWebdriverScreenshotsReporting: true,
    }],
  ],
```
**4. Run your tests**

**5. Generate and open report**
```shell
    allure serve _results_/allure-raw
```

Notes: You should be able to open report, navigate to failures section, click on one of them, and see video of failed test video execution.


Bingo! Now you know how to use video reporter. Let if you have any questions, feel free to send them by means below!


**Enjoy it!**
@Codemify - telegram, instagram, youtube