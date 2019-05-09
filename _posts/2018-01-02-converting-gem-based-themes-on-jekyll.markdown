---
title: Converting Gem-based themes on Jekyll
date: 2018-01-02 20:12:00 -06:00
tags:
- jekyll
- code
- productivity
layout: post
---

Today, Greg was sharing an issue he was having with Jekyll installs and builds. I thought was something tied to Bundler or Jekyll 3.0 issues I've had in the past, but Ethan figured out that the `_site` folder wasn't building correctly and that a pretty awesome solution is working around the gem-based themes.

This site is built on Jekyll, but I want tinker with this more on a new project, rather than mess with this one. Check out the Twitter conversation and Ethan's helpful suggestions below. I'm bookmarking this, here, for myself and anyone else who adores Jekyll.

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Dear Jekyll users,<br><br>When I try to create a new site, only one directory gets created and a gem file is left. I’ve installed all of the things required in the getting started doc and confirmed they are recent versions.<br><br>What am I doing wrong? <a href="https://t.co/sqoyhb97Cc">pic.twitter.com/sqoyhb97Cc</a></p>&mdash; Greg Storey (@Brilliantcrank) <a href="https://twitter.com/Brilliantcrank/status/948284261362216960?ref_src=twsrc%5Etfw">January 2, 2018</a>

</blockquote>

Ethan's Solution from Jekyll's docs:

<blockquote class="twitter-tweet" data-conversation="none" data-lang="en"><p lang="en" dir="ltr">Those files are in the gem for the default theme. It sounds like you want to do this: <a href="https://t.co/BgPvhBL0fz">https://t.co/BgPvhBL0fz</a></p>&mdash; Ethan Leon (@ethangl) <a href="https://twitter.com/ethangl/status/948296299270590464?ref_src=twsrc%5Etfw">January 2, 2018</a>

</blockquote>

And then Uncle Dave pops in and teaches us all how to start a new Jekyll project sans-theme at all. Where has this been my entire Jekyll-using life?

<blockquote class="twitter-tweet" data-conversation="none" data-lang="en"><p lang="en" dir="ltr">If you want no theme to start off with, you have to do `jekyll new myblog --blank` I wish this was the default but guhck.</p>&mdash; Dave Rupert (@davatron5000) <a href="https://twitter.com/davatron5000/status/948297978233720834?ref_src=twsrc%5Etfw">January 2, 2018</a>

</blockquote>

<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
