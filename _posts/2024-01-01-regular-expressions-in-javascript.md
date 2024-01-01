---
layout: post
title: Regular Expressions in JavaScript
date: 2024-01-01 19:44 +0800
description: This is a quick guide on JavaScript regular expressions.
image:
category: Work
tags: [javascript,regex]
published: false
sitemap: false
---

https://builtin.com/software-engineering-perspectives/javascript-regex

I was working on a secret project ♥️ and required to extract information from the browser's URL. 
This is a quick guide on JavaScript regular expressions.

> Disclaimer: I have a basic understanding of RegEx and have used them before.
{: .prompt-info}

## How to Create a Regular Expression in JavaScript

There are two ways to create a regular expression (RegEx) in JavaScript:
1. RegEx Cconstructor (RegExp)
2. RegEx Literal

 

## RegEx Cconstructor (RegExp)

Syntax: `new RegExp(pattern[, flags])` 

Example: 

```javascript
var regexConst = new RegExp('abc');
```

## RegEx Literal

Syntax: `/pattern/flags`

Example:

```javascript
var regexLiteral = /abc/;
```

Here, the flags are optional. I will explain these later in this article.

The result is going to be a regex object.

You can to escape the forward slash ( / ) with a backslash ( \ ) if you want to use it as a part of the regex.

## RegEx Methods

### Regex.prototype.test()

This method is used to test whether a match has been found or not. It accepts a string which we have to test against a regular expression, and it returns true or false depending upon if the match is found or not.

```javascript
var regex = /hello/;
var str = 'hello world';
var result = regex.test(str);
console.log(result);
// returns true
```

### Regex.prototype.exec()

This method returns an array containing all the matched groups. It accepts a string that we have to test against a regular expression.

```javascript
var regex = /hello/;
var str = 'hello world';
var result = regex.exec(str);
console.log(result);
// returns [ 'hello', index: 0, input: 'hello world', groups: undefined ]
// 'hello' -> is the matched pattern.
// index: -> Is where the regular expression starts.
// input: -> Is the actual string passed.
```
