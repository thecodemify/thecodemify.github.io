---
title: "1. Automation with WebdriverIO"
metaTitle: "WebdriverIO from zero to hero. Instagram example"
metaDescription: "Learn how to write Automation from scratch with Codemify"
---
### How to install WebdriverIO automation framework and run it. Instagram example

## Requirements:
- Macbook
- npm installed
- IDE

### Execute following steps in your IDE. I will use Visual Studio Code AKA VS Code

# 1. Open terminal, create automation folder, and get in it by running:
```javascript
mkdir automation && cd automation
```

# 2. Run this command to create default package.json file:
```javascript
npm init -y
```

# 3. Now install command line tool from webdriverIO:
```javascript
npm i --save-dev @wdio/cli
```

# 4. Generate configuration file for your framework:
```javascript
./node_modules/.bin/wdio config -y
```

# 5. In your wdio.conf.js file update specs section to be like this:
```javascript
specs: [
        './specs/**/*.js'
    ],
```

# 6. Create ’specs’ folder where you will store all testing files and folder login inside of it:
```javascript
mkdir -p ./specs/login
```

# 7. Create first test file:
```javascript
touch specs/login/login-spec.js
```

# 8. Add following code to your newly created login-spec file from step above. Don't forget to update instagram username and password in the code below to yours.

```javascript
const loginUrl = 'https://www.instagram.com/accounts/login/?source=auth_switcher';
const timeout = 20000;

describe('Login', () => {
    it('should not be able to login with none matching credentials', () => {
        // Declare and assign username and password consts
        const username = 'YourUsername';
        const password = 'YourPassword';

        // Navigate to login page
        browser.url(loginUrl)

        // Type in username, password, and click login
        $('[name="username"]').setValue(username);
        $('[name="password"]').setValue(password);
        $('div=Log In').click();

        // Wait for error message
        $('#slfErrorAlert').waitForDisplayed();
    })
})
```

# 9. Remove default test folder that we not gonna use

# 10. Overwrite package.json file with following code
```javascript
{
  "name": "codemify",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "npx wdio wdio.conf.js"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "@wdio/cli": "^7.5.2",
    "@wdio/local-runner": "^7.5.2",
    "@wdio/mocha-framework": "^7.5.2",
    "@wdio/spec-reporter": "^7.5.2",
    "@wdio/sync": "^7.3.0",
    "chromedriver": "^93.0.0",
    "wdio-chromedriver-service": "^7.0.0"
  }
}
```

# 11. Run this command to update all of the versions of dependencies:
```javascript
npm i
```
# 12. Run your test from terminal:
```javascript
./node_modules/.bin/wdio wdio.conf.js
```

Wolla, you got it!

Good luck ;)

<!-- Supports multiple languages.

The following is a code block with diff. Lines with `+` highlighted in green shade indicating an addition. Lines with `-` highlighted in red shade indicating a deletion.

```javascript
- const data = ['1','2'];
+ const data = [1,2];
``` -->

<!-- ## Live Editing example -->

<!-- ```javascript react-live=true
<button className={'btn btn-default'}>Change my text</button>
``` -->
