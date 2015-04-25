# About

This website was started for a few reasons.

1. I felt the urge to start writing again.
2. I had just gotten a static IP and I was wondering what to do with it. I then had the brilliant idea that maybe I should try hosting a website using a [Raspberry Pi 2](https://www.raspberrypi.org/).

So here we are. I have been noting down ideas for stories for a while now, so I will publish them here, they will go viral, and then I will become a billionaire! BWAHAHAHA!!!

---

## About the author

Despite all indications to the contrary, he is not crazy. That is, I am not. Why was I speaking in the third person again?

Ok. Start over.

I don't intend to keep my identity secret. I also do not intend to explicitly state my identity here. I used to maintain a blog with a rather flamboyant public persona and it had a modest readership, but I want this site to be about my thoughts and the stuff I write rather than about me. Having said that, if you really want to find out who I am and you are prepared to do some internet sleuthing, it should not be too difficult. Honestly, though, it is not going to be worth your effort. I am rather nondescript in real life... by day. At night, I patrol the streets of my city, fighting crime. Ok, not really. I would do that, but then it gets so hot in that latex suit, and it doesn't fit so well these days because of my burgeoning paunch.

---

## Technical Stuff (non-geeks stay away)

Given that the RPi 2 is not the most powerful computer in the world, I decided that the server must do as little computation as possible. Hence, the only interactivity on the site is achieved through Javascript. I am actually quite curious about how much traffic this setup can support before I will be forced to move it to a more professional milieu. I must remember to add some analytics to this shit...

Ok, I digressed. Anyway, I am also partial to [vim](http://www.vim.org/) and [the command line (no, not fucking MS-DOS, you plebs)](https://www.gnu.org/software/bash/bash.html), so, since I did not fancy editing HTML manually and since I was trying to learn [clojure](http://clojure.org), I decided to write my own CMS for a static [markdown](https://github.com/chjj/marked) site in clojure. Actually, it has only two commands, namely `create` and `publish`, so calling it a CMS is perhaps a bit of an exaggeration, but fuck it, this is my site, so I'll call it whatever I want.
