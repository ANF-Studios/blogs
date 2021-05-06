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

{{<admonition tip "My CodeCov and AppVeyor configuration" false>}}
If you're wondering if you can see my configuration, check out one of my projects; [WinPath](https://github.com/ANF-Studios/WinPath) -- people found it helpful as it's super simple. Don't forget to star it if it's helpful for you too :wink:. 
{{</admonition>}}

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

## Setting up CodeCov

Considering you have a CodeCov account, visit codecov.io/<version control\>/<username\>/ -- in my case; https://codecov.io/github/ANF-Studios/ -- and once there, create add/import a new repository:

![Add a new repository](add_new_repository.png)

Alternaitvely, you can directly visit codecov.io/<version control\>/<username\>/<repository\>.

Once there, you should see something like this:

![Initial CodeCov repository page](codecov_initial.png)

Keep note you might need to activate the repository in its settings if necessary. You should also notice your token, you don't really need it if your repository is public and your CI is any of Travis, CircleCI, AppVeyor, Azure Pipelines or GitHub Actions, otherwise, you do.

Perfect! We now have added our project to CodeCov, now, we need to set up AppVeyor. I trust that you already have a CI, so we'll skip the adding a codecov project part. Oh and, it usually doesn't matter what CI you use.
