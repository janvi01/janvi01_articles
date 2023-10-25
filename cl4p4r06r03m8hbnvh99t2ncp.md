---
title: "Outreachy - Everybody Struggles!"
datePublished: Wed Jun 22 2022 05:03:28 GMT+0000 (Coordinated Universal Time)
cuid: cl4p4r06r03m8hbnvh99t2ncp
slug: outreachy-everybody-struggles
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1655277178702/b6PuJTWk1.jpeg

---

Hello everyone, Thanks for dropping by!

This is the second blog of my Outreachy internship. It's been three weeks since the internship started and the journey has been phenomenal so far. I had a meeting with my mentors, it was a great feeling talking and getting introduced to them.

Coming to struggles, it starts the moment we start professional communication!! 
One of the most valuable skills I'm learning in this internship is the ability to speak with people in a professional setting. Working professionally for the first time can be overwhelming, it gives you real-world experience. <br/>
Initially, I was very hesitant to ask questions to my mentors, I thought they would judge me for asking such naive questions. But I was totally wrong, they are very friendly and helpful. Whenever I get stuck in my work or I don't understand something, I immediately ask them and they are always there to help me out. 

**Mozilla** has a particular process to contribute. It has **Bugzilla**, which is a website to track bugs.
There is **Phabricator** where we create and update patches. It also has a **Searchfox** which I was unaware of. Searchfox is a source code indexing tool for Mozilla Firefox. It has become my best friend now. It can be added to the browser as a search engine and as a bookmark.

While working on a Bug, I came across the term [**Fluent**](https://firefox-source-docs.mozilla.org/l10n/fluent/index.html) which I was completely unaware of. 
It is a system used for making Firefox available in several locales (languages, locations, cultures). 
It was completely a new vocabulary term for me. 

Fluent introduces a file format designed specifically for easy readability called **FTL - Fluent Translation List**. It uses unique identifiers basically IDs called **l10n-id**. 
Previously I was updating a title of a button using JS like :
```
document.getElementById("play").title = "Play"
```
Now using Fluent it can be done like :
```
// Creating a new string Id 
pictureinpicture-play =
   .title = "Play"
// Referencing the ID in Html using data-l10n-id
<button data-l10n-id="pictureinpicture-play"></button>
```

Fluent has some [major benefits](https://firefox-source-docs.mozilla.org/l10n/fluent/tutorial.html#major-benefits) for both developers and localizers. It aims to replace all existing localization models currently used at Mozilla.

Besides this, currently, I am brainstorming on how to create and add [Tests](https://firefox-source-docs.mozilla.org/testing/mochitest-plain/index.html#) for patches. By creating a test, we make sure the changes work as expected. We can't just assume our patch will work all the time.

While working on your patches, the Reviewer always asks:

-How about adding a test?

And you need to write a test… It’s often more challenging than the initial change because you need to reproduce the environment your changes are visible.

Nevertheless, I am striving to improve myself day by day and make progress.
> “The expert at anything was once a beginner.” – Helen Hayes

The completion of these tasks and appreciation is giving me the confidence to **believe in myself**.
I am hoping to get the best out of this internship and my growth curve goes upward and upward. :)

Thankyou!





