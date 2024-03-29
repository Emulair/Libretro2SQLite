# Description
This is a small Python script that converts all of RetroArch's .rdb files into a single .sqlite file so it can be used in an emulator front-end such as [Lemuroid](https://github.com/Swordfish90/Lemuroid) or [Emulair](https://github.com/RaduBratan/Emulair).

# Usage on Windows
### Prerequisites
To use this tool on Windows, you need to install and set up MSYS2 by following those steps:
1. download [Git Bash](https://git-scm.com/download/win)
2. download the [MSYS2 installer](https://www.msys2.org/) from the official website and follow their installation instructions
3. follow the [Libretro Doc's instructions](https://docs.libretro.com/development/retroarch/compilation/windows/) for developing RetroArch on Windows (skip installing Qt and the NVIDIA CG toolkit, stop when you reach the "RetroArch Compilation" section)

### Manual usage (with Git Bash)
- open Git Bash
- select a path on your computer to clone this repo in by typing `cd whatever/path/you/want` (note: if you don't want to select a specific path, *C:/Users/[USERNAME]* will automatically be selected)
- clone this repo by typing `git clone https://github.com/Emulair/Libretro2SQLite`
- open MSYS2 MINGW64 (for 64-bit computers) or MINGW32 (for 32-bit computers)
- navigate to the current folder by typing `cd whatever/path/you/have/Libretro2SQLite` (mine, for example, is simply *D:/Libretro2SQLite*, but yours could differ depending on where you cloned this repo)
- clone the Libretro database files in .rdb format by typing `git clone https://github.com/libretro/libretro-database` (only done once when you first use the tool)
- clone some necessary RetroArch files by typing `git clone https://github.com/libretro/RetroArch` (only done once when you first use the tool)
- navigate to *RetroArch/libretro-db* by typing `cd RetroArch/libretro-db`
- build the RetroArch database by typing `make`
- copy the file *libretrodb_tool.exe* to the root folder by typing `cp ./libretrodb_tool ../..`
- go back to the root folder by typing `cd ../..`
- generate the .sqlite file by typing `python3 libretro2sqlite.py`

### Automatic usage
- open MSYS2 MINGW64 (for 64-bit computers) or MINGW32 (for 32-bit computers)
- navigate to the current folder by typing `cd whatever/path/you/have/Libretro2SQLite`
- type `sh automatic-sqlite-generation.sh`

### Error messages
- if you encounter `make: Nothing to be done for 'all'.`, simply type `make clean` and start the process again
- if you get the error `syntax error: unexpected end of file` when using *automatic-sqlite-generation*, [use this tool](https://toolslick.com/conversion/text/dos-to-unix) to convert the *.sh* file to a compatible format for your operating system (when uploaded to GitHub, the special line endings - which differ from OS to OS - of *automatic-sqlite-generation* get removed, which is why this error occurs; the tool mentioned above brings them back)

### Postrequisites
Don't forget to regularly update the *RetroArch* and *libretro-database* folders by navigating to each of them with Git Bash and executing `git pull`.

# Usage on Linux
[COMING SOON]

# Usage on macOS
[COMING SOON]

# Credits
Major thanks to [Swordfish90](https://github.com/Swordfish90), [konsumer](https://github.com/konsumer) and [rwnobrega](https://github.com/rwnobrega) because this tool is a fork of [libretro-sqlite-db](https://github.com/Swordfish90/libretro-sqlite-db).
