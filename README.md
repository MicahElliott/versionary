versionary -- console util to show concise system info on \*nix tools
=====================================================================

## SYNOPSIS
Sometimes it’s a pain to figure out what version of a tool is available on your system. Versionary removes the pain and gives a quick-glance view of most of the relevant tools on most \*NIX systems. It also makes it quick to see what’s missing from your system. Useful in a [MOTD](http://parkersamp.com/2010/10/howto-creating-a-dynamic-motd-in-linux/).

`versionary` displays system info for distros based on _Arch_, _Debian_, _SuSE_, and _Redhat_. It’s similar to `system(2)`, but gives more info. Whereas top, free, uptime, etc give dynamic status indicators, `versionary` gives a static snapshot of system parameters. It also shows version info for the most common interpreters and services. Some munging of output is done to help commands aspire to [semantic versioning](http://http://semver.org/ "SemVer.org").

You may want to use this as a starter recipe for quickly showing the most pertinent info for your systems. The info shown is particularly useful for working with compilers (gcc, glibc, etc), but you may want to tune it for whatever common tools you work with (ruby/python/perl versions, etc). It’s also handy for generating consistent bug reports.

Info/tools worth tracking include: runtimes, interpreters/compilers, system services, databases, VCSs.

Might also be nice to indicate what services are running (`systemctl`). (not likely)

I’m trying to keep the running time of the script to under one second; so far, so good (but barely).

## SYNTAX
Just run it! There are no options. You’ll get some parsable output as key-values.

    % versionary
    hostname: ario
    distro:   archlinux
    release:  rolling
    codename: n/a
    kernel:   3.4.4-2-ARCH
    arch:     x86_64
    glibc:    2.15
    procs:    Pentium(R) Dual-Core CPU T4200 @ 2.00GHz (x2)
    cache:    1024 KB
    ram:      7924 MB
    swap:     517 MB
    bash:     4.2.29(2)-release
    zsh:      4.3.17
    gcc:      4.7.1
    java:     1.7.0_05-icedtea
    python:   3.2.3
    ruby:     1.9.3p194
    perl:     v5.16.0
    erlang:   5.9.1
    php:      5.4.4
    node:     v0.8.0
    haskell:  none
    mysql:    14.14
    postgres: 9.1.4
    sqlite:   3.7.13
    mongodb:  2.0.6
    couchdb:  1.2.0
    redis:    2.4.15
    apache:   2.2.22
    nginx:    1.2.1
    git:      1.7.11.1
    hg:       2.2.2

And it’s individually useful to avoid trying to remember whether a command uses: -v, -V, -version, --version, version, or something else.

    % alias ver=versionary
    % ver node  # NYI
    0.8.16

## OMISSIONS
Some tools are just too slow to get version info from in a generic fashion (without relying on pacman, apt-get, etc). And sometimes they’ll be installed manually (outside the packaging system). These somewhat common packages are excluded from the listing for speed or other concerns: clojure, scala, coffee, lsc, npm, go, dart, riak.

## HISTORY
Originally deployed in a compiler test lab to be used on 50+ diverse machines.

For Debian\* you may have to install something like `libpam-modules` to get motd going. We had a convention of putting a specific one-line status message into our MOTDs, and this parsed that out, so is likely not too useful unless you adopt a similar convention. Anyway, it’s a nice approach when using many systems.

Much more could be done with the [Platform Python library](http://downloads.egenix.com/python/platform.py) if you want to take the concepts here and apply to more OSes.

## SIMILAR
I don’t know of any tool that derives all the system version info, but there are other status/info tools....

There’s a neat [ascii-art utility](https://github.com/KittyKatt/screenFetch/blob/master/screenfetch-dev) similar in nature.

Also look for `archey` and `alsi`.

## BUGS
This has been tested recently only in Arch and Debian.

## TODO
See source for specific TODO items.

## AUTHOR
[Micah Elliott](http://MicahElliott.com)

Project originally hosted as [a gist](https://gist.github.com/719620 "sysinfo on github").

## COPYRIGHT
[WTFPL](http://sam.zoy.org "WTF Public License")
