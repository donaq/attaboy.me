# Topovica Done, Blitz Bot Next

In my [previous post](/#posts/blag/12), I said that I was going to get [Topovica](https://github.com/donaq/topovica) to a state that I am happy with. I am happy to say that I have finally done it! If you're too lazy to click on the github link to see what it actually is, it is a reimplementation of **T**he **O**nly **P**arts **O**f **V**imperator **I** **C**are **A**bout. [Vimperator](https://en.wikipedia.org/wiki/Vimperator) (may it rest in peace) was a Firefox extension that provided a <a href="https://en.wikipedia.org/wiki/Vim_(text_editor)">Vim</a>-like interface for the user. Unfortunately, Firefox internal architecture has significantly changed and extensions written on the old architecture can no longer run on the new.

Due to the fact that I had previously invested significant effort acquiring muscle memory for using Vimperator, I found similar but different extensions virtually unusable without significant retraining. Hence, I decided to write my own. The code is wildly inconsistent for a couple of reasons.

1. I am not a JavaScript developer. I haven't done enough of it to have an opinion on what's the best way to write code in it.

2. There were a few months' break in between when I started it and when I finished it, which exacerbated the inconsistency.

3. The things I did not know how to do, I borrowed from various sources. To put it candidly, JavaScript is a mess. They keep seeing good ideas in other languages, going "hey that's a good idea, we should totally have it in JavaScript", and adding them to the language. Unfortunately, they don't then get rid of the old (mainly bad) ideas. It's a bit [MPD](https://www.webmd.com/mental-health/dissociative-identity-disorder-multiple-personality-disorder#2-6) right now. It's a huge bag of bad ideas mixed with ideas that would be good if the bad ideas weren't also equally valid in the same space. Hence, searching for and transplanting JavaScript code from various sources into your own program is guaranteed to make it a kludgey mess.

Furthermore, some of the things Vimperator did are no longer easily possible, for example, running gVim to edit text input content. Be that as it may, I think some of the approaches I came up with were quite interesting and I stand by them. Also, I mostly did this to scratch my own itch. I was already sure it could be done, so it wasn't really a very interesting project. It's at a usable state, and I'm disinclined to put in more effort. I've submitted the extension for review so that it can be distributed by [Firefox](https://addons.mozilla.org/en-US/firefox/). If they don't reject it, and I give only 50% odds of that happening, you'll be able to install and use it if you liked Vimperator (may it rest in peace).

As usual, if my code causes your computer to explode or you to contract venereal disease, I take no responsibility for it whatsoever.

----

Enough about the past. I intend to write a program that will learn to play [Bejeweled Blitz](https://apps.facebook.com/bejeweledblitz) using [DL](https://en.wikipedia.org/wiki/Deep_learning) and [RL](https://en.wikipedia.org/wiki/Reinforcement_learning) techniques for the purpose of practising what I have learned for the first half of the year on [Coursera](https://www.coursera.org/specializations/deep-learning). The plan of attack is as follows.

1. Choose a weapon. Right now I am thinking [DL4J](https://deeplearning4j.org/documentation) (a deep learning library written in Java), so that I can use [Clojure](https://clojure.org/), my learning of which is another of the tasks I had neglected in order to focus on the deep learning course. Unfortunately, the state of the art seems to mostly be in Python right now, so I might have to abandon this and go for [PyTorch](https://pytorch.org/) instead.

2. Write an Google Chrome browser extension capable of sending messages to a http server running locally when I browse to the Blitz page.

3. Write a http server (in Clojure or Python, depending on (1)) that receives these signals and starts taking screenshots in response.

4. Label them. This is probably going to take the most effort.

5. Train a [ConvNet](https://en.wikipedia.org/wiki/Convolutional_neural_network) to recognize the various states the Blitz program might be in (we can't introspect game state because it is Flash, and besides, the point of this is not to write something that's necessarily efficient, it is to practice machine learning). This should probably have a final [softmax](https://en.wikipedia.org/wiki/Softmax_function) layer to tell us what state the game it is.

6. All states bar one are actually not playable. The bot would need to click through them to get to the playable state. I plan to cheat at this part and hand-engineer what to do for each of the output classes.

7. If it is in a playable state, train an RL agent to play it based on pixels and OCR of the score.

Simple, right? 😊
