---
title: "Guide for Newcomers contributing to Firefox."
datePublished: Wed Sep 21 2022 04:59:27 GMT+0000 (Coordinated Universal Time)
cuid: cl8b5ocwl09alv6nvdh791tuy
slug: guide-for-newcomers-contributing-to-firefox
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1663735264446/9GsqtLyTT.jpeg
tags: firefox, mozilla, opensource

---

Are you interested in contributing to one of the most widely used web browsers in the world? Mozilla Firefox, developed by the Mozilla Corporation, is a free and open-source web browser that runs on multiple operating systems. If you're new to contributing to Firefox, don't worry! This guide will walk you through the process of setting up your local development environment, finding bugs to work on, and submitting your first patch. Not only will you gain real-world experience with a large codebase, but you'll also be contributing to software used by over 100 million users worldwide. So let's get started!

## What is Mozilla?

Mozilla is a free software community founded in 1998. The Mozilla community uses, develops, spreads, and supports Mozilla products, thereby promoting exclusively free software and open standards.

Mozilla's current products include the [Firefox](https://en.wikipedia.org/wiki/Firefox) web browser, [Thunderbird](https://en.wikipedia.org/wiki/Mozilla_Thunderbird), [Bugzilla](https://en.wikipedia.org/wiki/Bugzilla) bug tracking system, Gecko, and others.

![MozillaLogo](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d2/Mozilla_logo.svg/560px-Mozilla_logo.svg.png align="center")

Let's talk specifically about Mozilla Firefox, or simply Firefox. It is a free and open-source web browser developed by Mozilla Corporation. Firefox runs on Windows, OS X, Linux, and Android. Firefox lets one access information in the form of text, audio, images, and videos from all around the world. It has an interface that is very user friendly and the user can use a number of add-ons on top of that user can customize the browsing also. It has more than 6,000 extensions, users can customize the browser with more than 500 themes.

![](https://upload.wikimedia.org/wikipedia/commons/thumb/a/a0/Firefox_logo%2C_2019.svg/242px-Firefox_logo%2C_2019.svg.png align="center")

## Why contribute to Mozilla?

* To get real-world experience with a large codebase.
    
* To contribute to software that is used by 100+ million users.
    
* To learn how to write good code and submit great pull requests/patches for code review.
    
* To build your resume as all of your open source contributions are public and demonstrate the skills you have mastered and the projects you've tackled.
    
* To connect with a community, interact with like-minded developers, and build connections along the way.
    

## How to get started?

To contribute to Mozilla Firefox, you will have to set up to build Firefox on your computer locally. The whole process can be a bit long, and it might take time to get things right.

The Mozilla community prides itself on being an open, accessible, and friendly community for new participants. If you have any difficulties getting involved or finding answers to your questions, please come and ask your questions in our [chatroom](https://chat.mozilla.org/#/room/#introduction:mozilla.org), where we can help you get started.

### Step-1 :

Create your account on :

* [Bugzilla](https://bugzilla.mozilla.org/) - It is a web-based general-purpose bug-tracking system and testing tool originally developed and used by the Mozilla project. (Make sure you enable [Two-Factor Authentication](https://bugzilla.mozilla.org/userprefs.cgi?tab=mfa) here)
    
* [Phabricator](https://phabricator.services.mozilla.com/) - It is a software development collaboration tool mainly for code review. (Please obtain an [API Token](https://phabricator.services.mozilla.com/settings) here)
    

### Step-2 :

There are two ways to set up the Mozilla repository.

1. using Git.
    
2. using Mercurial.
    

Since I was familiar with Git, I opted for git workflow and this guide will take you through setting up as a contributor to Mozilla-central, the Firefox main repository, as a git user. To set up using Mercurial, follow the guidelines mentioned [here](https://firefox-source-docs.mozilla.org/contributing/contribution_quickref.html#clone-the-sources).

First and foremost, you will need to download [git-cinnabar](https://github.com/glandium/git-cinnabar) which is a git remote helper to interact with mercurial repositories. To download git-cinnabar, make sure you have this installed:

* Git - https://git-scm.com/downloads
    
* Python3 - https://www.python.org/downloads/
    
* Java - [https://www.java.com/en/download/](https://www.java.com/en/download/)
    
* Mercurial - https://www.mercurial-scm.org/wiki/Download  
    *To download Mercurial, the preferred way should be via* `homebrew`*.*
    

Check that you have successfully installed Mercurial by running:

```bash
hg --version
```

Now, let's head over to download [git-cinnabar](https://github.com/glandium/git-cinnabar).

* Clone the repository.
    

```bash
git clone https://github.com/glandium/git-cinnabar.git
```

Navigate to the cinnabar directory. `cd git-cinnabar`

* Download git cinnabar.
    

```bash
git cinnabar download
```

> Note: If you get an error “Fatal error: curl/curl.h: No such file or directory”, do this: `sudo apt install curl` followed by `git cinnabar download`. You can then move on to its usage.

* Build it.
    

```bash
make
```

Add the git-cinnabar directory to your PATH. If you have another git-remote-hg project in your PATH already, make sure the git-cinnabar path comes before.

```bash
export PATH="$PATH:/somewhere/git-cinnabar"
echo 'export PATH="$PATH:/somewhere/git-cinnabar"' >> ~/.bash_profile
```

### Step-3 :

* Clone the Mozilla-unified repository:
    

```bash
git clone hg::https://hg.mozilla.org/mozilla-unified
```

* Once the cloning is done, navigate to the `mozilla-unified` directory and build:
    

```bash
cd mozilla-unified
```

```bash
./mach build
```

This will check for dependencies and start the build. This will take a while, a few minutes to a few hours depending on your hardware.

If you don’t plan to change C++ or Rust code, an [artifact build](https://firefox-source-docs.mozilla.org/contributing/build/artifact_builds.html#understanding-artifact-builds) will be faster. (You will be asked to choose build type while building.)

You will be asked to enter your Phabricator ID API token.

Tadaa🥳 , You have successfully set up the Mozilla repository locally, and now you are all set to start working on bugs.

### Finding a Bug to work on

* Find a bug that is identified as a good fit for new contributors.
    
* [Codetribute](https://codetribute.mozilla.org/) - Look for bugs based on your skill.
    
* Search on Bugzilla filtering with the keyword `Good First Bugs` - https://mzl.la/2yBg3zB
    
* Comment on the bug ticket that you think to work on something like "Hey, I would like to work on this ......"
    
* Start working on... Search your component/product code using search fox which is a source code indexing tool for Mozilla.
    
* Make the required changes and submit a patch. (Patch basically means Pull request.) Follow [these](https://firefox-source-docs.mozilla.org/contributing/contribution_quickref.html#to-write-a-patch) guidelines to create and submit a patch.
    

> Yay, you have made your first patch...🎉

Here is the link to reference articles.

* https://github.com/glandium/git-cinnabar/wiki/Mozilla:-A-git-workflow-for-Gecko-development
    
* https://firefox-source-docs.mozilla.org/contributing/contribution\_quickref.html#firefox-contributors-quick-reference
    
* https://github.com/glandium/git-cinnabar
    
* https://firefox-source-docs.mozilla.org/mobile/android/geckoview/contributor/mc-quick-start.html
    

You can connect with me on [Twitter](https://twitter.com/janvibajo01) or [Linkedin](https://www.linkedin.com/in/janvi01/).