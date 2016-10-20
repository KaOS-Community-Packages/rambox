pkgname=rambox
pkgver=0.4.4
#pkgrel=1
pkgdesc="Free, Open Source and Cross Platform messaging and emailing app ."
arch=('x86_64')
url="http://rambox.pro/"
license=("MIT")
#depends=
source=("$pkgname.desktop" "$pkgname.png" "https://github.com/saenzramiro/rambox/releases/download/$pkgver/Rambox-$pkgver-x64.tar.gz")
sha256sums=('6c6913dc53520981ade5d279ef4f9c3b8aeb7cc9f5e752c59da0ca984efdd13f'
            '6b77c271e8f94eb33ce7ad3a4596a861fedfea0ac45e69a2b6fc4ce6d12fe32d'
            '20a622f81000c274ec2bf7f1fc7300d3905f3dbd0caaebb38bde1d19f952bc17')

package() {
	install -dm755 "$pkgdir/usr/bin"
	install -dm755 "$pkgdir/usr/share/$pkgname"
	cp -rf $srcdir/Rambox-$pkgver/* $pkgdir/usr/share/$pkgname/
	install -dm755 "$pkgdir/usr/bin"
	echo -en "#!/bin/bash\nexec /usr/share/$pkgname/Rambox $@"  >"$pkgdir/usr/bin/rambox"
    chmod +x  "$pkgdir/usr/bin/rambox"
	install -dm755 "$pkgdir/usr/share/pixmaps"
	install -Dm644 "$srcdir/$pkgname.png" "$pkgdir/usr/share/pixmaps/rambox.png"
	install -dm755 "$pkgdir/usr/share/applications"
	install -Dm644 "$srcdir/$pkgname.desktop" "$pkgdir/usr/share/applications/rambox.desktop"

	#rm -r $pkgdir/usr/share/$pkgname/{$pkgname.png,Rambox-$pkgver-x64.tar.gz,$pkgname.desktop}

}
