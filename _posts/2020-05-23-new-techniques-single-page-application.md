---
title: New techniques: Single-page application
category: techniques
tags: [javascript, spa, unit-test]
---

In my previous blog, I wrote that I’m developing a new tool: Featrz ([featrz.com](https://featrz.com/)). Go ahead take a sneak-preview. You can see some Demo-features by selecting a Project from the top.

### Bootstrap
For the GUI, I used a Single Page Application. I was a bit hesitant at first, because it meant for me to learn a lot of JavaScript as well. But the architecture makes more sense to me: initially loading all the HTML, CSS, and JavaScript and after that it is just REST messages going back-and-forward. At least this makes more sense for this application.

I made a choice for [Bootstrap](https://getbootstrap.com/) where it could have been [Vue.js](https://vuejs.org/), [Angular](https://angular.io/) or any other framework. At that time Bootstrap was just what I heard most around me. Nowadays I probably would have picked Vue.js. It will be interesting to see if Bootstrap can be easily replaced without harming the architecture and giving me the same benefits (see below). But that’s for another time.

### Unit Tests for JavaScript
Since JavaScript was new to me, I wanted to use it in a clean manner. Not the hacky scripting way, but more in a structured OO way. And I wanted to create automated checks for them as well. I figured that if half of the lines of code of the entire tool is in JavaScript, I must have Unit-tests for that JavaScript as well. Using classes was the logical thing to do.

But I took it a bit further. I separated the data (model) from the services and the services from the views and controllers, creating a Model-View-Service structure. It allowed me to test the Services in a Unit Test manner, i.e. very well isolated, using [mocha](https://mochajs.org/).

Note that JavaScript does not prevent you to take short-cuts. This comes down to just don’t do hacks and a lot of self-discipline. Even if you keep to this, JavaScript will give you enough challenges with Callbacks, Promises and plain magic in some libraries. Most examples on the internet (yes, I google a lot) are not applicable for the way you want to use JavaScript (e.g. different ES-level, Browser-side vs Client-side). I learned a lot, but most importantly that JavaScript is BIG and a lot of libraries and solutions exist for the same problem. Don’t try to master it at first, but rather keep it simple and don’t use things that you don’t understand. Or else learn to understand it and adding Unit Tests certainly helps with that.

### Conclusion
I’m very happy with the Single Page Application setup in combination with JavaScript Classes and MVS structure. Since I do switch a lot between Java and JavaScript, I had no problem switching back to JavaScript and understanding the code quickly. I don’t think I could have said the same when it was a big 1-file script.

But I’m also very pleased with the set of Unit Tests to run on the code. I’ve just seen too many examples where Unit Tests were well in place on the server, but when it comes to GUI tests, the JavaScript logic is tested with Selenium in Integration or End-to-End Tests. The structure I used here checks the JavaScript logic on the right level, i.e. Unit-level, resulting in quick feedback with low maintenance.