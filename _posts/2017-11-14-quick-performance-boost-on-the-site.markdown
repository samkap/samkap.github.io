---
title: Quick performance boost on the site
date: 2017-11-14 19:16:00 -06:00
tags:
- code
- performance
layout: post
cover-image: /img/desktop-01-start.png
---

I'm sitting at home, with a sore throat and an almost-gone fever. I loathe feeling unproductive. And, with Firefox's new blazing fast, Quantum, I can't help but feel level more sick and tired. In order to cheer myself up and feel mildly productive, I thought I'd pick apart my site with a few performance speed tools, but briefly. I know better than to get too deep into code when not in a focused state of mind. So, I'll keep this brief and write I go through each step. The following are the steps I took:

## 1. First, re-read Dave's posts on RWD Bloats.

Dave's posts are [one](daverupert.com/2014/07/rwd-bloat/) and [two](http://daverupert.com/2014/07/rwd-bloat-part-ii/) on RWD bloat. I don't fully suspect RWD being the main culprit, but let's see. Based on Dave's advice, check my grades with quick tests from [Google PageSpeed](https://developers.google.com/speed/pagespeed/insights/) and [WebPageTest](https://www.webpagetest.org/).

### Google PageSpeed

![Google PageSpeed when I started, showing two suggestions](/img/desktop-01-start.png)
{: .full}

Both Mobile and Desktop have the same issues. According to Google, two important things to fix are: "Eliminate render-blocking JavaScript and CSS in above-the-fold content" that can be broken up into a few steps, and "Leverage browser caching", which I have no idea how to do, yet. So, this, friends, I will not be doing at this time. I would hate to misread something while sick and make a big mistake. So I'll return to this later.

![Google PageSpeed when I started, showing what was optimized ](/img/desktop-02-start.png)
{: .full}

These are things I'm not being lazy about, at least on this page, but I'm glad that images are optimized (yay [ImageOptim](https://imageoptim.com/) but if you know of a great Jekyll plug-in that could do this, let me know!

### WebPageTest

![webpagetest-start.png](/img/webpagetest-start.png)
{: .full}

Yay! Only one F! This is **just** like school all over again. Kidding. But according to this Typekit is out of control, making up over 54-point-freaking-7-percent (54.7%) of my site's bytes. That seems like a lot and I don't like. Also, I have six images on home, and I don't quite see why until favicons have anything to do with it. Now armed with knowledge, let's see what we can do about it. Here goes!

## 1. Moved Typekit to below my content

So, before you get mad at me, know that I'm mad at me. I do know better, I was being lazy for a long time. So now my Typekit codes, live in a `scripts` includes file that is included after my `</body>` tag.

## 2. Mess with Typekit Settings

![typekit-01.png](/img/typekit-01.png)
{: .full}

Log into Typekit and see if I'm missing any optimization settings there. My kit is 64k, 54k if I don't keep the OpenType feature. For now, I will keep it on and maybe come back to this later.

![typekit-02.png](/img/typekit-02.png)
{: .full}

I jumped into my Kit Settings and saw a "Optimize performance" option. It links to [more info](https://helpx.adobe.com/typekit/using/optimizing-performance.html), which states:

> Increasing the cache timeout means that you will no longer be able to make quick changes to this kit. When this option is enabled, updates may take up to a week to be visible to all your visitors; disabling the option won’t take full effect until after a week, either. Use this option only if you don't plan to make any further changes to your kit.

This is interesting and I don't need to change my fonts anytime soon, so I check it.

## 3. Now, this six image thing

Okay, so it is favicons. I don't need six. I should only have three, I think. One favicon, that photo of me, and my logo. The other three are coming, mainly for the purpose of serving as icons on mobile devices. I don't know about anyone else, but I don't even have my own site on my home screen. I feel like this is unnecessary to keep, so I take it out of my `head` includes, and in the process, clean up spaces and unused code in six other includes. I feel better about it, but I'm not sure if it's actually helping yet.

I also, re-optimized my logo (7k, no change) and the photo at the bottom of me (15.8k to 14.3k).

## Quick Results

After taking maybe 45-90min with a few random breaks and about six commits, here's how the page did:

### Google PageSpeed Results

![Google PageSpeed Results](/img/desktop-01-end.png)
{: .full}

I went from a 75 on Mobile and 87 on Desktop, to 87 on Mobile and 95 on Desktop! Yay, so that makes me excited for when my brain and body aren't all fever-y and I can dive into this caching stuff.

### WebPage Test Results

![webpagetest results which went from 1.487s to 1.168s, fully loaded](/img/webpagetest-end.png)
{: .full}

For this I was able to shave off a few hundredths of a second, to reduce load time. I did get rid of some images and added Disqus back in. Not sure how much all of this is playing into it. On the first run, load time came down from 1.363s to 1.125s, with the first byte at down from 0.230s to 0.168s. Fully loaded came down the most from 1.487s to 1.168s. I took out favicons and down-saved my images. The fonts in bytes were still in the 50s but I know 10kb came out from unchecking OpenType features. My sleepy and now hungry guess is the remaining 5kb came from image optimizing and making removing other favicons.

<style>
article img {
border: 2px #004A55 solid;
}
</style>
