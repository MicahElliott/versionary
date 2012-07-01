sysinfo -- console util to show concise system info for linux
=============================================================

## SYNOPSIS
`sysinfo` displays system info for distros based on _Arch_, _Debian_, _SuSE_,
and _Redhat_. It's similar to system(2), but gives more info. Whereas top,
free, uptime, etc give dynamic status indicators, `sysinfo` gives a static
snapshot of system parameters. It also shows version info for the most common
interpreters and services.

You may want to use this as a starter recipe for quickly showing the most
pertinent info for your systems. The info shown is particularly useful for
working with compilers (gcc, glibc, etc), but you may want to tune it for
whatever common tools you work with (ruby/python/perl versions, etc). It's
also handy for generating consistent bug reports.

## SYNTAX
Just run it! There are no options. You'll get some parsable output as
key-values.

    % sysinfo
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

## HISTORY
Originally deployed in a compiler test lab to be used on 50+ diverse machines.

For Debian\* you may have to install something like `libpam-modules` to get
motd going. We had a convention of putting a specific one-line status message
into our MOTDs, and this parsed that out, so is likely not too useful unless
you adopt a similar convention. Anyway, it’s a nice approach when using many
systems.

Note that there is also an `apt`-installable GUI tool called _sysinfo_, but I
think this existed first so I'll just keep with the name.

Much more could be done with the
[Platform Python library](http://downloads.egenix.com/python/platform.py)
if you want to take the concepts here and apply to more OSes.

## BUGS
This has been tested recently only in Arch and Debian.

## AUTHOR
[Micah Elliott](http://MicahElliott.com)

Project hosted as [a gist](https://gist.github.com/719620 "sysinfo on github").

## COPYRIGHT
[WTFPL](http://sam.zoy.org "WTF Public License")
