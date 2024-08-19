# 環境構築（MSYS+Ruby+Git）

1. Download Ruby

    * https://rubyinstaller.org/downloads/
        * Other Useful Downloads
            * 7-ZIP ARCHIVES

1. Extract .7z

1. Create cmd.bat

    * tree

    ```diff
    + ./
    +   + rubyinstaller-3.3.4-1-x64/
    +     + bin/
    +     + ...
    +   + cmd.bat
    ```

    * cmd.bat

    ```txt
    set RUBY_BIN=%~dp0rubyinstaller-3.3.4-1-x64\bin

    set PATH=%RUBY_BIN%;%PATH%

    cmd.exe /K
    ```

1. Install MSYS2

    * https://www.msys2.org/
        * https://www.msys2.org/wiki/MSYS2-installation/
            * -> [64-bit](https://repo.msys2.org/distrib/x86_64/)
                * -> Download msys2-base-x86_64-20240727.tar.xz (latest-version)

    * Extract .tar.xz

    ```diff
      ./
        + rubyinstaller-3.3.4-1-x64/
    +   + msys2-base-x86_64-20240727/
    +     + clang32/
    +     + ...
        + .gitignore
        + cmd.bat
    ```

    * cmd.bat

    ```diff
      set RUBY_BIN=%~dp0rubyinstaller-3.3.4-1-x64\bin
    + set MSYS_BIN=%~dp0msys2-base-x86_64-20240727

    - set PATH=%RUBY_BIN%;%PATH%
    + set PATH=%RUBY_BIN%;%MSYS_BIN%;%PATH%

      cmd.exe /K
    ```

1. Install ridk

    * Command prompt

    ```txt
    .\cmd.bat

    ridk install

        #  _____       _           _____           _        _ _         ___  
        # |  __ \     | |         |_   _|         | |      | | |       |__ \
        # | |__) |   _| |__  _   _  | |  _ __  ___| |_ __ _| | | ___ _ __ ) |
        # |  _  / | | | '_ \| | | | | | | '_ \/ __| __/ _` | | |/ _ \ '__/ /
        # | | \ \ |_| | |_) | |_| |_| |_| | | \__ \ || (_| | | |  __/ | / /_
        # |_|  \_\__,_|_.__/ \__, |_____|_| |_|___/\__\__,_|_|_|\___|_||____|
        #                     __/ |           _
        #                    |___/          _|_ _  __   | | o __  _| _     _
        #                                    | (_) |    |^| | | |(_|(_)\^/_>
        # 
        #    1 - MSYS2 base installation
        #    2 - MSYS2 system update (optional)
        #    3 - MSYS2 and MINGW development toolchain
        #
        # Which components shall be installed? If unsure press ENTER [1,3]
    
    > Which components shall be installed? If unsure press ENTER [1,3]

        # > sh -lc true
        # MSYS2 seems to be properly installed
        # Install MSYS2 and MINGW development toolchain ...

        # Which components shall be installed? If unsure press ENTER []

    > Which components shall be installed? If unsure press ENTER []
    ```

1. Install Git-bash

    * https://git-scm.com/download/win
        * -> 64-bit Git for Windows Portable

    * cmd.bat

    ```diff
      set RUBY_BIN=%~dp0rubyinstaller-3.3.4-1-x64\bin
      set MSYS_BIN=%~dp0msys2-base-x86_64-20240727
      set GIT_BIN=%~dp0PortableGit\bin

    - set PATH=%RUBY_BIN%;%MSYS_BIN%;%PATH%
    + set PATH=%RUBY_BIN%;%MSYS_BIN%;%GIT_BIN%;%PATH%

      cmd.exe /K
    ```
