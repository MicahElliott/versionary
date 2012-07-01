## Installing to Arch Linux

Installation (packaging) is the main point of this tiny package. I wanted to use
a tiny project to serve as an example of how to install directly from github
(a gist!) to Arch Linux. Normally a package would go through an approval
process to be put into AUR, but until your package is mature enough for that
this is a clean and simple way to go.

## User flow

    cd ~/abs
    # Get the one requisite file. Just download the PKGBUILD, or:
    wget https://raw.github.com/gist/719620/8f9af1f7683463a8977f7a758f80bd4be9acd587/PKGBUILD
    # Build the package
    makepkg
    # Install
    sudo pacman -U sysinfo-git-20120630-1-any.pkg.tar.xz
    # Run it
    sysinfo
    # Read about it
    man sysinfo
    # Uninstall
    sudo pacman -R sysinfo-git

## Developer flow

1. Write a script in any language.
2. Put some brief usage info into a `README.md`.
3. Create a simple `PKGBUILD`.
4. Create a gist or first-class repo out of it.
5. Hack, push, hack, push.

This is not a world changing package, but demonstrates that anything you write
can be packaged up to be run by anyone, and can have a trivial manpage
installed. It doesn't matter what the language is. And there's no messing with
complex install instructions, altering `PATH`s, copying files around, or
trying to uninstall misplaced things.
