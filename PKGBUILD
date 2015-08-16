# Maintainer: American_Jesus <american.jesus.pt AT gmail DOT com>

pkgname=meocloud
pkgver=latest
pkgrel=2
pkgdesc="Portuguese cloud storage, file synchronization service"
url="https://meocloud.pt"
arch=("i686" "x86_64")
license=('custom')
options=('!strip' '!upx')

case $CARCH in
  i686 )
    _ARCH=i386 ;;
  x86_64 )
    _ARCH=x86_64 ;;
esac

source=("https://meocloud.pt/binaries/linux/${_ARCH}/meocloud-latest_${_ARCH}.tar.gz"
        "termos.txt")
md5sums=('SKIP'
         'c13ee3f76fba2aaa236dd80448522f9e')

package() {
  cp -R $srcdir/{opt,usr} $pkgdir

  find "$pkgdir/opt/meocloud/" -type f -exec chmod 644 {} \;
  chmod 755 $pkgdir/opt/meocloud/core/meocloudd
  chmod 755 $pkgdir/opt/meocloud/cli/{daemon,meocloud,restart_meocloud.sh}
  install -Dm644 "$srcdir/termos.txt" "$pkgdir/usr/share/licenses/$pkgname/termos.txt"

}
