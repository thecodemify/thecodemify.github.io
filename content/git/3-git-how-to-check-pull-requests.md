---
title: "Git how to check pull requests"
metaTitle: "How to check git pull requests"
metaDescription: "Learn how to check pull requests with Codemify"
---

## What to look for in a pull request? ##

Everyone needs to check their pull requests, and PRs of their coworkers. Here is a basic list of what to check for:

### Before you push your code ###

- Run git diff command and check all your changes line by line

### After you push your code and about to create PR ###
Ask your self these questions:

- Did I leave any .pause .only .debug(webdriverIO specific) in my code?
- Did I beatify my code before committing?
- Did I leave one space between each function/hook?
- Did I not use xpath from browser? You can build it your self to make it efficient, but don't copy whatever browser spins to you
- Am I sure this test/file needs to live in this location? Example: if you write login test, it needs to live in login-spec.js
- Did I end every test with assertion? Do not end tests with a click, type, or similar action. You need verify result of your previous actions
- MAKE YOUR TESTS(assertions) FAIL AT LEAST ONCE to make sure this test is legit
- Cleanup: remove unused comments, spaces, code?

More to be added ..
