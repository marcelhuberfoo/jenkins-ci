# Maintainer: Marcel Huber <marcelhuberfoo at gmail dott com>
# Contributor: Illarion Kovalchuk <illarion.kovalchuk at gmail dot com>

pkgname=jenkins-ci
pkgver=1.478
pkgrel=1
epoch=
pkgdesc="An extendable open source continuous integration server"
arch=(any)
url="http://jenkins-ci.org"
license=('CCPL')
groups=()
depends=(java-runtime sudo net-tools)
makedepends=()
checkdepends=()
optdepends=()
provides=(jenkins)
conflicts=(jenkins)
replaces=(jenkins)
backup=(etc/conf.d/jenkins etc/logrotate.d/jenkins)
options=()
install=jenkins-ci.install
changelog=changelog
source=(http://mirrors.jenkins-ci.org/war/$pkgver/jenkins.war
        jenkins.conf
        jenkins.rcd
        jenkins.systemd
        logrotate)
noextract=(jenkins.war)
sha256sums=("6b399691ecece357116e344ed181f20ec337d062a37c044146eab91284741945" "d5c628861778745e0625b335ef9022b6d3d12ad72f8aa7911045ddc76c54e299" "508b6b938b41f160d585d50b013fe3e445fdf1d540108e14cad9f1d32d209bfd" "026ef46b36ba2752ae39d99f579dbf181ae4db8fd2de0798d4dc55dd19281b38" "2a43bf75c47dd237c510bb02ce2257cc0b75b072850cc89c0436a5039dabde96")
package() {
  install -D -m 444 "$srcdir/jenkins.war" "$pkgdir/usr/share/java/jenkins/jenkins.war"
  install -D -m 755 "$srcdir/jenkins.rcd" "$pkgdir/etc/rc.d/jenkins"
  install -D -m 644 "$srcdir/jenkins.systemd" "$pkgdir/etc/systemd/system/jenkins.service"
  install -D -m 644 "$srcdir/jenkins.conf" "$pkgdir/etc/conf.d/jenkins"
  install -D -m 644 "$srcdir/logrotate" "${pkgdir}/etc/logrotate.d/jenkins"
  install -m 755 -d "$pkgdir/var/log/jenkins"
  install -m 755 -d "$pkgdir/var/lib/jenkins"
  install -m 755 -d "$pkgdir/var/cache/jenkins/war"
}

# vim:set ts=2 sw=2 et:

