---
title: "2. How to Dockerize WDIO"
metaTitle: "How to dockerize automation framework"
metaDescription: "Learn how to dockerize automation framework with Codemify"
---

## How to dockerize automation framework

Prerequisite: Docker installed on your laptop

**1. Create Dockerfile - or simply use this one:**

Note: you need to create Dockerfile with no extension(no .js no .anything) in the framework directory

```shell
FROM node:12

# Set up working directory
WORKDIR /app

# Install chrome and other dependencies
RUN wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add -
RUN echo "deb http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google-chrome.list
RUN apt-get update -qq && apt-get install -y -qq --no-install-recommends \
    vim \
    python3-setuptools \
    python3-pip \
    google-chrome-stable \
    libnss3-dev \
    xvfb \
    openjdk-8-jdk \
    gcc libpq-dev \
    python3-dev python3-pip python3-venv python3-wheel \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*
RUN pip3 install wheel

COPY . .
RUN mkdir ~/Downloads
RUN npm i
RUN npm rebuild node-sass

# Run all tests
CMD npm test
```

**2. Create new docker image by running this command in a terminal:**

  docker build .

**3. Find id of your new docker image by running:**

  docker images

**4. Run your test inside docker container by specifying first 3 characters of your docker image id(9b2 is an example):**

  docker run -it 4b2


Bingo! Now you know how to dockerize your test app. Let if you have any questions, feel free to send them by means below!


**Enjoy it!**
@Codemify - telegram, instagram, youtube