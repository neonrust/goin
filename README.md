# GOIN

GO INstaller.

It's tested (and tuned) to run on Ubuntu.
Requires Python 3.x.

## Help

    # goin --help
    Usage: ./goin [options]

    General options:
      -y, -f           Answer "Yes" to all confirmation questions
    Mode options:
      --installed, -l  List installed versions and exit
      --available, -L  List available versions and exit
      --uninstall=VER, -U VER
                       Remove an existing version and exit

    Version selection options:
      --arch=ARCH      Select/filter architechture (amd64)
      --os=OS          Select/filter OS (linux)
      --version=VER, -v VER
                       Select/filter version (None)
                       Regular expression autodetected
    Installation options:
      --prefix=PATH, -p PATH
                       Use PATH as (un)install prefix (/usr/local)
      --activate       If using 'update-alternatives', activate the
                       newly installed version
      --alt-prio       If using 'update-alternatives', set priority
                       for the installed configurations
      --bin-dir        Set directory for symlinks (/home/andjonss/.local/bin)
      --symlink, -s    Use symlinks (even if 'update-alternatives' exist)
      --tmp=DIR        Use DIR as temporary storage during download (/tmp)


## Installing

Installs the Latest available version by default:

    # goin
	Fetching downloads... done

    Selected: 1.13.5  linux/amd64
    Downloading: 1.13.5  [linux/amd64]   https://dl.google.com/go/go1.13.5.linux-amd64.tar.gz
    ████████████████████████████████████████████████████████████▏ 100%  114 MiB
    Sorry, you don't have write-access to /usr/local   (see -p)
    Try running the same command with "sudo".

And redoing the same with 'sudo' will resume and conclude the
installation. The downloaded file is stored locally (currently, in
/tmp), thus not downloaded again.

The 'Fetching downloads' appears because it always checks for new
versions upon startup.

    # sudo goin
    [sudo] password for THEUSER:
    Fetching downloads... done

    Selected: 1.13.5  linux/amd64
    Downloading: 1.13.5  [linux/amd64]   https://dl.google.com/go/go1.13.5.linux-amd64.tar.gz
    Already downloaded: /tmp/go1.13.5.linux-amd64.tar.gz (114 MiB)
    Extracting archive... OK
    Installing as: /usr/local/go-1.13.5
    Installing alternatives for binaries... done

    # go version                                                                                                          ~/devel/goin
    go version go1.13.5 linux/amd64

Listing installed versions:

	#./goin -l                                                                                                           ~/devel/goin
    Installed Go versions in /usr/local:
      /usr/local/go-1.13.5  (go, gofmt)
