# FbTerm - a fast FrameBuffer based TERMinal emulator for linux

## DESCRIPTION

FbTerm is a fast terminal emulator for linux with frame buffer device or VESA video card. Features include:

  * mostly as fast as terminal of linux kernel while accelerated scrolling is enabled
  * select font with fontconfig and draw text with freetype2, same as Qt/Gtk+ based GUI apps
  * dynamicly create/destroy up to 10 windows initially running default shell
  * record scrollback history for every window
  * auto-detect current locale and convert text encoding, support double width scripts like Chinese, Japanese etc
  * switch between configurable additional text encodings with hot keys on the fly
  * copy/past selected text between windows with mouse when gpm server is running
  * change the orientation of screen display, a.k.a. screen rotation
  * lightweight input method framework with client-server architecture
  * background image for eye candy

read man page doc/fbterm.1 for usage help.

### INPUT METHOD
Instead of adding input method directly in FbTerm, a client-server based input method framework is designed to do this work. FbTerm acts as a client, standalone IM program as a server, and they run in seperated processes.

If you want to develope a new IM program for FbTerm, there is a IM example in im/ directory, which help you to understand IM architecture and provide some base sources to simplify the development.

### Change the default 16 colors

```conf
# Edit fbtermrc file
color-foreground=7
color-background=0
color-0=000000
color-1=AA0000
color-2=00AA00
color-3=AA5500
color-4=0000AA
color-5=AA00AA
color-6=00AAAA
color-7=AAAAAA
color-8=555555
color-9=FF5555
color-10=55FF55
color-11=FFFF55
color-12=5555FF
color-13=FF55FF
color-14=55FFFF
color-15=FFFFFF
```

### Install

```sh
sudo apt remove fbterm -y
sudo apt install libgpm-dev libconfig1-dev libfreetype6-dev libx86-dev pkg-config -y
git clone https://github.com/j16180339887/fbterm.git && cd fbterm
./configure && make && sudo make install
```

License: GPLv2, this is a frozen archive of https://github.com/ccapitalK/fbterm
