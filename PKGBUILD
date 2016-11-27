pkgname=rambox
pkpkgname=rambox
pkgver=0.4.5
pkgrel=1
pkgdesc="Free, Open Source, Cross Platform messaging & emailing app : Gmail, Whatsapp, Outlook, Yahoo, Telegram, TweetDeck ..."
arch=('x86_64')
url="http://rambox.pro/"
license=("MIT")
depends=('alsa-lib' 'bash' 'desktop-file-utils' 'gconf' 'gtk2' 'libnotify' 'libxtst' 'libxss' 'nss')
source=("$pkgname.desktop" "$pkgname.png" "https://github.com/saenzramiro/rambox/releases/download/$pkgver/Rambox-$pkgver-x64.tar.gz")
sha256sums=('aad836814026c20794a5979725f8021147863452b46b860d1a6e838e3a6d562d'
            '6b77c271e8f94eb33ce7ad3a4596a861fedfea0ac45e69a2b6fc4ce6d12fe32d'
            'a814733f0e0977de6a5b6e5500b5cea1ee062d6973e5f72714db2cc8a3ab597c')

package() {
    # create subdirectory in /opt as binary install
    install -dm755 "$pkgdir/opt/rambox"
    # copy from tar.gz files in /opt/rambox
	cp -rf $srcdir/Rambox-$pkgver/* $pkgdir/opt/rambox/
    #copy icon image in /opt/rambox
	install -Dm644 "$srcdir/$pkgname.png" "$pkgdir/opt/rambox/rambox.png"
	install -dm755 "$pkgdir/usr/share/pixmaps"
    ln -s "/opt/rambox/rambox.png" "$pkgdir/usr/share/pixmaps/$pkgname.png"
	
    # desktop file
	install -dm755 "$pkgdir/usr/share/applications"
    desktop-file-install $srcdir/$pkgname.desktop --dir $pkgdir/usr/share/applications/

  install -dm755 "${pkgdir}/usr/bin"
  ln -s "/opt/rambox/Rambox" "$pkgdir/usr/bin/rambox"
    

}
