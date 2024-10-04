---
title: How to optimize website
author: 
name: SilvieHong
date: 2024-10-04 13:58:05 +0900
categories: [Dev Progress, How to _______?]
tags: [optimization]
---

## Font Loading Optimization
### Avoid using @import
```css
@import url(http://fonts.googleapis.com/earlyaccess/nanumgothic.css);
```
Browser pauses while `@import` fetches fonts.
Because after loading font, it loads css.
<br>
It's not a bad way, but it's slow.
So a better way is to use link, @font-face, and Web Font Loader.

<br>

### link
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
```
<br>

### @font-face
```css
@font-face {
  font-family: "Roboto", sans-serif;
  font-weight: 100;
  font-style: normal;
}
```
<br>

### Web Font Loader
```html
<script src="https://ajax.googleapis.com/ajax/libs/webfont/1.6.26/webfont.js"></script>
<script>
  WebFont.load({
    google: {
      families: ['Droid Sans', 'Droid Serif']
    }
  });
</script>
```

It looks similar to @import, but it's asynchronous. It's useful when you need detail controlls and it prevents flickering when the font changes. But, slower than using link or @font-face. 

