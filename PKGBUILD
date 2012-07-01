# Maintainer: Micah Elliott <mde@MicahElliott.com>

pkgname=sysinfo-git
pkgver=20120630
pkgrel=1
pkgdesc="console util to show concise system info for linux"
arch=('any')
url="https://gist.github.com/719620"
license=('WTFPL')
depends=('lsb-release')
makedepends=('git' 'ronn')
md5sums=() #generate with 'makepkg -g'

#_gitroot="https://gist.github.com/719620.git"
_gitroot="git://gist.github.com/719620.git"
_gitname=sysinfo-git

build() {
  cd "$srcdir"
  msg "Connecting to GIT server...."

  if [[ -d "$_gitname" ]]; then
    cd "$_gitname" && git pull origin
    msg "The local files are updated."
  else
    git clone "$_gitroot" "$_gitname"
  fi

  msg "GIT checkout done or server timeout"
  msg "Starting build..."

  rm -rf "$srcdir/$_gitname-build"
  git clone "$srcdir/$_gitname" "$srcdir/$_gitname-build"
  cd "$srcdir/$_gitname-build"

  # BUILD HERE
  ronn README.md
  mv README sysinfo.1
  gzip sysinfo.1
}

package() {
  cd "$srcdir/$_gitname-build"
  #make DESTDIR="$pkgdir/" install
  #cp sysinfo $pkgdir
  #cp sysinfo.1 /usr/share/man/man1/sysinfo.1
  install -Dm755 sysinfo $pkgdir/usr/bin/sysinfo
  install -Dm644 sysinfo.1.gz $pkgdir/usr/share/man/man1/sysinfo.1.gz
}

# vim:set ts=2 sw=2 et:
