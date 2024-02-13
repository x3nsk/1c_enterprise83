# Maintainer: you but baset on tsn <tsn@rimit.ru>;
pkgname=1c_enterprise83
_pkgname1c=1C_Enterprise83
if test "$CARCH" == x86_64; then
    _pkgarch1c=$CARCH		# Если собираем пакеты для 64 бит
else
    _pkgarch1c=('i386')		# Если собираем пакеты для 32 бит
fi
pkgver=8.3.24        # Поменяйте на вашу версию
pkgrel=1439          # Поменяйте на вашу версию
_pkgname1c=1c-enterprise-$pkgver.$pkgrel
pkgdesc="1C 8.3 for Linux"
license=('custom')
arch=($CARCH)
options=('!strip')
#depends=('libwebkit' 'webkitgtk2') # Если не работает обновить liwebkit
depends=('freetype2' 'gtk3' 'libgsf' 'glib2' 'unixodbc' 'krb5' 'enchant' 'harfbuzz-icu' 'gst-plugins-base'
    'gst-plugins-good' 'gst-plugins-bad' 'libsecret' 'libsoup' 'sqlite' 'libxrender' 'libxfixes' 'libxslt'
    'geoclue' 'appmenu-gtk-module' 'gcc-libs' 'glib-networking' 'nuspell' 'hspell' 'libvoikko' 'aspell'
    'aspell-en' 'aspell-ru')
#makedepends=('pkgextract')
url="www.1c.ru"
source=(
$_pkgname1c-client-$pkgver-$pkgrel.$_pkgarch1c.rpm
$_pkgname1c-client-nls-$pkgver-$pkgrel.$_pkgarch1c.rpm
$_pkgname1c-common-$pkgver-$pkgrel.$_pkgarch1c.rpm
$_pkgname1c-common-nls-$pkgver-$pkgrel.$_pkgarch1c.rpm
$_pkgname1c-server-$pkgver-$pkgrel.$_pkgarch1c.rpm
$_pkgname1c-server-nls-$pkgver-$pkgrel.$_pkgarch1c.rpm
$_pkgname1c-thin-client-$pkgver-$pkgrel.$_pkgarch1c.rpm
$_pkgname1c-thin-client-nls-$pkgver-$pkgrel.$_pkgarch1c.rpm
$_pkgname1c-ws-$pkgver-$pkgrel.$_pkgarch1c.rpm
$_pkgname1c-ws-nls-$pkgver-$pkgrel.$_pkgarch1c.rpm
)

md5sums=('433c1e4a5e51e51a4e3f1a14229df948'
         '66e464b42d4aa716ea0b0f024f068dca'
         '79814816de5e225d29b7f307454cf798'
         '6fe8e5a365a5d0e65b09d6d842592052'
         '3dc9ad5262fc147e30b4c690b3b00fb8'
         '6612bb340bb6e6a27beef457244d69a7'
         '390944a1b9f7945657bf093c05a2f7c7'
         'b306140f24e4dcf782889c2a7073f8ca'
         'f0b6fb6116d0bef261e807d9c17aed39'
         'b90ebb3ccf490ca1c9840ab0fce1456e')
package() {
   cd $pkgdir
   rm -f $srcdir/opt/1cv8/$arch/$pkgver.$pkgrel/libstdc++.so.6
   rm -f $srcdir/opt/1cv8/$arch/$pkgver.$pkgrel/libgcc_s.so.1
   ln -s /usr/lib/libstdc++.so.6 $srcdir/opt/1cv8/$arch/$pkgver.$pkgrel/libstdc++.so.6
   ln -s /usr/lib/libenchant-2.so $srcdir/opt/1cv8/$arch/$pkgver.$pkgrel/libenchant.so.1

   cp -r $srcdir/usr $pkgdir
#   cp -r $srcdir/etc $pkgdir
   cp -r $srcdir/opt $pkgdir
#   mkdir -p $pkgdir/usr/lib
#   cp -f $srcdir/../libicuuc.so.59.1 $pkgdir/usr/lib/libicuuc.so.59
#   cp -f $srcdir/../libicui18n.so.59.1 $pkgdir/usr/lib/libicui18n.so.59
#   ln -sf /usr/lib/libicuuc.so $pkgdir/usr/lib/libicuuc.so.59
#   ln -sf /usr/lib/libicui18n.so $pkgdir/usr/lib/libicui18n.so.59
}
