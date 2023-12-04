# mpv-slicing-copy

`slicing-copy.lua` is a Lua script forked from [Kagami/mpv_slicing](https://github.com/Kagami/mpv_slicing).
The script is for mpv to cut fragments of the video.

## Installation

### Dependency

- a new enough mpv
- [ffmpeg](https://ffmpeg.org/)

After all dependencies installed, download `slicing_copy.lua` in the repository.
Then either put `slicing_copy.lua` in in `~~/scripts`, where `~~` refers to [mpv's configuration directory](https://mpv.io/manual/master/#files) or use option `--script=/path/to/slicing_copy.lua` to load it.

## Usage

Press `c` to mark the start of the fragment you want to slice. Press it again to mark the end of the fragment and write it to the disk.

Press `C` to clear the fragment.

Press `a` to toggle audio capturing (default on).

Output videos will be placed in `cutfragments` in mpv configuration directory by default. The directory will be created if it does not exist. You can change the directory by editing option `target_dir` in `script-opts/slicing_copy.conf`.

You can change the keybinds by editing [`input.conf`](https://mpv.io/manual/master/#input-conf)

You can configure how the script works by editing `script-opts/slicing_copy.conf`

Logs can be found in console (press `~` to open and `esc` to close by default), which might contains something useful when something went wrong.

## Limitation

Because ffmpeg does not support `edl://` protocal, the script won't work if `--merge-file` is used or `ytdl` passed such url (so currently it does not work with youtube videos. see #10).

When cutting online videos, `-referer` and `-user_agent`  will be passed to ffmpeg. In such case, the resulting filename tends to be wired.

## License

mpv_slicing_copy - Cut video fragments with mpv

Written in 2015 by Kagami Hiiragi <kagami@genshiken.org>

Modified in 2019 by Snylonue <snylonue@gmail.com>

To the extent possible under law, the author(s) have dedicated all copyright and related and neighboring rights to this software to the public domain worldwide. This software is distributed without any warranty.

You should have received a copy of the CC0 Public Domain Dedication along with this software. If not, see <http://creativecommons.org/publicdomain/zero/1.0/>.
