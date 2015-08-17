# Contributor: Ondrej Kucera <ondrej.kucera@centrum.cz>
pkgname='spring-framework'
true && pkgname=('spring-framework' 'spring-framework-doc')
pkgbase='spring-framework'
pkgver=4.1.5
pkgrel=1 
pkgdesc="An application framework for the Java platform"
url="http://spring.io/"
arch=('any')
license=('Apache')
depends=('java-runtime' 'java-commons-logging')
source=("http://repo.spring.io/libs-release-local/org/springframework/spring/$pkgver.RELEASE/spring-framework-$pkgver.RELEASE-dist.zip")
md5sums=('3bbbc2e952b28738cde673dea3e095f8')
options=(!strip docs libtool staticlibs !zipman)

package_spring-framework() {
  mkdir -p $pkgdir/usr/share/java/$pkgbase
  cd $srcdir/$pkgbase-$pkgver.RELEASE/libs
  for i in *.RELEASE.jar; do
    install -m644 "$i" $pkgdir/usr/share/java/$pkgbase
  done
}

package_spring-framework-doc() {
  mkdir -p $pkgdir/usr/share/doc/$pkgbase
  cd $srcdir/$pkgbase-$pkgver.RELEASE/docs
  cp -r javadoc-api $pkgbase-reference $pkgdir/usr/share/doc/$pkgbase
  rm -rf "$pkgdir/usr/share/doc/$pkgbase/$pkgbase-reference/htmlsingle"
}
