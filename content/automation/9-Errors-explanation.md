---
title: "9. JS Automation test errors explanation"
metaTitle: "What did my test fail?"
metaDescription: "Learn common JS Automation test errors meaning with Codemify"
---

# 1. Cannot read property 'click' of undefined
```javascript
Cannot read property 'click' of undefined
Cannot read property 'getText' of undefined
Cannot read property 'waitForClickable' of undefined
```
are all the same issues. Most likely your variable name is either: not defined, or misspelled.
If you this type of errors, always refer to whatever you have right before click, getText, waitForClickable.
Example: this.loginPage.loginBtn.click();
loginBtn is where issue is hidden. See if you can go into definition of that selector to verify referencing

# 2. Can't call getText on element with selector #exampleLoginBtn because element wasn't found
This one is self explained. Element wasn't found so it's either: 

Incorrectly chosen selector(dynamic, or just not the one that appears on the page) 

Race condition(it was called before it appeared. waitForClickable should fix it unless you need to update selector itself)

# 3. element click intercepted: Element ...

Click intercepted means there was another element on the top of one you've selected. Try to see what element exactly it was to solve this issue.


To be continued
