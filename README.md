Name Irc::Art
=============

Synopsis
========

    use IRC::Art;
    use YourFavoriteIrcClient;

    my $art = IRC::Art.new(4, 4); # A 4x4
    $art.rectangle(0, 0, 3, 3, color(4)); #draw a red square
    $art.text("6.c", 1, 1, :color(13), :bold); # put the 6.c text starting at 1,1
    for $art.result {
      $irc.send-message('#perl6', $_);
    }

Description
===========

IRC::Art offer you a way to create basic art on IRC. It work mainly like a small graphic library with method to "draw" pixel, text or rectangle.

Usage
=====

Create an `IRC::Art` object and use the various drawing method on it.  Every change override the previous of the canvas execpt for the text method.

new(?width, ?height)
--------------------

Create a new canvas filled with space according to the width and height information.

result
------

returns the canvas as an array of irc string. so you can easily put in a loop to send message

Str
---

The `Str` method return the first row of the canvas as a single string.

pixel($x, $y, :$color, $clear)
------------------------------

put or clear the pixel at the given x/y coordonate

rectangle($x1, $y1, $x2, $y2, :$color, $clear)
----------------------------------------------

put or clear a rectangle of pixel from x1/y1 to x2/y2 corners

text($text, $x, $y, :$color, $bold, $bg)
----------------------------------------

Put some text starting at the x/y coordonates.

$color is the color of the text

$bg is the color of the background

save($filename) load($filename)
-------------------------------

Save in a perl6 format the canvas. Use load to load it

Colors
======

These color are mainly indicative, it depends too much on the irc client configuration.

    0 : light grey
    1 : Black
    2 : Dark Blue
    3 : Dark Green
    4 : Red
    5 : Dark red
    6 : Violet
    7 : Orange
    8 : Yellow
    9 : Light Green
    10 : Dark light blue
    11 : Lighter blue
    12 : Blue
    13 : Pink
    14 : Dark Grey
    15 : Grey
