# Maintainer: you but baset on tsn <tsn@rimit.ru>;
pkgname=1c_enterprise83
_pkgname1c=1C_Enterprise83
if test "$CARCH" == x86_64; then
    _pkgarch1c=$CARCH		# Если собираем пакеты для 64 бит
else
    _pkgarch1c=('i386')		# Если собираем пакеты для 32 бит
fi
pkgver=8.3.24        # Поменяйте на вашу версию
pkgrel=1308          # Поменяйте на вашу версию
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

md5sums=('772c0e5ee93b7856ed95ac04c5061e46'
         '7f7267126c0c09f5877549690dc30b85'
         'b72c6e15e5288186a0e7bb9b9550589e'
         'bdf1d88b693d64604a00ee185d7397bd'
         'ffb0f5fb98b88d592bf0b0e5a86fdf22'
         '1fe613d5c494bcdd51aa5c76ca7c8108'
         'fa9c2411f492fbc438c67ca9d147b082'
         'e51b3d2778c6b1aca116f81fcbe0c494'
         'c62b96ced0db5bf94bc59cf5c7332525'
         '747231c43def025d71ea3931cc2155ac')
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
