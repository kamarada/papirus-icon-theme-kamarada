# Maintainer: Antonio Medeiros <linuxkamarada@gmail.com>
# Contributor: Felix Yan <felixonmars@archlinux.org>
# Contributor: kitsunyan <kitsunyan@inbox.ru>
# Contributor: Grigorii Horos <horosgrisa@gmail.com>

pkgname=papirus-icon-theme-kamarada
pkgbase=papirus-icon-theme
pkgver=20250501
pkgrel=1
pkgdesc="Papirus icon theme - Kamarada fork"
arch=('any')
url="https://github.com/PapirusDevelopmentTeam/papirus-icon-theme"
license=("GPL-3.0")
depends=('gtk-update-icon-cache')
provides=('papirus-icon-theme')
conflicts=('papirus-icon-theme')
replaces=('papirus-icon-theme')
source=(
  "https://github.com/PapirusDevelopmentTeam/$pkgbase/archive/$pkgver/$pkgbase-$pkgver.tar.gz"
  "https://raw.githubusercontent.com/PapirusDevelopmentTeam/$pkgbase/$pkgver/tools/build_color_folders.sh"
  "add-colors.patch"
  "change-default-color.patch"
)
sha512sums=(
  '0eca50c296a548733d9cb97f0d9b62cac99d6b1bb473bf016e33188986334b9fc84bc0682e9a6e5339d3d247f2cfefd24a1de3f901de9ffbc9e8a7ad1b5d39f8'
  '714d89493bcfaca19330e804e6ef3d14af05fb66f9eb0ae9558f64cf0e73e6c6bdf53c4b7c5b904cf2781356014eaafa6031341ecee50c50c434d460596432e8'
  '6490e494f41897fea51c317ee8f17f78e6abc77cc1e3e215e64e8463a639c69493e1319f7bbe4f9c017d6a52bb0fbdcbbfa9759a15e308ed4bfaf7d1414ac07f'
  '9fc13235dcac017763fb347143015366baef31ba4e67e609a9153a58f0efce1592cd9d2db2e21643f24eee50a7e765f8787ee2e3d4aa6bcd4991f0a8ca4748ee'
)
options+=(!strip)

prepare() {

  cd $pkgbase-$pkgver
  mkdir -p tools
  cp ../build_color_folders.sh tools/
  chmod +x tools/build_color_folders.sh
  patch -p1 -i ../add-colors.patch
  patch -p1 -i ../change-default-color.patch
}

package() {
  cd $pkgbase-$pkgver
  make DESTDIR="$pkgdir" install
}
