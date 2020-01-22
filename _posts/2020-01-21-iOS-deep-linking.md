---
title: iOS linking
date: 2020-01-21 00:00:00 -0600
cover-image: img/posts/patio-e-pepe.jpg
tags:
- mobile
- development
- design
- ux
layout: post

---
I'm working on a native iOS app at work. It's been an incredible awesome project for so many reasons. One of the reasons it's so fascinating is because it's given me a chance to understand more about how apps are put together on the backend and native development. Working mostly on web apps, React Native apps (which feel so webby in process), and websites, I mostly understood where front end and back end meet in the middle. In working with iOS developers, I'm learning a lot more about where back end and native meet, and where design needs to be in that conversation, specifically the user experience side.

Yesterday, I shared a playlist of music, that came together after asking friends on multiple social media about what music they'd recommend for a person spending her day off doing yard work, then later enjoying a sunset, and making some dinner to enjoy in said back yard. I took everyone's recommendations and put them into the following almost-five-hour Spotify list:

<iframe src="https://open.spotify.com/embed/playlist/3Tcwnx3ikFvyyRuM39etLd" width="300" height="380" frameborder="0" allowtransparency="true" allow="encrypted-media"></iframe>

It was a joy to put together and a few asked if I'd share the playlist, so I did—on both Twitter and Instagram. And then I tested both links, because, that's just something I always check. When I posted the link to Twitter, the following happened:

- Twitter embeds a playlist badge, which is clickable.

- When clicked the embed plays the first 30 seconds of the song, and encourages you to "Listen on Spotify"

- When you do, Twitter prompts with a  '“Twitter” wants to open “Spotify“' prompt which in turn, opens Spotify.

- Playlist played

<div class="limit">
<div class='embed-container'><iframe src="https://youtube.com/embed/X6V1QP4n43w" frameborder='0' allowfullscreen></iframe></div>
</div>

However, when it came to posting to Instagram, the following happened:

- Add link to bio

- In-app browser opens a link, a link from adjust.com, which suggests downloading the app

- If you click "download the app", it doesn't open the app (Spotify) if you already have it. It takes you to the App Store.

- If you click the top right "more options" to expose an action sheet, then you can open in Safari—or another default browser—and then load the web preview on the playlist with a large button reading "Play on Spotify"

<div class="limit">
<div class='embed-container'><iframe src="https://youtube.com/embed/Ge0RQYqfUjc" frameborder='0' allowfullscreen></iframe></div>
</div>

Neither of these options is perfect, however, one is severely less user-friendly than the other.

And then I found something even weirder. I tried going back to Twitter and deep press the playlist, and it opened the share action sheet (I'll spare from sharing it because it exposes contact names and photos). When I selected "Open in Safari", it opened Safari for a split second before rerouting to Spotify without the '“Twitter” wants to open “Spotify“' prompt.

And it gets worse for Instagram/Spotify from there. When I deep press the link to the playlist in the bio, it opens the same adjust.com "download app" link. When I use the share sheet to reopen in Safari, it opens the playlist without re-opening in Spotify.

There are a few things that fascinate me about this.

It's so interesting to me that this behavior is so different between the two apps that tried to access a third. I'm curious why they have a different experience. Is it the technology behind each app (are they both native?)?. Is this happening because of constraints set by Instagram and Twitter? Is it the fact that Instagram/Spotify might be using a service like adjust.com that is now making the user experience clunky? Which apps made these decisions and are they at the mercy of the other? Is it because Instagram is processing links in profile in a different way than the way Twitter has to (probably!)? I do not know the answer to either of these questions. What I do know is its making me think about how linking works in the app I'm working on.

Another thing that fascinating about this is that it gives me flashbacks to conversations about `href` targets in HTML and whether `_blank` was okay to use and when. It's fascinating watching the young adult field of web building, watch its teenage sibling grapple with the same thing they went through years before.

Finally, the last thing that really fascinated me is the type of music everyone shared. Hope y'all enjoy the playlist.


Also, if you're into Apple Music, my internet friend [Charles](https://twitter.com/charlesv/status/1219534732066770944?s=20) made the Apple Music of the list!

<iframe allow="autoplay *; encrypted-media *;" frameborder="0" height="450" style="width:100%;max-width:660px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.music.apple.com/us/playlist/patio-e-pepe/pl.u-qpaRaFogEP4"></iframe>
