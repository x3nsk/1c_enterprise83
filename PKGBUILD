# Maintainer: you but baset on tsn <tsn@rimit.ru>;
pkgname=1c_enterprise83
_pkgname1c=1C_Enterprise83
if test "$CARCH" == x86_64; then
    _pkgarch1c=$CARCH		# Если собираем пакеты для 64 бит
else
    _pkgarch1c=('i386')		# Если собираем пакеты для 32 бит
fi
pkgver=8.3.23        # Поменяйте на вашу версию
pkgrel=1782          # Поменяйте на вашу версию
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

md5sums=('2fe4dd00edf0981b708b86a06c9f24ae'
         '20cf0917a30a8fdaee42627b49595882'
         'b6a4644aaf038ff6086e2592486767eb'
         '62be05552eba781980d06f23bc8a3d8b'
         '50a49bc3602e5bd016c0e7f66bdb60fc'
         '9cd27390d4112ba2bd596a57a0006ceb'
         '49d3c575aa34db6cf4d2f6b3d524fb36'
         '8f5f55fca1aa9b904838191af761f0a5'
         'b285e9f96ca45fd4373513027e5f8d29'
         'c9fec17251c8527be706160f96e40e78')
package() {
   cd $pkgdir
   rm -f $srcdir/opt/1cv8/$arch/$pkgver.$pkgrel/libstdc++.so.6
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
