# Maintainer(Unoffical): Hope2333(幽零小喵) <hope2333me@gmail.com>
# Maintainer(Official): Mark Wagie <mark dot wagie at tutanota dot com>
pkgname=viper4linux-gui
pkgver=2.3a2_cn1.1
pkgrel=8
pkgdesc="Official UI for Viper4Linux with Chinese Translate"
arch=('x86_64')
url="https://github.com/Hope2333/Viper4Linux-GUI-debug"
license=('GPL3')
depends=('gst-plugins-bad-libs' 'mesa' 'qt5-multimedia' 'qt5-svg' 'viper4linux')
optdepends=('libappindicator-gtk3: tray icon support')
source=("$pkgname-$pkgver.tar.gz::$url/releases/download/2.3alpha2(fffc9b5)/$pkgver.tar.gz"
        "$pkgname.desktop")
sha256sums=('SKIP'
            '05a46b8ad3508e9275388d9255247cda09977eb8087fa5dd96d04bc25c17a77c')

build() {
  cd "Viper4Linux-GUI-$pkgver"
  qmake-qt5 V4L_Frontend.pro
  make PREFIX=/usr
}

package() {
  cd "Viper4Linux-GUI-$pkgver"
  install -Dm755 V4L_Frontend "$pkgdir/usr/bin/viper-gui"
  install -Dm644 "$srcdir/$pkgname.desktop" -t "$pkgdir/usr/share/applications"
  install -Dm644 viper.png "$pkgdir/usr/share/pixmaps/viper-gui.png"
}
