# mpv-iptv

Script for watching iptv with mpv.

### Install

- Save `iptv.lua` in `/mpv/scripts/`.

### Run

- `mpv --script-opts=iptv=1 playlist.m3u`
- Read `Suggestions` section below for a user-friendly way to run.

### Key bindings

You can change them by editing the file.

- `Alt + '`: show/hide playlist (for channel selection)
- `Esc`: hide playlist
- `↑`, `↓`, `Page Up`, `Page Down`, `Home`, `End`, `wheel up`, `wheel down`: navigate playlist items
- `Ctrl + Backspace`: return to previous playlist
- type to search/filter

Except by `Alt + '`, all keybindings above only work if playlist is visible.

### Comparison with original [iptv.lua](https://github.com/gthreepw00d/mpv-iptv) (differences and new features)

- Supports playlists with Kodi-like header manipulation, like this:

      https://example.com/playlist.m3u8|User-Agent=Firefox&Referer=https://foo.bar
- Display channel title as `media-title` instead of weird names such as "*playlist.m3u8?token=yadayada*".
- Added keys `Page Up`, `Page Down`, `Home` and `End` to navigate playlist items, original script only supports `↑` and `↓`.
- Displays playlist in original order even if user has `shuffle` in `mpv.conf`.
- Hides playlist right after selecting a channel.
- Support multiple providers *aka* playlist pointing to other playlists. Example:

      #EXTM3U
      #EXTINF:0, List 1
      https://example.com/playlist.m3u8
      #EXTINF:0, List 2
      https://example.com/playlist2.m3u8
      #EXTINF:0, List 3
      https://example.com/playlist3.m3u8
      #EXTINF:0, Sports Channels
      https://example.com/sports.m3u8
- If you have a playlist pointing to other playlists as per above, you can return to *parent* playlist by pressing `Ctrl + Backspace`.
- Added `Esc` as an intuitive way to hide playlist.
- Changed default keybinding to show/hide playlist from `z` to `Alt+'` (because `z` is already mapped on my profile).
- Increased `osd_time` to giant number to *never* hide playlist unless by user action (after selecting a channel or pressing key to hide it).
- Changed characters to display playing item and selected item. For instance, original uses `*` for playing item, my script uses `▷`.
- Increased amount of items to display to `25`, you should adjust depending on your screen size and your `osd-font-size` value in `mpv.conf` (mine is `24`).
- Removed left-click binding to work as `Enter` (to play selected item).
- Removed right-click binding to show/hide playlist because I use right-click to show context-menu.

### Suggestions

- Install [uosc](https://github.com/tomasklaen/uosc) to turn mpv into the typical media player with useful buttons, indicators and menus.
- Add `<idle>command:live_tv:set script-opts iptv=1;loadfile /your/playlist/path.m3u?IPTV [Alt+']` in the `controls=` line in your `uosc.conf` to create a button to activate IPTV.
- You can also create a context-menu item.

### Screenshots (click to display)

<details>
  <summary>Button in mpv interface to start IPTV (the screenshot was taken while hovering the button)</summary>
  
  ![image](https://user-images.githubusercontent.com/5483864/210293865-7f65f0f9-1ed3-4f91-857d-3c8ccc5018c4.png)
</details>
<details>
  <summary>Context-menu item to start IPTV</summary>
  
  ![image](https://user-images.githubusercontent.com/5483864/210294042-0b8811b4-b892-47bc-bd47-366e5021e53c.png)
</details>
<details>
  <summary>Playlist of playlists</summary>
  
  ![image](https://user-images.githubusercontent.com/5483864/210294138-3e0eb942-3a3f-4157-9846-898bee284dd7.png)
</details>
<details>
  <summary>Playing channel and filtering playlist</summary>
  
  ![image](https://user-images.githubusercontent.com/5483864/210294334-e43ac0aa-1932-4620-85db-27836a279798.png)
</details>
