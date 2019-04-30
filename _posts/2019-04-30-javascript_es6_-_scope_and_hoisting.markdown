---
layout: post
title:      "JavaScript ES6 - Scope and Hoisting"
date:       2019-04-30 18:04:01 +0000
permalink:  javascript_es6_-_scope_and_hoisting
---


Write a blog about JavaScript. Specifically, imagine you want to tell a beginner JS developer about scope and hoisting, and how ES6 syntaxes affect behavior regarding these concepts. Give an overview of these topics with some examples. The blog does not need to be really long. It should be a good tool for someone starting to write JS, a reference that introduces scope and hoisting such that a reader has a good initial understanding. Here are some questions the blog should answer: - What is "hoisting" in JS? - What is "scope" in JS? - How do ES6 syntaxes such as `let` and `const` affect hoisting and scope, compared to `var`?

ES6 is truly a beautiful update compared to ES5, but for some,  it can be a bit confusing to think about some of the new features, including how scope has changed with the addition of let and const, and hoisting. For people new to the coding world, these ideas can seem scary, but broken down into plain English, it's really simple.

### Let's start with scope. What is scope?

Scope basically defines where in your program you can access certain variables and functions. There are different types of scopes in JavaScript that give you different kind of access, such as module scope, function scope, block scope, lexical scope and global scope, but I won't be getting into those today. Basically, all you need to know is that different variable declarations (const, let, var) let you access variables in different 'scopes'.

### Const, Let, and our old friend Var

In pre-historic times, JavaScript only allowed you to declare variables using var. Var gave you function scope, which was restrictive in many ways, which led to the creation of let and const. The difference in scope between let, const, and var, is simply that let and const only allow you to access it within the block it's defined in. 

Let can be reassigned at any time within the block, whereas const signals that it will not be reassigned. For all intents and purposes, I would default to using const and change your variables to let only if they need to be reassigned; As a rule of thumb, var seems pretty unncessary with the introduction of ES6

### Hoisting

JavaScript is a lanugage which compiles all of your code before running, and therefore 'hoists' different variables and functions to the top of their local or global scope. Let's see a few examples to help us understand: 

```
console.log(name)
var name = "Nico";
```

What do you think will be the console.log output?

The answer is: ```undefined```

var is hoisted to the top; so the program recognizes that there is a variable name that exists within the program, but does not actually have a value assigned to it yet; Therefore, the output will be undefined.

With const and let on the other hand, the output will be an error, because of the scope that const and let have as we mentioned before.

```error: name is not defined```

Because of this, best practice is always to declare your variables at the top of their respective scopes. This will help you have less errors and undefined variables.

### Conclusion

Ultimately, understanding these different concepts should help clean up your code and have less bugs. If you follow JavaScript best practices, you'll notice a drastic improvement in your code. 





