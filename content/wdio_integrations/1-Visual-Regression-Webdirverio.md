---
title: "1. Visual Regression"
metaTitle: "WebdriverIO Visual Regression"
metaDescription: "Learn how to automation Visual Regression with Codemify"
---

## How to install visual regression tool:

1. Install wdio-image-comparison-service library 
```javascript
    npm install wdio-image-comparison-service
```

2. Import path library into your configuration file(likely to be wdio.conf.js)
```javascript
    const { join } = require('path');
```

3. Update services section in your config file to have an extra value(example contains chromedriver as a first one)
```javascript
    services: [
        ['chromedriver'],
        ['image-comparison', 
        // The options
        {
            // Some options, see the docs for more
            baselineFolder: join(process.cwd(), './tests/'),
            formatImageName: '{tag}-{logName}-{width}x{height}',
            screenshotPath: join(process.cwd(), '.tmp/'),
            savePerInstance: true,
            autoSaveBaseline: true,
            blockOutStatusBar: true,
            blockOutToolBar: true,
            ignoreNothing: true  // Without this option, it errors out only when mismatch is above 1.23%(by default)
            // ... more options
        }], 
    ],
```

4. Create new spec file and add these test cases into it

```javascript
describe('Example', () => {
    it('should save some screenshots', () => {
        browser.url('https://Codemify.com/interview/interview');
        // Save a screen
          browser.saveScreen('examplePaged', { /* some options */ });

        // Save an element
        browser.saveElement($('.rightSideBarUL'), 'firstButtonElement', { /* some options */ });

        // Save a full page screenshot
          browser.saveFullPageScreen('fullPage', { /* some options */ });

        //   // Save a full page screenshot with all tab executions
          browser.saveTabbablePage('save-tabbable', { /* some options, use the same options as for saveFullPageScreen */ });
    });

    it('should compare successful with a baseline', () => {
        browser.url('https://Codemify.com/interview/interview');
        // Check a screen
          expect(browser.checkScreen('examplePaged', { /* some options */ })).toEqual(0);

        // Check an element
        expect(browser.checkElement($('.rightSideBarUL'), 'firstButtonElement', { /* some options */ })).toEqual(0);

        // Check a full page screenshot
          expect(browser.checkFullPageScreen('fullPage', { /* some options */ })).toEqual(0);

        //   // Check a full page screenshot with all tab executions
          expect(browser.checkTabbablePage('check-tabbable', { /* some options, use the same options as for checkFullPageScreen */ })).toEqual(0);
    });
});
```

Bingo! Now it all works. Notice that there are quite a few ways to do visual regression. You can go as granular as one element verification.

Enjoy it!
@Codemify - telegram, instagram, youtube