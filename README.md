# GOIN

GO INstaller.

It's tested (and tuned) to run on Ubuntu.
Requires Python 3.x.

## Help

    # goin --help
    Usage: goin [command] [options]
    
    With no arguments, installs the latest version.
    
    General options:
      -y, -f             Answer "Yes" to all confirmation questions
    
    Commands:
      [install]          Install matching version
      list               List locally installed versions
      available          List available versions for installation
      uninstall VER      Uninstall a installed version
      switch VER         Switch to/activate the specified installed version
    
    Version selection options:
      --arch=ARCH        Select/filter architechture (amd64)
      --os=OS            Select/filter OS (linux)
      --version=VER, -v VER
                         Select/filter version (None)
                         Regular expression autodetected
    
    Installation options:
      --prefix=PATH, -p PATH
                         Use PATH as (un)install prefix (/home/andjonss/.local)
      --activate         Activate the just-installed version (default: auto)
      --no-activate      Skip activation of just-installed version
      --alt-prio         If using 'update-alternatives', set priority
                         for the installed configurations
      --bin-dir          Set directory for symlinks (/home/andjonss/.local/bin)
      --symlink, -s      Use symlinks (even if 'update-alternatives' exist)
      --tmp=DIR          Use DIR as temporary storage during download (/tmp)
    

## Installing

Without arguments, it installs the latest available version, for the
current user:

    goin --version 1.15.4                                                                           ~
    Fetching downloads... done
    
    Selected: 1.15.4  linux/amd64
    Downloading: 1.15.4  [linux/amd64]   /dl/go1.15.4.linux-amd64.tar.gz
    ████████████████████████████████████████████████████████████▏ 100%  115 MiB 
    Extracting archive... OK
    Installing as: /home/andjonss/.local/go-1.15.4
       /home/myself/.local/bin/gofmt -> /home/myself/.local/go-1.15.4/bin/gofmt
       /home/myself/.local/bin/go -> /home/myself/.local/go-1.15.4/bin/go

The -p/--prefix option allows using a system-global prefix,
e.g. /usr/local. This will of course require root privileges (i.e. use
'sudo')

Listing installed versions:

	#./goin list
    Installed Go versions in /usr/local:
      /home/myself/.local/go-1.15.4  (go, gofmt)
