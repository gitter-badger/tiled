Tiled Map Editor - http://www.mapeditor.org/

About Tiled
-------------------------------------------------------------------------------

[![Join the chat at https://gitter.im/bjorn/tiled](https://badges.gitter.im/bjorn/tiled.svg)](https://gitter.im/bjorn/tiled?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

Tiled is a general purpose tile map editor. It is meant to be used for editing
maps of any tile-based game, be it an RPG, a platformer or a Breakout clone.

Tiled is very flexible, for example there are no restrictions on map size, tile
size or the number of layers or tiles. Also, it allows arbitrary properties to
be set on the map, its layers, the tiles or on the objects. Its map format
(TMX) is relatively easy to understand and allows a map to use multiple
tilesets while also allowing each tileset to grow or shrink as necessary later.

[![Build Status](http://img.shields.io/travis/bjorn/tiled.svg)](https://travis-ci.org/bjorn/tiled) [![Bountysource](https://www.bountysource.com/badge/tracker?tracker_id=52019)](https://www.bountysource.com/trackers/52019-tiled?utm_source=52019&utm_medium=shield&utm_campaign=TRACKER_BADGE)

About the Qt Version
-------------------------------------------------------------------------------

Tiled was originally written in Java. In 2008 the Qt version was started with
the goal to replace the Java version with a faster, better looking and even
easier to use map editor. Qt offered many opportunities to improve the
performance and usability of the user interface, and has a more extensive
feature set than the standard Java libraries.

Compiling
-------------------------------------------------------------------------------

Make sure the Qt (>= 5.1) development libraries are installed:

* In Ubuntu/Debian: `apt-get install qt5-default qttools5-dev-tools zlib1g-dev libqt5opengl5-dev`
* In Fedora:        `yum install qt-devel`
* In Arch Linux:    `pacman -S qt`
* In Mac OS X with [Homebrew](http://brew.sh/): `brew install qt`

Now you can compile by running:

    $ qmake (or qmake-qt5 on some systems)
    $ make

To do a shadow build, you can run qmake from a different directory and refer
it to tiled.pro, for example:

    $ mkdir build
    $ cd build
    $ qmake ../tiled.pro
    $ make

You can now simply run Tiled using bin/tiled.

Installing
-------------------------------------------------------------------------------

For installing Tiled you can run `make install`. By default Tiled will install
to `/usr/local`. You can change this prefix when running qmake, and/or you can
change the install root when running make install, as follows:

Use `/usr` instead of `/usr/local`:

    $ qmake -r PREFIX=/usr

(Recursive needed when it's not the first time that you're running qmake, since
this affects nested pro files)

Install to some packaging directory:

    $ make install INSTALL_ROOT=/tmp/tiled-pkg

By default, Tiled and its plugins are compiled with an Rpath so that they can
find the shared libtiled library when running it straight after compile. When
packaging for a distribution, this Rpath should generally be disabled by
appending `RPATH=no` to the qmake command.
