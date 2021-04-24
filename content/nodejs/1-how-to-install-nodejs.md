---
title: "1. How to install NodeJS and npm"
metaTitle: "How to install NodeJS and npm"
metaDescription: "How to install to install NodeJS and npm"
---

## How to install Nodejs and npm?

### 1. Install Nodejs with Homebrew 


First, we need to run following code to install Homebrew
```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Then run brew update to make sure we have latest brew
```bash
brew update
```

Check system for potential problems
```bash
brew doctor
```

Add Homebrews location to your $path in .bash_profile or .zshrc file.
```bash
export PATH="/usr/local/bin:$PATH"
```

Install NodeJS and npm
```bash
brew install node
```

Make sure NodeJS was installed on your computer by checking version of it
```bash
node -v
```

If that worked fine and you got digit in response, check npm version
```bash
npm -v
```

If you ever face any issues and need a fast response, ask your questions here [YOUTUBE LINK TO BE ADDED]

Welcome to NodeJS family!