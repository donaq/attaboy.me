# Extension Done, Screenshots Taken

As has [previously been said](https://attaboy.me/#posts/tech/Blitz%20Bot/0), I have started working on a [bot](https://bitbucket.org/donaq/blitzcheat-ml/src/master/) that can learn to play Bejeweled Blitz. The first step in doing that was to write a browser extension that runs on Chromium. Right now, what the [extension](https://bitbucket.org/donaq/blitzcheat-ml/src/a1335c11a2feef4be2ade6db2aeaebdc4ff5ee8a/extension/) does is this:

1. Tries to connect to the [server](https://bitbucket.org/donaq/blitzcheat-ml/src/a1335c11a2feef4be2ade6db2aeaebdc4ff5ee8a/src/blitzcheat_ml/) with a WebSocket.

2. Figures out how big (height and width) the flash object is (easy).

3. Figures out the on screen location (x y coordinates in pixels from top left corner of the screen) of the flash object (fucking laden with iniquity because fucking nested iframes, windows and what that does to screenX and screenY, also the fucking browser address bar).

  1. This was so amazingly painful that I have decided to make it so that the extension will only do work if it is maximised. It's just easier that way.


4. Sends the dimensions and coordinates in json format to the server.

Right now, all the server does is take a screen capture of the area specified by the browser extension whenever it receives a message.

----

## Next steps

I ran the extension and played a few games of Bejeweled Blitz, and now have ~1500 images. I am a total novice, so the bot's operation is quite likely to change as I go along, but here are my observations and consequent plans.

1. There are basically two types of scenarios I care about:

  1. We are not in a game

  2. We are in a game

2. If we are not in a game, we want to click somewhere on the screen that will bring us closer to being in a game.

3. If we are in a game, we want to read the score and run some Reinforcement Learning algorithm on the screenshot.

4. I have no idea how to do any of this stuff, heh, but at least I know what the first step will be. The tedious labeling of 1500 images. For each image, I will need to label whether it is a game (1/0) and what coordinates to be clicked on (don't care if it is a game; x, y if it is).
