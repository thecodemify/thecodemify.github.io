---
title: "7. The Power Of XPath"
metaTitle: "How to use xpath for Automation"
metaDescription: "Learn how to use XPath with Codemify"
---

## Let's see what does XPATH consist of:
```javascript
    //*[@id = 'myArticle']/../../div[1]
```
1. // - is a root directory (start from the beginning)
2. //* - star means that we are looking in all of the nodes, for example if we do //div[@id = 'myArticle'], it will look for that id in all of the DIV nodes of the page. That is very helpful if you wanna save a time of the search with specifying a node
3. //*[@id = 'myArticle'] - inside of square brackets we have our search criteria. In this case it is id = myArticle (#myArticle)
4. //*[@id = 'myArticle']/.. - forward slash dot dot means go 1 level up
5. //*[@id = 'myArticle']/../../div - means go 2 levels up and choose div
5. //*[@id = 'myArticle']/../../div[1] - and a last part is [1]. That means if we have more then 1 div, choose first one



**Find element by text:**
```javascript
    //*[contains(text(),'Find element by text')]
	//*[contains(text(),'sibling')]
	//*[contains(text(),'power')]
```


Feel free to open up a DOM inspector and use this xpath to find it self :)

**Find element by class, id, or any key with a value:**
```javascript
    //*[@id = 'myArticle']
	//*[@class = 'post-area post']
	//*[@data-original-title = 'back to top']
```

**Find next(following) sibling which is a div:**
```javascript
    //*[@id = 'myArticle']/following-sibling::div
	//*[@id = 'myArticle']/../../following-sibling::footer
```

**Find previous(preceding) sibling which is a header:**
```javascript
    //*[@id = 'myArticle']/div/article/preceding-sibling::header
```
		
**Find fist, second, third etc child:**
```javascript
    //*[@id = 'myArticle']/div/article/div[5]
	//*[@id = 'myArticle'][1]
```

By the way, most people prefer not to use XPath, because they don't know how to use it. XPath is more powerful then CSS Selectors, because it can go backwards, which CSS can not :)
