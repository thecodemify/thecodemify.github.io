---
title: "5. How to use MAP?"
metaTitle: "WebdriverIO map method"
metaDescription: "Learn how to use map function/method with Codemify"
---

# How to use map in automation testing? WebdriverIO example

Let's start with: How does it work?
- The map() method creates a new array populated with the results of calling a provided function on every element in the calling array.

This might look too smart and not clear. Let's just see an example:
```javascript
// This is an example of helper method that uses map
clickByLabel(label){
    // Create object named hash
    let hash = {};

    // Loop through yourSelectors and fill up object with keys(text of each label with h1 tag), and values: "div a" selector so we could perform action on it
    $$('.fakeClasses').map(elem => hash[elem.$('h1').getText()] = elem.$('div a'));
    // Same as line above but: this.yourSelectors.map(elem => hash[elem.getText()] = elem);

    // Performing actual action on it. Note, one of your labels that we got text of must match with parameter that yo will pass in(label)
    hash[label].click();
}
```

# How to debug map if it doesn't work?

Case one:

![undefined](https://user-images.githubusercontent.com/33443927/73781992-1a22ea00-4746-11ea-981f-1af82b0caa80.png)

If you see following error, this means the parameter you are passing in:
- doesn't exist
- there is a race condition(it didn't show up yet, and click already happened)

### There are few ways to debug it:
- add browser.pause(2000) right before map. It will help if it's a race condition. If it is, then you will need to add waitUntil so all options would display before it actually maps them.
```javascript
    let hash = {};
    browser.pause(2000);
    $$('.fakeClasses').map(elem => hash[elem.$('h1').getText()] = elem.$('div a'));
```
- add a browser.debug() right before map. It will stop browser and you will be able to see if you element exist and there was a race condition.
```javascript
    let hash = {};
    browser.debug()
    $$('.fakeClasses').map(elem => hash[elem.$('h1').getText()] = elem.$('div a'));
```
- console.log all options that you've mapped. This will show you all available options of "h1" tag that we have mapped.
```javascript
    let hash = {};
    $$('.fakeClasses').map(elem => hash[elem.$('h1').getText()] = elem.$('div a'));
    console.log(Object.keys(hash));
```

We will add video with example of it soon
