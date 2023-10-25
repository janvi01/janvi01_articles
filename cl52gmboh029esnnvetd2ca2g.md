---
title: "A look into my project : Firefox Picture-in-Picture"
datePublished: Fri Jul 01 2022 12:56:45 GMT+0000 (Coordinated Universal Time)
cuid: cl52gmboh029esnnvetd2ca2g
slug: a-look-into-my-project-firefox-picture-in-picture
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1656677432770/OE4B-Ks1s.webp
tags: firefox, opensource, outreachy

---

Hello everyone!

Welcome to the third blog of my Outreachy Internship.
This blog is all about explaining my project to a newcomer. 
I am working on the project "**Firefox Picture-in-Picture Improvements**" under the guidance of my mentors **Kpatenio** and **Niklas**.



## What is Mozilla Firefox?
**Mozilla Firefox**, or simply **Firefox**, is a free and open-source web browser developed by **Mozilla** in **2002**. The web browser lets one access information in form of text, audio, images, and videos from all around the world.

![firefoxLogo](https://seeklogo.com/images/F/firefox-quantum-logo-BF9C2C7D9D-seeklogo.com.png align="center")
*Firefox logo by [seeklogo](https://seeklogo.com/ align="center") .*

Firefox has an interface that is very user-friendly and the user can use a number of add-ons on top of that user can customize the browsing also. Firefox is a huge Open-Source Software that makes it for anyone to see the code and have a look at it how it works. It is self-hosted [here](https://hg.mozilla.org/mozilla-central/) and anyone is welcome to contribute to it. Feel free to check out the [documentation](https://firefox-source-docs.mozilla.org/setup/index.html#) for getting started.

So Firefox browser has got a feature called **Picture-in-Picture** that makes multitasking with video content easy.

## What is Firefox Picture-in-Picture?
So basically, **Picture-in-Picture** is a feature that allows users to pop videos out of their webpage into a floating, **"always on top"** window so they can watch while continuing to work in other tabs.

![Pictureinpicture](https://www.mozilla.org/media/img/firefox/features/pip/pip-hero.714092ecfa0d.jpg align="center")

*Image credit : [Firefox](https://www.mozilla.org/en-US/firefox/features/picture-in-picture/)*

### Features :

- ** Full-screen view ** <br/>
On Double-clicking the picture-in-picture player window, the video appears on full-screen. Double click again to exit.

- **Player controls**<br/>
The picture-in-picture player comes with different controls button. The user can easily play/pause the video, close, and access the subtitles using the controls available while playing the video in the picture-in-picture window.

- **Keyboard shortcuts** <br/>
The picture-in-picture player video controls can be accessed via the keyboard.
Some of the shortcuts are:<br/>
Play/Pause - `Space`<br/>
Mute - `Cmd + ↓` (for macOS), `Ctrl + ↓` (for non-macOS)<br/>
Unmute - `Cmd + ↑` (for macOS), `Ctrl + ↑` (for non-macOS)<br/>
Seek back 5 secs - `←`<br/>
Seek forward 5 secs - `→`<br/>

*To know all shortcuts, visit [here](https://support.mozilla.org/en-US/kb/about-picture-picture-firefox).*

- **Subtitles support**<br/>
The picture-in-picture player comes with subtitles and captions support. The subtitles or captions can be turned on the in-page video player, and they will appear in Picture-in-Picture when launched.

Supported docs : [Firefox Picture-in-picture](https://support.mozilla.org/en-US/kb/about-picture-picture-firefox) , [Firefox features](https://www.mozilla.org/en-US/firefox/features/picture-in-picture/)




## How does picture-in-picture works?

#### **How does picture-in-picture work for Firefox users?**

1. Play any video in your Firefox browser.
2. Click the Picture-in-Picture button (as seen in the image below) that appears over the video, and it’ll pop out.
3. Go around to other tabs or outside of Firefox. The video stays put!


![PIP icon](https://cdn.hashnode.com/res/hashnode/image/upload/v1656599352899/ELCApPj5_.png align="center")
*Image: Screenshot*


#### **How picture-in-picture is implemented on the web?**

While browsing if a user encounters a `<video>` element and hovers over it, a mouse event is fired and `PictureInPictureToggleChild` causes the Picture-in-picture toggle button to appear over that `<video>` element.
If a user clicks on the toggle to open the video in the PIP (i.e. Picture-in-Picture) window, `PictureInPictureToggleChild` dispatches an event which upon handling, `PictureInPictureLauncherChild` sends a `PictureInPicture:Request` message to the parent process. It opens up the always-on-top player window, with a remote `<xul:browser>` that runs in the same content process as the original `<video>`.

The interesting part here is the Picture-in-Picture window is a browser window itself with most of the surrounding window decoration collapsed. Flags tell the operating system to keep it on top. That browser window contains a special <video> element that runs in the same process as the originating tab.

To know more about architecture and the inner workings of Picture-in-Picture, Please go through this [documentation](https://firefox-source-docs.mozilla.org/toolkit/components/pictureinpicture/pictureinpicture/index.html).

Want to know about the history of Picture-in-Picture? Feel free to check out this [blog](https://hacks.mozilla.org/2020/01/how-we-built-picture-in-picture-in-firefox-desktop/) by our Senior [Mike conley](https://www.mikeconley.ca/blog) .






## What exactly I am working on?

To improve Picture-in-picture overall and make it more user-friendly.

Currently, there are only specific video player controls available in the Picture-in-picture window. Adding more player controls would be a great enhancement for the Picture-in-picture window.

Another major enhancement is to add subtitles support in the picture-in-picture window for different video streaming sites by adding site-specific wrappers.
Recently, Firefox released version 100 where it shipped subtitles and captions support for various sites like Youtube and Netflix.

![PIPSubtitles](https://cdn.hashnode.com/res/hashnode/image/upload/v1656599976393/ZkDno4_xT.png align="center")

*Image: Screenshot*

The Picture-in-picture is a product of firefox written in HTML and powered by JavaScript and CSS.

There are difficulties that I face as I am doing my work. One of them is to work with [Fluent](https://firefox-source-docs.mozilla.org/l10n/fluent/tutorial.html) string and the other is how [localization](https://firefox-source-docs.mozilla.org/l10n/index.html) work. Firefox uses Fluent for making it available in several locales (languages, locations, cultures).

Another interesting thing that I learned is adding and running a [test](https://firefox-source-docs.mozilla.org/testing/mochitest-plain/index.html). Adding a test seems more challenging than the initial change because you need to reproduce the environment. 
Thanks to my mentors for being so supportive every time, I don't hesitant a bit asking question to them whenever I am stuck.


Altogether, I am pleased about my progress so far. It feels extraordinary to contribute to Firefox which millions of people use. I am looking forward to learning more exciting things and continuing the project with a positive spirit. 

Thanks for reading! Please check out my other blogs [here](https://janvi01.hashnode.dev/).

You can connect with me on [Twitter](https://twitter.com/janvibajo01) or reach out to me via [email](mailto:janvibajo1@gmail.com) for any help. :)

