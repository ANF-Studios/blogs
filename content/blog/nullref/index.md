---
title: "How to deal with Null Reference Exception"
description: "Here's a small article on how to fix null reference exception in Unity."
slug: nullref
date: 2021-02-13T12:02:32-05:00
draft: false
#categories:
#- C#
aliases: 
- /blog/nullreferenceexception
featuredImage: "" # nullref_thumb.png
---

<!--more-->

As a beginner, at some point or another, you must have encountered null reference exception while developing your application and, for some people it's really hard to understand how to fix it (mainly because, in my opinion, some game devs do not have prior knowledge of C#). So today, you'll be learning how to fix it, I'll try to simplify it as much as possible. So first of all, I want to start off with null reference exceptions because well, it's a really common programming mistake and commonly repeated especially by beginners, so I am going to guide you through about what this "Null Reference Exception" is and how to fix it.

So, why does null ref (short for null reference exception) even happen?
Well, the simplest answer for this could be that C# throws this exception when one of your variable is [null](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/null) which basically means
> a literal that represents a null reference, one that does not refer to any object. null is the default value of reference-type variables.

Is it an assigned value or not? Well, yes but actually no.

Let me break this down for you, your variable is allocated in memory i.e, it is stored somewhere in your RAM. And, when your un some function to access it, say some Unity function like [SetActive](https://docs.unity3d.com/ScriptReference/GameObject.SetActive.html) which sets a game object in your scene active or inactive (inactive means that it won't function but it still exists):
```cs
using UnityEngine;

public class MyScript : MonoBehaviour
{
    private GameObject myCube;
    
    void Start()
        => myCube.SetActive(false); // You shall see a null reference exception here.
}
```

![Null Reference Exception](/img/tutorials/unity/nullref/exception.png)

This is the output, nothing is really changed and our code does not work. Passionate beginners (perhaps ones like you, that could be one of the reasons you're here because you're stuck and some senior developer directed you here) often make this mistake without realizing, though this is nothing to be worried about.

Well, how do I know that my variable is null? As a programmer, you should debug your code, debugging. In software development, debugging is the process of finding and resolving bugs within computer programs, software, or systems.

The first thing that might come into your head is probably going to be `Debug.Log();`. It's really powerful (though there are several other ways to do this like the `print();` function or `Console.Write();`/`Console.WriteLine();`) and always helps you out.

So how do we tell this "logger" to tell us if our variable is null? Well, we're going to call our logger and say; hey logger, tell me if this variable of mine is null or not. To do so, we'll be using `Debug.Log();`, like so:
```cs
Debug.Log(myCube == null);
```

This would print `true` if the **variable is null** else it would print `false`.

![Is it null?](/img/tutorials/unity/nullref/null_variable_1.png)

Granted that this works perfectly fine and there's nothing really wrong with it, but personally, I like to prefer readability, so a good way of doing this would be to use the [`?:`](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/operators/conditional-operator) operator.

It should look something like this:
```cs
Debug.Log(myCube == null ? "Game object myCube is null" : "Game object myCube is not null");
```

What this'll do is print the first statement if `myCube == null` i.e, the variable is null and print the next one (instead of the first one) if it is not null. It's simple and makes it really readable:

![Is it null?](/img/tutorials/unity/nullref/null_variable_2.png)


Well, that's cool and all, but like.. I came here to know how to fix this, right? Tell me how to fix it. Gotcha, now that we've actually covered all the basic debugging ways, let's get to know how to fix that.

So, what do we first thing when we hear null ref? Keeping in view the defenition of null; a vairable not assigned, right? So we need to somehow assign it a value. In this case, it's a game object, a unity game object - so we will assign it our object to fix that error.

There are different cases of this, I'll be showing you two of those ways, firstly, we can try to cache our `myCube` object. But for that, I'll create a private Serialized object:
```cs
[SerializeField] private GameObject myCube;
```

Unity serializes only public objects, so if you really need this `myCube` variable to be private but still be serialized, you can use this SerializeField property. I'll save more of this for another blog, but for now, I recommend reading [UnityDocs/SerializeField](https://docs.unity3d.com/ScriptReference/SerializeField.html).

Anyhow, now you'll notice this in your inspector when you look at it:
![inspector](/img/tutorials/unity/nullref/inspector_script_field.png)

Now just drag and drop the cube object in there (or just click on the plus button to assign it) like so:
![Assign myCube](/img/tutorials/unity/nullref/assign.gif)

What we've done here is that we've "cached" our object - this is really great for runtime performance. And now, when we run our code, we should see that the null reference exception is now gone:
![Fixed results](/img/tutorials/unity/nullref/exception_fixed.png)

Quick side note, you can also create a new object instance, that'll also work out fine, it just at its core depends on what you really want to do.

Now if we want to access the SetActive property, we're going to need to access it. Which we can now do because we have the game object. Now, when we'll run this code, we won't see any errors - so far, you're code should look like this (that is if, you're following this tutorial in a sandbox playground project):
```cs
using UnityEngine;

public class MyScript : MonoBehaviour
{
    [SerializeField] private GameObject myCube;
    
    void Start()
    {
        Debug.Log(myCube == null ? "Game object myCube is null" : "Game object myCube is not null");
        myCube.SetActive(false);
    }
}
```
We have successfully set our object to inactive, cheers :tada:

So now we can access all these components being assured that we have have it working. There are other ways to access it, we're not going to get into those today however, but that's pretty much it. I really hope I could clear everything out, if you still have confusions or questions; I am often on discord (don't worry, if I'm not available, others are really helpful) so you can hit me up at [discord/ANF-Studios](https://discord.gg/fKWpK7A) :wink:

Other useful servers are [discord/Unity](https://discord.gg/Unity) and [discord/Brackeys](https://discord.gg/Brackeys).