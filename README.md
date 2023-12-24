# mpv-config

My MPV config. Requires mpv v0.37+

## Installation

### Linux/Mac

1. Clone this repo into the mpv config location
```sh
git clone https://github.com/warigan/mpv-config ~/.config/mpv
```

2. Create symbolic link:
```sh
cd ~/.config/mpv
ln -s mpv_linux.conf mpv.conf
```

3. (Optional) To use `autosubsync`, choose synctools in `script-opts/autosubsync.conf`, install them on your system then specify their paths.

### Windows

1. Clone this repo into the mpv config location
```pwsh
git clone https://github.com/warigan/mpv-config C:\users\$env:username\AppData\Roaming\mpv
```

2. Create symbolic link (might need admin privileges):
```pwsh
cd C:\users\$env:username\AppData\Roaming\mpv
New-Item -ItemType SymbolicLink -Path mpv.conf -Target .\mpv_windows.conf
```

3. (Optional) To use `autosubsync`, choose synctools in `script-opts/autosubsync.conf`, install them on your system then specify their paths.

4. (Optional) To use `autosub`, it is recommended to configure login credentials in `scripts/autosub.lua`.

## Usage

### Shader auto profiles

#### Anime4K

If the path of the currently playing file contains a directory named `Anime` (case insensitive) mpv will automatically load the `anime` shader profile which in turn will load the configured `Anime4K` profile.

The default (`Anime4K: Mode A (HQ)`) is my personal choice for my system (Ryzen 7 7800X3D, RX 6900 XT @ 165 Hz), if this is not ideal for you it can be changed in `mpv.conf` under `[anime]`. I recommend experimenting by enabling the statistics overlay (`Shift+I`) and enable one at a time with `Ctrl+[0-9]`. See the [Anime4K docs](https://github.com/bloc97/Anime4K/blob/master/md/GLSL_Instructions_Advanced.md) for more information.

#### FSR

If the path of the currently playing file contains a directory named `Movies`, `TV-Series`, `TV_Series` or `TVSeries` (all case insensitive) then mpv will automatically load the `live-action` shader profile. By default this will in turn load the `FidelityFX FSR` shader.

#### Key bindings

Use `Ctrl+[1-6]` to manually select a Anime4K profile and `Ctrl+9` for FSR. `Ctrl+0` clears the shaders so no profile is active.

NOTE: Profile switching is not saved across sessions, so if you don't want to use the configured default you would have to change every time you open a video. I recommend you instead change the defaults in `mpv.conf`.

### Subtitles

To auto-download subtitles for the currently playing video, press `b`. To auto-sync the currently selected subtitles with the audio, press `n`.

### Debug

To open a debug console, press `. It can be used to send mpv input commands, thanks to [repl](https://github.com/rossy/mpv-repl).

## Third-Party

This project includes third party software from the projects listed below.

### Fonts
* [Material Design Iconic Font](https://github.com/zavoloklom/material-design-iconic-font) v2.2.0

### Scripts
* [autosubsync-mpv](https://github.com/joaquintorres/autosubsync-mpv) v0.33
* [mpv-autosub](https://github.com/davidde/mpv-autosub) based on commit 35115355bd339681f97d067538356c29e5b14afa
* [ModernX](https://github.com/cyl0/ModernX) v0.6.0
* [repl.lua](https://github.com/rossy/mpv-repl) based on commit f7538adea92b441f2c7edd5dc07dd50dac28d3d5
* [thumbfast](https://github.com/po5/thumbfast) based on commit 03e93feee5a85bf7c65db953ada41b4826e9f905

### Shaders
* [Anime4K](https://github.com/bloc97/Anime4K) v4.0.1
* [FSR.glsl](https://gist.github.com/agyild/82219c545228d70c5604f865ce0b0ce5) v1.0.2
