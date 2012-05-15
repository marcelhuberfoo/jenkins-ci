# Maintainer: Illarion Kovalchuk <illarion.kovalchuk@gmail.com>

pkgname=jenkins-ci
pkgver=1.464
pkgrel=1
epoch=
pkgdesc="An extendable open source continuous integration server"
arch=(any)
url="http://jenkins-ci.org"
license=('CC')
groups=()
depends=(java-runtime sudo ttf-dejavu fontconfig net-tools)
makedepends=()
checkdepends=()
optdepends=()
provides=(jenkins)
conflicts=(jenkins)
replaces=(jenkins)
backup=(etc/conf.d/jenkins.conf etc/logrotate.d/jenkins)
options=()
install=jenkins-ci.install
changelog=
source=(http://mirrors.jenkins-ci.org/war/latest/jenkins.war
        jenkins.conf
        jenkins.rcd
        logrotate)
noextract=(jenkins.war)

md5sums=('a859f7340fa85edd18f7837d92b987a8'
         '689654a7022f5fa6bc586f9c2c3bf1bb'
         '7892399de89e709e915ae5043e6d2511'
         'ffa9e73e5382d4d16971dca7a2023868')

package() {
  install -D -m 444 "$srcdir/jenkins.war" "$pkgdir/usr/share/java/jenkins/jenkins.war"
  install -D -m 755 "$srcdir/jenkins.rcd" "$pkgdir/etc/rc.d/jenkins"
  install -D -m 644 "$srcdir/jenkins.conf" "$pkgdir/etc/conf.d/jenkins.conf"
  install -D -m 644 "$srcdir/logrotate" "${pkgdir}/etc/logrotate.d/jenkins"
  mkdir -p $pkgdir/var/lib/jenkins
}

# vim:set ts=2 sw=2 et:
