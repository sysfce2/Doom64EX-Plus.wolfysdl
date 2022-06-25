Doom64EX-Plus is a reverse-engineering project aimed to recreate Doom64 as close as possible with additional modding features.

I 'Gibbon' will be diligently comparing against several N64 decompilations to ensure all the correct calculations and math is in this port, things such as damage calculation, sight etc..

A note here: I am 'NOT' competing with the re-creation from NightDive.  This is primarily an effort to get an awesome version that is usable for those on macOS, GNU/Linux, FreeBSD etc.. although I also target Windows.  The re-creation serves its purpose and does a good job, we should thank Kaiser and NightDive for bringing Doom64 to a wider audience *tips hat*

**NOTE for Linux users:** The save data is located in `$XDG_DATA_HOME/doom64ex-plus` (typically `~/.local/share/doom64ex-plus`) and not in `~/.doom64ex-plus`. The files can be safely moved to their new home.

## Dependencies

* SDL2
* SDL2_net
* zlib
* libpng
* FluidSynth

## Compiling

### Linux

Clone this repo

    $ git clone https://github.com/atsb/Doom64EX-Plus

Create a new directory inside the repo root where compilation will take place

    $ mkdir Doom64EX-Plus/build
    $ cd Doom64EX-Plus/build

Run cmake and make

    $ cmake .. && make

Install doom64ex-plus (on macOS do not do this as root or with `sudo`)

    # make install

## Usage

Doom64EX-Plus needs the Doom 64 data to be present in any of the following directories:

* The directory in which `doom64ex-plus` resides
* `$XDG_DATA_HOME/doom64ex-plus` (eg. `~/.local/share/doom64ex-plus`)
* `/usr/local/share/games/doom64ex-plus`
* `/usr/local/share/doom64ex-plus`
* `/usr/share/games/doom64ex-plus`
* `/usr/share/doom64ex-plus`
* `~/Library/Application Support/doom64ex-plus` (macOS only)

The data files are:

* `doom64ex-plus.wad` (Generated by cmake)
* `doom64.wad`
* `doomsnd.sf2`

To generate the two latter files, acquire a Doom64 ROM and run:

    $ doom64ex-plus -wadgen PATH_TO_ROM

This will generate the required files and place them in `$XDG_DATA_DIR/doom64ex-plus`.

After this you can play.

    $ doom64ex-plus

PWAD support (user mods)

PWAD support is fully supported and works with the '-file' command on Unix-Like or Unix systems.  Windows users can drag and drop the PWAD onto the binary or use the Launcher to enter the commands manually.
