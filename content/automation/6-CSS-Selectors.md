---
title: "6. CSS Selectors for Automation"
metaTitle: "How to find css selectors for automation testing"
metaDescription: "Learn how to to use/find css selectors with Codemify"
---


### Id
 - selects simplest id tag. AKA id="main"
    
    `#main` 

### Class
- selects all elements with class="post-area post" - you are correct, you need to add dots instead of spaces if you use class
    
    `.post-area.post`   

### Multiple selectors
- selects all div elements that have id="myArticle" AKA div id="myArticle"
    
    `div #myArticle` 	

- selects same div but with a class="container main" AKA div class="container main"
    
    `div.container.main`

### Attributes
- selects all elements with a tag data-original-title="back to top". You simply choose tag and add [] around it

    `[data-original-title="back to top"]`

### Someone called all of these "pseudo selectors"

- It target first element of whatever is behind it

    `#top a :first-child`


- It targets last element. Example:

    `#top a :last-child`


- It target the nth element of whatever is behind it

    `#top a :nth-child(1) OR #top a :nth-child(2)`

### Combining selectors

- There are two types of relationships between selectors: save level(within one attribute), and multi level(different levels)

- Same level selectors will not have a space between them. Example:
    
    `#top.fake-class`

- Multi lever. Now imagine that id top is a parent or grand-grand-whatever-grand parent of class fake-class:

    `#tope. fake-class`

- The only one difference, is a space between them


Ask a question in instagram if you have any: @Codemify

