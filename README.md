mlbstreamer
===========

```mlbstreamer``` enables real-time and time-shifted viewing of MLB.tv streams.

The ```mlbstreamer``` package consists of the following programs:

* ```mlbstreamer``` - a full-featured TUI (terminal user interface) that allows
you to browse the MLB schedule and open game streams

* ```mlbplay``` - a simple command-line program for watching a single MLB game


Installation
------------

The easiest way to install is using pip:

    pip install mlbstreamer

To upgrade, just add ```-U```:

    pip install -U mlbstreamer

This installation method should pull down all the necessary dependencies from
PyPI.

Configuration
-------------

The first thing you'll need to do is configure your MLB.tv username, password,
etc. To do that, run:

```
mlbplay --init-config
```

The program should ask you for your username and password, then try to find your
media player (it just looks for mpv or vlc right now.). If it doesn't find it,
you can enter the full path to whatever you're using. If your player worked with
mlbviewer, it should work with mlbstreamer. It'll also ask you for your time
zone so that game times are displayed properly.

Using ```mlbstreamer```
-----------------------

When you run ```mlbstreamer```, you should see a list of today's MLB games.  Use
the left/right arrows to browse days, "t" to go to today's games, and "w" to
watch the currently selected game. The log window at the bottom should tell you
if there are any errors, like if the game doesn't have a stream, if it's blacked
out, etc. The toolbar at the top allows you to select the output resolution and
some other options.

Using ```mlbplay```
-----------------------

If you just want a simple command-line interface and know the game you want to
watch, you can use ```mlbplay```.  The simplest syntax to watch today's game
from your favorite team is:

    mlbplay [TEAM]

where [TEAM] is a three-letter team code, e.g. phi

To stream at a different resolution, use the ```-r``` option:

    mlbplay -r 360p phi

If you want to watch a game for a different date, run with the -d option, e.g:

    mlbplay -d 2018-04-03 phi

You can also save the stream to disk with the -s option, e.g:

    mlbplay -s ~/Movies/mlb phi

For a list of additional options, run

    mlbplay --help

Caveats
-------

* MLB.tv offers some free streams, but right now, this program only supports
  MLB.tv subscribers.  Support for playing free streams without an MLB.tv account
  should be forthcoming.

* Right now, only major league games are supported, though support for MiLB
  (minor league) games is planned.

