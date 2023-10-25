---
title: "Modifying Expectations!"
datePublished: Mon Jul 18 2022 08:04:26 GMT+0000 (Coordinated Universal Time)
cuid: cl5qgnvsd069bpsnv0od7fc18
slug: modifying-expectations
cover: https://cdn.hashnode.com/res/hashnode/image/unsplash/JFeOy62yjXk/upload/v1658128974453/HAafV_-g3.jpeg
tags: internships, firefox, outreachy

---

Hello everyone, Welcome to the fourth blog of my Outreachy series.

I am **Janvi**, an outreachy intern of the summer 2022 cohort. I am working on the project **" Firefox Picture-in-Picture improvement"** under the guidance of my mentors **Kpatenio** and **Niklas**.  I am halfway done with my internship and the journey has been amazing so far. I feel pleased as this internship is really shaping me in every prospect and I am glad of having such a wholesome community and mentors.

![Firefox](https://www.mozilla.org/media/img/firefox/template/page-image-master.1b6efe3d5631.jpg)
Image : [Firefox](https://www.mozilla.org/en-US/firefox/)

This blog is all about Progress what I have accomplished and my modified goals for the second half of the internship.
For the final application of outreachy, we were asked to make a timeline of our project so I made a general outline and divided my whole project into multiple subtasks. After this, I was all set to go!
 
But wait!

Delays to projects happen. Sometimes we need to learn a new skill, or sometimes this can take longer than expected, there can be delays in coordination or getting responses, honestly, so many small factors can go wrong that one can never know how to take all of it into consideration. Hence, things can slip a bit behind schedule even when you’re giving it your best.

So my first week started with getting introduced to the community, knowing more about work culture, registering for the mailing list, updating the built environment, getting commit access, etc.

Then I started working on the bugs. The first bug was to add a highlight on hover to Picture-in-picture controls button when in fullscreen. Whenever you are working on a patch, you have to update it a number of times and then it gets merged.

One of the features I worked on which took a longer time than expected was "[To implement hover states for Picture-in-Picture playback controls](https://bugzilla.mozilla.org/show_bug.cgi?id=1772339)".
Started with knowing more about [Fluent](https://firefox-source-docs.mozilla.org/l10n/fluent/tutorial.html) strings and how [Localization](https://firefox-source-docs.mozilla.org/l10n/overview.html) works in Mozilla , brainstorming upon [Shortcuts](https://bugzilla.mozilla.org/show_bug.cgi?id=1772339#c16) to be displayed while hovering on playbacks controls for different Operating systems, and learning how to add and run [tests](https://firefox-source-docs.mozilla.org/testing/mochitest-plain/index.html) for patches.

![Screenshot 2022-07-17 at 4.29.16 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658074729868/drGAPGsh5.png align="left")
*Ref: Displaying hover state while hovering over the play button in the Picture-in-Picture window.*

*Image: Screenshot*

Another one was adding [subtitles support](https://blog.mozilla.org/en/products/firefox/firefox-picture-in-picture-rolls-out-subtitles/) in the Picture-in-Picture window for different video streaming sites. I added caption support for [voot](https://www.voot.com/) and figured out some sites which use [video.js](https://videojs.com/) video player. The interesting thing here is we can use the same wrappers for mostly all the sites which use video.js. Some of them are sony liv, mxplayer, Funimation, etc.

![mxplayer.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658054089731/-ah6Q-gZq.png align="center")
*Ref: MX Player showing subtitles support in Picture-in-Picture Window.*

*Image: Screenshot*

My Merged Patches during the internship period are - 

- [Patch 1](https://github.com/mozilla/gecko-dev/commit/636286877d37954ff3139cd1ecb88459f04ef369)
- [Patch 2](https://github.com/mozilla/gecko-dev/commit/da99f1a9eaa72d7e89c4a36e60c84622fa20ebb4)
- [Patch 3](https://github.com/mozilla/gecko-dev/commit/580833a1669865379b8f8956b51c913358d44b6d)

The major feature now we are working on is **To add more playback controls for Picture-in-Picture window** like Fullscreen, rewind, video duration and etc.
Our ultimate goal is To make Picture-in-Picture more awesome and user-friendly so users can use the "always on top" picture-in-picture window while continuing to work in other tabs.

This internship is indeed going to be a great experience for me. Looking forward to growing more.


Thanks for reading! Please check out my other blogs [here](https://janvi01.hashnode.dev/).

You can connect with me on [Twitter](https://twitter.com/janvibajo01) or reach out to me via [email](mailto:janvibajo1@gmail.com) for any help. :)

