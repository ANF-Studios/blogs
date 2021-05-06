---
title: "How to setup Codecov, C#"
description: "Here's a quick tutorial on how to set up CodeCov with C# using AppVeyor!"
slug: setup-codecov
date: 2021-05-06T12:23:02-04:00
draft: true
categories:
- Other
aliases:
- /blog/how-to-setup-codecov
#featuredImage: null
author: "ANF-Studios"
---

<!--more-->

As a newbie or experienced programmer, you might have faced some issues when setting up [CodeCov](https://codecov.io), because I know I did. Being aware of how hard it can be, but still being able to do so (because I love DevOps personally) despite of that is great, but I'm also going to share how I did so!

Before we start, keep note that my project uses:
| Property          | Value                                                            |
| ----------------- | ---------------------------------------------------------------- |
| Language          | C#                                                               |
| Version control   | GitHub*                                                          |
| CI                | AppVeyor*                                                        |
| Testing framework | xUnit**                                                          |
| *                 | This is what I'll use, however, it doesn't *specifically* matter |
| **                | You can use any                                                  |

Now let's get started!
