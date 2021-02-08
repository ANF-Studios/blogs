---
title: "Introduction into C# and setting everything up"
date: 2021-02-07T15:45:18-05:00
draft: true
authors: ["ANF-Studios"]
categories: ["Programming"]
tags: []
series: "CSharp"
---

Oh, hello there!
I think you're interested in learning C# (pronounced as "See Sharp"). Well, you're in luck because [ANF](https://github.com/ANF) is planning to make tutorials and write some tips on C#. For those of you who like to interact through video, no this series will most likely never be based on video. There shall be nothing but plain text to read. So I hope you like reading!

Before we get into this, I want to give you a quick disclaimer that I am no C# professional and I am only really just going to teach you everything that I know. I will try to make everything as detailed and as simple to understand as possibly. Quick note that if something is incorrect, you can hit me up at my Discord at [discord/ANF-Studios](https://discord.gg/fKWpK7A) (you can also get some help by other cool programmers there :wink:) or just create a PR at the repository; [github/ANF/anf.github.io](https://github.com/ANF/anf.github.io/pulls).

So let's get started, shall we?

Well, there might be a number of different people here with different reactions:

1. The beginner, who asks;
    - What is programming and what is its extent?

2. The novice, who says;
    - Time to write something that works.

3. The professional, who says;
    - Stand back, time to write a game engine, an operating system, make a computer and whatnot.

The beginner has the right thought. So let's first get to know about programming itself, to know what we're dealing with. I'm going to give you a few seconds to think it out yourself. Ask yourself, "what is programming?". It's okay if you can't define it, just tell yourself whatever you know. Now let's compare it with the actual definition according to wikipedia:
> Computer programming is the process of designing and building an executable computer program to accomplish a specific computing result or to perform a specific task.

Automation, to make our lives easier. That is what we're going to learn.

So what is C#?

C# is a modern, object-oriented, and type-safe programming language.

Woah now, that sounds a bit complex and I can understand you. As promised; I will try to break it down for you. Okay so first of all; "modern", what does that mean? Does it mean it has fancy keywords or is recently made? Well, no, not really. "Modern" programming means "less programming". It's like building your software at a higher level (as in not having to redefine every word in the English dictionary) allowing you focus on what you want to make without having boilerplate code all over your codebase.

So that's nice I guess? So ANF.. when will we start programming, teach me how to do that. I didn't come here to get bored.

Well right, I'll get to that in a sec, right after we complete this. Anyways, what does "object-oriented" mean? I'm going to give you a second to guess it out. It's really simple, think of it yourself; "object", what is an object? What's its classification? Are you getting the hang of it? That's great if yes, but let me further clear it out:

The term object oriented means something, anything really, not specifically programming - forget programming for a second. Object oriented means some classification. Try to think of it has an object classified in a category which is classified in another category which goes up to a limit. So let me give you an example, hopefully it should clear it out. Say you have an apple, what's it categorized in? Food, alright great food? But let's be even more specific, what is it? A fruit, and from here and onwards, we can keep adding multiple "traits" to it and classify it such as can we eat an apple as a snack or not? Now in object oriented programming, you have types, types are useful for telling C#; hey C#, this is my character, store this much memory (into the RAM) for it. Another example of this can be; hey C#, here's another one of my variable, this is a number, an integer (which cannot have decimal points and takes a specific amount of memory) to be presice, allocate this much memory. That's basically all there's really to it.

We'll be allocating variables a lot and this is an important concept. I'll try to "allocate" more time to explain these because this will help you a lot :wink:

Now finally, what is "type-safe", well, type safety is.. well, a major problem, especially for beginners in more low level languages where you control the memory which is uh.. not an easy task as a beginner. What'll happen is that your application will just.. crash, that's it. You have to figure out why it crashes, thankfully, Microsoft's Visual Studio (it's what we'll be programming in :eyes:) has a built-in debugger which tells us as much as it knows. For example, when our application crashes, it *will* tell us which line caused it to crash and there we go! We can tell what's the problem. That really helps out, but this in C#, it's a managed language which means pretty much everything will be handled for us which is kind of nice. Back to the point; C# handles memory for us in most cases which prevents such crashes and mishaps that you would see when dealing with other languages (even I am guilty of this, but it works out eventually).

Now that that's covered, let's get to the fun part, shall we?

So what we're going to be using is Visual Studio Code, it's a "code editor" developed by Microsoft. There's an IDE called `Visual Studio 20XX` (where XX is the year), but I won't be using that because it's only for Windows and Macintosh, if anyone here is on Linux, they won't be really guided which is not what I want, I want my lessons to be covered for everybody, at least when it's possible.

If you *really* want to use the IDE, you can find some other guide and use it, but I would only half recommend.

For now, you can head over to [Code.VisualStudio](https://code.visualstudio.com/) and press the download button (for me, I'm on Windows 10 x64, you might see something else, don't worry about that however):

![Download VS Code](/img/tutorials/csharp/00_introduction/download_vscode.png)

Now you can wait for the installer to install, and as soon as that's done, you can configure it according to however you want. *However*, I wouldn't recommend changing any setting, they are the "best" ones or at least good enough. Beware that this "PATH" setting is really important, I would strictly prohibit you from leaving it unchecked. The "PATH" allows you to run the `code` command in your terminal/CLI.

As soon as that's installed, verify that it's there - you might want to restart your PC just in case to be safer, but you do not need to, unless it asks to.

After that, open up any terminal of yours, even command prompt will do and then type in `code` and wait for VS Code (Visual Studio Code) to launch. You can also fire it up via your start menu or whatever your prefer though I would recommend getting used to the CLI as well.

Side note: You can also supply arguments to the `code` command such as the path (not to be confused with PATH) argument which may look something like `code ../` (go one directory before the CLI's directory and launch VS Code in that directory). There are also other ones, type in `code --help` for more information.

Now that you've opened your preferred folder within VS Code, you should see something like so:

![VSCode](/img/tutorials/csharp/00_introduction/vscode.png)

Now yours will be most likely different from mine, don't worry about that. I'll explain the reason behind that; VS Code is highly customizable and there are these things called "extensions" which are like "Minecraft Addons" for those of your Minecraft players. There are almost no limits into how you want VS Code to look like, heck you can even change the colors of the interface.

You can have a look at some extensions that you can download yourselves by pressing `Ctrl` + `Shift` + `S`. But for now, we will be installing only one extension, the C# extension which enables intellisense for us, so in the search box, type in "C#" and install the very first extension you see named nothing but `C#` and is published by Microsoft.

![VSCode_C#_Extension](/img/tutorials/csharp/00_introduction/install_csharp_extension.png)


<!-- TODO: Fill in the rest of the page -->

