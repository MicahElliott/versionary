sysinfo -- console util to show concise system info for linux
=============================================================

## SYNOPSIS
`sysinfo` displays system info for distros based on _Arch_, _Debian_, _SuSE_,
and _Redhat_.

This also serves as a starter recipe for quickly showing the most pertinent
info for your systems.

## SYNTAX
Just run it! There are no options. You'll get some parsable output as
key-values.

    % sysinfo
    hostname: ario
    distro:   archlinux
    release:  rolling
    codename: n/a
    glibc:    2.15
    gcc:      gcc (GCC) 4.7.1
    kernel:   3.4.4-2-ARCH
    arch:     x86_64
    procs:    Pentium(R) Dual-Core CPU T4200 @ 2.00GHz (x2)
    cache:    1024 KB
    ram:      7924 MB
    swap:     517 MB

## HISTORY
Originally deployed in a compiler test lab to be used on 50+ diverse machines.

The info shown is particularly useful for working with compilers
(gcc, glibc, etc), but you may want to tune it for whatever common
tools you work with (ruby/python/perl versions, etc). It's also
handy for generating consistent bug reports.

For Debian\* you may have to install something like `libpam-modules`
to get motd going. We had a convention of putting a specific
one-line status message into our MOTDs, and this parsed that out, so
is likely not too useful unless you adopt a similar convention.
Anyway, it’s a nice approach when using many systems.

Note that there is also an apt-installable GUI tool called sysinfo,
but I think this existed first so I'll just keep with the name.

Much more could be done with the
[Platform Python library](http://downloads.egenix.com/python/platform.py)
if you want to take the concepts here and apply to more OSes.

## BUGS
This has not been tested in years on anything but Arch and Debian. In fact,
it's more of an example that I'm using to learn about Arch packaging.

## AUTHOR
[Micah Elliott](http://MicahElliott.com)

## COPYRIGHT
[WTFPL](http://sam.zoy.org "WTF Public License")
