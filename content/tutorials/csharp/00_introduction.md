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

Now that we have the C# extension, *the extension* (not VS Code itself) will install some tools that are required for debugging. While that is working, you also need to some how convert your text-based "code" into some binary form to run it, that's really important because that's just "[intellisense](https://en.wikipedia.org/wiki/Intelligent_code_completion)" you have and that doesn't have much worth without the actual tool to convert it, it's called the C# "compiler", that complies code and it's called .NET (pronounced as "dot net"). And yes, you also need to install dotNET to build tools.

Now if you're wondering what that .NET Framework thing-y was when updating Windows *specifically*, well, that's the "runtime" framework that *only* allows you to run dotNET Framework applications. But what we're installing is called dotNET, literally just dotNET. It's nothing more.

Before we head over, I want to explain to you about .NET Framework, .NET Core and dotNET.

- .NET Framework is a runtime framework that runs on Windows and is a bit older.
- .NET Core is a newer version of .NET Framework and runs better because the previous mistakes, or rather design flaws were now fixed but it does not really matter if you ask me. dotNET Core runs on all Windows, MacOS and Linux.
- .NET is so far, at the time of writing this, the newest framework which I highly recommend for you to adopt it and it does run on all Windows, MacOS and Linux.

Alright, let's get to installing it! Firstly, head over to [dotNET.Microsoft/Download](https://dotnet.microsoft.com/download) and select .NET 5.0 - or whatever is the latest **recommended** specification.

![dotNET](/img/tutorials/csharp/00_introduction/dotnet.png)

I don't know how the screen looks like on 32 bit systems, but if you are on one, **DO NOT** install the 64 bit version, it would not work. And make sure to install the "SDK" and not the runtime, you don't need that. This is because the SDK packs the runtime within it and also the development tools.

After that's installed, once again, restart your pc just in case if you want to, I highly recommend it however just to stay safe. If it does ask you to, then you really have no option at all.

Great! We have everything we need set up!

Now let's move on to the fun part, open back up the VS Code window and click on the terminal and type in `dotnet new console`.

Now a few things, if you do not see the terminal, press Ctrl + Shift + `.

You can also press the new terminal button from Terminal -> New Terminal.

![New_Terminal](/img/tutorials/csharp/00_introduction/new_terminal.png)

Now that you've run that command, you should see this or a similar output:

![dotNET_New_Output](/img/tutorials/csharp/00_introduction/dotnet_new_output.png)

Now you will see a csproj file, a cs file and an obj folder. Considering that you have .NET installed and the extension is running, it will ask you to "Generate Assets", always press yes as you need those, they will be a time-saver so that you don't need to set the project up.

![Generate_Assets](/img/tutorials/csharp/00_introduction/generate_assets.png)

Now you will see some folder(s), notably the `.vscode` folder. That is responsible for telling VS Code how we want to run our application within VS Code.

Now every setting is the nice, however there's this one config value I want to change, personally I like when our application is launched in a new window instead of the same one. So what I'll do is open up the `.vscode` folder by clicking on it in my explorer (in VS Code) and open up `launch.json`. Finally, this is how it looks, for me:
```json
{
    "version": "0.2.0",
    "configurations": [
        {
            // Use IntelliSense to find out which attributes exist for C# debugging
            // Use hover for the description of the existing attributes
            // For further information visit https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger-launchjson.md
            "name": ".NET Core Launch (console)",
            "type": "coreclr",
            "request": "launch",
            "preLaunchTask": "build",
            // If you have changed target frameworks, make sure to update the program path.
            "program": "${workspaceFolder}/bin/Debug/net5.0/learning_csharp.dll",
            "args": [],
            "cwd": "${workspaceFolder}",
            // For more information about the 'console' field, see https://aka.ms/VSCode-CS-LaunchJson-Console
            "console": "internalConsole",
            "stopAtEntry": false
        },
        {
            "name": ".NET Core Attach",
            "type": "coreclr",
            "request": "attach",
            "processId": "${command:pickProcess}"
        }
    ]
}
```

I want to change that `"console"`'s value from `internalConsole` to `externalTerminal`

![External_Terminal](/img/tutorials/csharp/00_introduction/external_terminal.png)

And that's it, we're all set up and we are reading to code! You can close `launch.json` and open up `Program.cs`. What you see is some basic code:
```csharp
using System;

namespace learning_csharp
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

These are only a few lines however, it can be complex to understand for some of you. Forget everything in there, just focus on `static void Main(string[] args)`. What that means is that `Main` is the main method meaning it tells our program where to start running, or rather executing. Without the main method, programs don't run as they don't know where to start. About static, well that means that there can't be more than one instance of that Main method, in programming, you can create more than one objects. And that completely makes sense, for example we have a "class" which is contains everything we can access user data, the class called User. We can access every variable in it, now it wouldn't really make sense to make it static because there can be more than one user, marking it as static would only really just not allow to have more user instances. That is a complex topic, we'll leave that for another lesson.

Now void, what does void mean? Is it some portal to nothing? Well, kind of, but no, not really. `void` means that our main method will not return anything, that's all you need to know for now.

`string[] args` is the argument of the main method. When we launch any application in our operating system, it may (or not) be launched with a few arguments, those arguments are stored there. You do not need to have it, you can freely remove `string[] args` though keep note that you do need the brackets and you can change `args` to *almost anything* you want to name it unlike the Main method.

Inside our main method, there is this thing called `Console.WriteLine("Hello World!");`. As you might have guessed, this tells our console; hey console, print whatever is __between__ these two double apostrophes. Now will it actually do that? I'm not going to say anything because *it may or may not*. There's only one way for you to find out :eyes:

<!-- TODO: Fill in the rest of the page -->

