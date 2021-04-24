---
title: "4. How to test API?"
metaTitle: "Basics of software api testing"
metaDescription: "Learn API Testing with Codemify"
---

## API verification

<!-- Since you have already learned: <a href="https://Codemify.com/api/2017/10/26/What-is-an-API.html">What is an API</a> and <a href="https://Codemify.com/api/2017/10/26/API-Testing-Using-Postman.html">How To Send API requests With Postman</a>, now we can go ahead and test some of these APIs. -->

Send GET request to https://jsonplaceholder.typicode.com/users as you see it on the image below and verify next:

<p><h3>1.Correct data is coming back.</h3></p>

Imagine that you work for a Facebook, and you navigate to a friends page. All of this information will be coming through an api and then displayed to you in a browser. But what if developers haven't build UI yet. So what you do, is you send an api request and verify that expected data is coming back in expected format.

![responseData](https://user-images.githubusercontent.com/33443927/73722777-27a38a00-46dc-11ea-9b16-2a4cb6bc5636.png)


<p><h3>2.Status code is 200 OK (success). That is a correct code for successful response.</h3></p>

![statusCode](https://user-images.githubusercontent.com/33443927/73722781-27a38a00-46dc-11ea-9dfe-b1df4207ee79.png)


<p><h3>3.Response time.</h3></p>

It is pretty important as well. Some companies have their businesses built on api only, and every second of latency will move their margins down. So, make sure you ask your management what is expected response time for your apis.

![responsetime](https://user-images.githubusercontent.com/33443927/73722779-27a38a00-46dc-11ea-972d-88cea5d06795.png)
