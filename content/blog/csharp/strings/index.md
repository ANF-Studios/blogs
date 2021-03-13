---
title: "Strings in C#"
description: "In this article, we'll be looking over the string type in detail and how it can be used."
slug: strings
date: 2021-03-08T19:47:06-05:00
# lastmod: null
draft: true
categories:
- CSharp
#featuredImage: "strings_thumb.png"
author: "ANF-Studios"
---

<!--more-->

Strings. What are they and how do we use them? Are strings a thread of cotton in our code? They seem very powerful and we have used them a lot. We'll be looking at how they can be used today.

{{<admonition info "Remember the previous challenge? 👀" false>}}
Hey there, if you haven't read the [previous article](/blog/csharp/overview), I recommend skimming over it, we looked through basic types and a bit on C# and dotNET itself.
{{</admonition>}}

## What are strings
So let's start simple. "What are strings?" A string is an "object" of type String whose value is text. Now, you might be confused on "String", well for now, just know that "String" is a class (just like the one we have in our program, but slightly different).

Internally, the text is stored as a sequential read-only collection of Char objects. As you would've guessed, there is another class like String called Char.

Fun fact! You can also declare a string or a char like:
```cs
String variable = "...";
Char variable = '.';
```

Keep note that you cannot directly do that, you will have to include the `using System;` part. Speaking of which, System is a namespace, just like our `learning_csharp` namespace declaration. Finally, these are valid because **s**tring and **c**har are literal aliases to System.**S**tring and System.**C**har.

But that was just for your information.

### Null Character
Now, another thing that is important for you to know is `0` - no, not the literal character/number, but rather the "null character". Generally, for strings, it tells our computer (since code does run on a CPU) that this is the point where the string finishes. However, in C#, this is just an empty character and the string does continue.

{{<admonition info "ASCII Table Cheat Sheet" false>}}
![ASCII Table](/blog/csharp/overview/ascii_table.png)
{{</admonition>}}

Now, since I am here not just to teach C#, but programming itself as well, I shall be giving examples from other languages. This is some C++ code:
```cpp
std::string str = "Hello Wo\0rld!";
```

Notice that there's a null character. The output of a program that prints that variable will be `Hello Wo`. That's because our variable ended, *apparently*.

Now, in C#, it'll be... empty. *Like* a space character, but not exactly.
```cs
string str = "Hello Wo\0rld!";
```

This program will output: `Hello Wo rld!`. Crazy, right? But that's how it works and as far as it goes to the design choice, I do believe this is the right thing as C# is a managed, high-level language.

Just a quick note that I used a space there and a space character is not a null character!

