# Maintainer: Tianjiao Yin <ytj000@gmail.com>
# Contributor: Gustavo Dutra <mechamo@gustavodutra.com>
pkgname=schemaspy
pkgver=5.0.0
pkgrel=2
pkgdesc="SchemaSpy generates an HTML representation of a database schema's relationships."
url="http://schemaspy.sourceforge.net/"
license=("LGPL")
depends=('java-runtime' 'graphviz')
optdepends=('mysql-jdbc: for mysql support'
            'postgresql-jdbc: for postgresql support'
            'javasqlite: for sqlite support'
	    'jtds: fr MSSQL Server support')
arch=(i686 x86_64)
source=("http://downloads.sourceforge.net/sourceforge/schemaspy/schemaSpy_${pkgver}.jar")
noextract=("schemaSpy_${pkgver}.jar")
build() {
    mkdir -p $pkgdir/usr/bin/ $pkgdir/opt/schemaspy/
    cp $srcdir/schemaSpy_$pkgver.jar $pkgdir/opt/schemaspy/schemaSpy_$pkgver.jar
    cd $pkgdir/opt/schemaspy
    ln -s schemaSpy_$pkgver.jar schemaSpy.jar
    echo -e "#!/bin/sh\njava -jar /opt/schemaspy/schemaSpy.jar \$*" > $pkgdir/usr/bin/schemaspy
    chmod 755 $pkgdir/usr/bin/schemaspy
}
md5sums=('d1a4ca73e932f8c22d6da0f563f42690')
