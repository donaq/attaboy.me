# Almost a Year Later...

Well, here are some updates.

## A New Language

After joining Singapore Power, I had to learn [a new language](https://golang.org/). There are a few things I quite like about it.

1. [defer](https://tour.golang.org/flowcontrol/12): helps a lot to mitigate that problem where you forget to close resources that require it

2. [context](https://golang.org/pkg/context/)s: I mainly use it to terminate related concurrent threads of execution at the same time(ish)

3. [select](https://tour.golang.org/concurrency/5): naise

4. [channel](https://tour.golang.org/concurrency/2)s: **really** naise

The combination of `context`s, `select` and channels just makes concurrency in Go a whole lot easier to manage, in my opinion. Of course, you can still make things hard for yourself by resorting to mutex locking and shared variables, but seriously, just `select` on channels if that is at all an option.

## Deep Learning

One of the things I am currently most interested in is machine learning. Singapore Power is a company that believes in developing its people, so as part of my personal development plan for last year, I spent the past 5 months doing the [deep learning](https://www.coursera.org/specializations/deep-learning) specialization by Andrew Ng at Coursera, totally sponsored by the company. Bloody decent of them. We're still hiring!

Anyway, I highly recommend this specialization to anyone who is interested in the subject and don't know where to start. I think Andrew Ng has a real knack for giving students good intuitions for complex things, although the programming assignments are a bit too simple. Now that I have gone through the course, I think my next step is to actually do a project where I get to apply what I've learnt, but first...

## [attaboy.me](https://attaboy.me)

Finally got round to continuing work on some projects that I had been putting off because I was busy with the course.

1. SSL for this site (thanks again [letsencrypt](https://letsencrypt.org/)!) Honestly, no one reads this site, so no one cares, but hey, no one in between you and me needs to know what goes on here, baby.

2. Setting up a [webhook](https://developer.github.com/webhooks/) so that this site updates itself when I push to github. Previously, I had a cron job that did a `git pull` every minute. I know, I know, it was ugly as fuck, not to mention discourteous to github, but hey, it worked. The reason why I did it that way was because I was reluctant to set up server side logic on a raspberry pi. At the time, I would have probably done it in Python. However, with my newly acquired 1337 Go skillz, it became less of an issue. The compiled go binary I'm running to handle the webhook consumes very little memory.

3. Gotta get [topovica](https://github.com/donaq/topovica) to a state I am happy to use. Either that or totally give it up. I have also been putting this off because I was doing the course.

## Bejeweled Blitz Bot, Machine Learning Version

I had previously written a [bot](https://github.com/donaq/blitzbot) to play Bejeweled Blitz for me at superhuman levels. This was accomplished by encoding my human knowledge of how to play this game into Python and having it click on the game board faster than a human could. I will, after having either finished or given up on topovica, attempt to get my computer to learn how to play the game on its own with just pixels and current score as inputs. This, and presenting how it was done, will be part of my development plan for the 2018/2019 work year. I'll try to document what I do here as I do it.

The next few months promise to be fun. 😄
