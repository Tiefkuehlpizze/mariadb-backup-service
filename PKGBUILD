# Maintainer: Pizze <piz2920@gmail.com>
pkgname="mariadb-backup-service"
pkgdesc='Lightweight MySQL backup script to backup MariaDB'

pkgver=1.0.0
pkgrel=1
branch=master

arch=('any')
url='https://github.com/Tiefkuehlpizze/mariadb-backup-service'
license=('GPL')

depends=('mariadb' 'pigz')

backup=('etc/conf.d/mariadb-backup' 'etc/my.cnf.d/mariadb-backup.cnf')

source=("${pkgname}-${pkgver}.zip::https://github.com/Tiefkuehlpizze/mariadb-backup-service/archive/refs/tags/${pkgver}.zip")
sha256sums=('SKIP') #self reference

package() {
  cd "$srcdir/$pkgname-${pkgver}/"
  install -D -m 644 "mariadb-backup.service"  "$pkgdir/usr/lib/systemd/system/mariadb-backup.service"
  install -D -m 644 "mariadb-backup.timer"  "$pkgdir/usr/lib/systemd/system/mariadb-backup.timer"
  install -D -m 644 "etc/conf.d/mariadb-backup" "$pkgdir/etc/conf.d/mariadb-backup"
  install -D -g mysql -m 640 "etc/my.cnf.d/mariadb-backup.cnf" "$pkgdir/etc/my.cnf.d/mariadb-backup.cnf"
}

