# Contributor: raubkopierer <mail[dot]sensenmann[at]googlemail[dot]com>
pkgname=python-bert-git
pkgver=20100324
pkgrel=1
pkgdesc="BERT serialization library for Python"
url="http://github.com/samuel/python-bert"
arch=('i686' 'x86_64')
license=('BSD')
depends=('python' 'python-erlastic-git')
makedepends=('git' 'python')

_gitroot="git://github.com/samuel/python-bert.git"
_gitname="python-bert"

build() {
  cd ${srcdir}
  msg "Connecting to github.com GIT server...."

  if [ -d ${srcdir}/$_gitname ] ; then
  cd $_gitname && git pull origin
  msg "The local files are updated."
  else
  git clone $_gitroot
  fi

  msg "GIT checkout done or server timeout"
  msg "Starting make..."

  cd ${srcdir}/${_gitname}
  python setup.py install --prefix ${pkgdir}/usr
  mkdir ${pkgdir}/usr/share
  mkdir ${pkgdir}/usr/share/licenses
  mkdir ${pkgdir}/usr/share/licenses/${pkgname}
  cp ${srcdir}/${_gitname}/LICENSE ${pkgdir}/usr/share/licenses/${pkgname}
} 
