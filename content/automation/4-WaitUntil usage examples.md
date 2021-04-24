---
title: "4. How to use waitUntil?"
metaTitle: "WebdriverIO waitUntil usage examples"
metaDescription: "Learn how to use waitUntil file with Codemify"
---

# How can I use wait until?

Let's start with: How does it work?
 - waitUntil is constantly checking if the returning condition is true. 
 - After curly brace you see 10000, it is timeout in milliseconds. 
 - Then you see string which is just an error message to show if 10 seconds have gone but true was not returned.
Example conclusion: Wait 10 seconds for fake link to be displayed. If it will not be displayed, show following error "Fake Link did not show up after 10 seconds".
```javascript
// It waits for true to be returned
browser.waitUntil(() => {
			return this.yourPageObject.fakeLnk.isDisplayed();
		}, 10000, 'Fake Link did not show up after 10 seconds');
```

WaitUntil 10 elements are visible
```javascript
browser.waitUntil(() => {
			return $$('.tenElementsClass').map((elem) => elem.isDisplayed()).length > 9;
			// Same code below but element is in page object
			// return this.pageObj.yourElements.map((elem) => elem.isDisplayed()).length > 9;
		}, 10000, 'Ten elements were not visible');
```

WaitUntil text equals to expected
```javascript
browser.waitUntil(() => {
			return this.yourPageObject.fakeTextLbl.getText() === 'I love rock & roll!'
		}, 10000, '"I love rock & roll "');
```

WaitUntil text is not there
```javascript
browser.waitUntil(() => {
			return this.yourPageObject.fakeTextLbl.getText() != 'I love rock & roll!'
		}, 10000, '"I love rock & roll "');
```

WaitUntil url contains word friends
```javascript
browser.waitUntil(() => {
	return browser.getUrl().includes('/friends');
		}, 10000, '"I love rock & roll "');
```

