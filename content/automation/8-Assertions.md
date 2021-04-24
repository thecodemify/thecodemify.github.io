---
title: "8. Assertions"
metaTitle: "WebdriverIO assertions with Chai and not only"
metaDescription: "Learn how to use assertions with Codemify"
---

# Assertions

Assertion - is a way of verification. We can verify that data exist on the page, url is the one we expect to have and.... pretty much anything else.

# WairFor... as a way of assertion
Let's start with making sure elements existence on the page. For this purpose, we don't even need to use any extra modules. We can simply use:
- waitForDisplayed(); - waits until selector is displayed
- waitForExist(); - waits until selector exists
- waitForClickable(); - waits until selector is clickable

# Assert module as a way of assertion
For more complicated cases where we need to verify, let's say url === 'https://www.google.com', we could use chai module. Don't forget to install it if you haven't done so:
- npm install chai

### Assert url
```javascript
// require assert from chai module
const assert = require('chai').assert;

// use this one in your test
const url = browser.getUrl();
assert.equal(url, 'https://www.google.com', 'Url mismatch');
```

### Assert text === 'expected text'
```javascript
// require assert from chai module
const assert = require('chai').assert;

// use this one in your test
const actualText = $('#fakeTextId').getText();
const expectedText = 'Expected fake text';
assert.equal(actualText, expectedText, 'Our fake text did not match expected one');
```

### Assert true
```javascript
// require assert from chai module
const assert = require('chai').assert;

// use this one in your test
const loggedInUserIcon = $('#fakeIconId').isExisting();
assert.isTrue(loggedInUserIcon, 'User was not logged in');
```

### Assert false
```javascript
// require assert from chai module
const assert = require('chai').assert;

// use this one in your test
const usernameTextfield = $('#fakeUsernameTxtId').isExisting();
assert.isFalse(usernameTextfield, 'User was not logged out');
```

See entire list of assertions at: <a href="https://www.chaijs.com/guide/styles/#assert">chais website</a>