---
title: "Introduction into C++ and setting everything up"
date: 2021-02-07T15:45:18-05:00
draft: false
authors: ["Geoff"]
categories: ["Programming"]
tags: []
series: "C++"
---

## Welcome to C++
 
Hallo!
 
You are reading this article, so I would imagine you are interested in C++. (Sometimes called Cpp) Well, you are in luck, cause I am going to be making a series on C++, from beginner to advanced (ish). One thing I will preface beforehand, I am *not* a C++ expert, I do not know everything there is to C++. That being said, I am working on a game engine in C++, and have some smaller projects in C++.
 
So, I think that’s all I need to say about myself, lets dive into it!
 
## What is C++?
 
C++ is a general-purpose, OOP or __Object Oriented Programming language__. I will explain more about OOP in a later post, as it is a slightly more advanced topic. It was developed by __Bjarne Stroustrup__, as an extension of the C programming language, or as some call it, "C with classes". C++ is most useful for systems programming, app development, and game development (Which is personally what I use it for).
 
Ok, enough boring history talk, let’s get started!
 
## Setting up C++ and a IDE 
 
What is an IDE? Well, an IDE is short for __Integrated Development Enviorment__. In other words, it’s a place where you can write and run code. The one we will be using is __Visual Studio__ or VS. So, head over to [Visual Studio Install Page](https://visualstudio.microsoft.com/vs/community/) and grab yourself a copy.
 
Now, Visual Studio can be used for many languages. Each package is for a different language, framework, or tool. The one we want is C++ Desktop Development. So, locate the package shown in the picture below and install it. If you would like to install other packages, select the ones you want, and press Install together.
![Visual Studio C++ Package](https://media.discordapp.net/attachments/243005537342586880/808666733593493504/unknown.png)
 
Now just wait for that to install, and we’re done! :D
 
Once you open it, you should see something like this:
![Visual Studio Start Page](https://cdn.discordapp.com/attachments/243005537342586880/808672472953782322/unknown.png)
 
Here, press File > New > Project. You should come to a screen like this:
![Visual Studio New Project](https://cdn.discordapp.com/attachments/243005537342586880/808675817991176212/unknown.png)
 
Here, select Visual C++. Then on the window on the other side, select "Console App". Then, give it a name and hit Ok.
 
Boom! We have a project made and some code inside it. Now the fun truly begins.
 
## CODEEE!!
 
Ok, that title may have been a bit exaggerated, but CODE!
We can finally get coding. If you followed the above steps properly, you should have gotten something like this
 
```
#include <iostream>
 
int main()
{
    std::cout << "Hello World!\n";
 
    return 0;
}
```
 
Let us analyze this code a little before we run it and see something happen, ok?
Firstly, what is this `#include <iostream>` bit?
 
This is something called a preprocessor directive. This line here is telling our code that when it runs, it should import a library. In this case, we are importing 'iostream'. This is short for input-output stream, and this gives us access to most of the base C++ keywords and functions. Just know, you will (mostly) always need this in your C++ project, don’t skip it.
 
Then, we have `int main()`. This is the entry point for our program, meaning our program starts here. 
In the function, we have 2 lines, `std::cout << "Hello World!\n";` and `return 0;`. First, `std::cout << "Hello World\n;"`. cout (pronounced "see-out") is an object used together with the insertion operator (<<) to output/print text. In our example, it will output "Hello World". Try to change the text in the quotes to get a different output! return 0 effectively ends the main function. Another thing, what is the `std` before cout? Well, that is something called the __Standard Namespace Library__. The std lets us use objects like cout in our program. Here, we are using the `::` operator to get the cout object from std. But there is another way to do this.
```
#include <iostream>
using namespace std;
 
int main()
{
    cout << "Hello World!\n";
 
    return 0;
}
```
 
Here, we are adding a new line, `using namespace std;` and getting rid of `std::` before out cout. This pretty much says to import all the objects from std at the start of the program, so we don’t need to keep getting it from std. Whether you use `using namespace std;` or `std::cout`, is completely up to you, but I personally prefer `using namespace std;`.
 
Ok, so now, let us run this program and see what happens!
 
![Visual Studio Run Button](https://cdn.discordapp.com/attachments/790465349895585794/808710470491570216/unknown.png)
 
Press this button, which you should find at the top of your program.
Once you run the program, you should see a black window appear with "Hello World" on it!
 
## Conclusion
 
That was the basics of the C++ Programming language. I know we did not write any code today, but now you can understand the bare basics of C++. Next time, we will actually start typing some code ourselves!
 
So until then, Bai bai!
 
# What if I want to contact you?
Well, if you do require my assistance, you can head over to the ANF Studio’s discord server, and ask for Geoff (there are also some other cool programmers who would be glad to help).

[ANF Studio’s Discord](https://discord.gg/Hy2eyuBkXa)




