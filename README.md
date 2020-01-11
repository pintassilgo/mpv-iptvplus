# mpv-iptv

Script for watching iptv with mpv.

INSTALL

	Put in ~/.config/mpv/scripts/

RUN

	mpv --script-opts=iptv=1 playlist.m3u

CONTROL

	\ or Mouse right click — to show/hide playlist

	UP/DOWN or Mouse scroll — to navigate

	type with keyboard — to search incrementally

	ENTER or Mouse left click — to play

It is possible to redefine keybindings (for example, to disable  mouse support remove all 'MOUSE_*' values from "keybinds" array in iptv.lua).
