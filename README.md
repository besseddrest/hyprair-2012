# HyprAir 2012

A step-by-step "guide" for installing Arch Linux, Hyprland, and the HyDE desktop environment on a 2012 Macbook Air

Before you read any further: This guide will use `archinstall`. Hate it or love it, to get my machine configured correctly it took quite a bit of tries, and the install script just made the process tolerable. If you want a manual install, be my guest; I've done that too in prior attempts and I always end up messing something up.

## Intro

The 2012 Macbook Air has been my ride or die since purchasing it new on
a friends Apple discount, but over the last year it has been sitting idle with
a fresh 1TB SSD inside. I wanted to give it new life and at the same time, dive
into Arch Linux, and see if it could handle HyDE.

And I'm happy to say that it runs pretty dang well on this machine! Of course the fan
runs any time I play YouTube but I've yet to get to a point where it just
becomes unsuable because of the load - my 2017 Macbook Pro, on which I've tried both a dual boot and Hyprland setup - does.

I was inspired to create this document after discovering pandiero's Arch on Air
guide. It's about 9 years old already, and more specific to the 2013 Air - but
since most of that info more or less applies, or the modern solutions are easy
to find, I didn't want to make a iteration of a guide would only need a few
changes to bring up to date.

After lots of research, Reddit questions, random help from YouTube, I thought it
would be appropriate to pay it forward and document the installation process
for anyone who has been interested in learning about Arch, Linux, and Hyprland
on and old Macbook.

To be clear: this is less about tuning Hyprland to perform well on the Air, but
more about the special/additional configuration required to get it installed,
identifiying mistakes that were made along the way - so that hopefully you won't
make them.

TLDR: I'm a newb, the tone of this document will be of a newb. If you find
inaccurate information here please let me know and I'll be sure to adjust.

## Before You Start

- you've backed up your files separately - this is going to be a full installation (not
  dual boot), so your drive will be wiped
- you've already created the USB flash drive, according to the Arch wiki
  - (hint: you don't need a third party app to do this, you can just use `dd` in
    your terminal)
- you have a wired internet connection (if you can only do wifi, you can set up
  your network connection in the Arch ISO, but you likely will run into a few
  problems later, which I should be able to address below)
- you can always start over
- you CAN do this plugged into a display (it will be mirrored) but you will need
  to make an adjustment in the next step, depending on your monitor resolution
  (and whether or not you are on a Retina laptop), you can also do this with
  a keyboard and mouse (both need to be wired).

## Installation

### The Arch ISO command line

- Shut down your laptop, plug in your USB flash drive (w Arch ISO) and your
  ethernet cable
- Power on your laptop, holding down Opt at the sound of the chime
- Release the Opt key when you see the flash drive as a boot option - this is
  labeled "EFI BOOT"

From that screen, you'll be given a few options to make a selection before the
installer makes that selection for you. You'll need to add a config before it
starts up, and you can interrupt the wait time by just pressing `e`

### Adjust the resolution

- after typing `e`, a configuration displays at the bottom of the list, to which
  you will add at the end the param `nomodeset`
- Once you've added this, make sure you are selecting the option at the top, and
  hit enter to start the installation.

`nomodeset` will fix the scaling issue that arises from Retina macbooks - in
which you would have been typing commands without being able to see them
(because they are off the screen)

### `archinstall` script

After hitting enter, the script runs and you eventually land on Arch in
a command line. This is being run from the USB flash drive (I think); and you
should keep the USB drive plugged in until you the installation is complete.

- type `loadkeys` followed by the language code that you will work in, e.g.
  `loadkeys us` \<-- sets the language to en_US
- you can run `loadkeys` a second time which I believe updates your keyboard
  layout to your preferred language. This is optional
- finally, run `archinstall`
