# libretro-sh-launcher
Based on [libretro-dolphin-launcher](https://github.com/RobLoach/libretro-dolphin-launcher).

Fork of [libretro-bash-launcher](https://github.com/SwedishGojira/libretro-bash-launcher), see full list of changes below.

Launch (ba)sh-scripts directly from [RetroArch](http://www.libretro.com/) to launch your Linux games.

![Sh Launcher Screenshot](screenshot.png)

## Changes from the original bash-launcher

- Use cmake instead of make. Two reasons - cmake code is more simplier, and I can't sort thing out of original make file.
- Add sh library to easy create your own sh launchers. For example, for wine.
- Add udev module for autolaunch Retroarch. Well, somebody say it's useless feature, but I want just plug in my controller and start playing.
- Playlists and thumbnails auto generation.
- Debian package.
- Rewrite on C++ (WIP)

## Installation

#### Depends

- libcurl
- imlib2
- compiller with c++14 support
- retroarch

#### Manual

1. Compile the core

  ``` bash
  git clone https://github.com/VolkMilit/libretro-sh-launcher.git
  cd libretro-sh-launcher
  mkdir build && cd build
  cmake ..
  make -j$(nproc)
  ```

2. Copy the core file to the RetroArch cores directory
  ``` bash
  cp bash_launcher_libretro.so /usr/lib/libretro/
  # or
  make install
  ```
  
  But actually I dare you to NOT do *make install* in /usr unless you realy want to. 
  Better using package system or launch it locally, because you can forget what you're install.
  
#### Debian package

1. Clone repo and Install necessary packages
  ``` bash
  mkdir libretro-sh-launcher && cd libretro-sh-launcher
  git clone https://github.com/VolkMilit/libretro-sh-launcher.git
  sudo apt install devsripts fakeroot libcurl4-gnutls-dev libimlib2-dev
  ```

2. Build the package
  ``` bash
  cd libretro-sh-launcher
  debuild -i -us -uc -b
  ```

3. Install package
  ``` bash
  cd ..
  sudo dpkg -i libretro_sh_launcher_1.0.0-1+stretch_amd64.deb
  ```

## Usage

See [usage](USAGE.md)

## Contributors

- [SwedishGojira](http://github.com/swedishgojira)
- [Rob Loach](http://github.com/robloach)
- [Alcaro](https://github.com/Alcaro)
