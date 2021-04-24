---
title: "3. What is wdio.conf.js?"
metaTitle: "WebdriverIO configuration file explanation"
metaDescription: "Learn how to use wdio.cong.js file with Codemify"
---

WDIO team did a really good job on explaining their config file. But here are another way of looking at it:

# Runner
You will most likely run your code on local runner mode. Although, some companies prefer to pay for cloud services like [Sauce Labs](https://saucelabs.com), or run your tests in Google Cloud Platform. In a code from previous articles you see runner: "local" as a part of config file. Here is an example how you could run your tests in a GCP:
```javascript
hostname: '31.55.77.117', // Hostname example AKA your GCP machine address
port: 4444, //Port number
user: '', // Username
key: '', // Password
```

# Path
We will use default path as we use chromedriver. In a case with running your tests remotely, I've commented out path since I've used Selenoid instead of selenium hub. But you don't need to worry about it, Chromedriver works fine and will be way enough for you to start with.
```javascript
// Override default path ('/wd/hub') for chromedriver service.
path: '/',
```

# Specs
Specs is a simple key of this big conf object that we export. It essentially defines files that we can run with command that runs all spec files. Run "npx wdio" to make sure it works. Then change specs path to anything else and you will get an error upon running same npx wdio. 

```javascript
specs: [
        './specs/**/*.js'
    ],

```

# Exclude
Exclude does an opposite. It excludes files that wanna run. Test it out by including one of your specs in exclude and then run same "npx wdio" command.
```javascript
exclude: [
        // './specs/login/login-specjs'
    ],
```

# MaxInstances
MaxInstances defines how many files you wanna run simultaneously AKA how many threads
```javascript
maxInstances: 10,
```

# Capabilities
With capabilities you can define a lot of things like: browser to use, browser version, window size, enable video recording etc.
```javascript
    capabilities: [{
		// maxInstances can get overwritten per capability. So if you have an in-house Selenium
		// grid with only 5 firefox instances available you can make sure that not more than
		// 5 instances get started at a time.
		maxInstances: 5,
		//
		browserName: 'chrome',
		'goog:chromeOptions': {
			w3c: false,
			args: ['window-size=1920,1080', // - full screen size
				'headless', // - run automation with or without actual browser. Headless === without
				"no-sandbox", // - this flag is needed in order to run automation in docker container
				"disable-gpu"] // - this flag is needed in order to run automation in docker container
		}
		// If outputDir is provided WebdriverIO can capture driver session logs
		// it is possible to configure which logTypes to include/exclude.
		// excludeDriverLogs: ['*'], // pass '*' to exclude all driver session logs
		// excludeDriverLogs: ['bugreport', 'server'],
	}],
```

# LogLevel
Log level defines how much of the logs we wanna get. I prefer to use 'error' level. Try it out your self and run tests to see difference.
```javascript
logLevel: 'error'
```

# Bail
Bail defines when should we bail out :) Example. 1 will force our automation to finish after anyone of our tests fail. 2 will do the same but after two tests have failed. You got it, right?
```javascript
 bail: 0
```

# BaseUrl
BaseUrl speaks of itself. It defines base url for our tests. I'll add instagram since that's the proj that we are automating here. You can use it just by passing './' to your url method. Example: browser.url('./');
```javascript
baseUrl: 'http://instagram.com',
```
# WaitforTimeout
Any of the wait commands in out framework(waitForDisplayed, waitForExist, waitForClickable etc) will use this timeout if you pass undefined into it. See example below: 
```javascript
// Default timeout for all waitFor* commands.
    waitforTimeout: 10000,
// Usage example:
this.loginPage.loginLnk.waitForDisplayed(undefined, false, 'This error message in element not found');
```

To be continued