---
title: "2. Page Object Model"
metaTitle: "Implementation of page object model to WebdriverIO"
metaDescription: "How create page object for Automation framework"
---

# What is page object?

## Why do we need it?
1. Organize your code(easy to read, easy to understand)
2. Avoid duplicates

Duplicated code from previous article:
```javascript
$('button=Not Now')...........
```
This selector was used twice in just a one simplest test case. Imagine that you have 500 test cases, I'm pretty sure you will have hundreds of dups. In order to avoid it, we are going to implement a Software Design Patterns which is called Page Object Model.

Page Object Model - is a very popular design pattern used that we will use in building our automation frameworks. In a few words: it's a way to structure code.
In a previous article you saw us running basic automation test of instagram website. It works fine, but looks a little ugly and some code is duplicated.

Based on a previous article, your framework should look like this:
- node_modules (all of our modules/packages/libraries live there)
- specs (all of tests live there)
- package-lock.json (history of your npm updates - not used much)
- package.json (basic information about your framework with list of modules/packages/libraries we've installed)
- wdio.cong.js (actual configurations file where we specify base information like: timeouts, baseUrl etc)

### Now we need to add a new folder page_objects folder and login folder inside of it:
```javascript
mkdir -p ./page_objects/login
```

### Create login-page.js file inside of that folder
```javascript
touch ./page_objects/login/login-page.js
```

### Paste following code into it
```javascript
"use strict";

class Login {
	// Reusable selector getters that will help us to avoid selector duplicates
	get usernameTxt() {return $('[name="username"]');}
	get passwordTxt() {return $('[name="password"]');}
    get loginLnk() {return $('div=Log In');}
    get loginErrorLbl() {return $('#slfErrorAlert');}

	// Helper method to avoid code duplication
	login(username, password){
        this.usernameTxt.setValue(username);
        this.passwordTxt.setValue(password);
        this.loginLnk.click();
	}
}
module.exports = new Login();
```

### Let's update our test with login helper method and selector from page object:
```javascript
const LoginPage = require('../../page_objects/login/login-page');
const CommonPage = require('../../page_objects/common/common-page');
const ProfilePage = require('../../page_objects/profile/profile-page');
const loginUrl = 'https://www.instagram.com/accounts/login/?source=auth_switcher';
const timeout = 20000;

describe('Login', () => {
    // This hook runs after each test
    afterEach(() => {
        // Deleting cookies after each session will allow us to have new session before next test starts
        browser.deleteCookies();
    });

    it('should not be able to login with none matching credentials', () => {
        // Declare and assign username and password consts
        const username = 'YourUsername';
        const password = 'YourPassword';

        // Navigate to login page
        browser.url(loginUrl);

        // Type in username, password, and click login
        LoginPage.login(username, password);

        // Wait for error message
        LoginPage.loginErrorLbl.waitForDisplayed();
    })
});
```

You should be able to run your tests with a same command:
```javascript
./node_modules/.bin/wdio wdio.conf.js

// Or if you wanna run single spec file
./node_modules/.bin/wdio wdio.conf.js --spec spec/login/login-spec.js
```