# Maintainer: René Herman <rene dot herman at gmail dot com>

pkgname=bst
pkgver=0.19.3
pkgrel=2

pkgdesc='The multi-platform Propeller Tool Suite'
license=('custom:Proprietary')
url='http://www.fnarfbargle.com/bst.html'

arch=('i686')
depends=('fontconfig' 'xorg-mkfontscale' 'xorg-mkfontdir' 'hicolor-icon-theme' 'gtk-update-icon-cache')
install='install'
options=('!strip')

manver=0.04
bstlver=
bstcver=0.15.3

source=("http://www.fnarfbargle.com/bst/Latest/bst-$pkgver.linux.zip"
        "http://www.fnarfbargle.com/bst/manual/bst_manual_$manver.pdf"
        "http://www.fnarfbargle.com/bst/bstl/Latest/bstl.linux.zip"
        "http://www.fnarfbargle.com/bst/bstc/Latest/bstc-$bstcver.linux.zip"
#       "Parallax.ttf.zip::http://forums.parallax.com/attachment.php?attachmentid=53903&d=1212437073" # bsdtar: "invalid central directory structure"
        "Parallax.ttf"
        "$pkgname.desktop"
        "$pkgname.png")
md5sums=('ba51e188ef501900f93ce42347d228ad'
         '301f0d51f8b120f67369b557d4e55ba6'
         'd8bf911472bff4533b5c61eb895c8b1d'
         '6b418d9b189aab5018ca3745f75947cf'
         '607331b0fa086539a5a312debe535037'
         'c81554cb7758a11b10628f8ef990e417'
         'd9eea1d9381b2aac07e7d215af8adc8f')

package() {
  mkdir -p $pkgdir/opt/$pkgname
  cp $srcdir/bst.linux $pkgdir/opt/$pkgname/bst
  cp $srcdir/bstc.linux $pkgdir/opt/$pkgname/bstc
  cp $srcdir/bstl.linux $pkgdir/opt/$pkgname/bstl
  cp $srcdir/bst_manual_$manver.pdf $pkgdir/opt/$pkgname/manual.pdf

  mkdir -p $pkgdir/opt/bin
  ln -s /opt/$pkgname/bstc $pkgdir/opt/bin/
  ln -s /opt/$pkgname/bstl $pkgdir/opt/bin/

  cp $srcdir/Parallax.ttf $pkgdir/opt/$pkgname/
  mkdir -p $pkgdir/usr/share/fonts/TTF
  ln -s /opt/$pkgname/Parallax.ttf $pkgdir/usr/share/fonts/TTF/

  cp $pkgname.desktop $pkgdir/opt/$pkgname/
  mkdir -p $pkgdir/usr/share/applications
  ln -s /opt/$pkgname/$pkgname.desktop $pkgdir/usr/share/applications/

  cp $pkgname.png $pkgdir/opt/$pkgname/
  mkdir -p $pkgdir/usr/share/icons/hicolor/48x48/apps/
  ln -s /opt/$pkgname/$pkgname.png $pkgdir/usr/share/icons/hicolor/48x48/apps/
}

# vim:set ts=2 sw=2 et:
