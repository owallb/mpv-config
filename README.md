# mpv-config

My mpv config. Requires mpv v0.37+

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

4. (Optional) To use `autosub`, it is recommended to configure login credentials in `scripts/autosub.lua`.

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

## Third-Party

This project includes third party software from the projects listed below. All respective licenses are available under the `third-party` directory.

### Fonts
* [Material Design Iconic Font 2.2.0](https://github.com/zavoloklom/material-design-iconic-font/tree/2.2.0) by [Sergey Kupletsky](https://github.com/zavoloklom), licensed under [CC BY-SA 4.0](third-party/material-design-iconic-font/License.md).
  * This font includes the official Material Design icons created and maintained by [Google](https://github.com/google/material-design-icons), licensed under [Apache 2.0](third-party/material-design-icons/LICENSE), alongside additional community-designed and brand icons for scalable vector graphics.
  * This font has not been modified from its original version.
  * The license text is available [here](third-party/material-design-iconic-font/License.md).

### Scripts
* [autosubsync-mpv v0.33](https://github.com/joaquintorres/autosubsync-mpv), licensed under [MIT](third-party/autosubsync-mpv/LICENSE)
* [mpv-autosub](https://github.com/davidde/mpv-autosub/tree/35115355bd339681f97d067538356c29e5b14afa), licensed under [MIT](third-party/mpv-autosub/LICENSE-MIT)
* [ModernX 0.6.1](https://github.com/cyl0/ModernX/tree/0.6.1)
* [thumbfast](https://github.com/po5/thumbfast/tree/03e93feee5a85bf7c65db953ada41b4826e9f905), licensed under [MPL 2.0](third-party/thumbfast/LICENSE)

### Shaders
* [Anime4K v4.0.1](https://github.com/bloc97/Anime4K/tree/v4.0.1), licensed under [MIT](third-party/Anime4K/LICENSE-MIT)*

  \* Except the following shaders which are licensed under [Unlicense](third-party/Anime4K/LICENSE-UNLICENSE):
  * [Anime4K\_AutoDownscalePre\_x2](shaders/Anime4K_AutoDownscalePre_x2.glsl)
  * [Anime4K\_AutoDownscalePre\_x4](shaders/Anime4K_AutoDownscalePre_x4.glsl)

* [FSR.glsl v1.0.2](https://gist.github.com/agyild/82219c545228d70c5604f865ce0b0ce5), licensed under [MIT](third-party/FSR.glsl/LICENSE)

### Lua stubs
* [emmylua-stubs](https://github.com/haolian9/emmylua-stubs/tree/6d6a51d9f64e30dfe2f57ff104485095361d4a7b), licensed under [MIT](third-party/emmylua-stubs/LICENSE)
