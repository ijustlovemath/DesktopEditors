0. Update your system

    - Debian/Ubuntu: `sudo apt update && sudo apt upgrade`
    - RHEL/CentOS: `TODO`
    - ArchLinux (add whatever AUR helper you use): `sudo pacman -Syu`

1. Install the following dependencies:

    - git 
        * Debian/Ubuntu: `sudo apt install git`
    - svn (for obtaining ICU)
        * Debian/Ubuntu: `sudo apt install subversion`
    - autoconf (for curl)
        * Debian/Ubuntu: `sudo apt install autoconf`
    - clang, clang++ (for compiling ICU)
        * Debian/Ubuntu: `sudo apt install clang-3.8`
    - 7zip (for obtaining Boost)
        * Debian/Ubuntu: `sudo apt install p7zip-full`
    - make, g++ compiler, gcc compiler, libc6 
        * Debian/Ubuntu: `sudo apt install build-essential`
    - Qt 5 qmake 
        * Debian/Ubuntu: `sudo apt install qt5-qmake`
    - Qt 5 development headers 
        * Debian/Ubuntu: `sudo apt install qt5-default qtdeclarative5-dev qtbase5-dev`
    - ICU Unicode library development headers
        * Debian/Ubuntu: `sudo apt install libicu-dev`
    - v8 `depot_tools`. Please don't follow this one blindly, especially if you use any shell other than bash!
        * Debian/Ubuntu: `mkdir -p ~/.local/bin && git clone https://chromium.googlesource.com/chromium/tools/depot_tools.git ~/.local/bin/depot_tools && echo "export PATH=\$PATH:\"\$HOME/.local/bin/depot_tools\"" >> ~/.bashrc"`
    - pkg-config (for v8)
        * Debian/Ubuntu: `sudo apt install pkg-config`
    - ninja (for v8)
        * Debian/Ubuntu: `sudo apt install ninja-build`
    - glib 2.0 (for v8)
        * Debian/Ubuntu: `sudo apt install libglib2.0-dev`

2. Clone this repository

        git clone https://github.com/ONLYOFFICE/DesktopEditors.git

3. Obtain ONLYOFFICE git submodule dependencies. This will take a long time, 
depending on your internet connection.

        cd DesktopEditors && git submodule init && git submodule update

4. Build `core`

    0. Change into the 'core' directory:
            cd core

    Note: all 3d-party libraries can probably be fetched and built in parallel, since they don't depend on the package manager. This could be done by modifying `Common/3rdParty/make.sh`
    1. Fetch and build 3rdParty libraries
            - Debian/Ubuntu: `cd Common/3rdParty && ./make.sh`
