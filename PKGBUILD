# Maintainer: Marcel Huber <marcelhuberfoo at gmail dott com>
# Contributor: Alexander Rødseth <rodseth@gmail.com>
# Contributor: Illarion Kovalchuk <illarion.kovalchuk at gmail dot com>

pkgname=jenkins-ci-latest
pkgver=1.541
pkgrel=2
pkgdesc='Extendable continuous integration server (latest and greatest)'
arch=('any')
url='http://jenkins-ci.org/'
license=('MIT')
depends=('java-runtime' 'ttf-dejavu' 'libcups')
provides=('jenkins')
conflicts=('jenkins' 'jenkins-ci')
replaces=('jenkins')
backup=('etc/conf.d/jenkins')
install=jenkins-ci.install
noextract=('jenkins.war')
source=("http://mirrors.jenkins-ci.org/war/${pkgver}/jenkins.war"
        'jenkins.conf'
        'jenkins.service'
        'jenkins.tmpfiles.d'
        'LICENSE')
sha256sums=('c4853208a72de71e38f97e81a72f794ce862dc02b2dca7e63682d568db9b3daa'
            '13b6e06de1dedff96bdb8e43f6830bbd954dc58df9d4ed5583693d2a6f8427f4'
            '23b748ae4c418bd1b98e33dd6bb55ad0d578803aecd26176998b759689b82e73'
            '0ccff16308b01b02f2699ea64a73b8dce1e1990ee1c656aa8d6119dee510262e'
            'd9f107920982cb61d807e349b4eaf190b2d593047e55d3f3ad286c7afe06cf55')

package() {
  cd "$srcdir"

  install -Dm444 LICENSE "$pkgdir/usr/share/licenses/jenkins-ci-latest/LICENSE"
  install -Dm444 jenkins.war "$pkgdir/usr/share/java/jenkins/jenkins.war"
  install -Dm644 jenkins.service \
    "$pkgdir/usr/lib/systemd/system/jenkins.service"
  install -Dm644 jenkins.tmpfiles.d "$pkgdir/usr/lib/tmpfiles.d/jenkins.conf"
  install -Dm644 jenkins.conf "$pkgdir/etc/conf.d/jenkins"
}

# vim:set ts=2 sw=2 et:
