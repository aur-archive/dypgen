# Maintainer: Sindre F. Devik <sindre.devik@gmail.com>

pkgname=dypgen
pkgver=20120619
pkgrel=3
pkgdesc="GLR parser generator for OCaml"
arch=('i686' 'x86_64')
url=("http://dypgen.free.fr")
license=('CeCILL-B')
depends=('ocaml')
makedepends=('ocaml' 'ocaml-findlib')
source=(http://dypgen.free.fr/dypgen-${pkgver}-1.tar.bz2)
sha256sums=('ecb53d6e469e9ec4d57ee6323ff498d45b78883ae13618492488e7c5151fdd97')
options=(!makeflags staticlibs)

build () {
  cd "${srcdir}/${pkgname}"
  make || return 1
}

package () {
  cd "${srcdir}/${pkgname}"

  make install \
    DYPGENLIBDIR="${pkgdir}/$(ocamlfind printconf destdir)" \
    DESTDIR="${pkgdir}" || return 1

  install -D -m 644 dypgen-doc.pdf $pkgdir/usr/share/doc/dypgen/dypgen-doc.pdf
  install -D -m 644 Licence_CeCILL-B_V1-en.txt $pkgdir/usr/share/licenses/dypgen/LICENSE
}
