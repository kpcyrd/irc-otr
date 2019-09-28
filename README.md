# Using irc with otr

This tutorial is trying to help more users enable otr in common irc clients on
common unix-like operating systems.

This document might work for you, if it doesn't please open an issue describing
what you did and what didn't work. Pull requests very welcome.

## irssi

### Install

- Archlinux: the `irssi` package already ships otr support, there's nothing you need to do.
- Debian based: `apt install irssi-plugin-otr`

### Setup

Add this line to your `~/.irssi/startup`:

    LOAD otr

now you either need to restart irssi or load the module explicitly:

    /LOAD otr

## weechat

Note: at the time of writing weechat 2.5 ships with python2 by default. The next release is going to ship with python3 support by default so the install instructions are going to change soonish.

### Install

- Archlinux: `yaourt -S python-potr`
- Debian based: `apt install python-potr python3-potr`
- Others: `pip install --upgrade --user python-potr`

### Setup

Install the weechat script:

    /script install otr.py
    /script autoload otr.py
    /script load otr.py

To make sure otr is used whenever possible also run this command:

    /set otr.policy.default.send_tag on
